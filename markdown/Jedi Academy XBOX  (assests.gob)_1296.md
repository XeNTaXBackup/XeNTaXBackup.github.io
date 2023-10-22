## Post #1
- Username: pureimpure
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 01, 2005 6:53 am
- Post datetime: 2005-05-31T22:54:57+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

Hi  , the file and folders are pretty much exactly like the PC version instead of pk3 though they are .Gob 

Cant open these with any program though . if you need files for testing please feel free to ask . Ive been dying to edit this game . Thanks
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-06-01T06:51:47+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

If you could supply us with some gob archives, it would definately help. We will then have a look at it to see what can be done to support the game.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-01T07:16:32+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

And if they are too big, get the Filecutter tool to cut the first and last part of a gob file to send it to us. 

Click the link in my signature below for the tool. 

Also, please note down the exact size of the gob file you use it on. We may need that.
## Post #4
- Username: pureimpure
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 01, 2005 6:53 am
- Post datetime: 2005-06-04T09:25:47+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-06-04T13:12:41+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

Ok, I downloaded the smaller file and will look at that - I won't be downloading the bigger file though because thats just too big for me to download over 56k dialup.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-04T13:41:43+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

I haven't got the gob file yet, dl it. But it seems the smaller file is an index of some sort. I think of the gob.
## Post #7
- Username: pureimpure
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 01, 2005 6:53 am
- Post datetime: 2005-06-04T18:43:01+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-06-05T04:54:16+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

Thanks - I will download the cut file and take a look.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: pureimpure
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 01, 2005 6:53 am
- Post datetime: 2005-06-07T00:27:52+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

did you guys get the files off of there ??

I took some down . 

also any luck with them ?
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-06-07T06:36:42+00:00
- Post Title: Jedi Academy XBOX  (assests.gob)

This is what I have so far...

```
| Star Wars Jedi Academy (XBox) *.gfc |
+-------------------------------------+

// NOTE: BIG ENDIAN FORMATTING

// The structure of the end loop contains junk data to pad the filename
// The junk data is unusual though because it contains many instances of
// the letters 'JA' which convert to 'PK' when xor with 26 and 10.
// Note that 26 and 10 only differ in 1 bit value
// This could be particularly important because the PC version of this game
// uses generic ZIP archives for the files.

4 - Unknown
4 - Unknown
4 - Number Of Files In Loop 1,2
4 - Number Of Files In Loop 3,4

// for each file in Loop 1,2
  4 - File Size
  4 - File Offset (needs some adjustment?)
  4 - Unknown
  
// for each file in Loop 1,2
  4 - Unknown
  
// for each file in Loop 3,4
  4 - Hash?
  4 - File Size?
  4 - File ID (incremental, starting at 14620)

// for each file in Loop 3,4
  96 - Filename (null) (filled with junk)
  8 - Checksum?
  
  
+-------------------------------------+
| Star Wars Jedi Academy (XBox) *.gob |
+-------------------------------------+

// Compressed files use ZLib compression

// for each file
  4 - File Start Header (STBL)
  1 - Compression tag (z=Compressed, 0=uncompressed) // note the 0 is the number 'zero'
  X - File Data
  4 - File End Header (ENBL)
  0-2047 - null Padding to a multiple of 2048 bytes
```


I havn't yet found a way to link the 2 files together, if they do indeed point to each other. I will try to make a plugin to read these files so I can hopefully make any adjustments.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
