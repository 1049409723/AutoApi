# AutoApi
### 项目说明 ###
* 利用github action实现定时自动运行api调用，保持E5开发活跃。
* 免费，不需要额外设备/服务器，部署完不用管啦。
* 本项目是建立在原教程可以正确调用api的假设上的，核心是paran/黑幕大佬的py脚本，本项目只是提供一个自动、免费、无需额外设备的脚本运行方式。
* 普通版

### 特别说明/Thanks ###
* 原教程博主-黑幕（酷安id-Paran）：https://blog.432100.xyz/index.php/archives/50/
* 普通版地址：https://github.com/wangziyingwen/AutoApi
* 加密版地址：https://github.com/wangziyingwen/AutoApiSecret
* 更新日志/旧版：https://github.com/wangziyingwen/Autoapi-test
* 网页获取refresh_token小工具（不建议使用）：https://github.com/wangziyingwen/GetAutoApiToken

### 区别 ###
项目用的是公共仓库（开放代码），所有人都能看到你的代码内容。

所以你的应用id、机密、令牌都会显示出来，不安全。

加密版，我把应用id、机密都隐藏了，令牌因为需要实时更新，隐藏不了（我不会！），安全性会高很多！

--------------------------------------------------------------

### 步骤 ###
* 先大致浏览[原教程](https://blog.432100.xyz/index.php/archives/50/)，或者根据原教程操作一遍，以方便接下来的操作。

* 登陆/新建github账号，回到本项目页面，点击右上角fork本项目的代码到你自己的帐号，然后你账号会出现一个一模一样的项目，接下来的操作均在你的这个项目下进行。

  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/fork.png)
  
* 根据[原教程](https://blog.432100.xyz/index.php/archives/50/)修改你自己项目里的1.py，1.txt。（现在里面的数据是我的）
  
  （两种方法：在线修改（推荐）。或者把项目下载下来修改，删掉项目里的1.py、1.txt，再把修改好的上传上去）
  
     > 1.txt内容的应该是开头OAQ....AA结尾（目前我看到的都是这种格式） ，结尾不要留空格或者空行
  
* 进入你的个人设置页面( 右上角头像 Settings，不是仓库里的 Settings )，选择 Developer settings > Personal access tokens > Generate new token,

  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/Settings.png)
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/token.png)

  设置名字为GITHUB_TOKEN , 然后勾选 repo , admin:repo_hook , workflow 等选项，最后点击Generate token即可。
  
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/repo.png)
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/adminrepo.png)
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/workflow.png)

* 点击右上角星星/star立马调用一次，再点击上面的Action就能看到每次的运行日志，看看运行状况

 （必需点进去Test Api看下，api有没有调用到位，有没有出错。外面的Auto Api打勾只能说明运行是正常的，我们还需要确认10个api调用成功了，就像图里的一样。如果少了几个api，就是注册应用的时候赋予api权限没弄好）

  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/日志.png)

* 没出错的话，就搞定啦！！再看看下面的定时次数要不要修改，不打算改就不用管了。

  我设定的每6小时自动运行一次，每次调用3轮（点击右上角星星/star也可以立马调用一次），你们自行斟酌修改（我也不知道活跃要调用多少、多久）：

  * 定时自动启动修改地方：（在.github/workflow/autoapi.yml文件里，自行百度cron定时任务格式）
   
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/定时.png)
   
  * 每次轮数修改地方：（在1.py最后面）
   
  ![image](https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/次数.png)
   
------------------------------------------------------------
### 题外话 ###
> Api调用
  你们可以自己去graph浏览器看一下，学着自己修改要调用什么api(最重要的是调用outlook、onedrive)
  https://developer.microsoft.com/zh-CN/graph/graph-explorer/preview

### GithubAction介绍 ###
提供的虚拟环境：

· 2-core CPU
· 7 GB RAM 内存
· 14 GB SSD 硬盘空间

使用限制：
* 每个仓库只能同时支持20个 workflow 并行。
* 每小时可以调用1000次 GitHub API 。
* 每个 job 最多可以执行6个小时。
* 免费版的用户最大支持20个 job 并发执行，macOS 最大只支持5个。
* 私有仓库每月累计使用时间为2000分钟，超过后$ 0.008/分钟，公共仓库则无限制。

（我们这里用的公共仓库，按理，你们可以设定无限循环调用，然后6小时启动一次，保证24小时全天候调用）

### 最后 ###
  教程很直白了，应该都会弄吧！

  我是代码小白，这整个项目都是我根据以往看过的代码整合的，如有什么奇怪地方，请多多包涵ORZ。
   
  有问题/修改建议可以单击上方issues发布一下，或者发邮件给我:
  wz.lxh@outlook.com
  
  建了个Q群：657581700，不过没人
  
  基安id-卷腿毛菌
