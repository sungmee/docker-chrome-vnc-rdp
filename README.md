# Google Chrome via VNC or RDP

可通过 VNC 或 RDP 远程桌面连接的基于 Ubuntu 16.04 的 Google Chrome Web 桌面浏览器。本 Fork 基于 [sfoxdev/docker-chrome-vnc-rdp](https://github.com/sfoxdev/docker-chrome-vnc-rdp) 修改为支持中文显示，使用“文泉驿微米黑”字体。

[![Docker Build Status](https://img.shields.io/docker/build/sfoxdev/chrome-vnc-rdp.svg?style=flat-square)]()
[![Docker Build Status](https://img.shields.io/docker/automated/sfoxdev/chrome-vnc-rdp.svg?style=flat-square)]()
[![Docker Build Status](https://img.shields.io/docker/pulls/sfoxdev/chrome-vnc-rdp.svg?style=flat-square)]()
[![Docker Build Status](https://img.shields.io/docker/stars/sfoxdev/chrome-vnc-rdp.svg?style=flat-square)]()

## 使用方法

### 建立容器
```
docker build -t sungmee/chrome-vnc-rdp .
```

### 运行没有密码的容器

```
docker run -d -p 5900:5900 -p 3389:3389 --name chrome sungmee/chrome-vnc-rdp
```
### 使用密码运行容器

```
docker run -d -e PASSWORD=mypassword -p 5900:5900 -p 3389:3389 --name chrome sungmee/chrome-vnc-rdp
```

### 使用 docker-compose

```
version: '3'

services:
  app:
    image: sungmee/chrome-vnc-rdp
    container_name: chrome
    restart: always
    ports:
      - 5900:5900
      - 3389:3389
    environment:
      - PASSWORD=mypassword
```

```
docker-compose up -d
```