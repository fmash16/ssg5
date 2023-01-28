<p align="center">
    <img src="template/img/ssg5.png">
</p>

# SSG5 - A static site generator

Forked from fmash16/ssg5

This POSIX compliable shell script has been written by [Roman
Zolotarev](https://www.romanzolotarev.com/). The documentation for this project
can be found [here](https://www.romanzolotarev.com/ssg.html)

<!-- In order to have a look at my personal customizations and usage, please head
over to [this](https://thebagarius.com/) post on
my blogsite, which has been built with this script. -->

## Usage

### Dependencies

1. Pandoc
2. Vim

### Install

```bash
PATH="$PATH:${$(find ~/.local/bin -printf %p:)%%:}"

mkdir -p packages/ssg5
git clone https://github.com/TheBagarius/ssg5.git bin/ssg5
ln -s bin/ssg5/ssg5 ~/.local/bin/ssg

cp bin/ss5/template website/
```

### Deploy

To build the site, run

```bash
cd website
ssg src dst "Your blog name here.com" "https://Your website address here"
```

### Dev_env
