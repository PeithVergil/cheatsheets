youtube-dl
==========


Installation
--------------------------------------------------
`pip install youtube_dl`


Show supported sites
--------------------------------------------------
`youtube-dl --extractor-descriptions`


Downloading a video
--------------------------------------------------

A basic example of downloading a video:

`youtube-dl "https://www.youtube.com/watch?v=xzCEdSKMkdU"`

Specify a video format using the `-f, --format FORMAT` option:

```bash
youtube-dl -f mp4 "https://www.youtube.com/watch?v=xzCEdSKMkdU"
```

Use the `-F` option to list the available formats:

```bash
youtube-dl -F "https://www.youtube.com/watch?v=xzCEdSKMkdU"
```