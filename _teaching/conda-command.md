
## 查看已安装的环境
```
conda info -e
#或者
conda info --envs
#或者
conda env list
```

## 虚拟环境
```
#创建新环境
conda create -n new_env
#激活新环境
conda activate new_env
#退出当前环境并返回到基础环境
conda deactivate
#删除环境(注：请确保在删除环境之前已经退出了该环境)
conda env remove -n new_env
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
