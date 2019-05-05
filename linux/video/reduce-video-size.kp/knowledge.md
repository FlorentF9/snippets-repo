---
title: Reducing the size of a video with ffmpeg
authors:
- FlorentF9
tags:
- linux
- video
- ffmpeg
created_at: 2010-05-05 00:00:00
updated_at: 2019-05-05 19:31:55.627204
tldr: How to compress a video and reduce its size while retaining good quality using
  ffmpeg in command-line.
---

### Cutting a video with `ffmpeg`

The `ffmpeg` command-line tool can be used to compress and reduce the size of a video file. There are at least two ways to achieve it:

1. Changing the bit rate
2. Setting the Constant Rate Factor

#### Changing the bit rate

The bit rate can be set using the `-b` option:

```shell
$ ffmpeg -i input.mp4 -b 1000000 output.mp4
```

To find the adequate bit rate, the formula is:

$\text{bit rate} [byte/s] = \frac{\text{video size} [byte]}{\text{video length} [s]}$

#### Setting the Constant Rate Factor

The CRF (Constant Rate Factor) is a number between 18 and 24 that reduces the bit rate while retaining better quality. The lowest value (18) corresponds to the best quality. It can be set using the `-crf` command-line option:

```shell
$ ffmpeg -i input.mp4 -vcodec libx264 -crf 20 output.mp4
```

For example, using a CRF of 20 reduced a video by a factor of 5 (from 2GB to 400MB).

* https://unix.stackexchange.com/questions/28803/how-can-i-reduce-a-videos-size-with-ffmpeg