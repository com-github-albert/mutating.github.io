---
layout:     post
title:      Git Commit Message Format
subtitle:   
date:       2018-05-10
tags:       code
card-brief: Why good commit messages matter? Because the specific commit messages can improve development efficiency.
card-image: https://thumbnail0.baidupcs.com/thumbnail/35a6bf93921fb7337352ea072ca27210?fid=3995765095-250528-233938923917580&time=1525932000&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-T3xH6X%2FRhYQfvtfUzLExWLp4MbE%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=3005428355757018692&dp-callid=0&size=c710_u400&quality=100&vuk=-&ft=video
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