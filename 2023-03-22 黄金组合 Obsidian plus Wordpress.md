---
title: 黄金组合：Wordpress + Obsidian
tags:
  - wordpress
  - obsidian
postId: '17'
categories:
  - 2
---

> 今日冥想：10分钟
> 单词学习：itinerary，旅程；rural，乡村；insolent，无礼
> 今日运动：引体向上5个

我用Hexo搭建的静态博客突然无法更新，想想还是用Wordpress更靠谱些。
另外搜索Obsidian有插件支持发布到Wordpress，二者组合有利于持续内容更新。

第一步 创建子域名
- 到域名管理后台（Dnspod），增加一个子域名：blog.qiaomu.life

第二步 创建站点资源和服务
- 登录服务器后台（宝塔Web UI），用子域名创建站点、数据库、FTP。

第三步 下载Wordpress安装包
- SSH登录服务器，进入站点目录，用wget 下载最新的Wordpress安装包
```
wget https://cn.wordpress.org/latest-zh_CN.tar.gz
```
- 解压安装包到当前目录
```
tar -xzvf latest-zh_CN.tar.gz -C . --strip-components=1
```
第四步 安装Wordpress
- 访问 blog.qiaomu.life ，按步骤填写网站资料、数据库信息完成安装。

第五步 配置读写权限（方便网站更新、插件和模版在线安装）
- SSH登录到服务器，修改wp_config.php文件，增加下面内容
```
define ("FS_METHOD","direct");
define ("FS_CHMOD_DIR", 0777);
define ("FS_CHMOD_FILE", 0777);
```

第六步 安装主题
网上搜到一个适合国人的博客主题
https://github.com/seatonjiang/kratos
下载压缩文件，然后到Wordpress后台上传安装主题并启用。

第七步 安装Obsidian插件
Obsidian中第三方插件市场搜Wordpress，安装“Wordpress 发布插件”，启用插件并做设置。

第八步 创建文章
发布到Wordpress的文章需要在Obsidian页面头部增加一段标记，格式如下
```
---
title: '文章标题'
tags:
  - 标签1
  - 标签2
---
```

写完文章，按Command+P 搜Wordpress，选择发布到Wordpress，输入账号密码，发布成功。

后续优化：
- 给发布功能设置一个快捷键，方便快速发布。
- 创建一个文章发布模版，不用每次输入头部标记。

博客地址：[http://blog.qiaomu.life/](http://blog.qiaomu.life/)



