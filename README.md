optpoly
====

概述
----
基于聚合物光波导的板级高速光互连的拓扑优化


快速开始
----
### 2D FDTD Simulation
```
cd ./optpoly
python setup.py install
cd mytest
python gdsgen.py # 生成gds文件
python mytest.py # 仿真
python monitors.py # 获得运行结果
```

### 3D FDTD Simulation
- 安装Docker (http://docker.com).
- 安装CUDA 10.0 Toolkit (https://developer.nvidia.com/cuda-10.0-download-archive).
- 安装NVIDIA-Docker (https://github.com/NVIDIA/nvidia-docker).
- 获取镜像源
```
$ git clone https://github.com/stanfordnqp/maxwell-b.git
$ cd maxwell-b
$ vim run_docker
```
- 修改`--mount`的`source=`为`MAXWELL_DOCKER_VOL`，保存，退出。
```
$ ./run_docker
$ docker exec -it [container-name-or-id] bash
```
- 进入容器后
```
# source /pyenv/bin/activate
(pyenv) # apt-get update
(pyenv) # apt-get install -y git
(pyenv) # apt-get install -y vim
(pyenv) # git clone https://github.com/stanfordnqp/spins-b.git
(pyenv) # pip3 install ./spins-b
```
- 从宿主机复制文件到容器内
```
$ docker cp *.py [container-name-or-id]:/app/spins-b/[dest]
$ docker cp *.gds [container-name-or-id]:/app/spins-b/[dest]
```

参考文献
----
- Su et al. Nanophotonic Inverse Design with SPINS: Software Architecture and Practical Considerations. arXiv:1910.04829 (2019).
