## Post #1
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-03T01:44:17+00:00
- Post Title: Help with a .pict File for playboy game

Hello everyone.   I Hope this is the right place for this question.
I just purchased the Game Extractor 1.52 to try and work with the Xbox playboy game.  I was able to open the .cam to find the file I wanted JZ13.  But instead of a tga file I find a .PICT file. I extracted the file and I was hoping that someone could help me find out what kind if file it is and how to open it.   Thanks
[JZ13.rar](https://xentaxbackup.github.io/file/322_JZ13.rar)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-03T12:27:08+00:00
- Post Title: Help with a .pict File for playboy game

Hi mate,

Thanks for purchasing Game Extractor hey  . We will all take a look at the file you posted to see if we can determine the structure. Mr Mouse will probably be the best at this - he usually gets the images every time. I, on the other hand, have hardily touched images so I don't know how much help I can be.

Thanks mate, we will let you know whether we have any success.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-04T14:01:03+00:00
- Post Title: Help with a .pict File for playboy game

OK well this is what I think the file looks like...

```
| Playboy: The Mansion *.pict |
+-----------------------------+

// Header (22 bytes)
  4 - Version (1)
  2 - Number Of Colors? (256)
  4 - Unknown (1)
  4 - Unknown (8193)
  2 - null
  2 - Unknown (512)
  2 - Number Of Colors? (256)
  2 - Color Depth? (8)

// Palette (256 colors)
  // for each color
    1 - Blue
    1 - Green
    1 - Blue
    1 - Alpha
  
// Image Data
  // for each pixel
    1 - Palette Index
```


Still need to examine it a bit more though, but it should hopefully be an easy one to write a converter for.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-04T14:22:00+00:00
- Post Title: Help with a .pict File for playboy game

Thanks again.  I think a donation to your favorite charity is in order
## Post #5
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-10T16:36:18+00:00
- Post Title: Help with a .pict File for playboy game

I have been looking at the File and it looks like the header is missing.  I am not sure.   I have tried everthing I know but I can;t seem to get it.  Can Anyone help me please
## Post #6
- Username: reznov
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-10T21:13:09+00:00
- Post Title: Help with a .pict File for playboy game

PICT2BMP

Here's a converter I wrote for you guys in need of conversion. 

Actually, Watto was a bit off, the second value of 256 and the 'unknown' 512 are height and width of the picture. 512x256 = image size. 

Check below for the program, a screenshot of it and the picture you attached to this thread.  A bra!
[PICT2BMP.zip](https://xentaxbackup.github.io/file/347_PICT2BMP.zip)

[pict2bmp.jpg](https://xentaxbackup.github.io/file/346_pict2bmp.jpg)

[512.jpg](https://xentaxbackup.github.io/file/345_512.jpg)
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-11T01:33:53+00:00
- Post Title: Help with a .pict File for playboy game

Excellent work Mr Mouse! At least I was partially there, which is impressive for me cause I usually can't do images or anything at all. Great work on the program too!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-11T10:55:31+00:00
- Post Title: Help with a .pict File for playboy game

I have investigated the .CAM files, and created a script for MultiEx Commander. Please read 

[viewtopic.php?p=9801#9801](http://forum.xentax.com/viewtopic.php?p=9801#9801)
## Post #9
- Username: DrPepper
- Rank: VIP member
- Number of posts: 9
- Joined date: Sun Jul 03, 2005 9:31 am
- Post datetime: 2005-07-11T22:05:29+00:00
- Post Title: Help with a .pict File for playboy game

PICT to BMP works Great.   Thanks for your help.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-12T08:02:04+00:00
- Post Title: Help with a .pict File for playboy game

No problem. The script I created for MultiEx Commander should enable you to replace (import) files as well in the .CAM archives.
