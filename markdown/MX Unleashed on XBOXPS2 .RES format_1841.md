## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-16T07:29:23+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Hi guys, 

We need your help here. There's this .RES format (XBox/PS2) that contains DXG, DXT files and the like, just like the MX vs ATV Unleashed PAK files for the PC. However, in the .RES files these are compressed/encrypted, and I'd like to ask you to investigate this along with us, cause it's not easy to find out what was used. 

Small info of the.RES format:

```

uint32  Unknown
uint32 Offset of file info start (from the offset of this variable)
uint32  Unknown
uint32  Unknown
uint32  Unknown 

// Unknown block

This block seems to grow as the number of files in the archive grow, hash variables??

// File info block header (see offset in main header)

uint32 Unknown
uint32 Number of files in the archive
uint32 Offset of file data start from right after this variable's position 

  // Start of file info block (per file, number of files-times)
 
 uint32 Size in bytes of filename
 byte() String depicting the filename of the file
 uint32 Uknown (uncompressed size of the file???? Relative offset of the file???)
 uint32 Size of file in bytes (probably)

// FILE DATA

All the files 

// TAIL

Is there a tail? Looks like it. 


```


See the attached file as an example.
## Post #2
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-16T07:58:48+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Zlib Compressed

Quick Notes... sorry they are a bit sloppy. In a hurry :p
0x10 Bytes Used (int32)  / 2 = # Files

Short - Compressed Chunk Size
~Ends

0xD8 - Number of Entries with names???
Int32 - Name/Chunk Size (current offset push (location + value))

Each Entry
Int32 - String Size
~string
4 bytes - Uknown 
4 Bytes - Decompressed Size

Name Table Ends.

Zlib Data Begins (See 789C)
Read Compressed Size from table starting 0x14
Loop
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-16T09:04:17+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Well, I noticed the ZLib tag immediately,  but when I tried to unpack chunks using ZLib the decompression failed consistently.  

I will read your notes carefully.

[EDIT] What you say is rather alike to what I thought. I must now see why I can't decompress it with ZLib. Perhaps my ZLib tool is faulty, because I think your and my specs make a lot of sense.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-16T09:58:10+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Okay, I confirmed my original suspicion that it is ZLib compressed. I have a problem with the ZLib dll. That returned error -5 each time I told it to use the original size of each file. Error code -5 is a buffer error. When I told it to reserve a lot more buffer it worked. This is odd.  The dll then returned the decompressed file in a too large buffer. Hmmm. Anyway, now the way is paved to start supporting full extraction. Thanks Silver, you're the second opinion I needed. 

[EDIT] I determined that the decompression buffer for the first file needed to be 0x5FFF. Otherwise the dll returned a buffer error. This shall not be the case for each file, especially if they are bigger than that!

[EDIT2] AH, I think I now know what the unknown variable means, the one before the decompressed size variable. Interesting. The files seem to be compressed in chunks, rather than in one go.
## Post #5
- Username: Teancum
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-16T12:43:19+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Ok, in the file I attached above , the files were originally truncated in 0x6000 block that were individually compressed. With this BMS one can uncompress all chunks, with those files that originally were larger than 0x6000 having more uncompressed chunks (they are numbered 0, 1, 2 etc). To get the whole file back, the 0x6000 chunks should be combined. Then the remainder (numberofchunks*0x6000 - original size) should be removed. 

```
ComType ZLib1 ;
Get D Long 0 ;
SavePos T 0 ;
Get FJ Long 0 ;
Get U1 Long 0 ;
Get U2 Long 0 ;
Get U3 Long 0 ;
Set UCB Long 24576 ;
Math T += FJ ;
SavePos UO 0 ;
GoTo T 0 ;
Get U4 Long 0 ;
Get FN Long 0 ;
Get DOO Long 0 ;
SavePos DO 0 ;
Math DO += DOO ;
For T = 1 To FN ;
Get FNS Long 0 ;
GetDString FName FNS 0 ;
Get NOff Long 0 ;
Get UCS Long 0 ;
Set F Long 0 ;
Set Co Long UCS ;
Do ;
SavePos FT 0 ;
GoTo UO 0 ;
Get CS Int 0 ;
SavePos UO 0 ;
Set FNA String FName ;
String FNA += F ;
CLog FNA DO CS 0 0 UCB 0 ;
Math Co -= 24576 ;
Math F += 1 ;
Math DO += CS ;
Math DO += 1 ;
GoTo FT 0 ;
While Co > 0 ;
Next T ;

```


Run custom script ... option in MexCom with a COMPILED BMS (use the MexScriptor (MexBinderPlus-->Scriptor) to create a compiled BMS. 

Or, get the attached BMS.
[res.zip](https://xentaxbackup.github.io/file/701_res.zip)
## Post #6
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-16T13:52:52+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

How do you put the pieces together?
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-16T13:57:45+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Well, you can just add them with a hex editor, but you also need to know the original size. I'll create a plugin for MexCom to be able to handle that better than the MultiEx Script can.
## Post #8
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-16T13:59:44+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Cool.
## Post #9
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-16T14:31:48+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

This .RES file is actually from MX Unleashed, not MX vs ATV Unleashed.  Just an FYI.

This is coming along great.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-17T17:36:29+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Done. I created a plugin for MexCom that will extract from the XBOX .RES files. 

Just extract, but I think that's exactly what you guys needed anyway. 

here's an example from the nat14.res file. 

Also, scrolll down to download the plugin. Create a 'res' dir in MexCom's plugin folder and copy it there. Run MexCom.
[nat14_finish.dxt.jpg](https://xentaxbackup.github.io/file/704_nat14_finish.dxt.jpg)
## Post #11
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-17T19:42:41+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

Holy crap you are the man!
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-17T19:59:50+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

I have set up a new blog to keep track of plugins and scripts and such. This would also probably be an easy location to direct new visitors that want to download it. 

[http://www.xentax.com/tblog/index.php](http://www.xentax.com/tblog/index.php)
## Post #13
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-05-19T12:15:12+00:00
- Post Title: MX Unleashed on XBOX/PS2 .RES format

I really hate to necropost, but given that it's directly related it seems smarter. I've read over the posts above in regards to the inability to reimport files, but I'm wondering if there's a way to either update the script or that I can reimport manually. I've put a lot of work and documentation into modding Cars: The Video Game, and this is the only thing that stops me from modding the Xbox version. I've found that I can extract the entire XBR archive, delete it, and run from folders, but the RES files have to be present still. It's frustrating, because the exact same files exist within the folders.

Anyway, I know everyone is busy, but I figured six years of experience since the last post might help. In the meantime I'll see if I can just dummy out the RES files to force the game to read from folders. Oh, and I've posted the exact error below, if that should help.

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select the BMS script or plugin to use
- select the input archives/files to extract, type "" for whole folder and subfolders
- select the output folder where extracting the files
- REIMPORT mode enabled!
- start the scanning of the input folder: C:\Games\Xbox\TOOLS\New Folder
- open input file C:\Games\Xbox\TOOLS\New Folder\.\debug\debug.dxt
- open script C:\Games\Xbox\TOOLS\res_script.bms
- set output folder C:\Games\Xbox\TOOLS

  offset   filesize   filename
------------------------------

Error: incomplete input file number 0, can't read 413311034 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted


Press RETURN to quit
```
