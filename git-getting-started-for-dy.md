# Git - Getting Started

!SLIDE

# Git - Getting Started

## dyTopic

2015.03.29 19:30 | Rotunda, SJTU MH

!SLIDE

# What is Git?

<img src="//upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" width="110" height="46" alt="Git">

!SLIDE

## What is Git

A distributed version control system developed by <span data-tooltip aria-haspopup="true" class="has-tip" title="The ten words that describe me the best: I cannot count.">Junio Hamano</span> and <span data-tooltip aria-haspopup="true" class="has-tip" title="Creator of Linux and git">Linus Torvalds</span>.

> I'm an egotistical bastard, and I name all my projects after myself. First 'Linux', now 'Git'.

> -- Linus Torvalds

!SLIDE

## A Short History of Git with Linux

- 1991 - 2002: Patches and archived files.
- 2002: Began using BitKeeper.
- 2005: Their own tool. Goals:
    - Speed
    - Simple design
    - Non-linear development
    - Fully distributed
    - Able to handle large projects efficiently

!SLIDE

## Tools

!SLIDE

### Git Shell

<img src="images/git-getting-started-for-dy/git-shell.png" width="707" height="400">

!SLIDE

### GitHub for Windows

<img src="https://windows.github.com/images/screenshot-overview@2x.png" width="1051" height="400">

!SLIDE

### GitHub for Mac

<img src="https://mac.github.com/images/screen1.png" width="646" height="400">

!SLIDE

### Git Extensions

<img src="https://git-extensions-documentation.readthedocs.org/en/latest/_images/commit_diff_view.png" width="647" height="400">

!SLIDE

# Git Basics

<img src="//upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" width="110" height="46" alt="Git">

!SLIDE

}}} //git-scm.com/book/en/v2/book/01-introduction/images/deltas.png

!SLIDE

}}} //git-scm.com/book/en/v2/book/01-introduction/images/snapshots.png

!SLIDE

}}} //git-scm.com/book/en/v2/book/01-introduction/images/distributed.png

!SLIDE

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/commit-and-tree.png

!SLIDE

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/commits-and-parents.png

!SLIDE

- [Branch?](#slide-15)

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/branch-and-history.png

!SLIDE

```bash
$ git branch testing
```

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/head-to-master.png

!SLIDE

```bash
$ git checkout testing
# git checkout -b testing
# git checkout -b testing master
```

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/head-to-testing.png

!SLIDE

```bash
$ git commit
```

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/advance-testing.png

!SLIDE

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/basic-rebase-1.png

!SLIDE

```bash
# Head poings to master
$ git merge experiment
```

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/basic-rebase-2.png

!SLIDE

```bash
# Head points to experiment
$ git rebase master
```

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/basic-rebase-3.png

!SLIDE

```bash
# Head points to master
$ git merge master
$ git branch -d experiment
```

[Branch!](#slide-37)

}}} //git-scm.com/book/en/v2/book/03-git-branching/images/basic-rebase-4.png

!SLIDE

# Git Command Line - Basic

<img src="//upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" width="110" height="46" alt="Git">

!SLIDE

## Up and Running

```bash
$ git clone {remote-url}
# Time goes and goes
$ git pull
```

!SLIDE

## Daily Operations

!SLIDE

}}} //git-scm.com/book/en/v2/book/02-git-basics/images/lifecycle.png

!SLIDE

## Daily Commands

```bash
$ git status
$ git add .
$ git add --all
$ git reset
$ git commit
$ git commit -a
$ git commit -am'{Commit message}'
$ git push -u {remote} {remote-branch}
$ git push
$ git pull
```

!SLIDE

## Handy Commands

!SLIDE

### Git Help

```bash
$ git {verb} -h
$ git {verb} --help
$ git help {verb}
```
!SLIDE

### Git Log

```bash
$ git log
$ git log --author 'Arrow Rowe' -StqChart -p
        --format="%h %Cgreen%ad%Creset %s"
$ git log --graph --oneline
```

!SLIDE

### Git Config

```bash
$ git config -e
$ git config -e --global
```

!SLIDE

### Git Diff

```bash
$ git diff
$ git diff head
$ git diff head~
$ git diff {from} {to}
$ git diff head^3 head~
$ git diff {file}
$ git diff {from} {file}
$ git diff {from} {to} {file}
```

!SLIDE

### Checkout into History

```bash
$ git checkout {wherever-you-want}
$ git checkout head~~~
$ git checkout {where} {file}       # Danger!
$ git checkout {file}               # Danger!
```

!SLIDE

### Ignore

```gitignore
# PhpStorm
.idea/

# Python
*.py[cod]

# Composer
vendor/

# NPM
node_modules/

```

!SLIDE

### Something more...

```bash
$ git commit --amend
$ git push -f
$ git branch -f {branch} {where}
```

!SLIDE

# Branching

<img src="//upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" width="110" height="46" alt="Git">

!SLIDE

- [Branch?](#slide-15)
- [Branch!](#slide-37)

!SLIDE

```bash
$ git branch
$ git branch -r
$ git branch -a
$ git branch -v
$ git branch -vv
```

!SLIDE

# Teamwork

<img src="//upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" width="110" height="46" alt="Git">

!SLIDE

## What if ...?

!SLIDE

### ... my push gets rejected?

- Change something, commit, push...
- Run into `! [rejected]`!
- Hint: The remote contains work that you do not have locally.
- Hint: See the 'Note about fast-forwards' in 'git push --help' for details.

!SLIDE

```bash
$ git pull --rebase
```

!SLIDE

### ... my pull is aborted?

- Change something, have not committed, pull...
- Run into `error: Your local changes to the following files would be overwritten by merge:`!
- Hint: Commit or stash.

!SLIDE

```bash
$ git stash
$ git pull
$ git stash pop
# Deal with confliction...
```

```bash
$ git stash list
$ git stash show
$ git stash drop
```

!SLIDE

### ... confliction occurs?

Just follow the hint...

from

```js
<<<<<<< Updated upstream
// Someone else has done this!
=======
// My work not committed
>>>>>>> Stashed changes
```

to

```js
// My work not committed is left!
```

!SLIDE

### ... write something on a wrong branch?

!SLIDE

- Have not committed yet?

```bash
$ git stash
$ git checkout {the-correct-branch}
$ git stash pop
# everything OK now...
```

!SLIDE

- Already committed?

```bash
$ git reset head~   # or wherever you want
```

!SLIDE

## Workflow

!SLIDE

### Naming branches

- dev or master, test, production or deploy
- enhance/aaa, feature/bbb, refactor/ccc
- hotfix/xxx

!SLIDE

### Working on a branch

0. Branch aside from master.
0. Rebase from time to time. Stay close with Master!
0. Send PR: Pull Request.

---

- Commits and branches, the smaller the better
- Clear commit messages and PR messages

!SLIDE

### Issues and Milestones

!SLIDE

### A Forker Forks a Fork

!SLIDE

# Webhooks and More

<img src="//upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" width="110" height="46" alt="Git">

!SLIDE

## Webhooks and Services

- dyGroup of hackShanghai
- Slack
- BearyChat, TeamBition, ...

!SLIDE

## Quality Assurance

- Unit Tests: PHPUnit, CI, ...
- Spell check, syntax check, ...

!SLIDE

# Anything missing?

<img src="//upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg" width="110" height="46" alt="Git">

!SLIDE

- Ignore crlf, filemode, ...
- Regard something as text or binary: Git Attributes
- Git Help, Pro Git, and Google
- Git Alias, alias for Mac or Linux, doskey for windows, AutoHotKey...

!SLIDE

# More

<img src="images/center.png">

[arrowrowe.github.io](http://arrowrowe.github.io/)

!SLIDE

# dyWeb

<img src="images/center.png">

2015.03.29 19:30 | Rotunda, SJTU MH
