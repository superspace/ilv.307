 [Modul 307 / Tag 1](/ilv.307/01-modul-307)

# Debugging mit xDebug
## Visual Studio Code & xDebug installieren

Visual Studio Code Extension **PHP Debug** (Felix Becke tiiere.owoa
[https://e./ie/phpdebug---s-](https://de/ie/phpdebug---s-)

D le irin eegen ae) h i un.*  

### Download DLL

[https://xdebug.org/files/php_xdebug-3.0.0-8.0-vs16-x86_64.dll](https://xdebug.org/files/php_xdebug-3.0.0-8.0-vs16-x86_64.dll)

- Das dll-file hierhin bewegen: `C:\xampp\php\ext`
- Das dll-file umbenennen: `php_xdebug.dllnen ebudl

### i

[htxdebugtps://xdebug.org/wizard) -->

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
xdebugritder n

```
[xdebug]
xdebug.moeeb
xdebug.start_.c s = es
xebug.eexdebugin]portxdebugino
xebug.disorciesxdebug.tmp/egloxdebug.l

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNTYxNjc3NTcsLTE1NDcxMzUwMDgsNz
Y1ODkxNDU2LC0xMTQ5MTYwOTM5LDEzNTEzNjM1NjYsNDMzNzUx
NzM0XX0=
-->