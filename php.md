# php开发环境设置

### hombrew

``` sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

可能需要翻墙，大概率需要`shadowsock`或者其他翻墙工具加上`proxychain-ng`可以做到翻墙使用homebrew。

### php环境

虽然Mac OS X 自带了php，但是我们可以选择使用Homebrew安装php56或者php54因为：

- 使用Homebrew安装更新的php版本
- 同时安装5.6和5.5和5.4的php
- Homebrew会同时安装xdebug和mcrypt等工具

安装python 56：

``` 
brew install homebrew/php/php56
brew install homebrew/php/php56-mcrypt
brew install homebrew/php/php56-xdebug
```

安装python 5.4：

``` 
brew install homebrew/php/php54
```

一般来说如果php安装了xdebug，大概率composer运行的时候会报错。所以用来运行脚本的php不能安装xdebug。可以这样把已经安装了xdebug调试工具的php从`PATH`中移除。

``` sh
brew unlink php56
```

### composer

##### 英文原版安装（需要翻墙）

参考网址https://getcomposer.org/doc/00-intro.md

You can place the Composer PHAR anywhere you wish. If you put it in a directorythat is part of your `PATH`, you can access it globally. On unixy systems youcan even make it executable and invoke it without directly using the `php`interpreter.

Run these commands to globally install `composer` on your system:

``` sh
curl -sS https://getcomposer.org/installer | php
mv composer.phar /usr/local/bin/composer
```

A quick copy-paste version including sudo:

``` sh
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
```

##### 中文镜像库安装

参考网址http://docs.phpcomposer.com/00-intro.html

如果你把它放在系统的 `PATH` 目录中，你就能在全局访问它。 在类Unix系统中，你甚至可以在使用时不加 `php` 前缀。

你可以执行这些命令让 `composer` 在你的系统中进行全局调用：

``` sh
curl -sS https://getcomposer.org/installer | php
mv composer.phar /usr/local/bin/composer
```

**注意：** 如果上诉命令因为权限执行失败，请使用 sudo 再次尝试运行 `mv` 那行命令。

或者

检查一些 PHP 的设置，然后下载 `composer.phar` 到你的工作目录中。这是 Composer 的二进制文件。这是一个 PHAR 包（PHP 的归档），这是 PHP 的归档格式可以帮助用户在命令行中执行一些操作。

你可以通过 `--install-dir` 选项指定 Composer 的安装目录（它可以是一个绝对或相对路径）：

``` sh
curl -sS https://getcomposer.org/installer | php -- --install-dir=bin
```

