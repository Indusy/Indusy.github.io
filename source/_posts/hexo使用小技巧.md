---
title: hexo使用小技巧
author: 梧矜
img: /source/images/1.jpg
top: false
cover: true
coverImg: /source/images/1.jpg
toc: false
mathjax: false
date: 2020-02-06 14:09:03
tags: 偷懒
password:
summary: hexo文章模板
categories: Markdown
---

# hexo文章模板

---

​	使用`hexo new` 新建文章时，在`_posts/`目录下会生成md文件，默认模板中只有`title` `date`和 `tags`，每次写文时必须手动添加其他项目。为了方便，可以建立个人模板。

---

方法：找到hexo目录/scaffolds/post.md，编辑之。把所需项目加入后，再输入`hexo new`，就生成了你所需的所有项目。

```shell
$ cd blog/scaffolds
$ vim post.md
```

示例如下：

```
title: {{ title }}
date: {{ date }}
tags:
author: 梧矜
img: /source/images/1.jpg
top: false
cover: true
coverImg: /source/images/1.jpg
password: 
toc: false
mathjax: false
summary: 
categories: 

```





