---
layout: post
category: "python"
title:  "关于Flask的一个简单的应用及Restful服务"
tags: [web,python]
---
最近开始找关于接口服务，刚好自己时常看Python，所以借用Python的Flask框架学习一下。
<!-- more -->

### 关于Flask的一个简单的应用

1. Python安装和升级  
Linux默认的python版本是2.6.6，为了使用Python2,7,需要进行升级。
考虑到部分服务依赖原有的Python，对其他服务的影响。不建议删除原有的版本。  
1)首先，下载源码包，命令如下：
```
wget --no-check-certificate https://www.python.org/ftp/python/2.7.8/Python-2.7.8.tgz
```
注：因为下载网址是https开头的，所以要给wget命令加上--no-check-certificate参数。  
2）下载好源码包后，解压：
```
tar -zxvf ./Python-2.7.8.tgz
```
3)解压出Python-2.7.8这个目录后，我们开始对源码进行编译：
```
cd Python-2.7.8
./configure --prefix=/usr/local/python
make
make install
```
4)编译安装完成后，要替换掉系统自带的Python，但CentOS的yum依赖于Python工作，为了保证yum的正常运行，我们要在替换前，先将自带的Python更名备份，方法如下：   
```
mv /usr/bin/python /usr/bin/python-2.4.3
ln -s /usr/local/python/bin/python /usr/bin/python
```
5)上面两行命令执行完后，可以分别用“python -V”和“/usr/bin/python-2.4.3-V”来验证部署是否成功，正确的结果应该是2.7.8和2.4.3。
最后，要修改yum，让其运行指向旧的版本： 
```
vi /usr/bin/yum    
```
6）将第一行中的“#!/usr/bin/python”修改为“#!/usr/bin/python-2.4.3”，保存即可。

2. Python进行安装setuptools软件包
(1)下载setuptools包
```
wget http://pypi.python.org/packages/source/s/setuptools/setuptools-2.0.tar.gz
```
(2)解压setuptools包
```
# tar zxvf setuptools-2.0.tar.gz
# cd setuptools-2.0
```
(3)编译setuptools
```
# python setup.py build
(4)开始执行setuptools安装
# python setup.py install
```
注：可能会出现
"Compression requires the (missing) zlib module"这个错误。
是因为缺少 zlib和  zlib-devel
执行下面命令
yum install zlib
yum install zlib-devel
在源安装文件目录重新编译make

3. pip安装
```
tar -xvf pip-1.4.1.tar.gz 
 cd pip-1.4.1/  
sudo python setup.py install 
##pip升级
python -m pip install -U pip
```
注：如果存在链接存在，则 rm -rf  /usr/bin/pip
yum install openssl -y
yum install openssl-devel -y

4. 虚拟环境安装
虚拟环境的安装
```
pip install virtualenv
ln /usr/local/python-2.7.13/bin/virtualenv  /usr/bin/python/virtualenv -- 无法执行
```
创建虚拟环境
```
/usr/local/python-2.7.13/bin/virtualenv  (虚拟环境名）
```
激活虚拟环境
```
source 虚拟环境名/bin/activate
```
返回全局环境
```
deactivate
```

5. Flask的安装
```
pip install Flask
```
注：pip如果版本太低，会出现安装失败。

6. flask简单应用  
hello.py
```
from flask import Flask
app = Flask(__name__)
@app.route('/')
def index():
        return '<h1>Hello World!</h1>'
if __name__ == '__main__':
        app.run(host='0.0.0.0',port=5000)
```
注：应用返回Hello World! 0.0.0.0用于局域网访问  
```
###测试服务，192.168.255.129为服务器IP
curl http://192.168.255.129:5000
```
显示如下：  
![](\img\post_img\1511623399(1).png)  
开通端口5000    
```
iptables -I INPUT 1 -p tcp --dport 5000 -j ACCEPT
```

### Restfulf服务