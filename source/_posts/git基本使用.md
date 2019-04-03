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

if you want to change file name,you can do this

~~~bash
git clone https://github.com/baylin87/hexo-theme-wikipile.git [fileName]
~~~

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


if you git push rejected ,do this
```bash
E:\blog\blog (master -> origin)
λ git push
To https://github.com/zhaoning740/blog.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/zhaoning740/blog.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
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

```

```



