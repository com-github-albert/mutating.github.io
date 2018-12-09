---
layout:     post
title:      Symbolicate Crash
subtitle:   
date:       2018-12-09
tags:       code
card-brief: It is a tool for symbolicating crash log by Apple.
card-image: https://coding.net/u/mutating/p/BlogAssets/git/blob/master/2018/12/2018-12-09-symbolicatecrash/Xcode.png
card-type:  image
---

# symbolicatecrash

## 工具配置

### 路径

如果你使用的是 Xcode9.0 或 Xcode10.0，symbolicatecrash 具体位置如下： 

```
/Applications/Xcode.app/Contents/SharedFrameworks/DVTFoundation.framework/Versions/A/Resources/symbolicatecrash
```
symbolicatecrash 在不同 Xcode 中存放位置不相同，可以通过这个命令找到 symbolicatecrash 所在的路径。

```shell
$ find /Applications/Xcode.app -name symbolicatecrash -type f
```

### 环境变量

在使用 symbolicatecrash 之前，还需要配置环境变量 `DEVELOPER_DIR `，否则会提示 ` "DEVELOPER_DIR" is not defined`。

当然这个配置是非常简单的。

* 你可以直接在 Terminal 中执行如下命令，但每次重启 Terminal 都需要再次执行；
* 你也可以在 ~/.bashrc 或者 ~/.bash_profile 中添加如下命令，添加保存之后执行 `source ~/.bashrc` 或者 `$ source ~/.bash_profile` 即可，当然你也可以重启 Terminal，这样以后就不用再次配置了。

```shell
$ export DEVELOPER_DIR="/Applications/XCode.app/Contents/Developer"
```

### 快捷方式

```
$ /Applications/Xcode.app/Contents/SharedFrameworks/DVTFoundation.framework/Versions/A/Resources/symbolicatecrash *.crash *.dSYM > symbol.crash
```

每次使用都要复制 `/Applications/Xcode.app/Contents/SharedFrameworks/DVTFoundation.framework/Versions/A/Resources/≈` 这么长一串文字有点麻烦，我们可以让他更简单一点。

* 打开 ~/.bashrc 或者 ~/.zshrc，添加如下命令

```shell
$ export PATH="/Applications/Xcode.app/Contents/SharedFrameworks/DVTFoundation.framework/Versions/A/Resources/:$PATH"
```

然后执行 `source ~/.bashrc` 或者 `source ~/.zshrc` 或者重启 Terminal 即可。
之后我们就可以直接使用 `symbolicatecrash` 这一命令了。

## 符号化 .Crash 文件

### .crash & .dSYM
symbolicatecrash  Sample 2018-12-6, 11-12.crash Sample.app > test
```
$ symbolicatecrash *.crash *.dSYM > symbol.crash
```

### .crash & .app

```
$ symbolicatecrash *.crash *.app > symbol.crash
```

> NOTE: 

> * *.crash 为 .crash 文件路径；
> * *.dSYM 为 .dSYM 文件路径；
> * *.app 为 .app 文件路径；
> * symbol.crash 为符号化之后输出的文件路径，这个就是你需要的。

## 匹配 UUID

事实上，一个 .dSYM 并不能解析所有的 .crash 文件，只有当 .crash 文件的 UUID 和 .dSYM 文件的 UUID 一致，才能进行解析。
接下来就需要了解获取这些文件的 UUID。

### 获取 dSYM 的 UUID

```shell
dwarfdump --uuid *.dSYM
```

```
UUID: 978B5CE7-1DE2-3E1B-8EC2-1FB5058003F8 (arm64) AppName.app.dSYM/Contents/Resources/DWARF/AppName
```

### 获取 app的 UUID

```shell
dwarfdump --uuid AppName.app/AppName
```

### 获取 crash 的 UUID

打开 .crash 文件，搜索 `Binary Images` 可以看到如下信息

```
Binary Images:
0x10010c000 - 0x100113fff AppName arm64  <df84b945cb9d34c4b906608cfdb29732> /var/containers/Bundle/Application/39684FFF-3A56-48C0-BCDC-547AC7B1165E/AppName.app/AppName
```

其中，`df84b945cb9d34c4b906608cfdb29732` 就是你要找的 UUID。

