# Golang开发环境配置

以Golang1.8为例

## 包下载

```
# 官方源
curl https://storage.googleapis.com/golang/go1.8.darwin-amd64.tar.gz -o golang.tar.gz 
```

### 也可以使用pkg包安装

## 解压

```
tar -zxvf go1.8.darwin-amd64.tar.gz -o golang.tar.gz
```

## 安装到指定位置

```
sudo mkdir -p /opt/local/go/
sudo mv go/ /opt/local/go/
```

## 配置环境变量

```
# vim ~/.bash_profile
# 如果不是用的自带的terminal，就不是这个名字。比例zsh是在~/.zshrc
# 添加以下内容

export GOROOT="/opt/local/go"
export GOBIN="$GOROOT/bin"
export PATH="$PATH:$GOROOT/bin"
export GOPATH="$HOME/code/go/external:$HOME/code/go/projectXX"
```

```
source ~/.bash_profile
```

## 检查是否生效

```
go env
```

以上命令输出为:

```
GOARCH="amd64"
GOBIN="/opt/local/go/bin"
GOEXE=""
GOHOSTARCH="amd64"
GOHOSTOS="darwin"
GOOS="darwin"
GOPATH="/Users/ooops/code/go/external:/Users/ooops/code/go/me"
GORACE=""
GOROOT="/opt/local/go"
GOTOOLDIR="/opt/local/go/pkg/tool/darwin_amd64"
GCCGO="gccgo"
CC="clang"
GOGCCFLAGS="-fPIC -m64 -pthread -fno-caret-diagnostics -Qunused-arguments -fmessage-length=0 -fdebug-prefix-map=/var/folders/dh/gf2msm053lqcvqwvy7g62sjh0000gn/T/go-build015052219=/tmp/go-build -gno-record-gcc-switches -fno-common"
CXX="clang++"
CGO_ENABLED="1"
PKG_CONFIG="pkg-config"
CGO_CFLAGS="-g -O2"
CGO_CPPFLAGS=""
CGO_CXXFLAGS="-g -O2"
CGO_FFLAGS="-g -O2"
CGO_LDFLAGS="-g -O2"
```

写个hello world吧

```
package main

import "fmt"

func main(){
	fmt.Println("hello world")
}
```
