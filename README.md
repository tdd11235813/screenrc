# screenrc
My GNU screen configuration.

## Setup

- Drop the files into `~/.screen`.
- Edit `.bashrc` adding:
```bash
export SCREENDIR=~/.screen
alias screen="screen -c $SCREENDIR/.screenrc"
```

## Statusbar

The statusbar contains user, uptime and load stats of remote server (called taurus here).
You can deactivate it by commenting in `.screen`:
```
backtick 0 0 10 sh -c 'sh ~/.screenrc_taurus'
```

## Emacs

If you use [my emacs config](https://github.com/tdd11235813/emacs_config) then you might want to enable additional screen terminals, just read the `.screen`.
It requires the aliases:
```bash
alias em="emacs -l ~/.emacs.d/init.el"
alias ems="em --daemon=workspaceC"
alias emc="emacsclient -s workspaceC"
alias emsci="emacs -l /home/mwerner/.emacs.d/init_scivis.el"
alias emssci="emsci --daemon=workspaceS"
alias emcsci="emacsclient -s workspaceS"
```


## Troubleshooting

- For nested screen sessions use `Ctrl-a a` to control inner screen session.
- You will not find the .screen option `shell bash` as it prevents ssh to connect to the remote server. If you need that option ensure that there already is an ssh tunnel open (using ControlPersist in ssh config).

## License

Public Domain (using [CC0](https://creativecommons.org/publicdomain/zero/1.0/)).
