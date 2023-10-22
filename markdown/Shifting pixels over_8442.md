## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-01T00:29:49+00:00
- Post Title: Shifting pixels over

Check out this image:



It's a start button. But it looks like it's shifted over and wrapping around.

How can I deal with this?

I think the format is just

```
int32 width
int32 height
int32 pixel format? (a lot of them are 24)
<pixel data>

```

[buttons.7z](https://xentaxbackup.github.io/file/5127_buttons.7z)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-03-03T06:00:48+00:00
- Post Title: Shifting pixels over

if you skip the blank data (~1024 bytes) your image shifts into view again



start.bmp (11.77 KiB) Viewed 30 times



also, [http://honyaku-subs.ru/forums/viewtopic.php?f=17&t=213](http://honyaku-subs.ru/forums/viewtopic.php?f=17&t=213)
