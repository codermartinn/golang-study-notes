# Golang 学习笔记



## 资料

- [8小时转职Golang工程师 (yuque.com)](https://www.yuque.com/aceld/mo95lb)





## Golang 环境

### 下载安装包

- Go 官网下载地址：https://golang.org/dl/
- Go 官方镜像站（推荐）：https://golang.google.cn/dl/



我是把安装包放到阿里云的`usr/local`文件夹下：

![image-20230310191159851](https://codermartinn.oss-cn-guangzhou.aliyuncs.com/img/image-20230310191159851.png)

然后解压到 `/usr/local`



### 配置环境变量

​	1.打开 `/etc/profile` 文件，可以使用 vim 等文本编辑器进行编辑：

```
sudo vim /etc/profile
```

​	2.在文件末尾添加以下语句，其中 `GO_HOME` 为你的 Golang 安装目录的路径：

```
export GOPATH=$HOME/go
export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
```

​	3.保存并退出编辑器。

​	4.重新加载 `/etc/profile` 文件，使配置生效：

```
source /etc/profile
```

​	5.检查是否安装成功

```shell
[root@iZ7xv5zwn1hd8xkfso1543Z ~]# go version
go version go1.20.2 linux/amd64
```

现在可以在任何目录下使用 `go` 命令了。





### 创建文件夹

在`$HOME`文件夹下创建go文件夹，并且在go文件夹下创建3个文件夹：

```shell
mkdir bin
mkdir src
mkdir pkg
```

在`/root/go/src/GolangStudy/01Golang`下写第一个go程序：

![image-20230310200534252](https://codermartinn.oss-cn-guangzhou.aliyuncs.com/img/image-20230310200534252.png)





## Golang基本

### 第一个Golang程序

```go
package main // 当前程序的包名

import "fmt"

// main函数
func main(){
	fmt.Println("hello go!")
}
```



> 这段 Go 代码定义了一个 `main` 包，并在其中定义了一个 `main` 函数。
>
> 在程序运行时，Go 语言的编译器将首先查找一个名为 `main` 的包，并查找其中的 `main` 函数。在本例中，`main` 函数使用 `fmt` 包中的 `Println` 函数将字符串 `"hello go!"` 输出到控制台。



```shell
[root@iZ7xv5zwn1hd8xkfso1543Z 01Golang]# go run hello.go 
hello go!
```



再引入`time`包，实现打印后1秒再结束：

```go
package main // 当前程序的包名


import "fmt"
import "time"

// main函数
func main(){
	fmt.Println("hello go!")

	time.Sleep(1 * time.Second)
}
```



`import(...)`引入多个包：

```go
package main // 当前程序的包名

/*
import "fmt"
import "time"
*/
import(
	"fmt"
	"time"
)

// main函数
func main(){
	fmt.Println("hello go!")

	time.Sleep(1 * time.Second)
}
```

