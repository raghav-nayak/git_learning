- alternative way to merge
- clean up tool
- merge everything into a single timeline

**Caution:** Never run this on master/main branch

![[Pasted image 20240411111811.png]]

before merging 
![[Pasted image 20240411111643.png]]

After merging master into bugfix
![[Pasted image 20240411111957.png]]


```sh
$ git log --oneline
2ea9621 (HEAD -> master) updated index file
5cfad24 added images
21f1dd1 updated main website
3e505b4 update index file
553d125 Merge branch 'footer'
5149ec0 (footer) update index file
2020251 add footer in index file
56ff0b5 add footer section to the code base
4fc3120 Merge branch 'nav-bar'
8076f8a add hero section to the code base
30217fe added navbar.html
c5ac897 added index.html
a9916ae initial commit
```
as you can see, there are many merge commits which are not useful

<hr>

Go to bugfix branch
```sh
$ git checkout bugfix
Switched to branch 'bugfix'
```
![[Pasted image 20240411112730.png]]

```sh
$ git rebase master
Successfully rebased and updated refs/heads/bugfix.
```
![[Pasted image 20240411112746.png]]


#### rebase with conflicts
```sh
$ git rebase master
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
error: could not apply f59af1d... add card to index file
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply f59af1d... add card to index file
```

```sh
$ git status
interactive rebase in progress; onto ed333a8
Last commands done (4 commands done):
   pick 4eacf00 fixed home page link
   pick f59af1d add card to index file
  (see more in file .git/rebase-merge/done)
No commands remaining.
You are currently rebasing branch 'bugfix' on 'ed333a8'.
  (fix conflicts and then run "git rebase --continue")
  (use "git rebase --skip" to skip this patch)
  (use "git rebase --abort" to check out the original branch)

Unmerged paths:
  (use "git restore --staged <file>..." to unstage)
  (use "git add <file>..." to mark resolution)
	both modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")

$ git add index.html

$ git rebase --continue
[detached HEAD f9fe434] add card to index file
 1 file changed, 1 insertion(+), 1 deletion(-)
Successfully rebased and updated refs/heads/bugfix.

$ git status
On branch bugfix
nothing to commit, working tree clean
```

