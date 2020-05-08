**注：本文转摘于：[高级农民工公众号](https://mp.weixin.qq.com/s/Sd-ndWpXTsvqJ5OIP0hnJA)**

## 前言
> 有很多朋友刚刚学Python的时候，会来问为什么pip下载东西这么慢啊？pycharm里面下载库也是非常的慢。

这其实是个常识性的问题，我们下载的慢是因为Python使用pip方法安装第三方包时，需要从 `https://pypi.org/` 资源库中下载。这个网站是国外的服务器，访问自然就很慢，但是国内有很多的镜像站，所谓镜像站就是内容一样，只不过服务器在国内，访问速度自然而然就很快了。下面给大家普及一下如何修改pip的下载源以及pycharm的下载源。

## 电脑修改下载资源
> 在国内，比较火的就是下面这几个下载源：

```
阿里云 http://mirrors.aliyun.com/pypi/simple/
中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/
豆瓣 http://pypi.douban.com/simple/
清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/
中国科学技术大学 http://pypi.mirrors.ustc.edu.cn/simple/
```
下面会介绍mac/Linux/windows系统的修改方式

### 1. Mac/Linux
#### 1.1 临时使用
`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package`
其中some-package就是你所需要安装的第三方库。上面的网址一定要正确，一字不漏！

#### 1.2 永久修改
> 修改 `~/.pip/pip.conf`

根据个人使用经验，有些朋友没有这个文件，甚至没有这个目录，这个时候我们先创建这个目录然后创建这个文件进行编写：
```
# 创建目录
mkdir ~/.pip
# 创建并编辑文件
vim ~/.pip/pip.conf
```
将文件中的内容填写或者修改为下面的内容：
```
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
```
index-url指的是需要更换的下载源，上面已经提供了很多的下载源了，可以直接填进去。
填写后按ESC，输入wq! ,保存退出。
此时去使用pip下载东西，使用的是清华源了。

![IMAGE](resources/DD464A9BF070707546D229E55FFF83E4.jpg =1132x206)

### 2. Windows
#### 2.1 临时使用
> Windows的临时使用和mac是同样的方法。

`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package`
其中some-package就是你所需要安装的第三方库。上面的网址一定要正确，一字不漏！

#### 2.2 永久使用
1. 直接在user目录中创建一个pip目录，如：C:\Users\xxx\pip
2. 新建文件pip.ini
3. 输入以下内容：
```
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
```
这样就OK了！

## pycharm修改下载源
> 有一些朋友是直接在pycharm的环境下安装库的，这样也有一定的好处就是不会导致电脑的环境比较混乱。那如何修改pycharm的下载源呢?

1. 进入设置

![IMAGE](resources/6480AE195E1DB693B35186BC436CA4F7.jpg =1080x758)

2. 到达上图界面,随意双击任意一个库

![IMAGE](resources/50FC81EC21FF1752656BFE709CB483C4.jpg =1080x758)

3. 到达下面这个界面后，点击Manage Repositories

![IMAGE](resources/0504EED44866CE3EF3C1C38145571409.jpg =1080x872)

4. 添加下载源地址

![IMAGE](resources/71ACCAEF79F2E5D29E76FA5081D9ED61.jpg =1080x893)

这样就可以将pycharm的下载源更换为国内下载源。