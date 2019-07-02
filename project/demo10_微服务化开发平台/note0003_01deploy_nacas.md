## 安装 mvn

```
shell脚本中source aaa.sh时提示 source: not found 或者sorce的东西并没有生效。

解决方法： 

命令行执行：sudo dpkg-reconfigure dash

在界面中选择no
```


shll 脚本
```
#! /bin/bash

cd /root
wget http://mirror.bit.edu.cn/apache/maven/maven-3/3.6.1/binaries/apache-maven-3.6.1-bin.tar.gz

mv apache-maven-3.6.1-bin.tar.gz /usr/local/

cd /usr/local/

tar -zxvf apache-maven-3.6.1-bin.tar.gz

rm -rf apache-maven-3.6.1-bin.tar.gz

addstr0="export M2_HOME=/usr/local/apache-maven-3.6.1"
addstr1='export PATH=${M2_HOME}/bin:$PATH'

file=/etc/profile

echo "\n" >> $file
echo $addstr0 >> $file
echo ${addstr1} >> $file

source /etc/profile
sudo mvn -v



```

## 安装 nacas
https://nacos.io/zh-cn/docs/quick-start.html

```
#! /bin/bash
git clone https://github.com/alibaba/nacos.git
cd nacos/
mvn -Prelease-nacos clean install -U  
ls -al distribution/target/

// change the $version to your actual path
cd distribution/target/nacos-server-$version/nacos/bin

ll

```