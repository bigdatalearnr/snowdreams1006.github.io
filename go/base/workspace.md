# 工作空间

搭建好 `Go` 的基本环境后,现在可以正式开始 `Go` 语言的学习之旅,初学时建议在默认的 `GOPATH` 工作空间规范编写代码,基本目录结构大概是这个样子.

```bash
.
|-- bin
|   `-- hello.exe
|-- pkg
|   `-- windows_amd64
|       `-- github.com
|           `-- snowdreams1006
|               `-- learn-go
|                   `-- strings.a
`-- src
    `-- github.com
        `-- snowdreams1006
            `-- learn-go
                |-- README.md
                |-- hello
                |   `-- hello.go
                `-- strings
                    |-- reverse.go
                    `-- reverse_test.go
```

`Go` 相关的代码保存在工作空间中,而工作空间目录默认情况下是 `GOPATH` 环境变量所指向的目录(例如: `GOPATH=C:\Users\snowdreams006-win7\go`).

工作空间下一般应包括三个一级子目录,分别是 `src`,`pkg` 和 `bin` 目录,其中最重要的就是 `src` 源码目录,其余两个目录都是派生目录.

- `src` 目录是**源代码**目录,是平时写代码的地方.
- `pkg` 目录是**包对象**目录,里面的文件大多以 `.a` 为后缀名,`Go` 工具自动处理,暂时不用关心.
- `bin` 目录是**可执行命令**目录,是最终产出的文件,例如 `Windows` 平台一般会生成 `.exe` 文件.

> 如果你刚刚安装 `Go` 语言或者不是默认形式安装的 `Go`,打开命令行窗口运行 `go env` 查看 `GOPATH` 那一项,`GOPATH` 指代的目录就是工作空间.

![go-base-workspace-go-env.png](../images/go-base-workspace-go-env.png)

## 体验别人的 `Go` 命令

默认情况下,刚刚安装完毕的 `Go` 环境并不会自动创建工作空间目录,可以手动创建也可以运行别人的 `Go` 命令时顺便创建.

```bash
snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 /
# 初始时工作空间并未创建
$ ls $GOPATH
ls: cannot access 'C:\Users\snowdreams1006-win7\go': No such file or directory

snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 /
# 下载别人的 `Go` 命令顺便创建了工作空间
$ go get github.com/snowdreams1006/learn-go/hello

snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 /
# 已经按照标准目录结构创建完毕,目前有src和bin目录就足够了
$ ls $GOPATH
bin/  src/
```

运行完 `go get github.com/snowdreams1006/learn-go/hello` 命令后,工作空间目前已近乎标准目录.

> 如果 `go get` 命令半天没什么反应,不要着急,说不定正在下载,只是比较慢而已,如果想要看到下载过程,可以添加额外参数: `go get -u -v`

![go-base-workspace-go-get-tree.png](../images/go-base-workspace-go-get-tree.png)

可以看出,`go get` 命令下载了 `hello` 命令所依赖的文件并生成 `bin/hello.exe` 可执行文件,现在终于可以说一声 `Hello world!`

```bash
snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~/go
$ hello
!oG,olleH
```

这个是啥?怎么不是传说中的 `Hello World` ?

![go-base-workspace-go-get-angry.png](../images/go-base-workspace-go-get-angry.png)

不管怎么说,创建工作空间的目的已经达到了,不是吗?

> 聪明的你,或许已经发现输出的语句的确不是 `Hello World` 而是 `Hello Go` 反过来写!

## 打造自己的 `Go` 命令

如果手头上没有 `Go` 项目或者说想要从零开发 `Go` 项目的话,那么只能手动创建工作空间了.

我们已经知道了工作空间的规范,但是现在涉及到自定义项目,同样需要确定项目的规范.

一般说来,项目需要唯一id用于区分其他可能出现的同名项目,也就是命名空间的概念.

作为个人开源项目,同广大的 `Go` 项目规范一样托管到 `github.com` 网站,因此命名空间 `github.com/user` 作为基本路径.

> 重要区别: 
> `Go` 的命名空间(即基本路径)是域名正写: `github.com/snowdreams1006`,如果是其他语言,命名空间可能就是域名反写形式: `com.github.snowdreams1006` .


```bash
snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~
# 当前并未创建过工作空间
$ ls $GOPATH
ls: cannot access 'C:\Users\snowdreams1006-win7\go': No such file or directory

snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~
# 在工作空间下创建 `learn-go` 项目
$ mkdir -p $GOPATH/src/github.com/snowdreams1006/learn-go/hello

snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~
# 在 `learn-go` 项目下创建 `hello.go` 文件
$ vim $GOPATH/src/github.com/snowdreams1006/learn-go/hello/hello.go

snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~
# `hello.go` 文件内容,输出 `Hello world`
$ cat $GOPATH/src/github.com/snowdreams1006/learn-go/hello/hello.go
package main

import "fmt"

func main() {
        fmt.Printf("Hello, world.\n")
}
```

现在 `Go` 语言版的 `Hello World` 已经编写完毕,接下来让我们编辑输出并安装 `hello` 文件命令吧!

在命令行窗口运行 `go install github.com/snowdreams1006/learn-go/hello` 命令会在工作空间的 `bin` 目录下生成 `hello.exe` 可执行文件.

![go-base-workspace-go-install-ls.png](../images/go-base-workspace-go-install-ls.png)

现在命令行窗口不负众望,输出了期待已久的 `Hello World`!

![go-base-workspace-go-install-hi.png](../images/go-base-workspace-go-install-hi.png)

## 简单讲解下 `Go` 命令 

无论是下载别人的远程代码还是自己从零编写代码,在命令行中都用到了相应命令,`go get` 和 `go install` 等.

- `go get` : 下载远程代码包,如果本地已安装,则执行逻辑退化为 `go install`.
- `go install` : 安装本地依赖包,如果本地没有相关依赖,则报错提示无法找到相关依赖包.

当然 `Go` 支持的常用命令远远不止这两个,直接输入 `go` 自然会提示有哪些命令可供使用,如果想要查询具体某一个命令的帮助文档,则输入 `go help <command>` 即可,例如 `go help get`

![go-base-workspace-go-help-command.png](../images/go-base-workspace-go-help-command.png)

这些命令比较简单,不用翻译也能猜出八九不离十,故此不浪费时间一一阐述.

下面直接上代码亲测运行一遍相关命令.

### `go get` 下载代码包

```bash
snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~/go
$ tree
.
|-- bin
|   `-- hello.exe
`-- src
    `-- github.com
        `-- snowdreams1006
            `-- learn-go
                `-- hello
                    `-- hello.go

6 directories, 2 files

snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~/go
$ go get github.com/golang/example/hello

snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~/go
$ tree
.
|-- bin
|   `-- hello.exe
`-- src
    `-- github.com
        |-- golang
        |   `-- example
        |       |-- LICENSE
        |       |-- README.md
        |       |-- appengine-hello
        |       |   |-- README.md
        |       |   |-- app.go
        |       |   |-- app.yaml
        |       |   `-- static
        |       |       |-- favicon.ico
        |       |       |-- index.html
        |       |       |-- script.js
        |       |       `-- style.css
        |       |-- gotypes
        |       |   |-- Makefile
        |       |   |-- README.md
        |       |   |-- defsuses
        |       |   |   `-- main.go
        |       |   |-- doc
        |       |   |   `-- main.go
        |       |   |-- go-types.md
        |       |   |-- hello
        |       |   |   `-- hello.go
        |       |   |-- hugeparam
        |       |   |   `-- main.go
        |       |   |-- implements
        |       |   |   `-- main.go
        |       |   |-- lookup
        |       |   |   `-- lookup.go
        |       |   |-- nilfunc
        |       |   |   `-- main.go
        |       |   |-- pkginfo
        |       |   |   `-- main.go
        |       |   |-- skeleton
        |       |   |   `-- main.go
        |       |   |-- typeandvalue
        |       |   |   `-- main.go
        |       |   `-- weave.go
        |       |-- hello
        |       |   `-- hello.go
        |       |-- outyet
        |       |   |-- Dockerfile
        |       |   |-- containers.yaml
        |       |   |-- main.go
        |       |   `-- main_test.go
        |       |-- stringutil
        |       |   |-- reverse.go
        |       |   `-- reverse_test.go
        |       `-- template
        |           |-- image.tmpl
        |           |-- index.tmpl
        |           `-- main.go
        `-- snowdreams1006
            `-- learn-go
                `-- hello
                    `-- hello.go

25 directories, 35 files

snowdreams1006-win7@WIN-FANS2DDDB06 MINGW64 ~/go
$
```

原本 `$GOPATH/src` 源码目录只有我们自己的 `github.com/snowdreams1006/learn-go` 项目,获取远程 `golang/hello` 代码包后多了一大堆源码文件.

真的是神奇的操作,其余语言调用开源工具一般都是作为依赖放到非源码目录,`Go` 直接放到正在编写的源码目录,看起来第三方源码像是我们自己写的一样,只不过用命名空间区分开了而已!

![go-base-workspace-go-get-surprise.png](../images/go-base-workspace-go-get-surprise.png)

### `go test` 测试代码包

### `go install` 安装代码包

### `go build` 编译代码包

### `go run` 运行代码包

## `GoLand` 编辑器选择和配置

- 常见的 `IDE` : `Sublime text2` ,`liteide` ,`Goland` 等

> 国人开发的 `liteide` ,推荐 `Goland`

- `GOLand` 下载安装(https://www.jetbrains.com/go/)
- `GOLand` 简单配置

打开设置,设置`GOROOT` -> `NO SDK` 更改为`go` 安装位置
`GOPATH` 添加项目路径

