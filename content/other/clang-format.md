---
title: "clang-format"
date: "2025-03-26"
summary: "clang-format config."
description: ""
toc: false
readTime: true
autonumber: true
math: true
tags: ["clang-format", "config"]
showTags: true
---

### My person clang-format configuration

base on google style

```yaml
---
# 基于Google的代码风格
BasedOnStyle: Google

# 缩进宽度设置为4
IndentWidth: 4
# 访问修饰符缩进设置为-4
AccessModifierOffset: -4

ColumnLimit: 80

# 关闭头文件排序
SortIncludes: Never
IncludeBlocks:   Preserve
InsertNewlineAtEOF: false

TabWidth: 4
UseTab: Never

```


