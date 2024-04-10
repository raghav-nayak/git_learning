
```sh
$ git --version
git version 2.23.0
```

checking the status
```sh
$ git status
fatal: not a git repository (or any of the parent directories): .git

$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	footer.html

nothing added to commit but untracked files present (use "git add" to track)

$ git status
On branch footer
nothing to commit, working tree clean
```

initializing a git repo
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

adding a file to staging area
```sh
$ git add test1.txt
```

```sh
$ git commit -m "added file one"
[master (root-commit) c3af50f] added file one
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.txt
```

viewing commits
```sh
$ git log
commit c3af50f2de90743d81c328c84e23d2099e39e39a (HEAD -> master)
Author: Raghav Nayak <ragsnayak@gmail.com>
Date:   Sun Apr 7 20:05:18 2024 +0530

    added file one
```

git commits in one line
```sh
$ git log --oneline
c3af50f (HEAD -> master) added file one
```

setting git config
```sh
$ git config --global user.name "Raghav Nayak" user.email "abc@example.com"

$ git config --global user.name
Raghav Nayak

$ git config --global core.editor "code --wait"

$ git config --list
filter.lfs.required=true
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
user.name=Raghav Nayak
user.email=abc@example.com
core.editor=code --wait
```

viewing current branch
```sh
$ git branch
* master
```

creating a new branch
```sh
$ git branch nav-bar
```

switching the branch
```sh
$ git checkout nav-bar
Switched to branch 'nav-bar'

$ git switch nav-bar
Switched to branch 'nav-bar'
```

create a branch and move to newly created branch
```sh
$ git switch -c footer
Switched to a new branch 'footer'

$ git checkout -c new-branch
```

merging a feature branch with master
```sh
$ git merge nav-bar
```

deleting a local branch
```sh
$ git branch -d nav-bar
Deleted branch nav-bar (was 30217fe).
```

git diff between two commits
```sh
$ git diff
diff --git a/index.html b/index.html
index 4f75fde..41ca6e8 100644
--- a/index.html
+++ b/index.html
@@ -3,7 +3,7 @@
 <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
-    <title>Document</title>
+    <title> Index file </title>
 </head>
 <body>
     footer was added successfully
```

git diff staged files
```sh
$ git diff --staged
diff --git a/index.html b/index.html
index 4f75fde..41ca6e8 100644
--- a/index.html
+++ b/index.html
@@ -3,7 +3,7 @@
 <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
-    <title>Document</title>
+    <title> Index file </title>
 </head>
 <body>
     footer was added successfully
```
