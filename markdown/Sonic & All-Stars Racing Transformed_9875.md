## Post #1
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-11-15T07:48:34+00:00
- Post Title: Sonic & All-Stars Racing Transformed

So I managed to extract the files from the SoundBanks.pck archive. However ww2ogg does not recognize the chunk type.

I will PM a file if anyone is interested
## Post #2
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2012-11-16T19:06:03+00:00
- Post Title: Sonic & All-Stars Racing Transformed

Oh, Well I was going to Ask about this Weird "RIFX" Format too  but 
I don't think I'm allowed to post samples anymore ):, Is it a XWMA or a XMA? i dont see why there sint jsut support for like some Winamp Plug-in namly VGMStream! for XMA Overall that is
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-11-17T01:08:16+00:00
- Post Title: Sonic & All-Stars Racing Transformed

It uses XMA but there's also RIFX headers that don't have an XMA flag so I think there might be a secondary codec being used as well but I can't be 100% certain.
## Post #4
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2012-11-20T11:16:25+00:00
- Post Title: Sonic & All-Stars Racing Transformed

I'm not sure if this will work for the 360 version but for the PS3 but I extracted the .oggs (.wavs) from the streamsmulti.pck file using aluigi's Darksiders II BMS script.

```
# script for QuickBMS http://quickbms.aluigi.org

endian big
idstring "AKPK"
goto 0x20
get DUMMYSZ long
getdstring DUMMY DUMMYSZ
get FILES long
for i = 0 < FILES
    get NAME_CRC long
    get ALIGNSZ long
    get SIZE long
    get OFFSET long
    get DUMMY long
    math OFFSET *= ALIGNSZ
    log "" OFFSET SIZE
next i
```


Following I used ww2ogg with the "packed_codebooks_aoTuV_603" switch and finally revorb to have playable oggs.
## Post #5
- Username: MrYeah
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 11, 2013 5:42 pm
- Post datetime: 2013-03-15T21:24:10+00:00
- Post Title: Sonic & All-Stars Racing Transformed

This script doesn't work for PC version.
```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file D:\Steam\SteamApps\common\Sonic & All-Stars Racing Transformed
\Data\sound\StreamsMulti.pck
- open script darksiders2_pck.bms
- set output folder C:\tmp\sonic

  offset   filesize   filename
------------------------------

- 0 files found in 1 seconds
  coverage file 0    30%   201326604  664273022
```

The files are in RIFF WAVE format. The value of wFormatTag is 0x4220.
Edit: [I solved the problem myself.](http://forum.xentax.com/viewtopic.php?f=17&t=10105&p=83928#p83928)
