# CaffeInstallConfig
A guidance to install caffe with python2.7 on UBuntu 16.04

## Prerequisite for compile on Ubuntu

```shell
sudo apt-get install libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler
sudo apt-get install --no-install-recommends libboost-all-dev
sudo apt-get install libatlas-base-dev
sudo apt-get install python-dev
sudo apt-get install libgflags-dev libgoogle-glog-dev liblmdb-dev
```

## Prerequisite for pycaffe using python2.7

```shell
sudo pip install numpy
sudo pip install scikit-image
sudo pip install protebuf
```

## Makefile.config &amp; Makefile

- [Makefile.config](Makefile.config)
- [Makefile](Makefile)

Please pay attention to PYTHON_INCLUDE and INCLUDE_DIRS in [Makefile.config](Makefile.config) &  LIBRARIES in [Makefile](Makefile)

## Add pycaffe to python path

```python
sudo touch /usr/local/lib/python2.7/dist-packages/mypkg.pth
```

edit mypkg.pth, input `CAFFE_HOME/python`

## Reference

- 官方install：

  [http://caffe.berkeleyvision.org/install_apt.html](http://caffe.berkeleyvision.org/install_apt.html)

- 在官方install前需要处理依赖 & 常见的安装错误及解决方法：

  [http://www.jianshu.com/p/246368c783d4](http://www.jianshu.com/p/246368c783d4)

- 在Makefile.config的配置：

  [http://blog.csdn.net/espace_2009/article/details/43604591](http://blog.csdn.net/espace_2009/article/details/43604591)

  其中，根据注释可以自己调整，比如加入matlab、nccl支持等

- hdf5：（Makefile, not Makefile.config）

  [https://github.com/BVLC/caffe/issues/4808](https://github.com/BVLC/caffe/issues/4808)

- pycaffe配置：

  [http://blog.csdn.net/zhangjunhit/article/details/73740402](http://blog.csdn.net/zhangjunhit/article/details/73740402)

  pip install protobuf

- 为Python添加默认模块搜索路径：CAFFE_HOME/python

  [https://www.douban.com/note/334738164/](https://www.douban.com/note/334738164/)

- nccl（用于多核训练）：

  [http://www.nvidia.cn/object/caffe-installation-cn.html](http://www.nvidia.cn/object/caffe-installation-cn.html)

  nccl共享库的问题：

  [http://blog.csdn.net/qq_15309757/article/details/71244346](http://blog.csdn.net/qq_15309757/article/details/71244346)

  [http://www.cnblogs.com/Anker/p/3209876.html](http://www.cnblogs.com/Anker/p/3209876.html)

- 多核训练时使用的参数：

  [https://github.com/BVLC/caffe/blob/master/docs/multigpu.md](https://github.com/BVLC/caffe/blob/master/docs/multigpu.md)