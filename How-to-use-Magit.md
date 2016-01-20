# 什么是 Magit

Magit 是 Emacs 用 Github 的接口，做出来一个的 Mode。它能实现 Git 绝大部分的功能。

# Magit 比在终端上使用 Git 优势在哪？

些许你会问，我已经在终端上会用 Git 的操作了，没有必要在 Emacs 上使用 Git 了。那么你
已经不知不觉忍受了 Git 那些反人类的的操作了，即使已经在 Zch 简化了 Git 的命令，但是用
了 Magit 后，你会有种幸福感，是多么幸运地遇到了 Magit 这样的神器

# Magit 的基本操作

1.假设你会了 git status, git add, git commit, git push, git pull 这些操作。
2.我使用的不是 Emacs 的键位，而是 Spacemacs 的键位设置。
3.下面提到的 SPC = 空格

## Git init

-   c-x c-f 打开你的本地 Git 仓库

-   输入 SPC g i 这键位相当于 git init 的命令

## Git status 和 Git commit

1.  先打开本地的一个文件，README.md,在第一行输入 Add a line
![此处输入图片的描述][1]
2.  输入 Spc g s 你会发发现了 README.md 这文件是 Unstage 的状态
![此处输入图片的描述][2]

在 Unstage 这一行按 Tab 键，可以看到改了那些地方。然后还是在这一行按 s
状态变成了 Staged 的状态。
![此处输入图片的描述][3]
1.  输入 c,跳出一些选项，再输入 c。
![此处输入图片的描述][4]
2.  这里是你输入 Commit 的理由的地方，我们输入 Frist commit
![此处输入图片的描述][5]
3.  输入完后，c-c c-c 运行
![此处输入图片的描述][6]
4.  在 Unpushed 这行输入 P(大写）,这里选择 p 的选项，意思是 Push master to 你的库p
![此处输入图片的描述][7]
![此处输入图片的描述][8]
![此处输入图片的描述][9]


  [1]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-20%20at%2011.47.30%20PM.png
  [2]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-20%20at%2011.49.44%20PM.png
  [3]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-20%20at%2011.52.04%20PM.png
  [4]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-20%20at%2011.58.47%20PM.png
  [5]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-21%20at%2012.01.01%20AM.png
  [6]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-21%20at%2012.01.07%20AM.png
  [7]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-21%20at%2012.01.07%20AM.png
  [8]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-21%20at%2012.05.13%20AM.png
  [9]: http://7xkeje.com1.z0.glb.clouddn.com/Screen%20Shot%202016-01-21%20at%2012.05.47%20AM.png