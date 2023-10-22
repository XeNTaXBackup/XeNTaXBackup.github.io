## Post #1
- Username: BMarquis
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Apr 18, 2010 6:13 pm
- Post datetime: 2010-10-15T09:32:20+00:00
- Post Title: Evilzone DPAC Archive (.pac)

It was a long night, so I came about learning how to open the Yukes DPAC Files.

First of all, the main header:

```
long   Offset?          //Always 0x100
long NumDList          //The number of entries this file has
long DListSiz            //The size of the directory list that is being used. Always NumDList*0x10
long DirSize             //The total size of data the directory holds
long NumDListBlk      //The total number of possible directories by multiplying it by 0x800

```


My theory is that either the UNK variable is actually the offset to the Directory Listing by multiplying it by 0x8, or, strange enough, the signature is actually null-terminated and the UNK is actually a 24-byte offset by multiplying it by 0x800.

Next is the directory listing, which, simply put, consists of this

```
short Offset          //The offset of the directory by multiplying it by 0x800.
short size             //The size of the directory by multiplying it by 0x800.

```


Next, is the actual directory, which consist of

```
long NumEntries    // Theory #2

```


This one could be either long or short, and the other 2 bytes mean nothing

Immediately following it is the entry group, which is 8 bytes, and consists of
short EntryNum       //An ID of sorts. usually subsequent starting from 0
uint24_t Offset       //The offset from the beginning of the data where the file is located
uint24_t Size         //The size of the file.

Keep in mind that files are not immediately following the next. There may be zero padding in the case of PACs within PACs
## Post #2
- Username: BMarquis
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Apr 18, 2010 6:13 pm
- Post datetime: 2010-10-18T23:38:25+00:00
- Post Title: Evilzone DPAC Archive (.pac)

[http://www.bmarquis.com/misc/dpacview.zip](http://www.bmarquis.com/misc/dpacview.zip)

Here's an experimental Win32 Console program, allowing you to view the file and extract a file. Right now, you can't go back a level and and you can only extract one file.

This is for testing purposes. I'm going to make a gui-based one as soon as I perfected the kinks, as well as update this one for file format recognition.
## Post #3
- Username: BMarquis
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Apr 18, 2010 6:13 pm
- Post datetime: 2014-11-25T23:34:47+00:00
- Post Title: Evilzone DPAC Archive (.pac)

It's been a while.

[http://s000.tinyupload.com/index.php?fi ... 1950259768](http://s000.tinyupload.com/index.php?file_id=75785172071950259768)

Here is my progress, in the form of a QuickBMS script. I've managed to extract all files in chunks. the script can identify .tim, .emd, .seq, and .vh files. All recognizable files will have the extension of .dat.


Known Issues
- Some files will have the same filename as previously extracted files. That's because the Entry ID is the same inside the folder. I do not know the implications of this, yet.
- The .vh files are shown as .vh files because the .dat file beside it might be .vb files instead of a whole .vab file
- Animation files are not located yet. I assume that the files in the root folder are such, but I do not know what format it is. If you can help, the signature of these particular files are 0x08
