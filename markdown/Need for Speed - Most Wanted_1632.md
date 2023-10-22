## Post #1
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-12-21T23:40:39+00:00
- Post Title: Need for Speed - Most Wanted

I wonder, if it's possible to open up Need for Speed Most Wanted BIN-files

These are archives for the need for speed textures (in the example, it's a vinyls-archive).

An example can be downloaded here:
[http://members.chello.nl/~g.berends1/VINYLS.BIN](http://members.chello.nl/~g.berends1/VINYLS.BIN)

Demo can be downloaded here:
[ftp://ftp.planet.nl/pub/planet/games/wi ... mwdemo.exe](ftp://ftp.planet.nl/pub/planet/games/win95/nfsmwdemo.exe)

Good luck and thanks in advance!
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-22T05:54:00+00:00
- Post Title: Need for Speed - Most Wanted

I saw where the BinTex v0.4 it is called. try by it... This program extracting textures in DDS format
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-23T02:02:35+00:00
- Post Title: Need for Speed - Most Wanted

Hi there,

I will be looking at this game soon - my brother bought it but I havn't had the chance to examine any of the files yet - will look soon and let you know if I have any success.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-28T10:33:46+00:00
- Post Title: Need for Speed - Most Wanted

The plugin for this game is in the latest Game Extractor - [http://www.watto.org/extract/download.html](http://www.watto.org/extract/download.html)

Have Fun - let me know if there are any problems.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: bubblepuzzle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 01, 2006 12:49 am
- Post datetime: 2005-12-31T17:12:32+00:00
- Post Title: Need for Speed - Most Wanted

"I wonder, if it's possible to open up Need for Speed Most Wanted BIN-files "

Please let me know about this game too.
[http://www.filetoad.com/bubblepuzzle.htm](http://www.filetoad.com/bubblepuzzle.htm)
## Post #6
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2005-12-31T17:27:11+00:00
- Post Title: Need for Speed - Most Wanted

> Reply from bubblepuzzle
>
> "I wonder, if it's possible to open up Need for Speed Most Wanted BIN-files "

Please let me know about this game too.
http://www.filetoad.com/bubblepuzzle.htm
 ban him
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-01T13:00:44+00:00
- Post Title: Need for Speed - Most Wanted

```
Get VarType Long 0 ;
Get RemainingSize Long 0 ;
Get U1 Long 0 ;
Get RelOff1 Long 0 ;
SavePos COff 0 ;
Math COff += RelOff1 ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get ResInfoSize Long 0 ;
Get VarType Long 0 ;
Get HeaderSize Long 0 ;
SavePos COff 0 ;
Get U2 Long 0 ;
GetDString BINName 28 0 ;
GetDString OriName 64 0 ;
Set FP String . ;
Get OriSize Long 0 ;
Math COff += HeaderSize ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get TableSize Long 0 ;
SavePos COff 0 ;
Math COff += TableSize ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get ResInfoSize Long 0 ;
Set FileNum Long ResInfoSize ;
Math FileNum /= 24 ;
For T = 1 To FileNum ;
Get VarType Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get UCS Long 0 ;
Get U3 Long 0 ;
Get U4 Long 0 ;
Set Name String OriName ;
String Name += FP ;
String Name += T ;
Log Name FO FS FOO FSO ;
Next T ;

```


Replacement allowed. Don't know if the game is cool with that though.

The script will also create filenames for you based on information about the original .tpk files that were used to create the bin files (probably). The info is in there.  The specs at the WIKI are not correct in this respect.
[bin.zip](https://xentaxbackup.github.io/file/531_bin.zip)
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-01T22:52:01+00:00
- Post Title: Need for Speed - Most Wanted

Mr.Mouse in the game besides BIN it is file there is still and BUN and LZC files... look their.... BUN files are very similar by size with BIN....

This BUN file
[http://rapidshare.de/files/10224422/InG ... e.zip.html](http://rapidshare.de/files/10224422/InGameB_BUN_File.zip.html)

This LZC file
[http://rapidshare.de/files/10224459/InG ... e.zip.html](http://rapidshare.de/files/10224459/InGameB_LZC_File.zip.html)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T00:03:45+00:00
- Post Title: Need for Speed - Most Wanted

Yes, it also works with BUN files. Haven't tried the other yet, but if you say so, I'll assume those also work!
## Post #10
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-02T00:33:45+00:00
- Post Title: Need for Speed - Most Wanted

This is what came out with discovery BUN of the file ... Screenshot attached.....   

On some BIN files is by the way obtained precisely just as with BUN 
[nfsmw_bun.PNG](https://xentaxbackup.github.io/file/538_nfsmw_bun.PNG)
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T06:54:46+00:00
- Post Title: Need for Speed - Most Wanted

Allright, I'll take a look at it. Could you attach that BUN file ?
## Post #12
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-02T07:04:59+00:00
- Post Title: Need for Speed - Most Wanted

Mr.Mouse I longer I can attach files therefore in me already the limit

```
Sorry, you have reached your maximum Upload Quota Limit of 5 MB
```
  

Download here
[http://rapidshare.de/files/10238700/DEM ... G.ZIP.html](http://rapidshare.de/files/10238700/DEMO_MARKETING.ZIP.html)
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T08:40:43+00:00
- Post Title: Need for Speed - Most Wanted

Ok, so this BUN file is not the same as a BIN file. It is totally different. So, not all BUN files are like BIN files. THis should be noted at the WIKI.
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T00:25:09+00:00
- Post Title: Need for Speed - Most Wanted

Mr Mouse,

All the BUN files I have looked at follow the following format

```
| Need For Speed: Most Wanted *.BuN |
+-----------------------------------+

// Note: There are padding file entries of varying sizes, including length=0
// Continue reading until the end of the archive has been reached.

// for each file
  4 - File Type ID?
  4 - File Length
  X - File Data
```


I havn't found any at the moment that conflict this, and I have not found any to have the same format as the BIN archives, which are significantly different:

```
| Need For Speed: Most Wanted *.bin |
+-----------------------------------+

// ARCHIVE HEADER
  2 - null
  2 - Unknown
  4 - Archive Length [+8]
  4 - null
  4 - Number Of Nulls (48)
  48 - null
  2 - null
  2 - Unknown
  4 - Directory Length?
  2 - Number Of Directories (1)
  2 - Unknown

  // for each directory
    4 - Directory Offset [+80]
    4 - Directory Name Length (not including nulls)
    28 - Directory Name (null terminated)
    64 - Filename
    4 - Unknown
    24 - null
  
// DIRECTORIES
  // for each directory
    2 - Unknown (2)
    2 - Unknown
    4 - Length of the Next FOR Loop (ie numFiles*8)

    // for each file
      4 - Hash?
      4 - null
      
    2 - Unknown (2)
    2 - Unknown
    4 - Length of the Next FOR Loop (ie numFiles*24)
  
    // for each file
      4 - Hash?
      4 - File Offset
      4 - File Length
      4 - Unknown (263324)
      4 - Padding Multiple? (256)
      4 - null

// FILE DATA  
  // for each file
    X - File Data
```


They are 2 distinct formats. They are already listed separately in the wiki.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #15
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2006-03-07T19:05:45+00:00
- Post Title: Need for Speed - Most Wanted

it works for most BIN's indeed, thanks 

now I still need to mess around, and see if I can open the TPK files that are inside it...
## Post #16
- Username: Extreme
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 26, 2006 8:21 am
- Post datetime: 2006-08-29T20:02:52+00:00
- Post Title: Need for speed most wanted

Hi guys 

Is there any reason why this is giving the wrong file format? Its saying the files inside the bin r tpk files when most id not all of them r dds files
## Post #17
- Username: GrahamDesigns
- Rank: VIP member
- Number of posts: 1
- Joined date: Sun Aug 06, 2006 5:46 pm
- Post datetime: 2006-11-01T20:34:25+00:00
- Post Title: Need for speed most wanted

hey has there been any progress on the .tpk files? its all well and good that we can open the .bins..but nearly ALL of the files inside the bins are .tpk..nothing i can open..how do u open them?
## Post #18
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-13T14:52:07+00:00
- Post Title: Need for speed most wanted

Just a note. I was able to extract the audio for the copspeech in the:

Need for Speed Most Wanted/SOUND/SPEECH/copspeech.big

file using my schl extractor (source: [http://www.xentax.com/uploads/author/dandapani/schl.cpp](http://www.xentax.com/uploads/author/dandapani/schl.cpp)) and then used the SX (Sound eXchange) tool to convert them from ASF format to WAV.
