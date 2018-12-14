---
layout:     post
title:      Git Commit Message Format
subtitle:   
date:       2018-05-10
tags:       code
card-brief: Why good commit messages matter? Because the specific commit messages can improve development efficiency.
card-image: https://github.com/mutating/mutating.github.io/blob/master/resources/2018/05/2018-05-10-git-commit-message-format/git.jpeg?raw=true
card-type:  image
---

Git Commit Message Format
==============
A good commit message serve at lease three important purposes:

* short log
* unified format
* clearly express

DO
==============
\<type\>: [-message-]

### Arguments:
	type:     value of TYPE
	message:  a single short (less than 50 character) line summarizing the change

> ### TYPE
> * Add:      a file is added
> * Update:   a code is updated
> * Feat:     a new feature
> * Fix:      a bug is fixed
> * Remove:   a file if removed
> * Refactor: a code chage that improves performance
> * Test:     adding tests
> * Chore:    changing to the build process or auxiliary tools and libraries
> * style:    changes that do not affect the meaning of the code
> * Docs:     documentation is added or changed