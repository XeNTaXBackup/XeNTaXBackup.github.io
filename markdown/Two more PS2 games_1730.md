## Post #1
- Username: ReMoveIn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 07, 2006 12:34 pm
- Post datetime: 2006-02-14T03:01:34+00:00
- Post Title: Two more PS2 games

Please help with this PS2 games :

[http://www.megaupload.com/?d=AZURSCIH](http://www.megaupload.com/?d=AZURSCIH)  Splinter Cell: Pandora Tomorrow

[http://www.megaupload.com/?d=XKUWRNE8](http://www.megaupload.com/?d=XKUWRNE8) King Arthur

I'm looking music.  

Thanks in advance.
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-02-23T10:47:25+00:00
- Post Title: Two more PS2 games

I have some specs for King Arthur, but havn't been able to do anything with them  ...

```
| King Arthur (PS2) *.rkv |
+-------------------------+

// first filename is empty
// Not sure how to work out the file size/offset, but probably has something
// to do with multiplying one of the fields by some value

4 - Header (RKV2)
4 - Number Of Files
4 - Filename Directory Length
4 - Number Of Files
4 - File Tree Name Directory Length
4 - Hash Directory Offset
4 - Total Directory Length (Length of all directories)
4 - Unknown
4 - Unknown
92 - null Padding to offset 128

X - File Data

// HASH DIRECTORY
  // for each file
    8 - Unknown
    12 - CRC?

// FILENAME DIRECTORY
  // for each file
    X - Filename
    1 - null Filename Terminator

0-11 - null Padding to a multiple of 12 bytes?

// FILES DIRECTORY
  // for each file
    8 - File Length?
    4 - Hash?
    4 - File Offset?

// FILE TREE NAME DIRECTORY
  // for each file
    X - Filename (including full path, starting with "L:\")
    1 - null Filename Terminator

0-11 - null Padding to a multiple of 12 bytes
```


I have done a plugin for Splinter Cell though, it is attached below. To install the plugin in Game Extractor...
1. Unzip the attachment to your computer (it will be *.class files)
2. Open the GameExtractor.jar file in a zip program like WinZip
3. Copy the *.class files into WinZip
4. Save the archive (as GameExtractor.jar, NOT GameExtractor.zip)
5. Restart Game Extractor.

Here are the specs for the splinter cell archive, for those interested...

```
| Splinter Cell: Pandora Tomorrow (PS2) *.img |
+---------------------------------------------+

// Compressed files use ZLib

4 - Archive Size
4 - Total Directory Length (not including padding at the end of the filename directory)
4 - Padding Multiple (2048)
4 - Empty Directory Offset
4 - Filename Directory Offset
4 - First File Offset
8 - null
4 - Unknown Directory Offset
2012 - null Padding to offset 2048

// FILES DIRECTORY
  12 - null
  4 - Unknown (585)
  32 - null
  
  // for each file (48-bytes per entry)
    4 - Filename Offset (relative to the start of the filename directory)
    4 - File ID?
    4 - Parent Folder ID (folder that this file/folder belongs to) [+1]
    4 - Folder ID (0=file, #=folder)
    4 - Compression (0=uncompressed, 1=compressed)
    4 - Entry Type (0=folder, 1=file)
    4 - Compressed File Length
    4 - Decompressed File Length
    4 - File Offset
    4 - Unknown
    2 - Unknown
    2 - Unknown
    4 - Unknown (often null)
    
// EMPTY DIRECTORY
  2400 - null
  
// UNKNOWN DIRECTORY
  X - Unknown
  
// FILENAME DIRECTORY
  // for each file
    X - Filename
    1 - null Filename Terminator
    
// FILE DATA
  // for each file
    if (compressed){
      4 - Unknown
      4 - Unknown
      X - Compressed File Data
      }
    else if (uncompressed){
      X - File Data
      }
    0-2047 - null Padding to a multiple of 2048 bytes
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_IMG_3.zip](https://xentaxbackup.github.io/file/625_Plugin_IMG_3.zip)
## Post #3
- Username: ReMoveIn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 07, 2006 12:34 pm
- Post datetime: 2006-02-24T03:56:19+00:00
- Post Title: Two more PS2 games

Wow. Thank you very much. Yesterday I thought: "They don't even try it". But today... 

Can you look at three more PS2 games, mr. Watoo?

Blade II - [http://www.megaupload.com/?d=RK2T1YYZ](http://www.megaupload.com/?d=RK2T1YYZ) - music
Rocky Legends - [http://www.megaupload.com/?d=RW1RH9H5](http://www.megaupload.com/?d=RW1RH9H5) - all + music
Splinter Cell ~ Chaos Theory - [http://www.megaupload.com/?d=K1QBDBW2](http://www.megaupload.com/?d=K1QBDBW2) - music
Splinter Cell ~ Chaos Theory - [http://www.megaupload.com/?d=DOS1K885](http://www.megaupload.com/?d=DOS1K885) - video



Thanks in advance

P.S. King Arthur is unopenable?
## Post #4
- Username: pablo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 30, 2005 2:07 am
- Post datetime: 2006-02-24T18:03:51+00:00
- Post Title: Two more PS2 games

So is it then possible to extract the unedited music files from the PS2 version of Pandora Tomorrow?
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-03-08T21:11:50+00:00
- Post Title: Two more PS2 games

Yes, King Arthur is unopenable - I havn't been able to complete those specs.

I am downloading the other files now and will look at them soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-10T03:06:58+00:00
- Post Title: Two more PS2 games

About this music and sounds:
All archives contains Sony VAG sound except Splinter Cell 
which had some format ive never seen before.

Rocky archive contains some TIM2 images aswell.
The video UMD was funny, as i didnt recognized much,
only an MPEG-1 marker, but that probably meens nothing.
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-03-16T20:51:58+00:00
- Post Title: Two more PS2 games

I have attached plugins for Blade 2 and Rocky Legends. As mentioned in the post above, there are a lot of VAG and TIM2 files in there that you should be able to view with an appropriate tool (i think there are some on the net that do it).

To use the plugins...

1. Unzip the attachment to your computer (it will be *.class files)
2. Open the GameExtractor.jar file in a zip program like WinZip
3. Copy the *.class files into WinZip
4. Save the archive (as GameExtractor.jar, NOT GameExtractor.zip)
5. Restart Game Extractor.

Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[plugins.zip](https://xentaxbackup.github.io/file/654_plugins.zip)
