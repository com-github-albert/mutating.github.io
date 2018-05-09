---
layout:     post
title:      Hello, Jekyll Theme
subtitle:   
date:       2018-05-08
tags:       code
card-brief: The simple Jekyll theme with all basic requirements of a GitHub Pages.
card-image: https://thumbnail0.baidupcs.com/thumbnail/6e1dd73d9933c5a2291801ffede395c5?fid=3995765095-250528-749845551833651&time=1525791600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-yzSuWQ9j6H9fPMzBC%2FWQgb18X04%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=2967826263800511526&dp-callid=0&size=c710_u400&quality=100&vuk=-&ft=video
card-type:  image
---

Jekyll Theme
==============
{{ page.card-brief }}

![Image]({{ page.card-image }})

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
Modifying the variables in _config.yml file.

|property|explain|
|:------:|:----------------------:|
|title   |your blog's name        |
|author  |your name               |
|url     |your blog's url         |
|mail    |your mail address       |
|github  |your github account name|

### Post folder
The *_post* folder is where your blog posts will live. These files are generally Markdown or HTML, but can be other formats with proper converter installed. All posts must have YAML Front Matter, and they will be converted from their source format into an HTML page that is part of your static sits.

### Creatubg Post Files
To create a new post, all you need to do is create a file in the _posts diretory. How you name files in this folder is important. Jekyll requires blog post files to be named according to the following format:

```
YEAR-MONTH-DAY-title.md (or .markdown)
```

Where YEAR is a four-digit number, MONTH and DAY are both two-digit numbers. For example, the following are examples of valid post filenames:

```
2018-05-08-hello-jekyll-theme.md
```

### Content Format
All blog post files must begin with YAML Front Matter. Here is a example:

```
---
layout:     post
title:      Hello Jekyll Theme
subtitle:   
date:       2018-05-08
tags:       work
brief:      The simple Jekyll theme with all basic requirements of a blog.
card-image: https://thumbnail0.baidupcs.com/thumbnail/6e1dd73d9933c5a2291801ffede395c5?fid=3995765095-250528-749845551833651&time=1525791600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-yzSuWQ9j6H9fPMzBC%2FWQgb18X04%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=2967826263800511526&dp-callid=0&size=c710_u400&quality=100&vuk=-&ft=video
card-type:  image
---
```

Tags similars to categories, one or multiple tags can be added to post.

> You can even create custom variables of your own. These variables will then be avilable to you access using Liquid tags both further down in the file and also in any layouts or includes that the page or post in question relies on.

After that, it's simply a matter of decidign with Markdown.