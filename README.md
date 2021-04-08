<p align="center">
    <img src="ssg5.png">
</p>

# SSG5 - A static site generator

This POSIX compliable shell script has been written by [Roman
Zolotarev](https://www.romanzolotarev.com/). The documentation for this project
can be found [here](https://www.romanzolotarev.com/ssg.html)

In order to have a look at my personal customizations and usage, please head
over to [this](https://fmash16.github.io/content/posts/ssg5_site.html) post on
my blogsite, which has been built with this script.

## Basic Usage

```bash
PATH="$HOME/bin:$PATH"
mkdir src dst
echo '# Hello, World!' > src/index.md
echo '<html><title></title>' > src/_header.html
bin/ssg5 src dst 'Test' 'http://www'
firefox dst/index.html
```

## My customizations

1. Generate a homepage with post list sorted according to date defined in the
   metadata of the md files

2. Paginate the post list with specified number of posts per page

3. Generate a post archive sorted by date

4. Use pandoc for generating the html files
