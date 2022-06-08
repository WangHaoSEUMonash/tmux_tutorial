# tmux_tutorial
[Reference(阮一峰的网络日志)](http://www.ruanyifeng.com/blog/2019/10/tmux.html)
## Basic

### Install
`$ sudo apt-get install tmux` Ubuntu或Debian

`$ sudo yum install tmux` CentOS或Fedora

`$ brew install tmux` Mac

### Open & Exit

`tmux`

### Management

### New
第一个启动的 Tmux 窗口，编号是0，第二个窗口的编号是1，以此类推。这些窗口对应的会话，就是 0 号会话、1 号会话。

使用编号区分会话，不太直观，更好的方法是为会话起名。
```
$ tmux new -s <session-name>
```

### Detach

在Tmux窗口中，按下**Ctrl+b d**或者输入**tmux detach**命令，就会将当前会话与窗口分离。
```
$ tmux detach
```
上面命令执行后，就会退出当前 Tmux 窗口，但是会话和里面的进程仍然在后台运行。

**tmux ls**命令可以查看当前所有的Tmux会话。

```
$ tmux ls
or $ tmux list-session
```

### Attach

**tmux attach**命令用于重新接入某个已存在的会话
```
# 使用会话编号
$ tmux attach -t 0

# 使用会话名称
$ tmux attach -t <session-name>
```

### Kill

**tmux kill-session** 命令用于杀死某个会话
```
# 使用会话编号
$ tmux kill-session -t 0

# 使用会话名称
$ tmux kill-session -t <session-name>
```

### Switch
**tmux switch**命令用于切换会话。
```
# 使用会话编号
$ tmux switch -t 0

# 使用会话名称
$ tmux switch -t <session-name>
```

### Rename

**tmux rename-session**命令用于重命名会话
```
$ tmux rename-session -t 0 <new-name>
```
上面命令将0号会话重命名。

### 快捷键
`Ctrl+b d` 分离当前会话

`Ctrl+b s` 列出所有会话

`Ctrl+b $` 重命名当前会话
