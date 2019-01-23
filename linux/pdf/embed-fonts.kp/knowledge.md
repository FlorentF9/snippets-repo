---
title: Embed fonts in PDF
authors:
- FlorentF9
tags:
- linux
- pdf
- ghostscript
created_at: 2019-01-23 00:00:00
updated_at: 2019-01-23 18:02:12.692838
tldr: Embedding fonts into a PDF file for printing using ghostscript.
---

### Embed fonts in PDF

#### Command line

This post presents how to embed fonts into a PDF file in Linux command-line. This is required for printing, if the fonts are not already embedded and not recognized by the printer.

This Ghostscript command embeds the fonts (if it can find the fonts automatically on the system):

```shell
$ gs -q -dBATCH -dNOPAUSE -sDEVICE=pdfwrite -dPDFSETTINGS=/prepress -sOutputFile=output.pdf input.pdf
```

**Warning**: using the input name as output will erase the input file and result in an empty file!

#### Shell script

To avoid remembering this command, it is very convenient to create a shell script and make it executable (for instance, `/usr/local/bin/pdfembedfonts`). The following script is also available as a gist: https://gist.github.com/FlorentF9/b96b0aaa24f8efc5e63f921d26cb2b92.

```sh
#!/bin/bash
# Embeds fonts in PDF file for printing (replaces existing file)
# Requires: ghostscript
if [ $# -ne 1 ]
then
  echo "Usage example: pdfembedfonts input.pdf"
  exit $E_BADARGS
else
    gs -q -dBATCH -dNOPAUSE -sDEVICE=pdfwrite -dPDFSETTINGS=/prepress -sOutputFile=$1.tmp $1
    mv $1.tmp $1
fi
```