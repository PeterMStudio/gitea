# win构建教程

## **编译环境**

### **Nodejs**

[**下载安装**](https://nodejs.org/en/download)最新的LTS版，我用的是18.17.1

### **Go**

[**下载安装**](https://golang.google.cn/dl/)最新版，我用的是1.21.0

### **Cmder**

[**下载解压**](https://github.com/cmderdev/cmder/releases/latest)最新**完整**版（也就是名字里没有`mini`的），我用的是v1.3.24

### **GNU Make For Windows**

[**网站**](http://www.equation.com/servlet/equation.cmd?fa=make) / [**64位最新版下载链接**](http://www.equation.com/ftpdir/make/64/make.exe)

下载完成后解压`make.exe`，向`PATH`环境变量中添加`make.exe`所在目录（嫌麻烦也可以直接丢进`C:\Windows`）

### **换源**

参考[**常用软件换源表**](https://young-lord.github.io/posts/常用软件换源表)。

```
npm config set registry https://registry.npmmirror.com
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,direct
```

## **拉代码**

打开`Cmder`（如果你没有单独安装`Git`），`git clone https://github.com/go-gitea/gitea --depth 1`

## **编译**

打开`Cmder`，进入`gitea`目录，依次执行：

```
set TAGS=bindata sqlite sqlite_unlock_notify
make build
```

会报一大堆`FIND: 参数格式不正确`的错误，忽略即可。只要最终当前目录下生成`gitea.exe`即算成功