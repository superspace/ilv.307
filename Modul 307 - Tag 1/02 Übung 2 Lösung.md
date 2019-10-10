```php
<?php

$runs = rand(1, 10);

print("Anzahl Durchl&auml;ufe: $runs<br><br>\n");

$run_counter = 0;
while($run_counter < $runs)
{
    $number = rand(1,100);

    if($number <= 30) $color = '#00FF00';
    else if($number >= 70) $color = '#FF0000';
    else if($number == 50) $color = '#0000FF';
    else $color = '#000000';

    if(($number < 20 || $number > 80) && $number%2 == 0)
    {
        $fontweight = "underline";
    }
    else
    {
        $fontweight = "normal";
    }

    print("<div style=\"color:$color; text-decoration:$fontweight\">$number</div>\n");
    
    $run_counter++;
}


print("<hr>");

$grade = rand(1,6);
print("Note: $grade (");

switch($grade) {
    case 1:
        print("schlecht");
        break;
    case 2:
        print("schwach");
        break;
    case 3:
        print("ungen&uuml;gend");
        break;
    case 4:
        print("gen&uuml;gend");
        break;
    case 5:
        print("gut");
        break;
    case 6:
        print("sehr gut");     
}
print(")");


```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNTc3NzEzMV19
-->