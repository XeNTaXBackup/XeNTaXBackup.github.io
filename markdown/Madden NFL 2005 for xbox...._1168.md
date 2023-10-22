## Post #1
- Username: CireZero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 12, 2005 9:56 am
- Post datetime: 2005-04-12T02:12:50+00:00
- Post Title: Madden NFL 2005 for xbox....

Madden 2005 uses a .dat file which was changed from the .big/.mad of the previous year. I'm not sure what you can get out of this bu here are some files...


[http://members.cox.net/kaorusama/DB_TEAMS.DAT](http://members.cox.net/kaorusama/DB_TEAMS.DAT)
## Post #2
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-14T02:53:18+00:00
- Post Title: Madden NFL 2005 for xbox....

are EA games off limit.. i noticed none of the sports games get any replies...
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-14T04:15:13+00:00
- Post Title: Madden NFL 2005 for xbox....

Hey sorry.

I downloaded the file yesterday but havn't had the time to look at it yet - just spent the last 5 hours digging holes in the backyard . I will take a look at it as soon as I can - I don't think it is too different from Madden 2004 though.

Oh, and no, EA Games are not off limits - just usually they are harder to add support for. With the amount of money that EA makes from their games, they can afford to add in things like custom compression algorithms - whereas most other game companies just use pretty standard techniques like ZLib compression.

Thats all - I will hopefully get back to you about this soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-14T06:36:30+00:00
- Post Title: Madden NFL 2005 for xbox....

No, they are not off-limit, of course, as you can see MultiEx Commander support the FIFA series as well, and Actua Soccer etc. 

I have looked at it, and it is possible to write a script for it. I just didn't have the time to look into it in more detail. My daily job as a scientist takes up 110% of my time...  Rest assured, that a script is possible and will be created.
## Post #5
- Username: CireZero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 12, 2005 9:56 am
- Post datetime: 2005-04-14T21:25:30+00:00
- Post Title: Madden NFL 2005 for xbox....

that's awesome thanks guys... i really would to be able to extract the database and figure out how to edit it... it would make everything alot easier..
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-15T10:54:47+00:00
- Post Title: Madden NFL 2005 for xbox....

OK, there are 3 formats that I have identified. Two of the formats are the same as Madden 2004, and there is one new one. The main difference between them is that some have compression directories, and each uses different padding sizes.

```
| Madden 2004 *.dat (Type 1 - No Compression Used) |
+--------------------------------------------------+

// NOTE: Files with length=0 still incur padding, so are actually 64 null bytes

4 - Header (TERF)
4 - Directory Offset (64)
4 - Unknown (83886594)
2 - File Padding Size (64)
2 - Number Of Files
48 - null

4 - Directory Header (DIR1)
4 - Directory Length (including these 2 fields)

// for each file
  4 - File Offset (relative to the start of the FileDataHeader)
  4 - File Length
  
0-63 - null Padding to a multiple of 64 bytes
  
4 - File Data Header (DATA)
4 - File Data Length (including these 3 fields)
56 - null

// for each file
  X - File Data
  0-63 - null Padding to a multiple of 64 bytes


+----------------------------------------------------+
| Madden 2004 *.dat (Type 2 - Some Compression Used) |
+----------------------------------------------------+

// NOTE: Files with length=0 still incur padding, so are actually 4 null bytes

4 - Header (TERF)
4 - Directory Offset (16)
4 - Unknown (83886594)
2 - File Padding Size (4)
2 - Number Of Files

4 - Directory Header (DIR1)
4 - Directory Length (including these 2 fields)

// for each file
  4 - File Offset (relative to the start of the FileDataHeader)
  4 - File Length
  
4 - Compression Header (COMP)
4 - Compression Length (including these 2 fields)

// for each file
  4 - Compression Tag (0=uncompressed, 5=compressed)
  4 - Decompressed Size (0=uncompressed)
  
4 - File Data Header (DATA)
4 - File Data Length (including these 3 fields)
4 - null

// for each file
  X - File Data
  0-3 - null Padding to a multiple of 4 bytes
  
  
+----------------------------------------------------+
| Madden 2005 *.dat (Type 3 - Some Compression Used) |
+----------------------------------------------------+

// NOTE: Files with length=0 still incur padding, so are actually 128 null bytes

4 - Header (TERF)
4 - Directory Offset (128)
4 - Unknown (83886594)
2 - File Padding Size (128)
2 - Number Of Files

4 - Directory Header (DIR1)
4 - Directory Length (including these 2 fields)

// for each file
  4 - File Offset (relative to the start of the FileDataHeader)
  4 - File Length
  
0-127 - Padding to a multiple of 128 bytes
  
4 - Compression Header (COMP)
4 - Compression Length (including these 2 fields)

// for each file
  4 - Compression Tag (0=uncompressed, 5=compressed)
  4 - Decompressed Size (0=uncompressed)
  
0-127 - Padding to a multiple of 128 bytes
  
4 - File Data Header (DATA)
4 - File Data Length (including these 3 fields)
4 - null

// for each file
  X - File Data
  0-127 - null Padding to a multiple of 128 bytes
```


Game Extractor (Full Version) will open the archives, but the compression is unknown so if the files are compressed then you can't view them. Mr Mouse or someone will probably be able to do a script for these formats as well, but they won't be decompressable either.

Sorry mate - thats the best we can do at this point in time.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: CireZero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 12, 2005 9:56 am
- Post datetime: 2005-04-15T21:25:02+00:00
- Post Title: Madden NFL 2005 for xbox....

Can you show what kinda files you got outta those.
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-16T13:48:07+00:00
- Post Title: Madden NFL 2005 for xbox....

Well, the archive you attached had compressed files in it - and *most* of the Madden 2005 archives do use compressed files, which is really bad for us. What is worse is that the compression is custom, thus we cannot determine how to get back to the original file, unless someone knows how to hack apart an exe, or unless someone from EA gives us some insider info 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: CireZero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 12, 2005 9:56 am
- Post datetime: 2005-04-16T14:53:15+00:00
- Post Title: Madden NFL 2005 for xbox....

the funny thing is that i purchased the full version of game extractor and it only opens that one file....  i tried to check out the player picture dat file and it was a no go.... said there was no plugin for it... it's 35megs so i can't load it any where...
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-16T14:57:10+00:00
- Post Title: Madden NFL 2005 for xbox....

Hmm OK, well maybe there are other formats that I am not aware of. I don't have the game, but a few people have sent me files from it and they have worked OK. I will take a look and see if there is anything obvious that is going wrong, otherwise I will need to look at some of the non-working archives.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-18T16:11:05+00:00
- Post Title: Madden NFL 2005 for xbox....

OK, you can give this plugin a go if you want - can't guarentee it will work though. Do the following...

1. go to the Game Extractor directory
2. Make a directory called "plugins"
3. Unzip the file into the plugins/ directory
4. Restart Game Extractor.

Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_DAT_TERF.zip](https://xentaxbackup.github.io/file/181_Plugin_DAT_TERF.zip)
## Post #12
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-24T07:35:43+00:00
- Post Title: Madden NFL 2005 for xbox....

what plugin?
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-24T09:10:00+00:00
- Post Title: Madden NFL 2005 for xbox....

You must be logged in to view files attached to posts. Then you will see the plugin.
