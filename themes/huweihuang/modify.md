### 备注

`/themes/huweihuang/layout/index.ejs` 是主页模版文件。

`themes/huweihuang/layout/post.ejs` 是文章详情页模板文件。

post.md 里面添加 `catalog: true` 表示显示文章目录。

### 修改记录

#### 样式

+ 主页文章简介去掉斜体

新建文件 `/themes/huweihuang/source/css/customize.css`，然后在 `/themes/huweihuang/layout/_partial/head.ejs` 文件中引入上述 css 文件。

注意，将该 css 文件放在最后面以覆盖原主题的样式。

```
<%- css('css/customize.css') %>
```

+ 主页文章列表简介去掉作者信息

```
/themes/huweihuang/layout/index.ejs

<% if (config.home_posts_author){ %>
    <p class="post-meta">
        Posted by <%- post.author || config.author %> on
        <%= post.date.format(config.date_format) %>
    </p>
<% } %>
```

#### 结构

```html
/themes/huweihuang/layout/_partial/footer.ejs

<div class="my-footer">
	<p class="copyright text-muted">
		&copy; Powered by <%= config.author %> 2017-<%= new Date().getFullYear() %> 
	</p>
</div>
```

#### hexo 配置  

```yml
/_config.yml

# 不显示标签
featured-tags: false 
# 不显示文章简介下的标签
home_posts_tag: false # show posts tags
# 不显示文章简介下的作者
home_posts_author: false
# 去掉页面底部分享（微信 微博 豆瓣...）
share: false
```
