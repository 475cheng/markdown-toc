# Table of Contents

* [markdown-toc](#markdown-toc)
  * [环境依赖](#环境依赖)
  * [Features](#features)
  * [变更日志](#变更日志)
* [快速入门](#快速入门)
  * [下载](#下载)
  * [脚本方式](#脚本方式)
    * [windows](#windows)
* [Table of Contents](#table-of-contents)
    * [linux](#linux)
  * [Java 运行方式](#java-运行方式)



# markdown-toc

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.houbb/markdown-toc/badge.svg)](http://mvnrepository.com/artifact/com.github.houbb/markdown-toc)
[![Build Status](https://www.travis-ci.org/houbb/markdown-toc.svg?branch=master)](https://www.travis-ci.org/houbb/markdown-toc?branch=master)
[![Coverage Status](https://coveralls.io/repos/github/houbb/markdown-toc/badge.svg?branch=master)](https://coveralls.io/github/houbb/markdown-toc?branch=master)

Markdown-toc 可以用来生成 markdown 页面的目录，便于 github 页面展现。

- 初衷

手写 github markdown 时没有目录，内容较多不便于阅读。

- 作用

为 markdown 文件生成 toc，直接写入文件开头。

- 备注

对于标题，md 有两种语法 [setext](http://docutils.sourceforge.net/mirror/setext.html) 
和 [atx](http://www.aaronsw.com/2002/atx/) 模式。

暂时只支持 **atx** 形式。

## 环境依赖

- JDK 

JDK7+, 请确保 JDK 设置正确。

## Features

- github Markdown 文件一键生成目录，且支持多次生成

- 支持重复标题的生成

- 支持特殊字符的过滤

## 变更日志

> [变更日志](doc/CHANGELOG.md)

# 快速入门

## 下载

使用 git 或者 直接下载本项目到本地。约定项目的根路径为 `${BASE_DIR}`

## 脚本方式

到 `${BASE_DIR}/bin` 下，文件如下：

```
markdown-toc.jar
markdownToc.bat
markdownToc.sh
```

### windows

运行 [markdownToc.bat](bin/markdownToc.bat) 脚本文件，根据提示输入对应的 md 文件信息。

- 属性说明

| 属性 | 说明 | 备注 | 
|:---|:---|:---|
| filePath | md 文件的路径 | 必填。|
| charset | md 文件的编码 | 选填。默认值 `UTF-8` |
 
- 实际日志

```
E:\CODE_GEN\markdown-toc\bin>markdownToc.bat
----------------------
Markdown file path is required, such as: E:\CODE_GEN\markdown-toc\README.md
Markdown file charset is optional, default value is UTF-8
----------------------
Markdown file path: E:\CODE_GEN\markdown-toc\README.md
Markdown file charset:

You input path: E:\CODE_GEN\markdown-toc\README.md
You input charset:
开始生成：【文件路径】E:\CODE_GEN\markdown-toc\README.md, 【文件编码】UTF-8
Markdown toc 生成完成
```

- 效果对比

比原来的文件在文件头新增内容:

```markdown
# Table of Contents

* [markdown-toc](#markdown-toc)
  * [环境依赖](#环境依赖)
* [快速入门](#快速入门)
  * [下载](#下载)
  * [脚本方式](#脚本方式)
    * [windows](#windows)
    * [linux](#linux)
  * [Java 运行方式](#java-运行方式)
```

注意：为了保证多次执行的目录结果保持正确。**请勿修改**目录生成内容，且添加内容在目录之后进行添加。

### linux

- 赋值权限 

```
chmod +x ./markdownToc.sh
```

- 运行

```
./markdownToc.sh
```

运行 [markdownToc.sh](bin/markdownToc.sh) 脚本文件，根据提示输入对应的 md 文件信息。


其他同上。



## Java 运行方式

- 环境依赖 

需要 mvn 环境

- 参考

直接参考 [Main.java](src/main/java/com/github/houbb/markdown/toc/Main.java) 编写测试代码。

或者参考类: [AtxMarkdownTocTest.java](src/test/java/com/github/houbb/markdown/toc/core/impl/AtxMarkdownTocTest.java) 编写测试代码。
