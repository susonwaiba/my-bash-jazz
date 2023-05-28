# my-bash-jazz

My collection of bash scripts.


## Documentation

### Dependencies

- fzf
- sd
- fd
- tmux
- openssl

### my-tmux-session

- Dir structure
- - ~/

- - ~/config <-- [S]
- - ~/config/* <-- [S]

- - ~/me <-- [S]
- - ~/me/* <-- [S]

- - ~/ew <-- [S]
- - ~/ew/* <-- [S]

- - ~/work <-- [S]
- - ~/work/* <-- [S]

- [S] = Searchable upto level 1

- List search directory

```bash
# For me
echo "~/.config" >> ~/.my-tmux-session-default
echo "~/me" >> ~/.my-tmux-session-default
echo "~/ew" >> ~/.my-tmux-session-default
my-tmux-session
my-tmux-session default

# For work
echo "~/work" >> ~/.config/.my-tmux-session-work
my-tmux-session work

# For something...
echo "~/something" >> ~/.config/my-bash-jazz/.my-tmux-session-something
my-tmux-session something
```

- Add additional directory

```bash
echo "~/Downloads" >> ~/.my-tmux-session-default-additional
echo "~/Pictures" >> ~/.my-tmux-session-default-additional
my-tmux-session
my-tmux-session default
```

### my-ssh

```bash
# For me
echo "local-server = ssh suson@192.168.x.x" >> ~/.my-ssh-default
my-ssh
my-ssh default
my-ssh default copy

# For work
echo "work-server = ssh ubuntu@x.x.x.x" >> ~/.config/.my-ssh-work
my-ssh work
my-ssh work copy

# For something...
echo "something-server = ssh ubuntu@x.x.x.x" >> ~/.config/my-bash-jazz/.my-ssh-something
my-ssh something
my-ssh something copy
```

### Setup aliases

```bash
# .bash_aliases
alias a="tmux attach -d"

alias t="$HOME/.config/my-bash-jazz/bin/my-tmux-session"
alias tw="$HOME/.config/my-bash-jazz/bin/my-tmux-session work"

alias s="$HOME/.config/my-bash-jazz/bin/my-ssh"
alias sw="$HOME/.config/my-bash-jazz/bin/my-ssh work"
alias s-copy="$HOME/.config/my-bash-jazz/bin/my-ssh default copy"
alias sw-copy="$HOME/.config/my-bash-jazz/bin/my-ssh work copy"
```

```bash
# .bashrc or .zshrc
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi
```

## Setup

- Clone the repository

```bash
git clone https://github.com/susonwaiba/my-bash-jazz ~/.config/
```

- Give perssions to execute

```bash
sudo chmod +x ~/.config/my-bash-jazz/bin/*
```

- Export PATH variable

```bash
# vim .bashrc or .zshrc
export PATH="$PATH:$HOME/.config/my-bash-jazz/bin";
```

#### Updates ?

```bash
cd ~/.config/my-bash-jazz/
git pull origin main
```

