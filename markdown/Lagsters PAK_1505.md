## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-12T15:59:19+00:00
- Post Title: Lagsters PAK

Help   
thx ... Mr.Mouse , Watto ?  
[data000.pak.zip](https://xentaxbackup.github.io/file/436_data000.pak.zip)
## Post #2
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2005-09-12T21:25:45+00:00
- Post Title: Lagsters PAK

```
v32  (4) - Directory Offset

// For each file

     byte  (x) - File data

// For each file/dir (50/54)

     byte (64) - File name (null-terminated)
     v32  (04) - 1=file(compressed) / 2=file(not compressed) / 3=directory

  - if current entry is a file:

     v32  (04) - Decompressed file length
     v32  (04) - Compressed file length
     v32  (04) - Absolute file offset

  - if current entry is a directory:

     byte (12) - null
     v32  (04) - Amount of files/directories in current directory
```


That should be about it ..
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-12T23:07:03+00:00
- Post Title: Lagsters PAK

The description it well and here still a script for MultiEx Commander would be super
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-20T05:50:42+00:00
- Post Title: Lagsters PAK

Sorry mate, I didn't notice this thread on the forums (it didn't show up as being a new post). I have downloaded the file, and will look at it soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-23T06:04:36+00:00
- Post Title: Lagsters PAK

OK these are the initial specs I have - kinda the same as posted a few above - I will look into a plugin or something when I have the time.

```
| Lagsters *.pak |
+----------------+

// Uses ZLib compression

// ARCHIVE HEADER
  5 - Header (FEPAK)
  4 - Directory Offset

// FILE DATA
  // for each file
    X - File Data

// DIRECTORY
  // for each file
    64 - File/Directory Name (null for the first directory)
    4 - Directory/File Identifier (3=directory, 1=file)
  
    if (directory){
      4 - null
      4 - null
      4 - null
      4 - Number Of Files In This Directory
      }
    else if (file){
      4 - Decompressed File Length
      4 - Compressed File Length
      4 - File Offset
      }
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-23T20:18:51+00:00
- Post Title: Lagsters PAK

Okido thx Watto
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-26T07:05:37+00:00
- Post Title: Lagsters PAK

OK, I have attached a Game Extractor plugin for this archive, which I will put in the next update (hopefully within a week) or you can use it now.

The plugin should work if you unzip it into your "GameExtractor/Plugins" directory, or the "GameExtractor/" directory. If not, you can do the following...

1. Unzip the attachment
2. Open GameExtractor.jar in a zip program like WinZip
3. Put the new plugin into the zip
4. Save it (as GameExtractor.jar , NOT GameExtractor.zip)
5. Run Game Extractor.

Good luck - I intend to get another Game Extractor update out soon, but I am still quite busy so my best estimate would be for an update in a weeks time.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_PAK_FEPAK.zip](https://xentaxbackup.github.io/file/447_Plugin_PAK_FEPAK.zip)
