## Post #1
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-04-29T21:50:57+00:00
- Post Title: WWII:Panzer Claws II

Hello! Can you look on this file

Thanks
## Post #2
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-04-29T22:33:46+00:00
- Post Title: WWII:Panzer Claws II

dont understand why i cant upload files.I sent files 1Mb size. And i see 0kb
in my message...
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-30T02:48:02+00:00
- Post Title: WWII:Panzer Claws II

Not sure why this is hapenning. You can email it to us though as it is only a small file.

My email is [watto@watto.org](mailto:watto@watto.org) and Mr Mouse is at 

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-04-30T15:49:16+00:00
- Post Title: WWII:Panzer Claws II

I sent the file to you and Mr.Mouse on email
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-01T14:30:55+00:00
- Post Title: WWII:Panzer Claws II

Hi mate,

Thanks for sending the files, but I couldn't find anything out from it. All I can tell is that it probably does use ZLib compression for some of it.

Are there any other files with the same name, such as Music.hdr or Music.fat? It will have the same name as the archive, but a different extension. It will probably be only really small, like <20kbs.

If you can find one of these files, send it to us and we might be able to work it out.

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-05-01T21:30:06+00:00
- Post Title: WWII:Panzer Claws II

Hi WATTO!
I sent more files to you .I don't know it will help.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-02T07:51:15+00:00
- Post Title: WWII:Panzer Claws II

I believe the header parts are also compressed. 

When I unzip a part of the header, I see the sign WD in the new part. That would fit the music.wd extension. Will have a closer look.
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-02T09:10:22+00:00
- Post Title: WWII:Panzer Claws II

Hi guys,

This is all I can tell from the file so far...

```
X - File Data
X - Compressed/encrypted Directory
4 - Length Of Directory (not including this field)
```


There is definately a directory at the end, but I cannot read it. I thought it was ZLib compressed since it starts with the letter "x" but my ZLib decompressor doesn't like it. Possibly the developers put the "x" all through the archive to throw us off the scent?

Also, I doubt the archives use ZLib for the compression of files, as some of the archives you sent me have plain text in them.

Thats all I've got - I don't think I can get any more than that 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-23T20:30:07+00:00
- Post Title: WWII:Panzer Claws II

I found  "easter egg" in Game Extractor! I decided to check up ".wd "archive from this game (which was not supported - [http://wiki.xentax.com/index.php/WWII_-_Panzer_Claws_2](http://wiki.xentax.com/index.php/WWII_-_Panzer_Claws_2) ) again with Game Extractor and miracle happens  - archive has been opened!
## Post #10
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-23T21:15:03+00:00
- Post Title: WWII:Panzer Claws II

2dimi - Page updated
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T05:35:24+00:00
- Post Title: WWII:Panzer Claws II

Hmm ok, I will have to look into why this works - I am very surprised that it does. Thanks for picking it up, will try to work out why, and will update if necessary.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
