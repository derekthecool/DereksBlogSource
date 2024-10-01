---
title: "GitConfig"
date: 2024-07-23T15:16:31
image: https://git-scm.com/images/logo@2x.png
categories:
  - git
  - terminal
draft: true
---

# Git Config

## Global - Without A `.gitconfig` File

There are several ways to make working with git easier, customizing is the first
step.

Here is a good set of global settings I like

```
git config --global user.name "Derek Lomax"
git config --global user.email "My email of choice"
git config --global pull.rebase true
git config --global fetch.prune true
git config --global diff.colorMoved zebra
git config --global core.eol lf
git config --global core.autocrlf input
```

## Global With A `.gitconfig` File

A .gitconfig file can be saved as part of your dotfiles to make things even
easier. Here is an example:

```
[user]
	name = Derek Lomax
	email = youremail@gmail.com
[core]
	editor = nvim
	eol = lf
	autocrlf = input
[pull]
	rebase = true
[fetch]
	prune = true
[diff]
	colorMoved = zebra
[help]
	format = man
[credential "helperselector"]
	selected = manager
[includeIf "gitdir:~/repos/"]
	path = "~/repos/.gitconfig"
```
