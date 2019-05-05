---
title: Cutting a video with ffmpeg
authors:
- FlorentF9
tags:
- linux
- video
- ffmpeg
created_at: 2010-05-05 00:00:00
updated_at: 2019-05-05 19:30:07.527213
tldr: How to cut a video using ffmpeg in command-line.
---

### Cutting a video with `ffmpeg`

The `ffmpeg` command-line tool can be used to cut out a specific time interval from a video, using start/end timestamps. Here is the signification of the necessary options:

* `-i` specifies the input file
* `-ss` specifies the start timestamp (seeking to the specified timestamp) *[optional]*
* `-t` or `-to` specify respectively a duration or an end timestamp *[optional]*
* `-async` audio sync method, set to 1 to simply sync the start of the audio stream 
* `-strict -2` is necessary for experimental aac codec

```shell
$ ffmpeg -i input.mp4 -ss 00:07:42 -to 00:09:33 -async 1 -strict -2 ouput.mp4
```

**NOTE:** `-ss` can be specified *before* the `-i` option to directly seek to the specified time stamp (faster), but the option `-to` won't work (it will specify a relative duration, behaving the same as `-t`)

* https://stackoverflow.com/questions/18444194/cutting-the-videos-based-on-start-and-end-time-using-ffmpeg