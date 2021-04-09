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


## Setup

To use my customized script, you can set it up as follows:

1. Clone the repository and put the executable in the /usr/bin directory

    ```bash
    git clone https://github.com/fmash16/ssg5
    sudoo cp ssg5/ssg5 /usr/bin
    ```

    Create a source directory for storing your website source and a destination
    directory to put the produced static site in

    ```bash
    mkdir -p blogsite/src
    mkdir -p blogsite/dst
    ```

2. A sample ```_header.html``` and a ```_footer.html``` has been provided, copy
   them over to your ```src``` directory.

   ```bash
   cp ssg5/_header.html blogsite/src/
   cp ssg5/_footer.html blogsite/src/
   ```

3. Put your css in a file named ```style.css``` in the css folder inside the
   ```src``` directory.

   ```bash
   cp -rv ssg5/css blogsite/src/
   ```

4. You can store your posts anywhere inside the src directory as you like. To
   keep things organized, you can create a posts directory inside the src dir.

   ```bash
   mkdir blogsite/src/posts/
   ```

   Then you can store your posts written in markdown inside the posts
   directory.

   **Important**
    For the index post list to work, you must include the following metadata
    at the beginning of each post

    ```bash
   ---
   title: Your post title
   description: Some description
   date: YYYY-MM-DD format is a must
   tags: keywords for your post
   image: image attached to post
   ---
    ```

    Among these, ```title``` and ```date``` must be given, rest can be ignored
    if you want. if title and date are not give, a proper homepage with post
    list would not be generated.

5. You can put information about yourself in the ```about.md``` file in your
   src directory.

6. For storing your static content like images, videos or other files, put them
   inside a folder named ```img``` inside the src directory.

   ```bash
   mkdir blogsite/src/img
   ```

7. Put your favicon in a file named ```favicon.png``` in the src directory.


### Dependencies

1. Pandoc
2. Vim


## Usage

To build the site, run

```bash
cd blogsite
ssg5 src dst "Your blog name here" "Your website address here"
```

Now, your site is built in the dst directory.

You can serve it using a webserver of your choice(like apache).
