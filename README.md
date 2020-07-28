# how-to-install-xdebug-and-config-with-phpstorm-in-ubuntu

To develop a PHP project, Ubuntu is a good choice. But how to debug it when you meet a problem? You can use echo, but it will make your web page messy. So Xdebug is a good choice. And many developers using PHPstorm as an IDE. So, in this paragraph, I will write down how I install Xdebug and config with PHPStorm in Ubuntu.

### Step1: install Xdebug

Following the instructions of the [Xdebug website](https://xdebug.org/docs/install), I try to install Xdebug with PCEL.

```
sudo apt-get install xdebug
```

But, it gave me the error "phpize" didn't find. When I go through the xdebug website, I knew that I need to install PHP development headers. 
So, install php-dev

```
sudo apt-get install php-dev
```

When it's done. I can install xdebug 
```
sudo pecl install xdebug
```

When it's done, system told me 
```
Build process completed successfully
Installing '/usr/lib/php/20190902/xdebug.so
You should add "zend_extension=/usr/lib/php/20190902/xdebug.so" to php.ini
```
 
Find where is my php.ini. 
```
sudo find / -name php.ini 
```
open it and add the following line
```
zend_extension=/usr/lib/php/20190902/xdebug.so
```
after
```
; If you use constants in your value,  and these constants belong to a
; dynamically loaded extension (either a PHP extension or a Zend extension),
; you may only use these constants *after* the line that loads the extension.
```
restart your web server.



