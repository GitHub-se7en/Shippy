#### 环境

==win7+win7docker+docker-compose+goland==

环境不同，坑太多，

* make build的命令不能用，折中的方法是使用goland进行交叉编译而不是使用命令行进行编译

* docker的使用，使用win7下面的docker模拟线上的部署环境，和之前部署java项目一样，甚至更简单，goland编译之后，形成Linux的执行文件，dockerfile把它放到容器里面，生成镜像，运行项目

  

==go module+go micro+jwt+==

* 使用go module作为项目的依赖管理工具，单独运行一次go build就可以更新go mod文件
* 使用go micro作为微服务框架，

==设置镜像==
有很多包使用go get的时候直接下载不下来
https://goproxy.io/zh/
一定要设置代理，可以省很多事

==关于go语言的包和文件夹的关系==

一个文件夹里面只能由一个包，

一个文件夹里面可以有多个文件，但是必须是是同一个包

不同的文件夹可以取相同名字的包名

导入的时候最小单位是文件夹

==docker-compose和dockerfile之间的关系==

dockerfile的作用的是在dockerbuild的时候有依据，构建镜像就指着这个dockerfile呢，

docker-compose是用来代替docker build run之类的命令的，不需要一个一个敲，直接写在yml文件里面就可以

==go module 和 gopath==

使用go module之后，之前的gopath文件夹就消失了，我感觉是go module把所有的依赖重新整合了起来，而且最重要的一点，这个是使用Git的标签的，而gopath是直接使用文件的，当时就有疑问，版本管理的问题 ，可能这些文件正在升级，这样就导致我在导包的时候，倒进来了不稳定的版本，而分支并不是做这个用处的，实际使用中，我在搭建go micro的时候，有依赖问题，有的名字是google.com有的时候叫github，相当混乱



==go get 和  go install 和  go build==

可能由于之前没有设置代理，导致go get 安装不了别的项目，