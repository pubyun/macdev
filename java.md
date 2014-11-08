# Java开发环境的设置

## Java安装

### 安装Mac原生的Java

Mac OS X 系统安装的时候，不带Java，但是可以通过简单的方法快速安装苹果原生的Java，版本是1.6。有三种安装方式：

* 第一次使用java程序，比如打开eclipse的时候，系统就会自动安装Java。

* 命令行下，执行下面的命令：

    java -version

* 直接从苹果官方网站下载Java安装文件:

    http://support.apple.com/kb/DL1572?viewlocale=zh_CN

### 安装新版的Java 1.7

从下列网站下载 Mac OS X 版本的JDK，文件名是jdk-7u51-macosx-x64.dmg：

    http://www.oracle.com/technetwork/java/javase/downloads/index.html

## 设置JAVA_HOME环境变量

很多Java应用需要使用到JAVA_HOME环境变量，在Mac下，可以使用下面的方法，动态获取这个环境变量：

获取Java 1.6的JAVA_HOME：

    /usr/libexec/java_home -v 1.6

获取Java 1.7的JAVA_HOME：

    /usr/libexec/java_home -v 1.7

使用动态的方式设置JAVA_HOME的好处是，当自动升级了新版本的JAVA时，总能找到合适的JAVA_HOME目录。基于这个原因，程序员不要将文件安装在'/System'目录的JDK，因为Java升级的时候，文件会丢失。

也可以通过下列方法设置用户的环境变量，编辑文件'~/.zshrc'或'~/.bash_profile'，加入下面两行之一：

对于Java 1.6：

    export JAVA_HOME=`/usr/libexec/java_home -v 1.6`
    export PATH=${JAVA_HOME}/bin:$PATH

对于Java 1.7：

    export JAVA_HOME=`/usr/libexec/java_home -v 1.7`
    export PATH=${JAVA_HOME}/bin:$PATH

## 扩展库(Extension Libraries)的目录位置 

其他平台的Java软件使用'$JAVA_HOME/lib/ext'来存放扩展库的jar文件，Mac OS X的Java虽然也存在这一个'lib/ext'目录，你不能将jar文件存放在这个目录。'/Library/Java/Extensions'目录可以用来存放系统级别的jar文件或JNI库，'~/Library/Java/Extensions'目录用来存放用户级别的jar文件或JNI库。存放在这两个目录下的文件，不需要设置在classpath环境变量下，任何运行的java程序都可以直接使用。

## 安装Eclipse

### 手工安装

从下列地址下载Eclipse的相应版本，我一般选用'Eclipse IDE for Java EE Developers':

    http://www.eclipse.org/downloads/

下载，解压文件，然后将eclipse目录拖到'Applications'目录，双击'/Applications/eclipse/'下的eclipse应用程序图标，就可以启动eclipse。

编辑文件'~/.zshrc'或'~/.bash_profile'，加入：

   export ECLIPSE_HOME=/Applications/eclipse

### 使用homebrew-cask安装

    % brew cask alfred link
    % brew cask install eclipse-ide
    ==> Downloading http://download.eclipse.org/technology/epp/downloads/release/kepler/SR1/e
    ######################################################################## 100.0%
    ==> Symlinking App 'Eclipse.app' to '/Users/ppyy/Applications/Eclipse.app'
    ==> Success! eclipse-ide installed to /opt/homebrew-cask/Caskroom/eclipse-ide/4.3.1

这里'brew cask alfred link'可以使homebrew cask安装的程序被Alfed搜索到，可以快速启动。

编辑文件'~/.zshrc'或'~/.bash_profile'，加入：

   export ECLIPSE_HOME=/opt/homebrew-cask/Caskroom/eclipse-ide/4.3.1/eclipse/

### eclipse的优化

安装完毕eclipse以后，为了优化eclipse的运行，可以编辑目录'$ECLIPSE_HOME/Eclipse.app/Contents/MacOS'下的eclipse.ini文件。如果没有设置ECLIPSE_HOME变量，则在'Finder'程序下，右键点击(Ctrl+点击)Eclipse执行程序，选择'Show Package Contents'，然后选择Contents目录下的MacOS目录，打开eclipse.ini文件，修改下列一些变量：

    --launcher.XXMaxPermSize
    2048m
    ...
    -vmargs
    ...
    -Xms512m
    -Xmx850m
    -XX:PermSize=512m
    -XX:MaxPermSize=1024m

## 安装ant, maven, tomcat, jetty

    brew install ant maven tomcat jetty

