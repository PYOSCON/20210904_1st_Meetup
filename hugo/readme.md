# Use HUGO to make your own blog
---

Table of Contents
============

* [Installation](#installation)
    * [MACOS](#macos)
    * [WINDOWS](#windows)
    * [LINUX](#linux)
    * [Build from source](#build-from-source)
* [Create a New Site](#create-a-new-site)
* [Write a post](#write-a-post)
* [Deploy to github pages](#deploy-to-github-pages)
* [References](#references)
---

## Installation

#### MACOS

```bash
$ brew install hugo # Homebrew
$ port install hugo # MacPorts

$ hugo version # verify
```

#### WINDOWS

1. From terminal (official recommendation)

```bash
$ choco install hugo -confirm
$ choco install hugo-extended -confirm # With extended Sass/Scss features

$ scoop install hugo
$ scoop install hugo-extended

$ hugo version # verify
```

2. Download zip file
An alternative way to install hugo is go directly to the github repository and download the zip file.
[Hugo Releases](https://github.com/gohugoio/hugo/releases)

#### LINUX
```bash
# Debian/Ubuntu
$ sudo apt-get install hugo

# Arch Linux
$ sudo pacman -Syu hugo

# Fedora/RedHat/Centos
$ sudo dnf install hugo

# OpenBSD
$ doas pkg_add hugo

# SNAP Package
$ snap install hugo
$ snap install hugo --channel=extended

$ hugo version # verify
```


#### Build from source
```bash
#If you are a Windows user, substitute the $HOME environment variable above with %USERPROFILE%.

$ mkdir $HOME/src
$ cd $HOME/src
$ git clone https://github.com/gohugoio/hugo.git
$ cd hugo
$ go install --tags extended

$ hugo version # verify
```

## Create a New Site
```bash
# use your github user name, i.e., {user_name}.github.io
# so that later you could push to your github account and be hosted automatically.
$ hugo new site walker088.github.io
$ cd walker088.github.io
$ mkdir theme
$ git clone https://github.com/razonyang/hugo-theme-bootstrap themes/hugo-theme-bootstrap

# check the current result
$ hugo server

# add the site config to your github repository
$ git init
$ git remote add origin {git_url} # e.g., git@github.com:Walker088/blog.git
$ git pull --set-upstream origin master
$ git add . && git commit -m "initial commit" && git push
```

## Write a post
```bash
hugo new posts/post-group-1/my-first-post.md
```

```yaml
# my-first-post.md
---
title: "Golang crawler (1) - Introduction"
date: 2021-08-13T15:19:26-04:00
draft: true
type: post

tags: [ "golang", "crawler" ]
categories: [ "golang" ]
series: ["Golang crawler"]

toc: true
comment: true
---

## Start the markdown content below

...

## Some preview content

...

<!--more-->

## More contents

```

## Deploy to github pages
```bash
$ hugo # will generate your site to /public
$ cd public
# add the site config to your github repository
$ git init
$ git remote add origin {git_url} # e.g., git@github.com:Walker088/Walker088.github.io.git
$ git pull --set-upstream origin master
$ git add . && git commit -m "initial commit" && git push
```


## References
1. [Hugo official document](https://gohugo.io/documentation/)
2. [Hugo Themes recommendations](https://themes.gohugo.io/)
3. [hugoThemes github](https://github.com/gohugoio/hugoThemes)
4. [hugo-theme-bootstrap](https://github.com/razonyang/hugo-theme-bootstrap)
5. [github pages](https://pages.github.com/)
6. [Why I migrated my blog from WordPress to Hugo](https://szymonkrajewski.pl/why-i-migrated-from-wordpress-to-hugo/)