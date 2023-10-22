## Post #1
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-08-10T14:04:32+00:00
- Post Title: WMA 5.1 console mixer

I need a console application that can mix wma 5.1 to wmv video. Sadly ffmpeg doesn't work propperly, i use 

```
ffmpeg -i CHL_01.wmv -i CHL_01.wma -c copy -map 0:5 -map 0:1 done.wmv
```

and all i get it's wmv video with broken sound, cause it sets format to Extensible ([http://puu.sh/jsJgE/3b0ca9a6e0.png](http://puu.sh/jsJgE/3b0ca9a6e0.png)). So is there any way to mix audio propperly with ffmpeg or another console app? 

Here are sample files
[http://www24.zippyshare.com/v/wkA8yexi/file.html](http://www24.zippyshare.com/v/wkA8yexi/file.html)
