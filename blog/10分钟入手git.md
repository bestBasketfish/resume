## git是什么


> Git(读音为/gɪt/。)是一个开源的分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理。Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。


**使用git的优势**
- 速度快
- 涉及的原理简单
- 允许上前个并行分支
- 分布式管理系统


## git的下载安装
  大家可以前往[git官网](https://git-scm.com)下载安装包，根据自己的系统选择相应的安装包，进行默认安装即可。windows版本安装好后会有一个叫Git Bash的文件。

 ![ 打开后就是这样的](https://upload-images.jianshu.io/upload_images/14545801-43b87add628dbf56.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## 下载安装好后我们先创建一个自己的github远程仓库

> 1.gitHub是一个面向开源及私有软件项目的托管平台，因为只支持git 作为唯一的版本库格式进行托管，故名gitHub。
2.github是一个基于git的web 协作社区，它有多种机制让大家协同的和你一起的对项目进行贡献。
3.github全平台、全设备支持，你可以在任何终端上，随时随地的共享你的代码、评论或着其他有意义的信息。
4.这个世界上最大的开源软件社区。

大家可以[github官网](https://github.com)进行注册。

注册成功后可以点下图所示创建一个自己的库

![点这里](https://upload-images.jianshu.io/upload_images/14545801-7957fe4decdfecb6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![点点点](https://upload-images.jianshu.io/upload_images/14545801-d22dba0dafb583fc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
到这里你就创建你自己的github仓库了。
下面让我们回到Git Bash
输入下面两条命令
```
git config --global user.name "your name"  
输入你的用户名,按回车输入下一行
git config --global user.email "your email"  
输入你的邮箱名，按回车输入
```
现在我们可以创建连接远程仓库的公钥私钥了

`ssh-keygen -t rsa-C "你注册github的邮箱" `

输入后一直按回车就可以了
![箭头所指就是钥匙存放的地址](https://upload-images.jianshu.io/upload_images/14545801-f0ca45ba70e290f7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

使用命令行打开该文件或者找到存放地址复制文件里的信息。**注意一定要是公钥噢后面.pub的，私钥千万不要给别人。**
![复制从SSH开始到.com结束](https://upload-images.jianshu.io/upload_images/14545801-5cbbcb68cf64bf70.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

到这里git就设置好了 接下来进入github设置

![点头像点这](https://upload-images.jianshu.io/upload_images/14545801-74c0caf81a0292f8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![点点点](https://upload-images.jianshu.io/upload_images/14545801-b159f7ae8c7d0ba8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![最后公钥终于搞好啦](https://upload-images.jianshu.io/upload_images/14545801-cc4d590bd2d80d00.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

然后通过git把我们github的库拷贝到本地来

![点点](https://upload-images.jianshu.io/upload_images/14545801-5d703c4280b33bc7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![复制这个SSH地址](https://upload-images.jianshu.io/upload_images/14545801-b7ef88b314a190d4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

` git clone 你刚才复制的`  在Git Bash中进入一个自己存放代码的文件夹输入这个，如下图所示已经进入远程仓库成功啦
![我是下图额....](https://upload-images.jianshu.io/upload_images/14545801-8b8e44a86498732b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## git基本命令学习

**1.创建新文件 **
`touch a.md`

![ls 可以查看文件](https://upload-images.jianshu.io/upload_images/14545801-98bab941eee28e21.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**2.在文件里写入一个字符串**
` echo "hahaha" > a.md `
![cat可以查看文件内容](https://upload-images.jianshu.io/upload_images/14545801-e897ee4b04993fea.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**3.查看工作区文件是否被跟踪 ，是否已经放入暂存区**

`git status`

![上传到远程仓库大概的流程](https://upload-images.jianshu.io/upload_images/14545801-a67f9bd8556d982b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![红色就说明未被跟踪](https://upload-images.jianshu.io/upload_images/14545801-909aaf33ba23786e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![绿色说明已经在暂存区了](https://upload-images.jianshu.io/upload_images/14545801-6ebae26fa4b235af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![这就说明暂存区啥也没，说明已经保存到本地仓库了](https://upload-images.jianshu.io/upload_images/14545801-29cc07cf53c6b38e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


**4.将工作区修改的文件放入暂存区**

![我已经在暂存区啦](https://upload-images.jianshu.io/upload_images/14545801-aed61fbe976101ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**5.将暂存区文件保存至本地仓库**

` git commit -m "test" `  后面的test是一个备注，可以是任意文本，用于备注
![我已经在本地仓库保存了，不保存不能去远程仓库啦](https://upload-images.jianshu.io/upload_images/14545801-fb66d3ed89a9dc5b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**6.将本地仓库的文件上传到远程仓库**
` git push`
![上传](https://upload-images.jianshu.io/upload_images/14545801-3554865c6e3d4471.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![上传成功啦](https://upload-images.jianshu.io/upload_images/14545801-b4071508c83410be.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**7.将本地仓库更新成远程仓库**

`git pull`  
如果不先把自己本地仓库更新到最新版本，上传就会报错。
![啊 我错啦](https://upload-images.jianshu.io/upload_images/14545801-85760103c363475a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)![现在就好啦 同步了](https://upload-images.jianshu.io/upload_images/14545801-bed9cd051ac05d4b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**8.修改文件**
`vim a.md`  进入修改页面按i进入插入模式，修改好了按ESC退出插入模式。
输入`:wq`就会保存退出，若不想保存则按`:q!`退出。
![谁乱打文字我要哈哈哈](https://upload-images.jianshu.io/upload_images/14545801-3c257a949410c211.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**9.删除文件**
`rm a.md`
![删除](https://upload-images.jianshu.io/upload_images/14545801-5ae729cf5a81d049.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 结束啦



















