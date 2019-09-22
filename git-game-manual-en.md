# Table of Contents

* [Simple introduction](#simple-introduction)
* [Detailed introduction](#detailed-introduction)
  * [1\.Preparation: clone the repository to local](#1preparation-clone-the-repository-to-local)
  * [2\.How to begin](#2how-to-begin)
  * [3\.Began to recruit](#3began-to-recruit)
* [Extension :Git game recommended](#extension-git-game-recommended)

## Simple introduction

Is one of the game is one of the few git (more git game see: [Extension :Git game recommended](#extension-git-game-recommended)), is suitable for the beginners who have certain basis (with some simple command), at the same time the author add some command links to the game, if you don't use the corresponding commands or forget the usage of this command, you can get some help from the related links.

However, there are some barriers to entry and you may not know how to get started.

```markdown
You should always check the README.md file for your next clue!

Level 1

Your first task is to checkout the commit whose commit message is the answer to this question:

> When a programmer is born, what is the first thing he/she learns to say?
```

I felt so abstract that I didn't know how to start.

## Detailed introduction

### 1.Preparation: clone the repository to local

Maybe some people say why should such a simple step be singled out? But have you ever thought about this question: why is there 2700+star in a repository with only 6 commits? At first I didn't notice this problem, but in the process of recruit (off) 2 encountered in the need to use the branch, and we use `git clone https://github.com/git-game/git-game.git` default can only download the default branch of the repository, if not particularly to set the default to the master branch. And this repository has **18** branches.

```bash
$ git clone https://github.com/git-game/git-game.git
Cloning into 'git-game'...
remote: Enumerating objects: 243, done.
remote: Total 243 (delta 0), reused 0 (delta 0), pack-reused 243
Receiving objects: 100% (243/243), 2.44 MiB | 52.00 KiB/s, done.
Resolving deltas: 100% (84/84), done.

$ cd git-game/

# View local branches
$ git branch
 master
# View remote branches
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

So what to do? Download the remote branch by loop:

```bash
# $ cd git-game
# Download the other branches in a loop with shell command
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

See: [how to clone all remote branches of Git](https://blog.csdn.net/weixin_41287260/article/details/98987135)

### 2.How to begin

As the saying goes: **A good beginning is half done. ** You may not know what to do at first, but when you start, you'll be happy.
<br/>

`You should always check the README.md file for your next clue!`, which simply means that you should always check the `README.md` file. It may give you clues to the next level. It's not just the `README.md` file, it's the ** branchs (name), the commits (info, author), the tags **, etc.

<br/>
In general, `Level x` means you have passed the previous Level. There may be some indication of success (congratulations), followed by clues to the next Level or a guide to where to look for clues.

### 3.Began to recruit

Level 1：

```markdown
Level 1

Your first task is to checkout the commit whose commit message is the answer to this question:

> When a programmer is born, what is the first thing he/she learns to say?
```

We all know that the first program is `Hello world`, according to the prompt we go to see the commit information:

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

Or display a short commit message  (graphical, one-line commit, short commit HASH1):

```bash
$ git log --graph --pretty=oneline --abbrev-commit
* d851edd (HEAD -> master, origin/master, origin/HEAD) updated README for badge notification
* 7c8c3cc added level1
* 228389a added welcome screen
* db99f2d updated README
* 6402738 Hello World!
* 8cafb7c (origin/vector, origin/map, origin/SteveJobs2014, origin/Kevin, origin/KenThompson2014, origin/Daniel, origin/BillGates2014, vector, map, SteveJobs2014, Kevin, KenThompson2014, Daniel, BillGates2014) Initial commit
```

Back to commit message as "Hello World!" Version:

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

# Review the submission information to determine that you have returned to the specified branch
$ git log --graph --pretty=oneline --abbrev-commit
* 6402738 (HEAD) Hello World!
* 8cafb7c (origin/vector, origin/map, origin/SteveJobs2014, origin/Kevin, origin/KenThompson2014, origin/Daniel, origin/BillGates2014, vector, map, SteveJobs2014, Kevin, KenThompson2014, Daniel, BillGates2014) Initial commit

# Check README.md for clues
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

OK，The routine comes with "congratulations, level 2 clues" to show that you passed this level!

Next, have fun

## Extension :Git game recommended

1. git-game-v2: <https://github.com/git-game/git-game-v2>
   The introduction：<https://kingsleyxie.cn/git-game-v2>

2. learnGitBranching：<https://github.com/pcottle/learnGitBranching>
   The game site：<https://learngitbranching.js.org/?demo>