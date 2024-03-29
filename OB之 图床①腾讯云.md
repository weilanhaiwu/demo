## 什么是图床

### 图床是什么

简单讲，所谓的图床就是用来**在线存放图片的地方**，你可以先简单粗暴地理解为图床就是专门用来存放图片的网盘。图床上的每一张图片都能够生成一个唯一的访问链接，使用这个链接，任何人都能够访问你的这张图片。

### 图床有什么用

个人图床可以搭配 Markdown 编辑器使用。

-   因为 Markdown 编辑器的文档无法内嵌图片，所有图片都以 `![](图片链接)`的形式写在 Markdown 文档内，如果这里的「图片链接」使用的是本地图片的链接，则当你分享这一个 Markdown 文档、或者你自己在别的地方打开这个 Markdown 文档时，文档里的图片就无法正常显示了。
-   所以需要将图片上传到图床，生成一个在线的图片链接后，在任意地方分享、打开这个 Markdown 文件，所有的图片就都能正常显示


## 基础流程简介
1.  注册腾讯云账号，并实名认证 ；5 分钟
2.  开通对象存储，并配置参数；10 分钟
3.  下载安装 PicGo，并配置参数；10 分钟
4.  完成图床搭建，并实际应用；5 分钟

## 具体操作

### 免费创建腾讯云账号

1.  访问 [腾讯云](https://eryinote.com/go?_=b40bb5185daHR0cHM6Ly91cmwuY24vZGE0S1V6ek0%3D)

2.  点击右上角的「免费注册」图标，根据提示注册腾讯云账号
![[OB基础附件/Pasted image 20221121002857.png]]

3. 微信扫码注册，然后在手机上完成「实名认证」操作。另外，不论是购买腾讯云还是阿里云，**按照政策规定都是需要实名认证的**，大家不用过度担心实名认证是否会泄露个人隐私。
![[OB基础附件/Pasted image 20221121003147.png]]

### 开通并配置腾讯云对象存储（COS）

这里你可以将「对象存储」简单理解为网盘，我们的所有图片最终都会上传到这个网盘中，那么就像百度网盘一样，你是需要为这些存储空间或者下载图片的流量进行付费的，不过就我个人的使用体验而言，使用对象存储搭建的图床费用真的非常非常低，**每个月的资费只需要几毛钱就够了。**

1.  点击 [这个网址](https://eryinote.com/go?_=fb37322f65aHR0cHM6Ly9jb25zb2xlLmNsb3VkLnRlbmNlbnQuY29tL2Nvcw%3D%3D) 进入对象存储的开通页面

2.  点击「同意协议」，然后再点击「开通 COS」
![[OB基础附件/Pasted image 20221121003533.png]]

3.  开通后你会获得 50G 的免费存储额度，有效期为 180 天，到期后，你可以购买一个 10G/1年 的存储包，只需要不到 10 元，10G 的容量用来当个人笔记的图床完全够用了
![[OB基础附件/Pasted image 20221121003832.png]]

4.  点击左侧「存储桶列表」- 「创建存储桶」
![[OB基础附件/Pasted image 20221121003910.png]]

5.  按照下图所示，填写个人资料，并选择「公有读、私有写」，然后点击「下一步」
![[OB基础附件/Pasted image 20221121003938.png]]

6.  按照下图所示，自行决定是否要开启「多 AZ 特性」，然后「下一步」，再「创建」即可。
![[OB基础附件/Pasted image 20221121004058.png]]

7.  在「文件夹列表」中，找到并点击「创建文件夹」，然后记住下图中的两个参数
![[OB基础附件/Pasted image 20221121004127.png]]

8.  获取存储桶的所在区域
![[OB基础附件/Pasted image 20221121004258.png]]

9.  获取用户秘钥配置
-   [点我](https://eryinote.com/go?_=7e4b37595eaHR0cHM6Ly9jb25zb2xlLmNsb3VkLnRlbmNlbnQuY29tL2NhbS9jYXBp) 登录秘钥管理面板
-   点击 「新建秘钥」，然后复制并**谨慎保存** `APPID`、 `SecretID` 以及 `SecretKey`，等下要用到。注意这些秘钥一定不能泄露
![[OB基础附件/Pasted image 20221121004328.png]]


### 配置 PicGo

#### 下载 PicGo

1.  访问 PicGo 的 Github 项目地址：[Releases · Molunerfinn/PicGo (github.com)](https://eryinote.com/go?_=31614169aaaHR0cHM6Ly9naXRodWIuY29tL01vbHVuZXJmaW5uL1BpY0dvL3JlbGVhc2Vz)
2.  选择适合你的 PicGo 客户端，支持 Windows、macOS，以及 Linux
3.  安装后打开 PicGo

#### 配置 PicGo

1.  按照下图所示，填写 PicGo 的参数，然后点击确定
![[OB基础附件/Pasted image 20221121011738.png]]

2.  将默认图床切换至腾讯云图床，然后将图片拖到上传框中，测试是否可以上传，如果提示「上传成功」，就说明所有配置都成功了，恭喜！
![[OB基础附件/Pasted image 20221121011825.png]]

### 使用 PicGo

1.  在 PicGo 的默认设置中，图片上传成功后，会自动复制这张图片的链接到你的剪贴板中
2.  如果你是要搭配 Markdown 笔记软件进行使用，你可以将「链接格式」切换到「Markdown」这一栏中
3.  这样做的好处是，图片上传成功后，它会自动将图片链接转化为 `![]()` 的 Markdown 图片格式
4.  然后就可以直接到 Markdown 笔记软件中进行粘贴了
![[OB基础附件/Pasted image 20221121011946.png]]


### 对象存储到期后怎么办

1.  以腾讯云为例，到期 24 小时候视为欠费状态，欠费期间对象存储将无法进行读取操作，但会对存储空间保持原有的计费状态
2.  将账户余额充值到 0 元以上，则能恢复所有功能
3.  到期 120 天后视为放弃 COS，腾讯云会删除所有数据

### 注意：

如果用的是 Obsidian，则需要下载 `Image auto upload Plugin` 这个插件，也能实现插入图片自动上传图床的效果
![[OB基础附件/Pasted image 20221121012320.png]]