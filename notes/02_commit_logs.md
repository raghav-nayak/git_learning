`git add` 
to add a file or files from working area to staging area
. means all the files

`git commit`
- always use -m to add commit message
- atomic commit -> keeps commits centric to one feature/component/fix
- official doc says use present tense and imperative; give order to code base

```sh
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test2.txt

nothing added to commit but untracked files present (use "git add" to track)
```

you can check use `git status` command to frequently to check what the current status of your git repo. Check the last line in the above output.

`git log`
to show the history of commits
you can use `--oneline` to a precise history of commits

