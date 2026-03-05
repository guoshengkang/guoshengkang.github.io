
## 镜像源设置
```
添加新镜像源
# 清华镜像
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --set show_channel_urls yes
#阿里
conda config --add channels https://mirrors.aliyun.com/pypi/simple/
#中国科技大学
conda config --add channels https://mirrors.ustc.edu.cn/pypi/web/simple

#移除镜像源
conda config --remove channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
```
