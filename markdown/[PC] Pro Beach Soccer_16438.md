## Post #1
- Username: CrispX
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Feb 24, 2016 2:55 am
- Post datetime: 2017-06-22T16:59:40+00:00
- Post Title: [PC] Pro Beach Soccer

[https://www.youtube.com/watch?v=w7Y-Wl-QwTk](https://www.youtube.com/watch?v=w7Y-Wl-QwTk)

Pro Beach Soccer the only PC Game ever made have one easy file called WadPc.wad and i need a tool was able to extract/import in to the file different textures and maybe as well player names, if they are textured even better.
I'm going to send the .wad file.

[https://drive.google.com/open?id=0B_SB6 ... 2NtY3MxRGc](https://drive.google.com/open?id=0B_SB6dqSCGW8eG5aZ2NtY3MxRGc)

Inside of the game as i can see it have this folders.
Medias folder have 4 easy .mpg files we can change it.
Comments and Music are .rws files. 
If you need those ones too i will send.

It will be amazing if this happens.
## Post #2
- Username: CrispX
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Feb 24, 2016 2:55 am
- Post datetime: 2017-07-07T19:36:41+00:00
- Post Title: [PC] Pro Beach Soccer

No help?
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2017-07-15T10:57:17+00:00
- Post Title: [PC] Pro Beach Soccer

This is the format I have so far - still trying to work out how to build the directory tree. ie. the filenames and directory names are all stored in the one directory - there must be something in the "UNKNOWN DIRECTORY" that links the files to their filenames, and probably also therefore linking them to a directory name?

```
| Pro Beach Soccer *.wad |
+------------------------+

// Uses ZLib Compression
// Files are listed in the directory in Reverse Order (ie the first entry in the directory is the last file in the archive)

// ARCHIVE HEADER
  8 - Header ("PAM_PAK" + (byte)0)
  2 - Number Of Files
  2 - Unknown
  4 - Filename Directory Length
  4 - File Data Offset

// FILES DIRECTORY
  // for each file
    4 - File Length (Compressed)
    4 - File Offset
    
// UNKNOWN DIRECTORY
  // for each file
    2 - Unknown
    2 - Unknown
    2 - Unknown
    2 - Unknown (52685)

// FILENAME DIRECTORY
  // for each file and directory
    X - Filename/Directory Name
    1 - null Name Terminator
  
  1 - null End of Filename Directory terminator

// FILE DATA
  // for each file
    8 - File Header ("PAM-ZLB" + (byte)0)
    4 - Compression Flag? (1)
    4 - Decompressed Length?
    4 - null
    4 - Decompressed Length?
    4 - Header Length (32)
    4 - Hash?
    X - File Data (ZLib Compression)
    0-3 - null Padding to a multiple of 4 bytes (This field does not exist for the Last file in the archive!)
```


Happy for someone to convert this to a BMS if they feel the desire
## Post #4
- Username: CrispX
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Feb 24, 2016 2:55 am
- Post datetime: 2017-07-17T22:34:23+00:00
- Post Title: [PC] Pro Beach Soccer

Thanks.
I do not know. But you can try to get a copy of this online and install it.  
If someone converts to .bms will be great for everyone. 
This game deserves modding whatever the music sounds being boring we can change it all.
## Post #5
- Username: CrispX
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Feb 24, 2016 2:55 am
- Post datetime: 2021-07-14T11:03:55+00:00
- Post Title: [PC] Pro Beach Soccer

friendsofwatto - Still any clues about this?   
Strage how DOOM tools can´t read any texture, even dragon unpacker.
## Post #6
- Username: CrispX
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-20T19:21:34+00:00
- Post Title: [PC] Pro Beach Soccer

Try this script [https://aluigi.altervista.org/bms/pro_beach_soccer.bms](https://aluigi.altervista.org/bms/pro_beach_soccer.bms)
It can unpack data from WadPc.wad file without any issues.

Also, Game Extractor is able to unpack it with proper filenames [https://i.imgur.com/0vpI3g7.png](https://i.imgur.com/0vpI3g7.png)
## Post #7
- Username: CrispX
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Feb 24, 2016 2:55 am
- Post datetime: 2021-07-21T11:52:15+00:00
- Post Title: [PC] Pro Beach Soccer

> Reply from ikskoks ↑Wed Jul 21, 2021 3:21 am at Wed Jul 21, 2021 3:21 am
>
> 
Try this script https://aluigi.altervista.org/bms/pro_beach_soccer.bms
It can unpack data from WadPc.wad file without any issues.

Also, Game Extractor is able to unpack it with proper filenames https://i.imgur.com/0vpI3g7.png

Thanks ikskoks and sorry for the private rep. but can you tell me if there is a nother script to create a new WadPc.wad to change the game textures? Thanks!
## Post #8
- Username: CrispX
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-21T13:18:31+00:00
- Post Title: [PC] Pro Beach Soccer

As far as I know there are no other scripts, so you could try use reimport mode in quickbms with the script mentioned above, but it is not always working properly.

There is also a possibility of creating custom tools for that (for example in Python), but that requires some programming knowledge.
For start, it would be good to see Game Extractor's code as it is handling filenames for Pro Beach Soccer pretty good.


Also, some of the files are compressed with ZLIB, so if you're lucky you could try to use reimport mode in offzip.
## Post #9
- Username: CrispX
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Feb 24, 2016 2:55 am
- Post datetime: 2021-07-22T10:40:43+00:00
- Post Title: [PC] Pro Beach Soccer

> Reply from ikskoks ↑Wed Jul 21, 2021 9:18 pm at Wed Jul 21, 2021 9:18 pm
>
> 
As far as I know there are no other scripts, so you could try use reimport mode in quickbms with the script mentioned above, but it is not always working properly.

There is also a possibility of creating custom tools for that (for example in Python), but that requires some programming knowledge.
For start, it would be good to see Game Extractor's code as it is handling filenames for Pro Beach Soccer pretty good.


Also, some of the files are compressed with ZLIB, so if you're lucky you could try to use reimport mode in offzip.

Any tutorial how to do it?
## Post #10
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-22T10:47:39+00:00
- Post Title: [PC] Pro Beach Soccer

If you want a good source of reverse engineering knowledge,
you can choose something from this topic [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

But if you only want to learn how to use quickbms or offzip,
you can google something like "how to use quickbms" and you'll get a lot of youtube tutorials for that.
Check also documentation for quickbms [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
