```sh
$ git --version
git version 2.23.0
```

```sh
$ git status
fatal: not a git repository (or any of the parent directories): .git
```

```sh
$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
Initialized empty Git repository in /git_learning/dir_one/.git/
```

```sh
$ git add test1.txt
```

```sh
$ git commit -m "added file one"
[master (root-commit) c3af50f] added file one
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.txt
```

```sh
$ git log
commit c3af50f2de90743d81c328c84e23d2099e39e39a (HEAD -> master)
Author: Raghav Nayak <ragsnayak@gmail.com>
Date:   Sun Apr 7 20:05:18 2024 +0530

    added file one
```

```sh
$ git log --oneline
c3af50f (HEAD -> master) added file one
```

