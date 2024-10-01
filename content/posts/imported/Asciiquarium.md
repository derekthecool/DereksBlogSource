---
title: "Asciiquarium"
date: 2024-07-17T10:06:34
categories: ["terminal"]
image: https://imgs.search.brave.com/SffeYBma4ibmGOnt7jpySkGa-HB0qWFxx5NsyROabE0/rs:fit:500:0:0:0/g:ce/aHR0cHM6Ly9pLnNz/dGF0aWMubmV0LzIx/UzlGLnBuZw
draft: true
---

# Asciiquarium

{{< featuredImage alt="asciiquarium terminal image" >}}

This application is a wonderful terminal aquarium! How cool is that!
The application is a Perl script that shows fish and other items like sea
monsters scrolling across the screen.

Go to the github page [cmatsuoka/asciiquarium](https://github.com/cmatsuoka/asciiquarium).

## Install And Run

### Containerized

This is my preferred method. It's just so easy!
Of course you'll need podman or docker to be installed.

```sh
# podman
podman run -it --rm danielkraic/asciiquarium

# docker
docker run -it --rm danielkraic/asciiquarium
```

### Debian & Ubuntu

1. `sudo apt install libcurses-perl`
2. `cpan` agree to the defaults and type out quit to leave
3. `sudo cpan Term::Animation`
4. Download asciiquarium with `git clone https://github.com/cmatsuoka/asciiquarium.git ~/`
5. Move the file to /usr/local/bin `sudo mv ~/asciiquarium/asciiquarium /usr/local/bin`
6. Run `asciiquarium` and enjoy the show

### Arch Linux

```sh
# Install
sudo pacman -S asciiquarium

# Run
asciiquarium
```
