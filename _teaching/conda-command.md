
## 查看已安装的环境
```
conda info -e
```

## 切换不同python版本内核
```
ctivate python27
#返回默认版本
deactivate
```

## 更新Conda
```
conda update conda
```
## 更新Anaconda
```
conda update anaconda
```
## package管理命令
```
#查看所有已安装包
conda list
#查看package信息
conda search requests
#安装package
conda install requests
#更新package
conda update requests
#删除package
conda remove requests
```

## 镜像源设置
```
#添加新镜像源
#清华镜像
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --set show_channel_urls yes
#阿里镜像
conda config --add channels https://mirrors.aliyun.com/pypi/simple/
#中国科技大学镜像
conda config --add channels https://mirrors.ustc.edu.cn/pypi/web/simple

#移除镜像源
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
```
