---
title: 一些P话
updated: 
categories: 网站设置
description: 网站设置的一些心得
tag: [网站设置, 常用命令]
---
————
常用：
Hexo三连：```hexo clean; hexo g; hexo d(本地浏览是hexo s)```
新建文章：```hexo new post "name"```
Post Front-matter:[参考链接](https://butterfly.js.org/posts/dc584b87/#Page-Front-matter)
————
魔改过程中浏览了无数教程，发现Blog目前**最好**的教程是[这篇](https://meuicat.com/blog/24/)，而且该作者的美化也很好看，跟着学估计后面不用怎么改了。（后悔没早点遇到啊，悲！）
————
正文
#### 2024.04.12
Butterfly主题的Waline用不了是因为Waline升级了，需要在`plugins.yml`这个文件中修改一下Waline的版本。[参考文章](https://github.com/walinejs/waline/issues/2204)
```
waline_js:
  name: '@waline/client'
  file: dist/waline.js
waline_css:
  name: '@waline/client'
  file: dist/waline.css
```
修改后：
```
waline_js:
  name: '@waline/client@3.0.0-alpha.8'
  file: dist/waline.umd.min.js
waline_css:
  name: '@waline/client@3.0.0-alpha.8'
  file: dist/waline.min.css
```
Waline新版本不稳定，后续更新可能会影响评论系统，可用回老版本：
```
waline_js:
  name: '@waline/client@2'
  file: dist/waline.js
waline_css:
  name: '@waline/client@2'
  file: dist/waline.css
```
电影模块设置参考[文章](https://meuicat.com/blog/42/#%E8%B6%B3%E8%BF%B9%E9%A1%B5)，比`hexo-douban`好用很多！而且该作者的其他魔改也很好看！强推跟着他学！！！
#### 2024.04.10
评论系统改为Valine和Livere双系统，[参考文章](https://blog.imlete.cn/article/Valine-LeanCloud-Config.html#%E5%89%8D%E8%A8%80)给Valine评论增加了QQ和微信的消息提示，[参考文章](https://moonshuo.cn/posts/51359.html#%E8%AF%84%E8%AE%BA%E7%95%8C%E9%9D%A2%E7%9A%84%E7%BE%8E%E5%8C%96)给Valine增加了博主小伙伴标识

继续探索电影界面了~ 其他界面还在路上~

！晚上突然发现Valine被墙了！我说怎么一会正常一会不正常的......[参考文章](https://blog.chyk.ink/2022/07/19/valine-block-china-fix/)弄着API域名了，过几天试试能不能用吧...不行的话只能双系统凑合用了......悲啊！！！

发现Waline好像比Valine更好玩......换系统啦~

数据储存在Leancloud，Waline也用的Leancloud，同样的问题出现了......明天再看看吧
#### 2024.04.07
livere广告太多了，评论系统想改用Valine，国际版LeanCloud上自定义域名一直显示正在部署证书，可能有点问题，改天再看看。（等了两天证书才成功）部署教程：[Valine系统设置](https://moonshuo.cn/posts/51359.html#%E9%83%A8%E7%BD%B2)

加了个在线聊天系统，用的是tidio，感觉很神奇，可惜自动回复都用的繁体，懒得一个个改了，浅浅摸个鱼~

~~电影模块用的插件```hexo douban```，[使用文档](https://github.com/mythsman/hexo-douban?tab=readme-ov-file)，还有很多没来得及探索的功能，以后再试试，[链接](https://butterfly.js.org/posts/4073eda/#%E5%BB%BA%E8%AD%B0)~~
#### 2024.04.01
今明天估计都要继续学习Md语法了
#### 2024.03.31
根据butterfly主题作者的文档，进一步完善了网站。一些Markdown语法的花里胡哨的使用手册,包含[图标、相册等用法](https://butterfly.js.org/posts/4aa8abbe/#%E6%A8%99%E7%B1%A4%E5%A4%96%E6%8E%9B%EF%BC%88Tag-Plugins%EF%BC%89)
___
发现Visual Studio可以直接编辑并预览Markdown文件，但感觉还是不如重新学习用VScode来系统学习一下Markdown，毕竟教程啥的足够多。
虽然VS也内置了Markdown，但是感觉可能不够完善吧，一些插件也不知道适不适用，还是稳妥点好哇。
暂时先记录一下这两天干的事情吧。

#### 2023.12.18
拖更至今完全是因为卡死在了把==本地图片上传到网站==这一步...网上相关的解决方法可以说是不计其数，然后试了nnnnn种方法到现在才实际解决问题，改天出个问题合集吧；）

先浅浅记录一下关键点，要不然忘了捏
首先是FN+F12进入开发者模式查看问题，再搜索相关解决方案
1.浏览器之前安装过的屏蔽插件可能拦截了图片加载，还有设置的拦截cookies也可能影响（针对重定向次数过多打不开网站）
2.网上各种安装其他插件的（包括不限于hexo-asset-img/hexo-image-link/hexo-asset-image/...），最后是下了hexo-filter-image才解决了问题，目前存在的插件有`hexo-filter-image`和`hexo-image-link`，后者有没有用不知道，前一个解决不了再试下第二个呗
3.中间还尝试了用图床的方法上传图片，后面发现本地图片也能正常上传了，所以图床方法也就可有可无了。参考：[阿里云OSS PicGo 配置图床教程 超详细](https://zhuanlan.zhihu.com/p/104152479)
4.本地图片上传方法，写Md文件时引用格式也是千奇百怪（网上发现各有各的问题...解决方法时灵时不灵...只能都试试了呗）
[参考链接1](https://ifwind.github.io/2021/06/17/hexo%E6%90%AD%E5%BB%BA%E5%8D%9A%E5%AE%A2%E5%87%BA%E7%8E%B0%E7%9A%84%E4%B8%80%E4%BA%9B%E9%97%AE%E9%A2%98%EF%BC%88%E6%8C%81%E7%BB%AD%E6%9B%B4%E6%96%B0-%EF%BC%89/#tips)   [参考链接2](https://unpurerationalist.github.io/2023/02/23/Hexo-%E5%8D%9A%E5%AE%A2%E6%97%A0%E6%B3%95%E6%98%BE%E7%A4%BA%E5%9B%BE%E7%89%87%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95/)   [参考链接3](https://blog.csdn.net/CHN_Joker/article/details/125339751?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-8-125339751-blog-107191688.235^v39^pc_relevant_anti_vip_base&spm=1001.2101.3001.4242.5&utm_relevant_index=11)
其他还没来得及整理


在解决问题过程中还尝试了一些有的没的hhh
1.VScode的主题亲测Monokai Pro好看！[vscode插件(扩展)Monokai pro提示需要li**se解决办法](https://blog.csdn.net/BjarneCpp/article/details/111565063)
2.用VScode打开js文件有可能是未经格式化的，需要另外下载一些拓展才能实现格式化，网上教程很多一搜就能找到了，应该是会用到Prettier-Code formatter这个插件的。[Vscode插件——自动格式化代码：Prettier](https://blog.csdn.net/weixin_43533151/article/details/113416862)
3.网站没有备案的话（国内大部分CDN加速服务是需要网站备案的），CDN加速用cloudfare吧（baipiao真的香），虽然好像大家评价不是很好（服务器在国外，国外进去快，国内加速不明显），实际体验没啥问题（当然也可能是网站现在东西太少的缘故hhhhhh）[Cloudflare新手指南：如何使用并快速上手](https://blog.csdn.net/qq_58995858/article/details/132418319)

#### 2023.12.2
1.换了头像
2.给Blog新加了网易云音乐，不过不能自动播放，还是需要手动点一下，不知道是不是浏览器的问题，反正代码的autoplay是true了的。
3.博客文章下加了评论功能，用的是livere（来必应）的。

#### 2023.12.1
建了blog，网上教程一堆，推荐[知乎这篇](https://zhuanlan.zhihu.com/p/102592286/)，跟着来就行。
主题从next换成了butterfly，感觉butterfly的主题更有趣些，过于简洁的next还是显得略微无趣了。