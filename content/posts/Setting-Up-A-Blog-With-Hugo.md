---
title: "Setting Up a Blog With Hugo"
date: 2022-08-17T08:20:06-06:00
draft: true
---

# Setting Up A Blog With Hugo

It site uses [hugo](hugo) and setup was easy. Following the
[hugo quick-start](https://gohugo.io/getting-started/quick-start/) was very
straight forward and simple.

Make sure you have git and go installed first.

The commands to setup were these:

```sh
# No, no, I do not use a mac but brew ending up being the easiest install method
brew install hugo

# Check version latest version now is: hugo v0.101.0+extended linux/amd64
hugo version

# Create new site, NOTE: this command creates a new directory
hugo new site DereksBlogSource

# Add a theme
cd DereksBlogSource && git init
git submodule add -f https://github.com/panr/hugo-theme-terminal.git themes/terminal

# Add theme to the file config.toml

# Add a first page
hugo new posts/Setting-Up-A-Blog-With-Hugo.md

# Start hugo live server
hugo server -D
```

For setting up [hugo live server in WSL](https://www.saotn.org/hugo-development-environment-in-wsl-2/)
I found this helpful tip to use your WSL IP address.
