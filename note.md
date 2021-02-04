## how to use

其中 sources 分支是源文件分支，直接 clone 下来就可以使用，website 分支是博客站点分支，hexo-d 命令就是将文件发布的这个分支的。

初始化时拉取下远程仓库代码即可，以后都不需要在拉取了。

```
# clone 仓库
git clone git@github.com:coderlmm/coderlmm.github.io.git
cd coderlmm.github.io
```

每次发文执行以下操作就可。

```
# 添加博客文章
add file to source/_posts/

# 发布到 github page
sh ./hexo-d.sh

# 上传源文件至 GitHub
sh ./push.sh
```
