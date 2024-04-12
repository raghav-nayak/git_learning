
#### checking the git version
```sh
$ git --version
git version 2.23.0
```

#### checking the status
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

#### initializing a git repo
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

#### adding a file to staging area
```sh
$ git add test1.txt
```

#### adding a commit
```sh
$ git commit -m "added file one"
[master (root-commit) c3af50f] added file one
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.txt
```

#### add and commit in one command
```sh
$ git commit -am "updated main website"
[master 21f1dd1] updated main website
 1 file changed, 2 insertions(+)
```

#### viewing commits
```sh
$ git log
commit c3af50f2de90743d81c328c84e23d2099e39e39a (HEAD -> master)
Author: Raghav Nayak <ragsnayak@gmail.com>
Date:   Sun Apr 7 20:05:18 2024 +0530

    added file one
```

#### git commits in one line
```sh
$ git log --oneline
c3af50f (HEAD -> master) added file one
```

#### setting git config
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

#### viewing current branch
```sh
$ git branch
* master
```

#### creating a new branch
```sh
$ git branch nav-bar
```

#### switching the branch
```sh
$ git checkout nav-bar
Switched to branch 'nav-bar'

$ git switch nav-bar
Switched to branch 'nav-bar'
```

#### git checkout a particular hash
```sh
$ git checkout 56ff0b5
M	footer.html
Note: switching to '56ff0b5'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 56ff0b5 add footer section to the code base

$ git switch master
M	footer.html
Previous HEAD position was 56ff0b5 add footer section to the code base
Switched to branch 'master'
```

#### renaming a branch (master to main)
```sh
$ git branch -M main
```

#### git checkout two commits prior to head
```sh
$ git log --oneline
3e505b4 (HEAD -> master) update index file
553d125 Merge branch 'footer'
5149ec0 (footer, bugfix) update index file
2020251 add footer in index file
56ff0b5 add footer section to the code base
4fc3120 Merge branch 'nav-bar'
8076f8a add hero section to the code base
30217fe added navbar.html
c5ac897 added index.html
a9916ae initial commit

$ git checkout HEAD~2
M	footer.html
Note: switching to 'HEAD~2'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 2020251 add footer in index file


$ git log --oneline
2020251 (HEAD) add footer in index file
56ff0b5 add footer section to the code base
4fc3120 Merge branch 'nav-bar'
8076f8a add hero section to the code base
30217fe added navbar.html
c5ac897 added index.html
a9916ae initial commit
```

#### to check the complete list of changes done in the repo
it keeps track of where your HEAD is moving from one branch to another. 
```sh
$ git reflog
3e505b4 (HEAD -> master) HEAD@{0}: checkout: moving from 2020251ce107b0483f1220648a8aaea08d1fe911 to master
2020251 HEAD@{1}: checkout: moving from master to HEAD~2
3e505b4 (HEAD -> master) HEAD@{2}: checkout: moving from 56ff0b53e213ef3feb8c741eb2c89e32eb411d9c to master
56ff0b5 HEAD@{3}: checkout: moving from master to 56ff0b5
3e505b4 (HEAD -> master) HEAD@{4}: reset: moving to HEAD
3e505b4 (HEAD -> master) HEAD@{5}: checkout: moving from footer to master
5149ec0 (footer, bugfix) HEAD@{6}: checkout: moving from master to footer
3e505b4 (HEAD -> master) HEAD@{7}: checkout: moving from footer to master
5149ec0 (footer, bugfix) HEAD@{8}: checkout: moving from bugfix to footer
3e505b4 (HEAD -> master) HEAD@{9}: checkout: moving from footer to bugfix
5149ec0 (footer, bugfix) HEAD@{10}: checkout: moving from bugfix to footer
3e505b4 (HEAD -> master) HEAD@{11}: checkout: moving from master to bugfix
3e505b4 (HEAD -> master) HEAD@{12}: commit: update index file
553d125 HEAD@{13}: commit (merge): Merge branch 'footer'
2020251 HEAD@{14}: checkout: moving from footer to master
5149ec0 (footer, bugfix) HEAD@{15}: commit: update index file
56ff0b5 HEAD@{16}: checkout: moving from master to footer
2020251 HEAD@{17}: commit: add footer in index file
56ff0b5 HEAD@{18}: merge footer: Fast-forward
4fc3120 HEAD@{19}: checkout: moving from footer to master
56ff0b5 HEAD@{20}: commit: add footer section to the code base
4fc3120 HEAD@{21}: checkout: moving from master to footer
4fc3120 HEAD@{22}: merge nav-bar: Merge made by the 'ort' strategy.
8076f8a HEAD@{23}: checkout: moving from nav-bar to master
30217fe HEAD@{24}: checkout: moving from master to nav-bar
8076f8a HEAD@{25}: checkout: moving from nav-bar to master
30217fe HEAD@{26}: checkout: moving from master to nav-bar
8076f8a HEAD@{27}: commit: add hero section to the code base
c5ac897 HEAD@{28}: checkout: moving from nav-bar to master
30217fe HEAD@{29}: commit: added navbar.html
c5ac897 HEAD@{30}: checkout: moving from master to nav-bar
c5ac897 HEAD@{31}: commit: added index.html
a9916ae HEAD@{32}: commit (initial): initial commit
(END)

--  example from another repo
$ git reflog show HEAD
11e6485 (HEAD -> main) HEAD@{0}: Branch: renamed refs/heads/master to refs/heads/main
11e6485 (HEAD -> main) HEAD@{2}: commit (initial): add index.html
```


#### create a branch and move to newly created branch
```sh
$ git switch -c footer
Switched to a new branch 'footer'

$ git checkout -c new-branch
```

#### merging a feature branch with master
```sh
$ git merge nav-bar
```


#### restore a file
```sh
$ git restore footer.html
```


#### deleting a local branch
```sh
$ git branch -d nav-bar
Deleted branch nav-bar (was 30217fe).
```

#### git diff between two commits
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

#### git diff staged files
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

#### git stash
```sh
$ git stash
Saved working directory and index state WIP on master: 3e505b4 update index file

$ git stash list
stash@{0}: WIP on master: 3e505b4 update index file

$ git stash pop
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   footer.html

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (a058137ffc829f33517757a6e9dcff8ffa9ec973)

$ git stash pop stash@{2}
```


#### git rebase
```sh
$ git checkout bugfix
Switched to branch 'bugfix'

$ git rebase master
Successfully rebased and updated refs/heads/bugfix.
```


#### git remote

to add remote 
```sh
$ git remote add origin https://github.com/raghav-nayak/git-test-demo.git
```

to show all the remote repo urls
```sh
$ git remote -v
origin	https://github.com/raghav-nayak/git-test-demo.git (fetch)
origin	https://github.com/raghav-nayak/git-test-demo.git (push)
```

to rename
```sh
$ git remote rename old_name new_name
```

to remove
```sh
$ git remote remove name
```


#### git push

to push local changes to remote
```sh
$ git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 575 bytes | 575.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/raghav-nayak/git-test-demo.git
   96e220b..0c1aeea  main -> main
```

to set up an upstream
```sh
$ git push --set-upstream origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 474 bytes | 474.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/raghav-nayak/git-test-demo.git
   0c1aeea..e5f0db3  main -> main
branch 'main' set up to track 'origin/main'.
```

#### git clone

```sh
$ git clone https://github.com/raghav-nayak/histesh-choudhary-golang.git
Cloning into 'histesh-choudhary-golang'...
remote: Enumerating objects: 121, done.
remote: Counting objects: 100% (121/121), done.
remote: Compressing objects: 100% (90/90), done.
remote: Total 121 (delta 1), reused 121 (delta 1), pack-reused 0
Receiving objects: 100% (121/121), 15.11 MiB | 18.25 MiB/s, done.
Resolving deltas: 100% (1/1), done.
```

### git fetch
to get changes from one branch or remote to local repo.

```sh
$ git fetch
```

### git pull
pull will get the changes from remote you working area
```sh
$ git pull origin main
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 868 bytes | 289.00 KiB/s, done.
From https://github.com/raghav-nayak/git-test-demo
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> origin/main
```