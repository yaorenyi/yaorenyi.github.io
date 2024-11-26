# 第一篇文章


# 第一篇文章

## 特性
### 优雅的设计，优雅的阅读体验，时刻关注最新最热的新闻。
### 支持 Github 登录，支持数据同步。
### 默认 30 分钟缓存，登录用户可以强制拉取最新数据。但也会根据内容源的更新间隔设置不同的爬虫间隔时间（最快两分钟），节约资源的同时避免频繁爬取而导致 IP 封禁。

## 部署
如果不需要登录，缓存，可以直接部署到 Cloudflare Pages，Vercel 等。Fork 之后在对应平台上导入即可。

Cloudflare Pages 需要填入构建命令 pnpm run build, 构建输出文件夹 dist/output/public。

登录涉及到 Github Oauth，只需要 创建一个 Github App 即可，不需要申请任何权限。Callback URL 为 https://your-domain.com/api/oauth/github。

然后就会得到 Client ID 和 Client Secret。关于环境变量，不同平台有不同的填写位置，请关注 example.env.server 文件。如果本地运行，需要将其重命名为 .env.server，然后按照要求添加。

```
# Github Clien ID
G_CLIENT_ID=
# Github Clien Secret
G_CLIENT_SECRET=
# JWT Secret, 通常就用 Clien Secret
JWT_SECRET=
# 初始化数据库, 首次运行必须设置为 true，之后可以将其关闭
INIT_TABLE=true
# 是否启用缓存
ENABLE_CACHE=true
```



---

> 作者: wolkasem  
> URL: https://blogs.wolkasem.cn/posts/%E7%AC%AC%E4%B8%80%E7%AF%87%E6%96%87%E7%AB%A0/  

