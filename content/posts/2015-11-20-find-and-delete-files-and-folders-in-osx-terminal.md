---
layout: post
title: "Find and delete files and folders in OSX terminal"
date: 2015-11-20T10:54:00+00:00
tags:
- osx
- terminal
- find
- delete
- files
- folders
---

Finding and deleting files and folders in OSX is simple. Open your terminal. In order to just find your files/folders (__non destructive__):

For files:

```bash
find . -name "Icon?" -type f
```

For folders:

```bash
find . -name "Icon?" -type d
```

For files and folders:

```bash
find . -name "Icon?" -type f -o -name "Icon?" -type d
```

In order to delete them, just add `-delete` operator to the end (__DESTRUCTIVE__):

For files:

```bash
find . -name "Icon?" -type f -delete
```

For folders (although you may get a warning message saying 'No such file or directory'):

```bash
find . -name "Icon?" -type d -exec rm -rf {} \;
```

The `?` symbol after the filename is a wildcard for a single character. To enable more characters, use `*` instead.
