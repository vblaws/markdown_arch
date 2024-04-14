# 这一篇文章主要是教大家如何在linux命令行使用git提交代码
> 提醒博主的用的是arch,所以接下来的安装命令可能会有一些不一样

## 一:Git的基本原理

`git`：一种管理文件的工具，是C/S模式的，一般都是在终端，往Github上提交。

`Github`：相当于是一个Git的服务平台，我们可以使用其提供的服务。这里面的文件是按仓库来划分的，可以认为一个仓库就是一个文件夹。
## 二:当然还是安装好git
- 先检测是否安装git
```shell
git -version
```
- 没有的话可以使用以下命令安装
```shell
sudo pacman -S git
```

## 设置用户名和邮箱
> 注意:这里只是第一次使用是时需要用到,之后就不需要了,把邮箱和姓名替换成自己的就行了，实际用处就是在提交代码时能够知道是谁提交的，让别人能够找到你。

```shell
git config --global user.email "YourEmail"
git config --global user.name "YourName"
```

## 生成`ssh`密钥对,并且将你的公钥添加到github中
- 1:生成密钥对
```shell
ssh -t rea -C "YourEmail"
然后直接按四下回车就可以了
```

- 2:获取公钥
```shell
cat .ssh/id_rsa.pub
```
> 注意,是要后面为`.pub`的

复制显示出来的内容

- 3:放在github中
 - 点击你的头像
 - 点击`Settings`
 - 找到`SSH and GPG Keys`点击
 - 再次找到`New SSH key`点击
 - 标题随便取就行
 - 下面key那一栏,就把刚刚复制的公钥黏贴进去就可以了

## 检验是否成功
 ```shell
ssh -T git@github.com
 ```
如果成功,将会有以下信息出现
```shell
Hi "YourName"! You've successfully authenticated, but GitHub does not provide shell access.
```

[先参考这个](https://www.cnblogs.com/eaglezb/p/6602123.html)
