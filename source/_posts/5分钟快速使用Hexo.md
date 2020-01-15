---
title: 5分钟快速使用Hexo
date: 2020-01-15 16:03:35
tags: 建站
---
>民间有传言，没有手撸过个人网站的程序员不是一个好的前端开发工程师，可是！强撸灰飞湮灭！为了自己的身体健康，还是少撸为妙！不要998，也不要98，完全免费，hexo你直接带回家。通过hexo，可以快速构建个人博客，并搭建到 github 上供他人访问，三秒真男人，我们开始吧！

# 新建仓库
都说了要给他人访问，如果你连个仓库都没有，是不是说不过去？出门右转上 github 新建一个仓库，仓库名必须为 user-name.github.io 格式，其中 user-name 是你 github 的昵称。不要问我为什么，问我我也不想回答你。

# 全局安装hexo
如果你连 npm 是啥都不知道，对不起，我们的缘分尽了，你走吧。...别，别，别，开个玩笑，有啥问题可以留言。打开命令行，输入下面的命令，全局安装 hexo。

``` bash
$ npm install -g hexo
```

# 初始化项目
只要一个 命令，hexo init，就会自动构建一个 hexo 项目，紧接着执行 hexo sserver，浏览器访问 localhost:4000 就可以看到效果啦！过程一定要快，凉了就不好吃了！

``` bash
$ hexo init
```

``` bash
// 本地运行
$ hexo server
```

# 部署到github
虽然只有一份 Hello World，但是我也想让全世界的人看到，成为最闪耀的那个崽，可咋整？不要慌，快速在项目根目录下找到 _congif.yml，找到 deploy 字段并填写完整，下面请开始你上学时最擅长的事情：抄写！

# Deployment
## Docs: https://hexo.io/docs/deployment.html

``` yml
deploy:
  type: git
  repo: <你的仓库地址> # https://github.com/liugu0914/liugu0914.github.io
  branch: master
```

抄写完毕！但是！我们需要额外的一个工具来帮助我们推到仓库上，那就是！那就是！那就是 hexo-deployer-git。搞它！


```bash
$ npm install hexo-deployer-git --save
```

万事俱备，只欠东南风！执行下面两个命令，就可以把项目自动部署到 github 上啦啦啦啦啦。

``` bash
$ hexo clean
```

``` bash
$ hexo deploy
```

5. 查看效果
凡是连环杀手都喜欢在杀人后留在现场，因为他喜欢欣赏自己的杰作！

浏览器访问：https://liugu0914.github.io/ 即可看到效果。
至此，已经完成了个人博客的搭建，也可以在浏览器中访问，下面将介绍一些常用的野外生存技能。

如何创建新文章
阳光明媚，一杯温暖的咖啡，一束倾斜的阳光，惬意地抿一口咖啡，我要开始写博客了！

``` bash
// [layout] 为布局，可选项为 `post`、`page`、`draft`，这将决定文章所在文件路径。
// <title> 为文章标题
// 如 hexo new post 除了帅气，我还有啥！
$ hexo new [layout] <title>
```

更换主题皮肤
风格不喜欢？换之。

更换主题流程：下载主题 -> 配置主题，以 xoxo 为例（不要想歪了！）

# 下载到themes文件夹下

```bash
$ git clone https://github.com/ikeq/hexo-theme-inside inside
```

# 修改 _config.yml 配置

```yml
theme: inside
```

部署优化
每次都要执行 hexo clean 和 hexo deploy，不如写个新的脚本

```json
// package.json
"dev": "hexo server",
"build": "hexo clean & hexo deploy"
```

``` bash
//部署命令
$ npm run build
```