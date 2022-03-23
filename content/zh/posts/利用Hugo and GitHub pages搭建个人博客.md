---
title: "利用Hugo and GitHub Pages搭建个人博客"
date: 2021-02-02T12:23:38+08:00
draft: false
toc: True
---
> 本人最近使用Hugo和GitHub Pages搭建了个人博客兼个人主页，这篇笔记记录了搭建过程。

## GitHub pages

参考GitHub pages的[官方入门文档](https://pages.github.com)即可

注意：仓库名必须为`<your_user_name>.github.io`

## Hugo

[Hugo官网](https://gohugo.io/)

可以直接参考Hugo的[quickstart](https://gohugo.io/getting-started/quick-start/)和[basic Usage](https://gohugo.io/getting-started/usage/)

注意：quickstart中是使用`git submodule`安装主题的，而似乎使用`Hugo Modules`安装更为便捷，更新也更为方便，因此我使用该种方式进行安装与更新。

我使用的主题是[eureka](https://github.com/wangchucheng/hugo-eureka)

这个[文档](https://www.wangchucheng.com/zh/docs/eureka/)有关于该主题详尽的安装，配置，发布内容等等的说明。

以下记录一下我的操作

1. `hugo mod init wxp_site`

2. 将exampleSite中的config文件夹复制到项目根目录下，对config文件夹的内容进行配置。

3. 在本地服务器中预览项目 `hugo server -D`其中 -D 选项可以显示在`front matter`中`draft`设置为`true`的内容。该功能主要用来调试。

4. `hugo`用来生成最终的网页。它默认会将内容写进public文件夹中，但如果你想要部署在GitHub pages上，那么你可以在`config.yaml`中修改`baseURL`以及`publishdir`的值，我的值为

   ```yaml
   baseURL: https://WindowsXp-Beta.github.io
   publishdir: /Users/weixinpeng/Desktop/computer_science/sjtu-windowsxp.github.io #即为github.io的本地仓库
   ```

5. 配置主页，按照[文档](https://www.wangchucheng.com/zh/docs/eureka/)配置主页。你可以参考examplesite中关于homepage的配置来生成样例。

   > 注意：主页配置中需要加入`index.md`文档，详见[hugo-eureka discussions/42](https://github.com/wangchucheng/hugo-eureka/discussions/42).
   >
   > 似乎用`hugo module`安装没有examplesite了:sob::sob::sob:了，可以先用git submodule安装，基本配置完再换回hugo module，[文档](https://www.wangchucheng.com/zh/docs/eureka/)中有转换的方法。当然，不参考examplesite直接配也行，你也可以ask me:stuck_out_tongue_winking_eye::stuck_out_tongue_winking_eye::stuck_out_tongue_winking_eye:

6. 在本地修改调试完成后，直接`hugo`即可上传到本地`<user_name>.github.io`仓库（你需要按照4中提到的修改`config.yaml`文件）。再`git pull`到GitHub上即可完成发布。

## 绑定域名

1. 去域名注册商购买域名

   > 我在[阿里云](https://www.aliyun.com/)购买了我的域名

2. 域名解析直接参考阿里云的教程 [添加网站解析](https://help.aliyun.com/document_detail/106535.html?spm=a2c4g.11186623.2.3.18f65cfaIrFU4p)。

   > 注意：如果直接按照新手教程解析，是按照A记录进行解析的，此时GitHub会报一个warning，解决方法就是使用CNAME进行解析。

3. 在`<user_name>.github.io`仓库中添加文件 CNAME 。文件内容即为你的新域名，比如我的CNAME文件为

   ```yaml
   www.windowsxp.xyz
   ```

4. 在`<user_name>.github.io`的GitHub仓库的settings中的options选项找到Custom domain添加域名。

   > 这一步网上教程都有，但我添加完 CNAME 文件后这里就自动设置好了。

---

<strong>至此搭建完毕，可以通过 新域名 访问你的博客啦！！Cheers！！:beers::beers::beers:</strong>