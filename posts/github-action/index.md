# Github Action


## 为什么要配置自动发布
基于前两个部分组成方案中，一次更新过程如下：

1. 在本地写好md文章
2. 用hugo发布到public/目录下
3. 复制到本地仓库(也可以将git本地仓库配置到public/目录下，但因为我同时也在用git管理md，这么做会将两个项目的git纠缠在一起，不够清爽，违背我的审美)
4. 再推到远程仓库
   
这样做的弊端是：

1. 本地必须管理两个git仓库，一个是hugo-md源码库，另一个是生成的静态网页库，增加了更新文章的复杂度；
2. 发布必须先发一个本地，然后手动上传，也增加了出错的风险。

一个理想的状态是，我只负责写文，和将好的md提交到git备份，然后就可以坐等网站内容更新了。github官方提供的GitHub Action正可以满足这个需求。

这样的需求下，整个Github Action只需要做两件事：

1. 编译，生成静态文件
2. 部署，把静态文件移动到合适的位置
然后我们再通过git push来触发Github Action就可以了。

---

> 作者: wolkasem  
> URL: https://blogs.wolkasem.cn/posts/github-action/  

