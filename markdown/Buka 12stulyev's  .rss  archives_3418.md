## Post #1
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-04-05T12:51:22+00:00
- Post Title: Buka 12stulyev's  .rss  archives

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-05T13:57:52+00:00
- Post Title: Buka 12stulyev's  .rss  archives

do you have another sample? maybe containing textual or image files
## Post #3
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-05-09T01:42:01+00:00
- Post Title: Buka 12stulyev's  .rss  archives

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-09T02:24:29+00:00
- Post Title: Buka 12stulyev's  .rss  archives

Here is some information on the game
website
[http://www.buka.com/int_sales.Our_games ... e__up.aspx](http://www.buka.com/int_sales.Our_games.Current_line__up.aspx)
Game Name: Territory Of Darkness: Dusk 12

can you post the games main exe file on a different host besides rapidshare.
megashare.com is good or filefront anything but rapidshare.

could you also post the smallest archive file.
## Post #5
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-05-09T07:05:31+00:00
- Post Title: Buka 12stulyev's  .rss  archives

@chrrox:

    The real web site is here :
[http://www.saturnplus.com/game/5/](http://www.saturnplus.com/game/5/)

    block0.rar
[http://www.MegaShare.com/875940](http://www.MegaShare.com/875940)
    block2.rar
[http://www.MegaShare.com/875941](http://www.MegaShare.com/875941)
    12chairs.rar--->exe file
[http://www.MegaShare.com/875946](http://www.MegaShare.com/875946)

   Thank you for take a look.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T10:50:28+00:00
- Post Title: Buka 12stulyev's  .rss  archives

well the format is more simple than how it looked:

```
for i = 0 < FILES
    getdstring NAME 0x50
    get OFFSET long
    get SIZE long
    get TYPE long

    log NAME OFFSET SIZE
next i
```

the only doubt remain for the first file you posted because that "Sound\subtitres.SUB" extracted from it seems to contain other data (if you open it you can see various .wav filenames) but seems they are referred to another file because the size values (well I guess they are size values) don't match... mah
## Post #7
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-05-09T11:55:56+00:00
- Post Title: Buka 12stulyev's  .rss  archives

OK.Very thank you.
In the first file i post,the data after wav file name table is the subtitle splited by 0x00 in UTF-16 (russian) i think.

And can you take a look at this  dlg.sub?
[http://www.MegaShare.com/876672](http://www.MegaShare.com/876672)
Can you find how it be compressed?
I can't find anything by offzip.exe.
It is another game's subtitle file by buka.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T15:38:54+00:00
- Post Title: Buka 12stulyev's  .rss  archives

it's a gzip file, open it with 7-zip
