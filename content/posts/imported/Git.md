---
title: "Git"
date: 2024-07-17T13:25:55
image: https://git-scm.com/images/logo@2x.png
categories:
  - git
  - terminal
draft: true
---

# Git Guide

## Commit Helpers

See [GitCommitHelpers.md](GitCommitHelpers.md)

## Git Sub Module

### [Removing](https://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule)

```git
git rm path-to-submodule
git commit
```

## Git Subtree

This seems to be a better alternative to git submodules.

### Without Remote Tracking

```powershell
# Without adding the other repos commits
git subtree add --prefix .vim/bundle/tpope-vim-surround https://bitbucket.org/vim-plugins-mirror/vim-surround.git main --squash

# With adding the other repos commits
git subtree add --prefix .vim/bundle/tpope-vim-surround https://bitbucket.org/vim-plugins-mirror/vim-surround.git main
```

For dot files

```powershell
cd ~/
dot subtree add --prefix $HOME/.config/awesome/awesome-wm-widgets https://github.com/streetturtle/awesome-wm-widgets.git master --squash
```

#### Update Without Remote

```powershell
git subtree pull --prefix .vim/bundle/tpope-vim-surround https://bitbucket.org/vim-plugins-mirror/vim-surround.git main --squash
```

Adding a awesomeWM repo for nice widgets in my dotfiles would use this command

```powershell
cd ~/
dot subtree pull --prefix $HOME/.config/awesome/awesome-wm-widgets https://github.com/streetturtle/awesome-wm-widgets.git master --squash
```

### With Adding Repository As A Remote

```powershell
git remote add -f tpope-vim-surround https://bitbucket.org/vim-plugins-mirror/vim-surround.git
git subtree add --prefix .vim/bundle/tpope-vim-surround tpope-vim-surround main --squash
git subtree pull --prefix .vim/bundle/tpope-vim-surround tpope-vim-surround main --squash
```

## Git Error Handling

### Reset A Repo

I used this command when I wanted to convert my private GitHub repos to public.

[Guide](https://stackoverflow.com/questions/1657017/how-to-squash-all-git-commits-into-one)
here.

Command used:

```sh
git reset $(git commit-tree HEAD^{tree} -m "Reset private repo for public use")

# For use with my bash function "dot" to access my bare repo use this
dot reset $(dot commit-tree HEAD^{tree} -m "Reset private repo for public use")
```

### Loose Object Error

I ran into this error with this wiki repository 2020-10-31. Scary 💀!
I found a solution on Stack Overflow https://stackoverflow.com/a/18238322/9842112

```sh
rm -fr .git
git init
git remote add origin your-git-remote-url
git fetch
git reset --hard origin/master
git branch --set-upstream-to=origin/master master
```

## Another Git Process In This Repository

Today I got an error with git saying this message

```git
Another git process seems to be running in this repository, e.g.
an editor opened by 'git commit'. Please make sure all processes
are terminated then try again. If it still fails, a git process
may have crashed in this repository earlier:
remove the file manually to continue.
```

This can be caused by several things. I think the biggest reason is having a
terminal status line such as starship.
I found that `git stash` was not working and found this fixed it.

Following the guide from [intellipat com](https://intellipaat.com/community/21175/another-git-process-seems-to-be-running-in-this-repository)
I just deleted the file `.git/index.lock` and it worked again.

## Configure Git Remote Url To SSH

```sh
# Read the current git remote url
git remote -v

# Set the url
git remote set-url origin git@github.com:username/repo.git

# Read the current git remote url again if wanted
git remote -v
```

## Create New Ssh key with ssh-keygen

### Single Key

```sh
# Create the key, by default it creates an rsa key with 3048 bits
# Use email as an easy identifier
ssh-keygen -t ed25519 -C "bob@gmail.com"
ssh-keygen -t rsa -b 4096 -C "bob@gmail.com"

# You will be asked to set the keyphrase
# If you are the only user on the machine then skipping this is probably okay

# If prompted to input the ssh key everytime use this command
ssh-add ~/.ssh/id_rsa &>/dev/null
```

See [PowerShellRemoting](PowerShellRemoting.md) for how to remote on
windows machines to either another windows server or even Linux servers.

### Working With Multiple Keys (new version I used)

It is easy to use multiple keys. This [stackoverflow post](https://superuser.com/a/912281)
shows how easy it is to do.

You just need to set the git config option `core.sshCommand` like this

```sh
# Most simply like this
git clone -c "core.sshCommand=ssh -i ~/.ssh/id_rsa_example"

# To set the remote as well
git clone -c "core.sshCommand=ssh -i ~/.ssh/id_rsa_example -F /dev/null" git@github.com:example/example.git
```

### Working With Multiple Keys (old version I used)

Create another ssh key following the previous steps, save the file as work_rsa
in the ~/.ssh folder.

Now we need to manage which keys get used for what services. For this we need to
use the ssh config file ~/.ssh/config. My problem was I needed a key for
personal Github and for work Azure repos.

Here is my current ~/.ssh/config

```txt
# Personal GitHub account
Host github.com
 HostName github.com
 User git
 IdentityFile ~/.ssh/id_rsa

# Work GitHub account
Host dev.azure.com
 HostName dev.azure.com
 User git
 IdentityFile ~/.ssh/work_rsa
```

#### Last Resort If The Above Fails

I was having the problem where if I manually ran this command to add my second
key it would work.

```sh
eval $(ssh-agent) && ssh-add ~/.ssh/id_rsa_work2
```

So to get that in every terminal session I added this line to my
`/etc/zsh/zprofile`.

```
# Send all output to /dev/null starting now
exec >/dev/null
exec 2>/dev/null
# Add the dang ssh key with ssh-add
eval $(ssh-agent) && ssh-add ~/.ssh/id_rsa_work2 &
# Enable normal output again
exec >/dev/tty
exec 2>/dev/tty
```

### Debug SSH Key Authentication

- [Github Guide](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- [SSH Key Debug Guide by chuyeow](https://chuyeow.wtf/2007/02/28/debugging-ssh-public-key-authentication-problems)

The problem I had on 2021-06-28 was showing an error about cannot connect to
remote host and to make sure the repo exists and that I have permission.

The problem I had was that I killed the ssh-agent and did not re add the ssh
key. You can test to see if any keys are added by running this command:

```sh
ssh-add -l
```

It will either show you key information or it will say you have no keys.

## Git Show Untracked Branches

```
git branch --format "%(refname:short) %(upstream)"
```

## Uncommit A File

```sh
git restore --staged file
```
