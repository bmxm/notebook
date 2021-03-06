Dockerfile 是一个文本格式的配置文件，用户可以使用Dockerfile来快速创建自定义的镜像。


## 1 基本结构


Dockerfile由一行行命令语句组成，并且支持以#开始的注释行。

一般而言，Dockerfile主体内容分为四部分：基础镜像信息、维护者信息、镜像操作指令、容器启动时执行的命令。


主体部分首先使用FROM指令指明所基于的镜像名称，接下来一般是使用LABEL指令指明维护者信息。
再后面这是镜像操作指令，例如RUN指令将对镜像执行跟随的命令。每运行一条RUN指令，镜像添加新的一层，并提交。
最后是CMD指令，来指定运行容器时的操作命令。


## 2 指令说明

- 配置指令
    - AGE：定义创建镜像过程中使用的变量
    - FORM：指定所创建镜像的基础镜像
    - LABEL：为生成的镜像添加元数据标签信息
    - EXPOSE：声明镜像内服务监听的端口
    - ENV：指定环境变量
    - ENTRYPOINT：指定镜像的默认入口命令
    - VOLUME：创建一个数据卷挂载点
    - USER：指定运行容器是的用户名或UID
    - WORKDIR：配置工作目录
    - ONBUILD：创建子镜像是指定自动执行的操作指令
    - STOPSIGNAL：指定退出的信号量
    - HEALTHCHECK：配置所启动的容器如何进行健康检查
    - SHELL：指定默认shell类型
- 操作指令
    - RUN：运行指定命令
    - CMD：启动容器时指定默认执行的命令
    - ADD：添加内容到镜像
    - COPY：复制内容到镜像