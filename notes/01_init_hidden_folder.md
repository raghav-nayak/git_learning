[official documentation](https://git-scm.com/doc)
[Pro Git book](https://git-scm.com/book/en/v2)

Version control system
- track file for changes
- helps to work in a collaborative env

Terminalogy
- repo (repository)
	- git on system vs tracking

after running `git init`, you will see `.git` folder
```sh
 $ pwd
/git_learning/dir_one

 $ ll -l
total 0
drwxr-xr-x  9 raghavnayak  staff  288 Apr  7 01:00 .git
drwxr-xr-x  3 raghavnayak  staff   96 Apr  7 01:00 .
drwxr-xr-x  5 raghavnayak  staff  160 Apr  7 01:00 ..

$ cd .git

$ ll
total 24
drwxr-xr-x   4 raghavnayak  staff  128 Apr  7 01:00 objects
drwxr-xr-x   9 raghavnayak  staff  288 Apr  7 01:00 .
-rw-r--r--   1 raghavnayak  staff   23 Apr  7 01:00 HEAD
drwxr-xr-x   4 raghavnayak  staff  128 Apr  7 01:00 refs
-rw-r--r--   1 raghavnayak  staff  137 Apr  7 01:00 config
drwxr-xr-x  16 raghavnayak  staff  512 Apr  7 01:00 hooks
-rw-r--r--   1 raghavnayak  staff   73 Apr  7 01:00 description
drwxr-xr-x   3 raghavnayak  staff   96 Apr  7 01:00 info
drwxr-xr-x   3 raghavnayak  staff   96 Apr  7 01:00 ..

$ tree
.
├── HEAD
├── config
├── description
├── hooks
│   ├── applypatch-msg.sample
│   ├── commit-msg.sample
│   ├── fsmonitor-watchman.sample
│   ├── post-update.sample
│   ├── pre-applypatch.sample
│   ├── pre-commit.sample
│   ├── pre-merge-commit.sample
│   ├── pre-push.sample
│   ├── pre-rebase.sample
│   ├── pre-receive.sample
│   ├── prepare-commit-msg.sample
│   ├── push-to-checkout.sample
│   ├── sendemail-validate.sample
│   └── update.sample
├── info
│   └── exclude
├── objects
│   ├── info
│   └── pack
└── refs
    ├── heads
    └── tags

8 directories, 18 files
```

`commit` is like a checkpoint in games. 

write -> add -> commit -> git push

working area -> git add -> staging area -> git commit -> repo -> git push (github or gitlab)
