# 本地conda环境配置

## 1. update channels

```python
# alibaba mirror
https://mirrors.aliyun.com/anaconda/pkgs/main/
https://mirrors.aliyun.com/anaconda/pkgs/free/
https://mirrors.aliyun.com/anaconda/cloud/conda-forge/
https://mirrors.aliyun.com/anaconda/cloud/msys2/
```

## 2. anaconda安装在D盘，为什么new envs的位置还是C盘？

找到anaconda3文件夹所在位置，把文件夹安全属性里users的权限改为完全控制，这样new envs就可以默认保存在D:\anaconda3\envs\下。

![image-20230531225415937](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531225415937.png)
![image-20230531225835471](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531225835471.png)
![image-20230531225918658](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531225918658.png)

## 3. 添加环境变量

此电脑->属性->高级系统设置->高级->环境变量->系统变量->path->编辑->新建

![image-20230531230223489](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531230223489.png)
![image-20230531230318735](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531230318735.png)
![image-20230531230441594](https://cdn.jsdelivr.net/gh/ZL85/ImageBed@main//image-20230531230441594.png)

```python
# 需要添加的位置。
D:\anaconda3
D:\anaconda3\Scripts\
D:\anaconda3\Library\bin
D:\anaconda3\Library\mingw-w64\bin
```