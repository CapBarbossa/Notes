```shell
docker run -it \
    --restart always \
    --runtime nvidia \
    --network host \
    -v /data4:/home/work \
    --name mytrain3 \
    capsparrow/360_gpu_2080_geforce_tf1.9.0_further /bin/bash
```

启动容器时,采用docker run -it的交互方式可以在容器退出但未被删除的情况下,通过docker start重新在后台运行起来, 有效应对服务器重启等意外或者无法避免的情况. 在使用交互模式创建容器时,--restart选项可以有效保持容器始终处于UP状态,非常实用.

从基础的 `ubuntu` 的 `docker` 镜像玩起的时候, 直接安装软件会报
```shell
root@c3698c616251:/# apt-get install -y ping
Reading package lists... Done
Building dependency tree       
Reading state information... Done
E: Unable to locate package ping
```
这样的错误.
往往这种刚开始的错误对人的自信心打击比较大, 解决它的办法是: `apt-get update`
注意,这只是让系统可以使用ubuntu的官方源安装软件可行. 下一步是更换清华源,这是一个坑.
初始的 `Ubuntu` 镜像只有64.2Mb,里面很多东西都不完善, 包括一些证书的安装都没有. 这里所说的证书我现在的理解是一些具有公信力的网站如国内的清华源等网站并不会被镜像所认可, 而下载的 `tensorflow` 等比较大的镜像则会已经安装了这些证书, 导致自己忽略这个问题的存在. 那么, 现在遇到这个问题了, 就好好来解答一下吧.
直接简单粗暴地更换 `/etc/apt/sources.list` 文件的内容, 然后 `apt-get update` 会报错, 说清华镜像这个网站不被信任. 来来回回搞了好多次, 问题总得不到解决. 那么, 使得清华镜像等国内镜像网址被系统信任的解决办法是: 
    ```shell
    sudo apt install ca-certificates
    ```
卧槽, 无情~~~~
为什么生活就不能够简简单单一点呢?
现在,经过这些挫折以后, 简单粗暴的更换 `/etc/apt/sources.list` 就可以无误地执行了.









