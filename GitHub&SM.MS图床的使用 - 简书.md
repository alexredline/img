# [GitHub&SM.MS图床的使用 - 简书 (jianshu.com)](https://www.jianshu.com/p/155fa7e46763)

2020.03.11 21:54:51字数 770阅读 1,370

引言
--

 markdown原则上不建议使用base64内嵌图片，因为太麻烦。

 如果只是在本机浏览、编辑的话，那引用相对路径或者绝对路径即可，但是考虑到要发布、分享的情况，使用图床是比较好的解决方案。

 本教程可以快速得到一个相对稳定的免费图床，不需要已经备案的域名，而且在免费图床中较为稳定。

 以下是作为个人免费图床GitHub和SM.MS的对比，

| 图床 | 稳定性 | 安全性 | 访问速度 | 上手难度 |
| --- | --- | --- | --- | --- |
| GitHub | 高 | 高 | 一般 | 简单 |
| SM.MS | 一般 | 一般 | 较快 | 简单 |

 GitHub由于不可描述的原因，在国内访问速度并不是很稳定，下文讲通过修改host文件来达到加速的效果，而[SM.MS](https://links.jianshu.com/go?to=http%3A%2F%2FSM.MS)是由V2EX大佬@[Showfom](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.v2ex.com%2Fmember%2FShowfom) 在2014年上线的免费图床项目，目前在国内访问速度较快，偶尔可能出现不能用的情况，个人免费额度是5G。

 准备工具：PicGo。这是一款开源的本地图片上传图床管理的工具，支持markdown、html、url等格式，地址：[https://github.com/Molunerfinn/PicGo/releases](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2FMolunerfinn%2FPicGo%2Freleases)，选择相应的版本下载即可，如windows版本选择PicGo-Setup-2.2.2.exe，安装过程略过。

GitHub
------

#### 1.先解决访问慢的问题

 在C:\\Windows\\System32\\drivers\\etc目录下找到hosts文件，右键用记事本或者其他编辑器打开，在最下面另起一行添加下面的文本：

```
192.30.253.112 github.com 
185.199.109.153 assets-cdn.github.com 
199.232.5.194 github.global.ssl.fastly.net 
140.82.114.9 codeload.github.com 
199.232.28.133 raw.githubusercontent.com 
```

 保存。

#### 2.创建一个GitHub账号

 在官网[https://github.com/](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2F)注册登录即可，过程略。

#### 3.新建一个仓库（Repositories）用来存放图片

```
1. 登录后在主页左侧点击New
2. 填写Repository name名称，这里以img为例。
3. Description随便填，如这是我的图床。
4. 选择Public公开。
5. Initialize this repository with a README可不选。
6. 最后单击Create repository即可。 
```

#### 3.获取Token

1.  单击右上角头像，下来菜单中选择settings。
    
2.  在左侧导航栏找到Developer settings。
    
    ![](https://upload-images.jianshu.io/upload_images/17029678-7656c08d619ed359.png)
    
    img
    
3.  在弹出的产生token页面，Token description随意填写，但是一定要勾选上这几项。
    
    ![](https://upload-images.jianshu.io/upload_images/17029678-55b2842f6875b416.png)
    
    img
    
    注：token要保管好，丢了只能重新获取，之前的就失效了。

#### 4.配置PicGo

```
1. 打开后左侧选择图床设置，找到GitHub图床。
2. 仓库名填写自己的ID/刚刚创建的仓库名，如Tom/img。
3. 分支名填master。
4. Token填入刚刚获取到的Token。
5. 存储路径不用填。
6. 自定义域名按https://raw.githubusercontent.com/id名/仓库名/master的格式填写。
7. 单击确定，大功告成。 
```

SM.MS
-----

1.  #### 创建一个SM.MS账号
    
    进入官网：SM.MS，注册登录过程略。
    
2.  #### 获取Token
    
    1.  单击右上角User，选择Dashboard进入控制台。
    2.  左侧选择API Token。
    3.  点击按钮生成Token，复制。
3.  #### 配置PicGo
    
    1.  打开后左侧选择插件设置，注意：内置的SM.MS已经无法使用，这里需要另外设置。
    2.  在插件设置中搜索smms-user，单击下载安装即可。
    3.  在[https://nodejs.org/zh-cn](https://links.jianshu.com/go?to=https%3A%2F%2Fnodejs.org%2Fzh-cn)中安装node.js，选择长期支持版。
    4.  在左侧图床设置中找到刚刚安装的SM.MS-登录用户，单击后在弹出的菜单填入刚刚的token即可。
    5.  单击确定，大功告成。
