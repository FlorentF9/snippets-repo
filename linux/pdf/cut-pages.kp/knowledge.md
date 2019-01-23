---
title: Cut pages from PDF
authors:
- FlorentF9
tags:
- linux
- pdf
- ghostscript
- pdftk
created_at: 2019-01-23 00:00:00
updated_at: 2019-01-23 18:01:40.660118
tldr: Cutting out pages from a PDF file using ghostscript or pdftk.
---

### Cut pages from PDF

This post presents two ways to cut out pages from a PDF file in Linux command-line. In this example, we want to extract pages 9 to 17.

#### Using Ghostscript

```shell
$ gs -dBATCH -dNOPAUSE -sDEVICE=pdfwrite -dFirstPage=9 -dLastPage=17 -sOutputFile=output.pdf input.pdf
```

**Warning**: using the input name as output will erase the input file and result in an empty file!

#### Using pdftk

```shell
$ pdftk input.pdf cat 9-17 output output.pdf
```