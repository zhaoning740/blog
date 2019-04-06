---
title: vue项目起步
date: 2018-05-23 16:28:46
tags: vue
---

# Mac OS X环境配置

1. 安装包管理工具

[brew](https://brew.sh/index_zh-cn)

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

将以上命令粘贴至终端。

2. 通过brew安装node

```bash
brew install node 
```

3. 查看是否安装成功

```bash
node -v 
npm -v
```



> 2019年4月更新

# Vue启动

1. 安装[Vue-cli](https://cli.vuejs.org/zh/guide/installation.html)命令行工具 （脚手架）

   ```bash
   npm install -g @vue/cli
   ```

2. 检验是否安装成功

   ```bash
   vue --version
   ```

3. 创建一个项目

   ```bash
   vue create hello-world
   ```

   手动选择一个 preset

4. run一下

   ```bash
   npm run server
   ```

   server可更改，在packsge.json中的scripts
