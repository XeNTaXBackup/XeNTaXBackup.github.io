## Post #1
- Username: ReMoveIn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 07, 2006 12:34 pm
- Post datetime: 2006-01-07T05:14:18+00:00
- Post Title: Please help with 3 PS2 games.

Hi, mr. Watto. Please help. This so important for me.

Timesplitters: Future Perfect - [http://www.megaupload.com/?d=BKV3R8BB](http://www.megaupload.com/?d=BKV3R8BB)
Gladius - [http://www.megaupload.com/?d=QPXN2MCN](http://www.megaupload.com/?d=QPXN2MCN)
Wrath Unleashed - [http://www.megaupload.com/?d=3S5OBOEL](http://www.megaupload.com/?d=3S5OBOEL)

All archives contains music.

Thanks in advance.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-07T06:53:35+00:00
- Post Title: Please help with 3 PS2 games.

Downloaded, will take a look at it.
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-08T09:27:10+00:00
- Post Title: Please help with 3 PS2 games.

Hi mate,

I will take a look at this soon too, but I start my new job tomorrow so I don't know how much time I will be devoting to GE from now on - we will just have to wait and see.

Mr Mouse: One of these formats is already on the wiki for XBox, so it should probably be similar... [http://wiki.xentax.com/index.php/Time_S ... re_Perfect](http://wiki.xentax.com/index.php/Time_Splitters_Future_Perfect)

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-08T16:20:45+00:00
- Post Title: Please help with 3 PS2 games.

[viewtopic.php?t=1239&highlight=p5ck](http://forum.xentax.com/viewtopic.php?t=1239&highlight=p5ck)

looks like this one....
## Post #5
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2006-01-08T17:06:23+00:00
- Post Title: Please help with 3 PS2 games.

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: ReMoveIn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 07, 2006 12:34 pm
- Post datetime: 2006-01-11T18:02:08+00:00
- Post Title: Please help with 3 PS2 games.

Any progress?  [img][http://smilies.sofrayt.com/^/aiw/dont-know.gif](http://smilies.sofrayt.com/%5E/aiw/dont-know.gif)[/img]
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-15T10:41:35+00:00
- Post Title: Please help with 3 PS2 games.

Hi mate,

Yeah sorry, I have started full time work this week, so consequently I hadn't worked on file formats during the week.

I have looked at the archives now, and I have determined these formats...

```
| Gladius (PS2) *.bec |
+---------------------+

// Some file entries are listed more than once, with the same offset and length,
// so you need to remove all duplicates.

4 - Header ( ceb)
2 - Version (3)
2 - Padding Multiple (2048)
4 - Number Of Files
4 - null

// for each file
  4 - Hash?
  4 - File Offset
  4 - Unknown (0/2) (BIG)
  4 - File Length
  
0-2047 - null Padding to a multiple of 2048 bytes

// for each file
  X - File Data
  0-2047 - null Padding to a multiple of 2048 bytes
```


```
| TimeSplitters Future Perfect (PS2) *.pak |
+------------------------------------------+
  
4 - Header (P5CK)
4 - Unknown
4 - Directory Length
2036 - null Padding to offset 2048
  
// FILE DATA
  // for each file
    X - File Data
    0-2047 - null Padding to a multiple of 2048 bytes
  
// DIRECTORY
  // for each file
    4 - Hash?
    4 - File Offset
    4 - File Length
    4 - null
```


I have written Game Extractor plugins for these games - I was unable to do anything with the other game 

Attached is the plugins. You should hopefully be able to unzip them straight into the "plugins/" directory. If GE doesn't recognise them, then do the following...

1. Unzip the attachment to your computer.
2. Open GameExtractor.jar in a zip program like WinZip
3. Copy the unzipped attachment into WinZip (the Plugin_*.class files)
4. Save the archive (as GameExtractor.jar, NOT GameExtractor.zip)
5. Restart Game Extractor.

If all else fails, you can always wait until the next update 

Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugins.zip](https://xentaxbackup.github.io/file/582_Plugins.zip)
## Post #8
- Username: ReMoveIn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 07, 2006 12:34 pm
- Post datetime: 2006-02-12T23:35:38+00:00
- Post Title: Please help with 3 PS2 games.

OOO. Thank you very much. All worked.
## Post #9
- Username: blahblah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 05, 2012 10:38 am
- Post datetime: 2012-03-05T12:38:40+00:00
- Post Title: Please help with 3 PS2 games.

What's the best approach for extracting the contents from the Gladius .bec music file? After using GE with the .bec archive, I get a listing of files with unknown description. Upon inspecting their contents, they don't appear to be a valid audio file. Any insight on this would be well appreciated!
