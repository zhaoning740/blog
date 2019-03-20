---
title: git基本使用
date: 2018-03-19 12:38:07
tags: git
---

![git](E:\blog\shiyue\source\_posts\img\git.jpg)

第1步：项目下载

```bash
git clone https://github.com/baylin87/hexo-theme-wikipile.git 
```

第2步：改代码

第3步：提交代码

3.1 提交到工作区(缓存区/本机)

快捷方法

```bash
git acm -m '提交说明'
```

分解方法

```bash
git add . //将所有修改文件提交
git commit -m '提交说明'
```

3.2 上传代码(上传到服务器)

```bash
git push
```

## 其他

查看git状态

```bash
git status
```

切换分支

```bash
git checkout 分支名字
git checkout 分支名 -b  //创建新分支
```

更新代码

```bash
git pull
```

合并分支

```bash
git merge 分支名
```



