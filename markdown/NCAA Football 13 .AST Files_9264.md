## Post #1
- Username: SnarbleBarb
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 15, 2011 4:24 pm
- Post datetime: 2012-07-14T01:55:16+00:00
- Post Title: NCAA Football 13 .AST Files

Hello,

I would like to open the .AST files from the xbox360 version of NCAA Football '13. I tried using aluigi's Madden '10 BMS script here [viewtopic.php?t=8179](http://forum.xentax.com/viewtopic.php?t=8179) but quickbms.exe is spitting out 0 files found. I have a feeling that the file may have some sort of encryption because quickbms thinks the string name is:

> 00000040 06  10  get NAME string
>
>              >set NAME (3) to "┤
>
> ╡dxnyLS3#lkjªæe⌡║x╛Æt▼à↓♣↑¿╕pyRPX.tvESσ╥┬W┘╢σÅ◄♂┼ⁿH╟▌╫↕♥"

Here's a picture of what the beginning of the file looks like in hex.



I'm guessing that there is some modification needed from the Madden '10 bms script to make it work, but I have no idea where to begin. Can anyone help, please?

Thanks.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-14T14:59:25+00:00
- Post Title: NCAA Football 13 .AST Files

Send small archive in pm.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-14T15:34:14+00:00
- Post Title: NCAA Football 13 .AST Files

in the meantime try also the script I wrote for NBA jam fire:
[http://aluigi.org/papers/bms/others/nbajamfire.bms](http://aluigi.org/papers/bms/others/nbajamfire.bms)
maybe it's the same format, I hope
## Post #4
- Username: SnarbleBarb
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 15, 2011 4:24 pm
- Post datetime: 2012-07-14T16:06:56+00:00
- Post Title: NCAA Football 13 .AST Files

> Reply from aluigi
>
> in the meantime try also the script I wrote for NBA jam fire:
http://aluigi.org/papers/bms/others/nbajamfire.bms
maybe it's the same format, I hope

Thanks for responding. I tried the nbajamfire.bms but it didn't work. It got farther at least! Here's the verbose output:

```
             <get NAME (11) "RPX.tvESσ╥┬W┘╢σÅ◄♂┼ⁿH╟▌╫↕♥"
             <get OFFSET (4) 0xcc28fba0
             <get ZSIZE (9) 0x00a81805
             <get SIZE (10) 0x012188bd
  cc28fba0 18974909   RPX.tvESσ╥┬W┘╢σÅ◄♂┼ⁿH╟▌╫↕♥

Error: incomplete input file number 0, can't read 11016197 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted
```


For sanity check's sake, I'm using quickbms 0.5.13.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-14T16:25:09+00:00
- Post Title: NCAA Football 13 .AST Files

ok so it's another format to reverse, I don't understand why EA makes these games using the BGFA format with some differences in each one... mah
## Post #6
- Username: SnarbleBarb
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 15, 2011 4:24 pm
- Post datetime: 2012-07-14T16:33:21+00:00
- Post Title: NCAA Football 13 .AST Files

What are the steps to reverse it? So that I can poke around a bit on my own while I await the reversing gods to work their magic  I tried using your comtype_scan method, but that failed because the smallest archive is 88MB and it would either complain of not enough memory or harddrive space (the bigger 3GB+ archive).

Also, anyway that I can help expedite the process? I have never reversed an archive before so no experience there, but I'm willing to help in whatever way that I can.

Thanks.
## Post #7
- Username: SnarbleBarb
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 15, 2011 4:24 pm
- Post datetime: 2012-07-17T18:51:13+00:00
- Post Title: NCAA Football 13 .AST Files

It looks like I made a huge error here. I had downloaded the Madden '10 bms script as HTML instead of plain text. It made the less than sign to be "&lt" instead of "<" *facepalm*. I fixed it and it doesn't work on the file that I sent Ekey, but it works beautifully on the larger archives. I'll report back when I can confirm that I actually have models and textures when it finishes dumping!

Sorry for the earlier confusion and thanks!!
## Post #8
- Username: SnarbleBarb
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 15, 2011 4:24 pm
- Post datetime: 2012-07-17T21:30:10+00:00
- Post Title: NCAA Football 13 .AST Files

I was only able to extract one file, "qkl_stream.AST". It had a bunch of bgf, mvh, and dat files in it. The Madden and Nbajamfire scripts couldn't open the new bgf files (same BGFA header as the .AST files though). None of the other .AST files would open with either script.

Here's a screenshot of a directory listing of all of the .AST files so that you know what I'm talking about:



Let me know if anyone needs any files to take a crack at it.

Thanks!
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-17T21:39:55+00:00
- Post Title: NCAA Football 13 .AST Files

Try this script -> [Electronic Arts AST archive extractor (BGFA identifier)](http://forum.xentax.com/viewtopic.php?f=13&t=4450&start=285) in end.
## Post #10
- Username: flowersongs
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2016 2:40 am
- Post datetime: 2016-02-03T12:53:24+00:00
- Post Title: NCAA Football 13 .AST Files

Slightly off topic from original post, but in relation to the NBA on fire script and ea games in general, has anyone figured out what type of image files are expanded from the AST big files? The script you posted aluigi worked successfully to extract the files, but they have no extension. They seem to be complete. Are they compressed files or encrypted? I've tried adding multiple different extensions and importing to photoshop with no luck so far.
## Post #11
- Username: flowersongs
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2016 2:40 am
- Post datetime: 2016-02-18T02:34:34+00:00
- Post Title: NCAA Football 13 .AST Files

Does anyone know how to run Aluigi's NBA extraction script in reverse to make an ast?  I tried running it in quickbms with the Reimport batch, but it errored saying expected BGFA, this file is XPR2. The script worked to Extract the files, now I need to inject them or re-import them to .ast ... Please help me run this script in reverse and my project is complete. Has anyone successfully re-imported files back to AST.

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "BGFA"
getdstring VER 4
get DUMMY long
get FILES long
get OFFSET long
goto OFFSET
getdstring DUMMY 12
for i = 0 < FILES
    getdstring DUMMY 10
    get OFFSET long
    get ZSIZE threebyte
    get SIZE threebyte
    getdstring NAME 0x2a
    math OFFSET *= 8
    if SIZE == 0
        log NAME OFFSET ZSIZE
    else
        math SIZE += ZSIZE
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
