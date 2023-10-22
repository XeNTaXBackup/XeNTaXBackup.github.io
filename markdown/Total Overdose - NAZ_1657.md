## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-02T07:00:42+00:00
- Post Title: Total Overdose - NAZ

Hi guys.. help me   I cut out 2 archives therefore as me it seemed that they all different

Downloading here - 2276083 Bytes
[http://rapidshare.de/files/10238635/Tot ... Z.zip.html](http://rapidshare.de/files/10238635/Total_Overdose_2_Archives_NAZ.zip.html)

Big thanks .. Mike , Watto
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T01:30:33+00:00
- Post Title: Total Overdose - NAZ

Hi mate,

I think the issue with these files was that they didn't actually have a directory, or something like that. I think that they just contained all the file data, and the first file in some of the archives was directory-like, but it wasn;t actually a directory.

This is what I kinda have for one of the files...

```
| Total Overdose 2 *.naz |
+------------------------+

// Only some have this format - others don't seem to have the directory

113 - Junk?
4 - Unknown (212)
4 - Unknown (44512)
4 - null

// for each file
  4 - Unknown (8)
  4 - First Filename Offset (relative to the offset of this field)
  4 - null
  4 - Junk
  10 - null
  4 - Unknown
  2 - null
  4 - Maximum Filename Length (64)
  4 - Junk
  60 - First Filename (null-terminated)
  4 - Rate Value
  4 - Rate Value [*2]
  2 - null
  4 - Unknown (16384)
  6 - null
  4 - Sample Rate (44100)
  4 - Rate Value [*4]
  4 - Channels? (1)
  2 - Unknown (51)
  4 - File Offset?
  2 - null
  4 - Quality? (16)
  4 - Second Filename Length (including null)
  4 - Unknown
  4 - null
  52 - Second Filename (null-terminated)
  
X - File Data
```


But like I said, I don't think it is an actual directory. Why?
1. Not all the *.naz files have them
2. There doesn't seem to be a way to find the directory offset
3. There are no fields for the number of files
4. There are no file offsets or file sizes
5. Every 15ish files, the size of the directory entry changes, perhaps suggesting that they are actually separate directories or something.

Maybe Mr Mouse or others have a better idea about this.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T08:18:12+00:00
- Post Title: Total Overdose - NAZ

Jaeder Naub 1.7.5f rips out the OGG files from this archives
without problems (tested on the full archives) 

...just boasting..., just thought if anyone wanted to rip out the music and
sounds from the files before the archiveparser is ready =o
## Post #4
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-01-03T16:20:18+00:00
- Post Title: Total Overdose - NAZ

you should definitely mirror your excellent Jaeder Naub 1.7.5x to an 100% online place,it worth the use!
## Post #5
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-05-05T13:16:55+00:00
- Post Title: Total Overdose - NAZ

14 years later, i Found this .naz to .zip converter:
[http://www.ctpax-x.org/index.php?goto=f ... 64&lang=en](http://www.ctpax-x.org/index.php?goto=files&show=64&lang=en)
