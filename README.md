# 安装方法
本系统升级到golang1.12,请开启如下支持
```
#开启go mod支持
export GO111MODULE=on
#使用代理
export GOPROXY=https://goproxy.io

```
## 1.下载项目
```bash
git clone https://git.imooc.com/coding-339/chat.git
```


## 2.项目配置
### 2.1 ide配置

+ goland IDE

ADD Configuration->左上角+->go build类型,右侧填写
```
files :{你的项目路径}/hellox.x/main.go
workdir:{你的项目路径}/hellox.x/
```
+ vscode
安装golang插件即可,无需配置,推荐使用

### 2.2 数据库配置
修改service/init.go 中数据库配置文件
```cgo
const (
	driveName = "mysql"  //数据库类型,不要动
	dsName    = "root:root@(127.0.0.1:3306)/tech-chat?charset=utf8"  //tech-chat是数据库名称,请先创建
	showSQL   = true  //是否显示sql语句
	maxCon    = 10  //最大连接数
	NONERROR  = "noerror" //一个字符串标记常量
)
```
为你自己的数据库以及密码,格式如下
```
用户名:密码@(ip:port)/数据库名称?charset=utf8
```
### 2.3 页面入口地址
```
http://127.0.0.1:8080/user/login.shtml
```

## 3.依赖包安装

本项目依赖的`x/net`,`x/time`包可能会被墙，使用如下指令可以安装

```bash
$mkdir -p $GOPATH/src/golang.org/x/
$cd $GOPATH/src/golang.org/x/
$git clone https://github.com/golang/net.git net
$git clone https://github.com/golang/time.git time

```

其他包依赖

```bash
go get github.com/go-xorm/xorm
go get github.com/gorilla/websocket
go get gopkg.in/fatih/set.v0
go get github.com/go-xorm/xorm
```
