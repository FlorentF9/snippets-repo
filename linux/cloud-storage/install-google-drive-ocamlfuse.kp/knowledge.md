---
title: Install google-drive-ocamlfuse on Ubuntu Linux
authors:
- FlorentF9
tags:
- linux
- ubuntu
- google-drive
created_at: 2019-03-09 00:00:00
updated_at: 2019-03-09 19:22:08.162854
tldr: Installing google-drive-ocamlfuse on Ubuntu to mount Google Drive filesystem.
---

### Installing google-drive-ocamlfuse on Ubuntu Linux

#### Installation

On Ubuntu, add PPA repository and install package:

```shell
$ sudo add-apt-repository ppa:alessandro-strada/ppa
$ sudo apt update
$ sudo apt install google-drive-ocamlfuse 
```

#### Usage

First, authenticate using the Google account, by running `$ google-drive-ocamlfuse`. This will open a browser and the authentication page.

Then, create the directory where the Google Drive will be mounted:

```shell
$ mkdir ~/gdrive
$ google-drive-ocamlfuse ~/gdrive
```

To mount it automatically on start-up, add the last command line to the start-up programs.

### References

* https://doc.ubuntu-fr.org/google_drive#google-drive-ocamlfuse