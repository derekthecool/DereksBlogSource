---
title: "Setting Up a Blog With Hugo"
date: 2022-08-17T08:20:06-06:00
draft: false
---

# Setting Up A Blog With Hugo

It site uses [hugo](hugo) and setup was easy. Following the
[hugo quick-start](https://gohugo.io/getting-started/quick-start/) was very
straight forward and simple.

## Install

Install prerequisites:

- go
- git
- hugo minimum version of 0.74.x for the terminal theme

```bash
# Check version latest version now is: hugo v0.101.0+extended linux/amd64
hugo version

# Create new site, NOTE: this command creates a new directory
hugo new site DereksBlogSource

# Add a theme
cd DereksBlogSource && git init
git submodule add -f https://github.com/panr/hugo-theme-terminal.git themes/terminal

# Add theme to the file config.toml

# Add a first page: this command just creates a markdown file with yaml metadata header
hugo new posts/Setting-Up-A-Blog-With-Hugo.md

# Start hugo live server
hugo server -D
```

For setting up [hugo live server in WSL](https://www.saotn.org/hugo-development-environment-in-wsl-2/)
I found this helpful tip to use your WSL IP address.

## Deploy Website

There are many ways to do this. Check the
[Hosting & Deployment](https://gohugo.io/hosting-and-deployment/) for many ways
to do this.

For my website [dereklomax.com](dereklomax.com) I prefer to use the rsync
option.
