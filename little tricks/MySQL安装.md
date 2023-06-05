# MySQL安装

## 1. 下载

[Download MySQL Installer](https://dev.mysql.com/downloads/windows/installer/5.7.html)

## 2. 安装

自定义安装位置D:\MySQL\MySQL Server 5.7

## 3. 设置环境变量

将D:\MySQL\MySQL Server 5.7\bin添加到系统变量中

## 4. 验证是否安装成功

win+R -> cmd -> cd D:\MySQL\MySQL Server 5.7\bin -> mysql -h localhost -u root -p登录数据库，再输入数据库密码 -> 输入 status 命令可以查看 MySQL的 版本信息，说明安装成功。

![image-20230602161926351](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230602161926351.png)