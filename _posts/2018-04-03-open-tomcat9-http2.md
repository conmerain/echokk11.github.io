---
author: Wuk
date: 2018-04-03 11:42:32+00:00
layout: post
title: tomcat9开启http2支持
tags:
- http2
- tomcat9
- ssl
---

### 生成证书
下载tomcat9
```bash
cd $tomcat9/
mkdir ssl
cd ssl
openssl genrsa -out server.key 2048
openssl rsa -in server.key -out server.key
openssl req -new -x509 -key server.key -out ca.crt -days 3650
```

### 修改server.xml
```xml
<Connector port="8443" protocol="org.apache.coyote.http11.Http11AprProtocol"
            maxThreads="150" SSLEnabled="true" >
    <UpgradeProtocol className="org.apache.coyote.http2.Http2Protocol" />
    <SSLHostConfig>
        <Certificate certificateKeyFile="ssl/server.key"
                        certificateFile="ssl/ca.crt"
                        type="RSA" />
    </SSLHostConfig>
</Connector>
```

### 安装apr，mac为例
下载[apr](https://apr.apache.org/download.cgi)
```bash
cd apr
CFLAGS='-arch x86_64' ./configure
make
sudo make install
```
默认安装路径在`/usr/local/apr`

```bash
brew install openssl
```

```bash
cd $tomcat9/bin
tar zxvf tomcat-native.tar.gz
cd tomcat-native-1.2.16-src/native
CFLAGS='-arch x86_64' ./configure --with-apr=/usr/local/apr --with-ssl=/usr/local/opt/openssl --with-java-home=/Library/Java/JavaVirtualMachines/jdk1.8.0_152.jdk/Contents/Home
make
sudo make install
```

最后加链接
```bash
sudo ln -s /usr/local/apr/lib/libtcnative-1.dylib /Library/Java/Extensions/
```