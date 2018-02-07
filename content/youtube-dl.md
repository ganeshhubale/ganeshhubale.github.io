Title: How to install YouTube-DL on Fedora!
Date: 2017-11-04 12:21
Category: Fedora
Tags: general
Slug: install-youtube-dl-on-fedora
Authors: Ganesh Hubale
Summary:

Today, I will introduce you to the youtube-dl. It is a Python based small command-line tool that allows to download videos from [YouTube](https://www.youtube.com/), [Dailymotion](http://www.dailymotion.com/in), [Photobucket](photobucket.com) etc. It is not platform restricted. It is written in Python interpreter. So that it requires Python interpreter to run. It can run on any Unix, Windows or Mac OS X based systems. I came to know about it because, I always need to download random videos. But before this I need to download each of them individually. Here we can create one text file of these video's URLs and can be able to download them all in one hit.

* To install youtube-dl on Fedora.

```
sudo dnf install youtube-dl
```

* To download videos.

```
youtube-dl <url-of-the-video> 
```

* To see the list of available formats of video.

```
youtube-dl --list-formats <url-of-the-video>
```

* To download a perticular file format of video, use -f for format and 43 is for format webm, there are other formats too. 


```
youtube-dl -f 43 <url-of-the-video>
```

* To download a list of videos, need to create text file of links of videos.

```
youtube-dl -a video_links.txt
```

* To more help or to find more options available 

```
youtbe-dl --help
```

Thank you,

