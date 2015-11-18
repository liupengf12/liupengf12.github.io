---
layout: post
title: 第一篇Blog
---

用GitHub Pages + Jekyll来搭建一个博客真简单呀，一个上午的时间就全部搞定啦 :)

首先得要非常感谢以下文章：

* [使用 GitHub, Jekyll 打造自己的免费独立博客](http://blog.csdn.net/on_1y/article/details/19259435)
* [Build A Blog With Jekyll And GitHub Pages](http://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/)
* [Atlassian提供的Git教程](https://www.atlassian.com/git/tutorials/setting-up-a-repository)

接下来就该换一个自己中意的皮肤了，另外就是慢慢熟悉用Markdown方式写博客

刚才试着在本地用Atom编辑一个Markdown文件然后再通过Cmder提交到Github，遇到很多问题要解决呀：

## 配置Atom作为Git的编辑工具

```bash
git config --global core.editor "atom --wait"
```

## 为博客这个Git库配置不同的用户和Email

```bash
git config user.name "Peter Liu"
git config user.email "liupengf12@gmail.com"
```

## 练习Git的各种基本用法
Atlassian提供的[Git教程](https://www.atlassian.com/git/tutorials/setting-up-a-repository)写的很不错

## 在本地安装Jekyll
可以参考[Run Jekyll on Windows](http://jekyll-windows.juthilo.com/)

运行Jekyll的时候遇到下面的错误：

```bash
λ gjekyll serve
Configuration file: C:/Users/Peter/Documents/Blog/_config.yml
            Source: C:/Users/Peter/Documents/Blog
       Destination: C:/Users/Peter/Documents/Blog/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
  Conversion error: Jekyll::Converters::Markdown encountered an error while converting '_posts/2015-11-7-first-blog.md':
                    Failed to get header.
jekyll 3.0.0 | Error:  Failed to get header.
```

在Google搜索后发现一些人说是由于Python版本的原因，我安装了3.5版本，应该安装2.7，为方便起见我直接把语法标亮选项换成了rouge：

```
highlighter: rouge
```

最后Jekyll执行成功！

```bash
λ jekyll serve
Configuration file: C:/Users/Peter/Documents/Blog/_config.yml
            Source: C:/Users/Peter/Documents/Blog
       Destination: C:/Users/Peter/Documents/Blog/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.448 seconds.
 Auto-regeneration: enabled for 'C:/Users/Peter/Documents/Blog'
Configuration file: C:/Users/Peter/Documents/Blog/_config.yml
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```
