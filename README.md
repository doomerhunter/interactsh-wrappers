# interactsh-wrappers

## Why ?

Interact-sh logging is a bit complicated. To have long running sessions in the background, you either have to configure disk storage + encryption, or keep your client running

## Solution 

Create aliases to execute the interact-sh client on a remote server within a tmux session. 

## Create a new session

The `interactsh` script will create a new tmux session if it does not exists (ex: clientname.yourdomain.org) and only monitors interactions on that domain. 
Tmux scrollback is set to 99999

![](https://github.com/doomerhunter/interactsh-wrappers/blob/main/img/doc-launch.png)
![](https://github.com/doomerhunter/interactsh-wrappers/blob/main/img/doc-tmux.png)

## Attach and interact

The interactsh-list will, if given no args, list the remote tmux sessions and prompt you a nice UI (FZF) to choose your session and automatically attach to it

![](https://github.com/doomerhunter/interactsh-wrappers/blob/main/img/fzf.png)
![](https://github.com/doomerhunter/interactsh-wrappers/blob/main/img/fzf2.png)
![](https://github.com/doomerhunter/interactsh-wrappers/blob/main/img/tlist.png)

## Requirements 

- Remote server with interactsh-client (go install -v github.com/projectdiscovery/interactsh/cmd/interactsh-client@latest)
- Remote server with tmux installed (apt install tmux)
- Adapt the placeholders within the code :
    - `<yoursub>.<yourdom>.<yourtld>`
    - `<youruser>@<yourserver>`
