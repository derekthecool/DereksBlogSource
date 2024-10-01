---
title: "GitCommitHelpers"
date: 2024-07-29T09:59:13
image:
categories:
  - git
draft: true
---

# GitCommitHelpers

Making git commits is fairly easy. However, there are some tools that can be
used to make things even better.

## [commitizen](https://commitizen-tools.github.io/commitizen/)

This tool offers these powerful features

- Helps to interactively create commits using the [conventional-commits][conventional-commits]
  guidelines
- Update your projects version files
- And my most favorite is to generate a CHANGELOG.md file based on the
  guidelines of [keep-a-changelog][keep-a-changelog.md]

### Install

#### pip

```sh
pip install --user -U commitizen
```

#### Arch Linux

I had errors when trying to add it using the normal pip install command.
This worked for me 2024-07-29.

```sh
sudo pacman -S pipx
pipx install commitizen
```

### Usage

Setup your repository commitizen settings.
Most things are straight forward to answer.
Though, you can install a [pre-commit][pre-commit] hook to help validate
[conventional-commits][conventional-commits]. See the section in this document
on how to use and install [pre-commit][pre-commit].

```sh
cz init
```

You can interactively create a commit using the `cz` tool like this. It will
take you through several questions to help you build a
[conventional commit][conventional-commits].

```sh
cz commit
```

But, it can be slow to always commit like this. I want it to be much faster and
still stick with my normal command-line commit method `git commit --message "...."`

## [pre-commit][pre-commit]

This tool makes it very easy to use [git commit hooks][git-hooks].
There are many options, plenty of ready to use hooks. You can easily create your
own as well.

### Install

```sh
pip install pre-commit
```

### Usage

```sh
# Check version
pre-commit --version
```

```sh
# Install: creates a local yaml config file and installs the git hook to .git/hooks/pre-commit
pre-commit install
```

```sh
# Run manually (only runs on changed files)
pre-commit run

# Run manually on all files, even unchanged files
# Recommended when adding new hooks
pre-commit run --all-files
```

### Finding Hooks

The [webpage](https://pre-commit.com/hooks.html) shows several popular hooks
ready for use.

Also included on this page is how to search GitHub for hooks.
Use this [GitHub advanced search filter](https://github.com/search?q=path%3A.pre-commit-hooks.yaml+language%3AYAML&type=code&l=YAML)
optionally add an additional query string to search for a specific keyword.

[git-hooks]: https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks
[conventional-commits]: https://www.conventionalcommits.org/en/v1.0.0/
[keep-a-changelog.md]: https://keepachangelog.com/
[semantic-versioning]: https://semver.org/
