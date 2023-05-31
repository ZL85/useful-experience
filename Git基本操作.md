# Git基本操作

## 1. Git下载

[Git - Downloading Package (git-scm.com)](https://git-scm.com/download/win)

## 2. Git与GitHub连接

### 2.1 本地配置

(1)使用以下命令进行本地配置

```c
git config --global user.name "your name"
git config --global user.email "email@example.com"
```

(2)启用默认的颜色设置（单纯为了好看）

```c
git config --global color.ui auto
```

> git config命令的--global参数，用了这个参数，表示你这台机器上所有的 Git 仓库都会使用这个配置

(3)查看配置的相关信息

```c
git config --list
```

### 2.2 连接GitHub

(1)生成ssh公钥

```C
ssh-keygen -t rsa -C "email@example.com"
```

> 按三次回车键即可生成 ssh key

(2)找到id_rsa.pub这个文件，用文本编辑器（如记事本）打开，复制里面的所有内容。

(3)登陆github账号，点击头像旁的小三角展开，点击settings-SSH and GPG keys-New SSH key

![image-20230531213843503](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531213843503.png)

(4)在Title中取一个名字（任意），key中粘贴你刚刚复制的内容。然后点击Add SSH key即可。

![image-20230531213950311](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531213950311.png)

(5)验证是否成功，在git bash里输入下面的命令

```c
ssh -T git@github.com
```

> 出现`Hi your name! You've successfully authenticated, but GitHub does not provide shell access.`即为成功。

## 3. 将本地仓库推送到GitHub

### 3.1 在GitHub上新建仓库

![image-20230531214610847](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531214610847.png)
![image-20230531214704459](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531214704459.png)

### 3.2 初始化本地仓库

(1)在你要提交的目录下

```c
git init
```

(2)和远程创建的仓库建立连接

```c
git remote add origin git@github.com:your name/reposotory name.git
```

(3)push前先将远程repository的修改pull下来, 避免之前本地仓库和远程仓库不一致, 导致提交出错

```c
git pull origin main
```

### 3.3 本地作出修改后提交

(1)将文件添加至暂存区

```c
git add .
```

(2)将暂存区内容添加到本地仓库中

```c
git commit -m "update"
```

(3)将本地仓库内容推送至GitHub仓库main分支下

```c
git push -u origin main
```

(4)查看Git状态

```c
git status
```

## 4. 拉取远程仓库到本地

```c++
git clone git@github.com:your name/reposotory name.git
```

