Jekyll Theme
==============
The simple Jekyll theme with all basic requirements of a GitHub Pages.

Installation
==============
Running these scripts in order with terminal:

1. git clone https://github.com/mutating/mutating.github.io.git
2. cd mutating.github.io/
3. gem install bundle
4. bundle install
5. bundle update (optional)
6. jekyll serve
7. run http://127.0.0.1:4000/ in browser
8. copy this repo to your repo

Usage
==============
### Configuration
Updating these properties in _config.yml file.

|property|explain|
|:------:|:----------------------:|
|title   |your blog's name        |
|author  |your name               |
|url     |your blog's url         |
|mail    |your mail address       |
|github  |your github account name|

### Post folder
The *_post* folder is where your blog posts will live. These files are generally Markdown or HTML, but can be other formats with proper converter installed. All posts must have YAML Front Matter, and they will be converted from their source format into an HTML page that is part of your static sits.

### Creatubg post files
To create a new post, all you need to do is create a file in the _posts diretory. How you name files in this folder is important. Jekyll requires blog post files to be named according to the following format:
```
YEAR-MONTH-DAY-title.md (or .markdown)
```
Where YEAR is a four-digit number, MONTH and DAY are both two-digit numbers. For example, the following are examples of valid post filenames:
```
2018-05-08-hello-jekyll-theme.md
```

Finally, you can start writing your first posts.