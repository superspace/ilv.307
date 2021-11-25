 [Modul 307 / Tag 1](/ilv.307/01-modul-307)

# Debugging mit xDebug
## Visual Studio Code & xDebug installieren

Visual Studio Code Extension **PHP Debug** (Felix Becker) aktivieren.

### Download DLL

[https://xdebug.org/files/php_xdebug-3.0.0-8.0-vs16-x86_64.dll](https://xdebug.org/files/php_xdebug-3.0.0-8.0-vs16-x86_64.dll)

- Das dll-file hierhin bewegen: `C:\xampp\php\ext`
- Das dll-file umbenennen: `php_xdebug.dll`

### php.ini

Den Abschnitt `[xdebug]` bearbeiten oder erstellen:

```
[xdebug]
zend_extension = xdebug
xdebug.mode = debug
xdebug.start_with_request = yes
xdebug.idekey = VSCODE
xdebug.client_port = 9003
xdebug.client_host = "127.0.0.1"
xdebug.discover_client_host  = 1
xdebug.log="/tmp/xdebug.log"
xdebug.cli_color = 1
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NDcxMzUwMDgsNzY1ODkxNDU2LC0xMT
Q5MTYwOTM5LDEzNTEzNjM1NjYsNDMzNzUxNzM0XX0=
-->