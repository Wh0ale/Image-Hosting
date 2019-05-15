# Image-Hosting
新浪图床迁移

考虑到现在免费的图床都不是很稳定，七牛云，新浪图床，imgur等。

这下我清楚了免费的才是最贵的。于是我在github新建了一个仓库存放图片



下面写下详细的步骤

1. 创建token

创建完后记录下token，这里的token只出现一次

![](https://raw.githubusercontent.com/Wh0ale/Image-Hosting/master/blog/1.png)

2. 使用picgo

创建的的仓库名为Wh0ale/Image-Hosting，分支默认填master。这里我选择使用picgo作为上传图片的工具。

![](https://raw.githubusercontent.com/Wh0ale/Image-Hosting/master/blog/3.png)



![](https://raw.githubusercontent.com/Wh0ale/Image-Hosting/master/blog/2.png)

3. 使用 grep命令将所有新浪图床的图片从文章下载下来

```
grep -r 'http://ww1.sinaimg.cn/' | cut -d '(' -f 2 | cut -d ')' -f 1 | wget -i -
```

4. sed命令替换图片（windows下可以直接用sublime 的全局替换）

```
sed -i 's/ws1.sinaimg.cn\/large/raw.githubusercontent.com\/Wh0ale\/Image-Hosting\/blog\/picgo\//g' *
```

![](https://raw.githubusercontent.com/Wh0ale/Image-Hosting/master/blog/4.png)

5. 最后一步是将图片上传到仓库

这里因为我是用的picgo是无法批量上传的，所以我使用github  desktop把仓库clone下来，在把图片放到相应的文件夹，然后使用profixier让github  desktop走代理流量（不走代理实在太慢了）

![](https://raw.githubusercontent.com/Wh0ale/Image-Hosting/master/blog/5.png)

![](https://raw.githubusercontent.com/Wh0ale/Image-Hosting/master/blog/6.png)


