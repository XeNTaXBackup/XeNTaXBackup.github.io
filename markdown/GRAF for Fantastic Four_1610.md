## Post #1
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-12-10T16:56:35+00:00
- Post Title: GRAF for Fantastic Four

```

    * Format Type : Archive
    * Endian Order : Little Endian


Format Specifications


// FILE DATA
  
   // for each file
  
      byte {X}     - File Data


// FILENAME DIRECTORY
  
   char {4}     - Header (STR )
   uint32 {4}   - Filename Directory Length
    
   // for each file

      char {X}     - Filename
      byte {1}     - Null Filename Terminator 

// DIRECTORY
  
   char {4}     - Header (DIR )
   uint32 {4}   - Directory Length
    
   // for each file

      uint32 {4}   - Compressed Size (if was zero file not compressed)
      uint32 {4}   - File Offset / 2048 (always begins with an offset module 2048)
      uint32 {4}   - Uncompressed Size
      uint32 {4}   - Filename Offset (offset start from Filename Directory Offset + 8)

// ARCHIVE HEADER

    char {4}     - Header (END )
    uint32 {4}   - null
    uint32 {4}   - Filename Directory Offset


NOTE: ZLib Compression used.
      Number of File = Directory Length / 16
```


You can update your database with this GRAF!  
[data_x1.fs.zip](https://xentaxbackup.github.io/file/485_data_x1.fs.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-10T20:15:23+00:00
- Post Title: GRAF for Fantastic Four

Thanks!
## Post #3
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-12-20T22:15:45+00:00
- Post Title: GRAF for Fantastic Four

In refer:
[http://wiki.xentax.com/index.php/Fantastic_4_FS](http://wiki.xentax.com/index.php/Fantastic_4_FS)

```

        uint32 {4}   - Unknown (often null)
        uint32 {4}   - File Offset [*2048]
        uint32 {4}   - File Length
        uint32 {4}   - Filename Offset (relative to the start of the filename directory)

```


Why unknown???
I give you the full graf without unknow!    Unknown is File Compressed Length, if was zero file is not compressed.
If GameExtractor used your script some of files extracted was corrupted, all compressed file, because this script extract more bytes from archive when extract compressed file.
Bye
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-21T06:13:13+00:00
- Post Title: GRAF for Fantastic Four

Uhm, you've got a point there obviously. We have got to have a word with Watto, as he's the one who entered this page in the WIKI I think.  

In any event, in general, if you have better information than the WIKI, feel free to change that in the WIKI ! That's what it's for! Thanks!
## Post #5
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-12-21T09:59:35+00:00
- Post Title: GRAF for Fantastic Four

> In any event, in general, if you have better information than the WIKI, feel free to change that in the WIKI ! That's what it's for! Thanks!

I did not know thanks to it
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-23T01:45:28+00:00
- Post Title: GRAF for Fantastic Four

The specs I wrote on the wiki were, i think, from the exploration of the Fantastic 4 PS2/XBox game and it didn't use any compression - something like that - but like Mr Mouse said, you can just go in to the wiki and edit it yourself  . Thanks for your assistance!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
