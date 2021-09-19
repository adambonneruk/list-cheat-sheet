# Cheat Sheet

## Table of Contents

* [Git](#Git)
* [Linux](#linux)
  * [ls](#ls--list)
  * [du](#du--disk-usage)
  * [df](#df--disk-free)
  * [tmux](#tmux--terminal-multiplexer)
  * [base64](#base64)
  * [wc](#wc--word-count)
  * [misc.](#misc)
* [Docker-Compose](#docker-compose)
* [Vi / Vim](#vi--vim)

# Git
Doing complex stuff / fixing problems in Git.

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
