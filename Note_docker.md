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













