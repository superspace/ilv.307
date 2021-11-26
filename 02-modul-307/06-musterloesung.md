[Modul 307 / Tag 2](/ilv.307/02-modul-307)

# Musterlösung Superheld

```php
const FILENAME = 'heroes.json';

$output = '';

if (isset($_POST['send'])) {

    // Sanitize

    $data = [];

    foreach ($_POST as $key => $value) {
        $data[$key] = htmlspecialchars(trim($value));
    }

    $name = $data['name'];
    $realname = $data['realname'];
    $universe = $data['universe'];
    $popuplarity = (int) $data['popularity'];

    // Validierung

    $errors = [];

    if (empty($name)) {
        $errors[] = 'Geben Sie bitte einen Namen ein.';
    }
    if (empty($universe)) {
        $errors[] = 'Wählen Sie bitte ein Universum aus.';
    }

    if ($popuplarity < 1 || $popuplarity > 5) {
        $errors[] = 'Wählen Sie eine Beliebtheit von 1 bis 5.';
    }

    if (count($errors)) {

        // Fehlermeldung ausgeben

        foreach ($errors as $error) {
            $output .= "<div class=\"alert alert-danger\">$error</div>";
        }
    } else {

        // Nachricht ausgeben

        $output .= '<div class="alert alert-success">';
        $output .= $name;
        if (!empty($realname)) $output .= " ($realname)";
        $output .= " von $universe ist ";
        switch ($popuplarity) {
            case 1 :
                $output .= 'überhaupt nicht';
                break;
            case 2 :
                $output .= 'nicht so';
                break;
            case 3 :
                $output .= 'ein bisschen';
                break;
            case 4 :
                $output .= 'ziemlich';
                break;
            case 5 :
                $output .= 'sehr';
                break; 
            default :
                $output .= ' ';
        }
        $output .= " beliebt.";
        $output .= "</div>";

        // In JSON umwandeln und in Datei speichern

        if (!file_exists(FILENAME)) {
            fopen(FILENAME, 'w');
        }
        
        $json = file_get_contents(FILENAME);
        $data = json_decode($json, true);

        $data[] = array(
            'name' => $name,
            'realname' => $realname,
            'universe' => $universe,
            'popuplarity' => $popuplarity
        );

        $json = json_encode($data);
        file_put_contents(FILENAME, $json);
    }

}
```
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Superheld</title>
        <meta  charset="utf-8">
        <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    </head>
    <body>
        <div class="container">

            <h1>Superheld</h1>

            <?= $output ?>

            <hr />

            <form action="" method="post">

                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" class="form-control" name="name" value="" required/>
                </div>

                <div class="form-group">
                    <label for="realname">Realer Name</label>
                    <input type="text" id="realname" class="form-control" name="realname" value="" />
                </div>

                <div class="form-group">
                    <label for="universe">Universum</label>
                    <select name="universe" id="universe" class="form-control" required>
                        <option value="DC">DC COMIC</option>
                        <option value="MARVEL">MARVEL COMIC</option>
                    </select>
                </div>

                <div class="form-group">
                    <label>Beliebtheit</label><br />
                    <div class="form-check form-check-inline">
                        <input class="form-check-input" type="radio" name="popularity" id="popularity-1"  value="1" required />
                        <label class="form-check-label" for="popularity-1">1</label>
                    </div>

                    <div class="form-check form-check-inline">
                        <input class="form-check-input" type="radio" name="popularity" id="popularity-2"  value="2" required />
                        <label class="form-check-label" for="popularity-2">2</label>
                    </div>

                    <div class="form-check form-check-inline">
                        <input class="form-check-input" type="radio" name="popularity" id="popularity-3"  value="3" required />
                        <label class="form-check-label" for="popularity-3">3</label>
                    </div>

                    <div class="form-check form-check-inline">
                        <input class="form-check-input" type="radio" name="popularity" id="popularity-4"  value="4" required />
                        <label class="form-check-label" for="popularity-4">4</label>
                    </div>

                    <div class="form-check form-check-inline">
                        <input class="form-check-input" type="radio" name="popularity" id="popularity-5"  value="5" required />
                        <label class="form-check-label" for="popularity-5">5</label>
                    </div>

                </div>

                <button type="submit" name="send" class="btn btn-primary">Senden</button>

            </form>

        </div>
    </body>
</html>
```