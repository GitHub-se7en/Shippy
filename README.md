#### 环境

==win7+win7docker+docker-compose+goland==

环境不同，坑太多，

* make build的命令不能用，折中的方法是使用goland进行交叉编译而不是使用命令行进行编译

* docker的使用，使用win7下面的docker模拟线上的部署环境，和之前部署java项目一样，甚至更简单，goland编译之后，形成Linux的执行文件，dockerfile把它放到容器里面，生成镜像，运行项目

  

==go module+go micro+jwt+==

* 使用go module作为项目的依赖管理工具，单独运行一次go build就可以更新go mod文件
* 使用go micro作为微服务框架，