git is a software.
github
- most popular git service provider to host git online.
- collaboration and backup
- opensource
other popular service providers - gitlab and bitbucket

[generating ssh key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)


### git remote
to push and pull from any hosted service provider repo, you need to set up the remote.

to add remote 
`git remote add <name> <url>`
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
`git push <remote> <branch>`
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

```sh
$ git push
fatal: The current branch main has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin main

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

```

you can use `-u` or `--set-upstream`  to setup an upstream that allows you to run future command `git push`.
You dont have use `origin main` 

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

$ git commit -am "add a list to index file"
[main 2d00f71] add a list to index file
 1 file changed, 4 insertions(+)

$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 363 bytes | 363.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/raghav-nayak/git-test-demo.git
   e5f0db3..2d00f71  main -> main
```



### git clone

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


#### git pull = git fetch + git merge

### github features
1. adding collaborators
2. README file
3. adding gists
4. code spaces
5. dev container
