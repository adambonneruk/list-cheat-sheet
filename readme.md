# Adam's Cheat Sheet

## Table of Contents

* [Git](#Git)
* [Linux](#Linux)
  * [tmux](#tmux--terminal-multiplexer)

## Git

## Linux

### ```ls``` / List
```sh
# long, human readable (file sizes), including hidden files
ls -lah
```

### ```du``` / Disk Usage
```sh
# print size of sub-directories
du -cksh *
```

### ```tmux``` / Terminal Multiplexer
#### Commands
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
> #### Shortcuts
> - __ctrl + b__ _then_ __d__: detach session
> - __ctrl + b__ _then_ __&__: kill session
> - __ctrl + b__ _then_ __%__: split horizontally
> - __ctrl + b__ _then_ __"__: split vertically

### ```base64```
```sh
# encode
base64 original_file.txt > encoded_file.txt

# decode
base64 -d encoded_file.txt > decoded_file.txt
```

### ```wc``` / Word Count
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