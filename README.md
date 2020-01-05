# Casper（中文优化版）
此 Repo 为 [Ghost](https://github.com/TryGhost/Ghost) 官方默认主题 [Casper](https://github.com/TryGhost/Casper) 的改良版。如若有意见或建议，请加 Issue，无需特别标注，说明情况即可。

- [JerryZhang.blog](https://JerryZhang.blog) 使用了此主题

## 具体优化内容如下:
### 添加了归档页面
由于 Ghost 官方不相信归档，Ghost 一直没有归档功能，本版本的主题添加了归档功能。使用前需要在 Labs 页面下载 YAML 路径配置文档 `routes.yaml`，在顶部添加：   
```
routes:
  /archive/: 
    template: archive
```

如果您的路径配置文件已存在  `routes:`，复制后两行粘贴 `routes:` 的下一行在即可。
配置文件上传完后即可通过 `/archive/` 访问归档页面。

### 添加了标签页面
标签页面将列出您站点使用过的所有标签和文章数量。使用前需要在 Labs 页面下载 YAML 路径配置文档 `routes.yaml`，在顶部添加：   
```
routes:
    /tags/: 
        template: tags
```

如果您的路径配置文件已存在  `routes:`，复制后两行粘贴 `routes:` 的下一行在即可。
配置文件上传完后即可通过 `/tags/` 访问归档页面。

### 中文 CSS 优化
- 在 `default.hbs` 增加了 RSS 订阅链接和邮件订阅链接
- 从 `partials/floating-header.hbs` 中移除了分享按钮
- 从 `partials/post-card.hbs` 当中移除了预估阅读时长的功能
- 在 `partials/post-card.hbs` 的主页文章卡片中加入了博客发布日期
- 在 `partials/site-nav.hbs` 增加了邮件订阅链接和一键去图功能，开启方式请看下方的「一键去图」标题
- 在 `post.hbs` 将英文日期更改为中文日期并将页面进行了汉化
- 将所有页面进行了汉化
- 将主题中的非衬线文字全部转换为衬线体
- 缩小了大部分文字的尺寸，增加了行高
- 将 RSS 链接从 Feedly 的链接转换成原生链接

#### 一键去图
在 Code Injection 里的 Site Footer 栏中加入
```
<script> 
    function removeImage(){
        $(".post-card-image-link").remove()    
        $(".post-card-large").removeClass("post-card-large")
        $(".post-card").css("flex", "1 1 1000px");
        $(".post-full-image").remove()
        $(".post-full-content:before").css("display", "none");
    }
</script>
```
