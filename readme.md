# Cheat Sheet

## Table of Contents

* [Git](#Git)
  * [Porcelain](#porcelain)
    * [worktree](#worktree)
    * [clean](#clean)
    * [reset](#reset)
    * [diff](#diff)
    * [revert](#revert)
    * [bisect](#bisect)
    * [move](#mv)
    * [remove](#rm)
    * [remote](#remote)
    * [log](#log)
    * [status](#status)
    * [stash](#stash)
    * [rebase](#rebase)
    * [tag](#tag)
    * [submodule](#submodule)
    * [merge](#merge)
  * [Plumbing](#plumbing)
     * [cat-file](#cat-file)
     * [reflog](#reflog)
  * [Git-LFS](#git-lfs)
  * [BFG](#bfg)
  * [GPG](#gpg)
* [Linux](#linux)
  * [ls](#ls--list)
  * [du](#du--disk-usage)
  * [df](#df--disk-free)
  * [tmux](#tmux--terminal-multiplexer)
  * [base64](#base64)
  * [wc](#wc--word-count)
  * [misc.](#misc)
* [Useful Combinations](#useful-linux-commands)

# Git
Doing complex stuff / fixing problems in Git.

## Porcelain

### Worktree
A git repository can support multiple working trees, allowing you to check out more than one branch at a time

```sh
# start a new branch "topic" in the folder specified
git worktree add ../topic

# create worktree using an existing branch
git worktree add ../foobar feature/foobar

# delete/remove a worktree
git worktree remove ../topic
```

### Clean
Remove files/folders from the working directory
```sh
# remove file not tracked by git
git clean -fd

# remove files not tracked by git (including those ignored by .gitignore)
git clean -fdx
```

### Reset
Reset working directory (HEAD?) to specific commit
```sh
# undo changes made to any/all tracked files (revert both working tree and index to last commit)
git reset --hard
```

### Diff
Differences between commits/files
```sh
# compare working tree (your files) to staging area
git diff

# compare things in staging area to most recent commit (HEAD)
git diff --staged

# compare your working tree and index to HEAD
git diff HEAD

# compare words instead of lines using the --color-words command
git diff --color-words

# compare words with some syntax defining the change instead of whole lines using --word-diff command
git diff --word-diff

# use the stat command to list summary changes at the file level
git diff --stat
```

### Revert
Sometimes the wrong code is checked in, and things break. To revert back to earlier commits you can use the following commands

```sh
# revert back 2 commits but record the reverts as separate named commits
git revert HEAD~2..

# revert back 4 commits but record the jump back as a single commit
git revert --no-commit HEAD~4..
```

### bisect
### mv
### rm
### remote
### log
### status
### stash
### rebase
### tag
### submodule
```
--recursive
--recurse-submodules
```

### merge
```sh
## Merging Two Repositories ##
# pull from origin (optional)
git pull

# add a new remote (we'll call this "another")
git remote add another ssh://git@git-remote-url-here.git

# fetch from the "another" remote
git fetch another

# merge the another branch into the current branch
git merge another/master --allow-unrelated-histories
```

## Plumbing

### cat-file
### reflog

## Git-LFS
Git LFS replaces large files in your repository with tiny pointers. During normal usage, you'll never see these pointer files as they are handled automatically by Git LFS. Git LFS is a FOSS plug-in for Git. When adding a new file type to git-lfs tracking a filter must be added to the project-level .gitattributes file.

```sh
# adding all new bitmap files (.bmp) to lfs tracking
git lfs track "*.bmp"
```

If LFS failed to pull down the files for whatever reason lfs-pull can be used to resolve the pointers

```sh
# grab missing LFS files
git lfs pull
```

# BFG

# GPG
Create a key, export (paste into forge), and enable client-side
```ps
gpg --full-generate-key
gpg -k
gpg --armor --export
git config --global user.signingkey 0000000000000000000000000000000000000000
git config --global commit.gpgsign true
```

<!-- ------------------------------------------------------------------------------------- -->
<!-- Linux ------------------------------------------------------------------------------- -->
<!-- ------------------------------------------------------------------------------------- -->

# Linux
Common Linux commands (including ```coreutils```) available in many environments.
## ```ls``` / List
```sh
# long, human readable (file sizes), including hidden files
ls -lah
```

## ```du``` / Disk Usage
```sh
# print size of sub-directories
du -cksh *
```

## ```df``` / Disk Free
```sh
# print human readable free disk space
df -H
```

## ```tmux``` / Terminal Multiplexer
### Commands
```sh
# start a new tmux session
tmux

# attach to the previous running tmux session
tmux a

# list running tmux sessions
tmux ls

# attach to a specific session
tmux a -t 0
```
> ### Shortcuts
> - __ctrl + b__ _then_ __d__: detach session
> - __ctrl + b__ _then_ __&__: kill session
> - __ctrl + b__ _then_ __%__: split horizontally
> - __ctrl + b__ _then_ __"__: split vertically

## ```base64```
```sh
# encode
base64 original_file.txt > encoded_file.txt

# decode
base64 -d encoded_file.txt > decoded_file.txt
```

## ```wc``` / Word Count
```sh
# bytes
wc foobar.txt -m

# characters
wc foobar.txt -c

# lines
wc foobar.txt -l

# words
wc foobar.txt -w
```

## Misc.
```sh
# file system
cd
chmod
dd
cp
mkdir
mv
rm
rmdir
touch
ls

# files
cat
cksum
sha1sum
tail
diff

# system
whoami
ps
htop
top
shutdown

# utils
yes
sed
grep
watch

# networkings
dig
nslookup
ping

# application software
vi
vim
certbot
docker-compose
```

<!-- ------------------------------------------------------------------------------------- -->
<!-- Useful Linux Commands --------------------------------------------------------------- -->
<!-- ------------------------------------------------------------------------------------- -->

# Useful Linux Commands
Cross-Platform commands used to get useful Linux information, leveraging the tools above

```sh
# print linux version information
cat /etc/*release
```
