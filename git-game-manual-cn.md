Table of Contents
=================

* [简单介绍](#%E7%AE%80%E5%8D%95%E4%BB%8B%E7%BB%8D)

* [使用说明](#%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)
  * [1\.准备工作：克隆仓库到本地](#1%E5%87%86%E5%A4%87%E5%B7%A5%E4%BD%9C%E5%85%8B%E9%9A%86%E4%BB%93%E5%BA%93%E5%88%B0%E6%9C%AC%E5%9C%B0)
  * [2\.如何开始](#2%E5%A6%82%E4%BD%95%E5%BC%80%E5%A7%8B)
  * [3\.闯关演示](#3%E9%97%AF%E5%85%B3%E6%BC%94%E7%A4%BA)
  
* [扩展:Git游戏推荐](#%E6%89%A9%E5%B1%95git%E6%B8%B8%E6%88%8F%E6%8E%A8%E8%8D%90)

---

## 简单介绍

该游戏是为数不多的git游戏之一（更多git游戏请看：[扩展:Git游戏推荐](#%E6%89%A9%E5%B1%95git%E6%B8%B8%E6%88%8F%E6%8E%A8%E8%8D%90)），适合有一定基础的初学者（会用一些简单命令的），同时作者在游戏里面添加了一些命令的相关链接，如果你没有使用过对应的命令或者是忘记了该命令的用法，你可以从相关链接中获得一些帮助。



尽管如此，但是这个游戏还是有一定门槛的，你可能不知道该如何开始这个游戏，原文中相关说明就这有下面这段话：

```markdown
You should always check the README.md file for your next clue!

Level 1

Your first task is to checkout the commit whose commit message is the answer to this question:

> When a programmer is born, what is the first thing he/she learns to say?
```

我感觉很是抽象，以至于不知道该如何开始。



## 使用说明

### 1.准备工作：克隆仓库到本地

也许有些人说为什么这么简单的步骤也要特别指出来吗？但是你想过这个问题没有：一个只有6个提交的仓库，为什么会有2700+star ?一开始我并没有注意到这个问题，但是在闯关的过程（第2关）中遇到需要使用分支，而我们使用 `git clone https://github.com/git-game/git-game.git` 默认只能下载该仓库的默认分支，如果不特别进行设置默认为master分支。而这个仓库有**18**个分支。


```bash
$ git clone https://github.com/git-game/git-game.git
Cloning into 'git-game'...
remote: Enumerating objects: 243, done.
remote: Total 243 (delta 0), reused 0 (delta 0), pack-reused 243
Receiving objects: 100% (243/243), 2.44 MiB | 52.00 KiB/s, done.
Resolving deltas: 100% (84/84), done.

$ cd git-game/

#查看本地分支
$ git branch
 master
#查看远程分支
$ git branch -r
  origin/BillGates2014
  origin/Daniel
  origin/HEAD -> origin/master
  origin/Henry
  origin/KenThompson2014
  origin/Kevin
  origin/LinusTorvalds2014
  origin/Mike
  origin/SteveJobs2014
  origin/array
  origin/bug
  origin/code4life
  origin/keyboard
  origin/map
  origin/master
  origin/mouse
  origin/tree
  origin/trees
  origin/vector
```



那怎么办呢？循环下载远程分支即可：

```bash
# $ cd git-game
#循环下载其他分支
$ for b in `git branch -r | grep -v -- '->'`; do git branch --track ${b##origin/} $b;done

Branch 'BillGates2014' set up to track remote branch 'BillGates2014' from 'origin'.
Branch 'Daniel' set up to track remote branch 'Daniel' from 'origin'.
Branch 'Henry' set up to track remote branch 'Henry' from 'origin'.
Branch 'KenThompson2014' set up to track remote branch 'KenThompson2014' from 'origin'.
Branch 'Kevin' set up to track remote branch 'Kevin' from 'origin'.
Branch 'LinusTorvalds2014' set up to track remote branch 'LinusTorvalds2014' from 'origin'.
Branch 'Mike' set up to track remote branch 'Mike' from 'origin'.
Branch 'SteveJobs2014' set up to track remote branch 'SteveJobs2014' from 'origin'.
Branch 'array' set up to track remote branch 'array' from 'origin'.
Branch 'bug' set up to track remote branch 'bug' from 'origin'.
Branch 'code4life' set up to track remote branch 'code4life' from 'origin'.
Branch 'keyboard' set up to track remote branch 'keyboard' from 'origin'.
Branch 'map' set up to track remote branch 'map' from 'origin'.
fatal: A branch named 'master' already exists.
Branch 'mouse' set up to track remote branch 'mouse' from 'origin'.
Branch 'tree' set up to track remote branch 'tree' from 'origin'.
Branch 'trees' set up to track remote branch 'trees' from 'origin'.
Branch 'vector' set up to track remote branch 'vector' from 'origin'.
```

详见：[如何克隆Git的所有远程分支](<https://blog.csdn.net/weixin_41287260/article/details/98987135>)



### 2.如何开始

**好的开始是成功的一半**，用在这里是再合适不过了！一开始你可能会无从下手，但是当你开始时，你就会不亦乐乎。

<br/>

回过头来看看说明：`You should always check the README.md file for your next clue!`，这里只是说你应该经常检查（查看）`README.md`文件，它可能会给你的下一关的提供线索（clue）。其实不仅仅是README.md文件，**分支（名）、提交（提交信息、提交者信息）、标签**等都是你需要关注的重点。

<br/>

一般情况下，看到`Level x`表示通过了上一关卡，前面可能会有通关成功的一些说明（祝贺），后面会提供下一关的线索或者是会告诉你去哪里找线索。

### 3.闯关演示

第一关：

```markdown
Level 1

Your first task is to checkout the commit whose commit message is the answer to this question:

> When a programmer is born, what is the first thing he/she learns to say?
```

有编程基础都知道第一个程序是`Hello world`，按照提示我们去看下提交信息：

```bash
$ git log
commit d851edda3009332dd5d3f8f949a102f279dad809 (HEAD -> master, origin/master, origin/HEAD)
Author: Henry Garcia <hgarc014@ucr.edu>
Date:   Wed Jun 10 21:03:04 2015 -0700

    updated README for badge notification

commit 7c8c3ccc2f4bb118a657f1f7a7ab4e163d1b7a30
Author: Henry Garcia <hgarc014@ucr.edu>
Date:   Wed Jun 10 20:57:08 2015 -0700

    added level1

commit 228389a54073ed1e6ec98e3bfa59039b416efd4d
Author: Henry Garcia <hgarc014@ucr.edu>
Date:   Wed Jun 10 20:56:34 2015 -0700

    added welcome screen

commit db99f2d9df4b2288d29a97d2d04a1703b4f3c107
Author: Henry Garcia <hgarc014@ucr.edu>
Date:   Wed Jun 10 20:55:35 2015 -0700

    updated README

commit 640273807f9bac8af03575f82b788663d4b99927
Author: Henry Garcia <hgarc014@ucr.edu>
Date:   Wed Jun 10 20:55:07 2015 -0700

    Hello World!

commit 8cafb7c87b129686da362b14c3f3c750c1fe4bf5 (origin/vector, origin/map, origin/SteveJobs2014, origin/Kevin, origin/KenThompson2014, origin/Daniel, origin/BillGates2014, vector, map, SteveJobs2014, Kevin, KenThompson2014, Daniel, BillGates2014)
Author: Henry Garcia <hgarc014@ucr.edu>
Date:   Sun Nov 30 18:29:35 2014 -0800

    Initial commit
```

或者 显示精简的提交信息（图形化的、单行的提交信息、简短的提交HASH1）
```
$ git log --graph --pretty=oneline --abbrev-commit
* d851edd (HEAD -> master, origin/master, origin/HEAD) updated README for badge notification
* 7c8c3cc added level1
* 228389a added welcome screen
* db99f2d updated README
* 6402738 Hello World!
* 8cafb7c (origin/vector, origin/map, origin/SteveJobs2014, origin/Kevin, origin/KenThompson2014, origin/Daniel, origin/BillGates2014, vector, map, SteveJobs2014, Kevin, KenThompson2014, Daniel, BillGates2014) Initial commit
```

回退到提交信息为“Hello World!”的版本：

```bash
$ git checkout 6402738
Note: checking out '6402738'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at 6402738 Hello World!

# 查看提交信息，确定已回到指定分支
$ git log --graph --pretty=oneline --abbrev-commit
* 6402738 (HEAD) Hello World!
* 8cafb7c (origin/vector, origin/map, origin/SteveJobs2014, origin/Kevin, origin/KenThompson2014, origin/Daniel, origin/BillGates2014, vector, map, SteveJobs2014, Kevin, KenThompson2014, Daniel, BillGates2014) Initial commit

# 查看README.md有没有线索
$ cat README.md
git-game
========

Hello World!

It looks like you have some knowledge about traversing commits!
Well, let's get this party started!

``Level 2``

We want to get to a branch whose name is the answer to this riddle:
I am a creature that is smaller than man, but many times more in number.
In code, my appearance can be subtle and no matter where I am found, I am unwanted.

What am I?
```

OK，祝贺语，第2关线索。



Have fun!





## 扩展:Git游戏推荐

1. git-game 的第二个版本：git-game-v2:<https://github.com/git-game/git-game-v2>

   入门介绍：[https://kingsleyxie.cn/git-game-v2](https://kingsleyxie.cn/git-game-v2)

2. learnGitBranching：<https://github.com/pcottle/learnGitBranching>

   游戏网址：<https://learngitbranching.js.org/?demo>