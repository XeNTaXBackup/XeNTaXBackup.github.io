## Post #1
- Username: stephanehl
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 20, 2008 2:25 am
- Post datetime: 2012-07-10T15:13:38+00:00
- Post Title: How to rip images from psx games.

Dear,

Please anyone know how to rip images from SD Gundam GGeneration series and super robot wars series on psx?

Please i really need your help.

Any help.

Best Regards,
stephanehl
## Post #2
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2012-07-10T16:08:43+00:00
- Post Title: How to rip images from psx games.

.arc files - Super Robot Wars NEO for Wii - [viewtopic.php?f=21&t=5261&p=44096&hilit ... bot#p44096](http://forum.xentax.com/viewtopic.php?f=21&t=5261&p=44096&hilit=super+robot#p44096)

It's a good idea to use the search on this website
## Post #3
- Username: stephanehl
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 20, 2008 2:25 am
- Post datetime: 2012-07-10T16:15:42+00:00
- Post Title: How to rip images from psx games.

Sorry, i'm not interest with wii games but only psx games only...

For ps 2, no need, i already have them...
## Post #4
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2012-07-11T00:51:10+00:00
- Post Title: How to rip images from psx games.

If its the same game who cares what systems it's on 
But if you are putting the modified files back in I understand... 
Did you search the Header of the file then see if there was a BMS script for it?
## Post #5
- Username: stephanehl
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 20, 2008 2:25 am
- Post datetime: 2012-07-11T15:17:49+00:00
- Post Title: How to rip images from psx games.

Here is the link

```
http://bitshare.com/files/52awjfhx/SD-Gundam-GGeneration-FIF_DATA.rar.html
```


I have send you the link for the files so that if anyone can help me to decompress the .bim for psx games.

Thank you for all.
## Post #6
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2012-07-13T08:23:43+00:00
- Post Title: How to rip images from psx games.

I took a look for you the DATA.BIN file uses a PKD file header, took a quick look through my bms scripts some googling and a few others sites no luck... sorry man
I'm just a noob tho maybe someone with more experiance can help you.
## Post #7
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2012-09-04T06:48:38+00:00
- Post Title: How to rip images from psx games.

get PSXVRAM > get ePSXe > play the game > wait until the image you need is on the screen > make a savestate > use a gzip unpacker like 7zip on the savestate > open the save state in PSXVRAM and all the textures on the screen at the time should be present in whatever format the PSX loads them in memory...

Otherwise, try running timviewer on the disc... failing that, run whatever file you suspect of having an image you want, through GGD and see if there's an image in it.

Those are my top most reliable ways of finding images, that work on more than one game. As for the game you specified... I've never heard of it, and thus can't say anything more specific.
