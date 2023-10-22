## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2010-04-10T21:02:19+00:00
- Post Title: Splinter cell : conviction

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-04-10T21:25:05+00:00
- Post Title: Splinter cell : conviction

Xbox 360?
## Post #3
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2010-04-10T22:26:08+00:00
- Post Title: Splinter cell : conviction

yep, pc isnt out till the end of the month
## Post #4
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-04-27T18:59:22+00:00
- Post Title: Splinter cell : conviction

So PC version is out now and here we got some umd files

They all have EPCK header

[loc-int.umd](http://www.sendspace.com/file/1ksl8f) - seems like some localization source, 156kb

[PEC-Main.umd](http://www.sendspace.com/file/wcewys) and one of main 'umd' files. 1.85mb

may be someone will make some research as i want translating the game.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-04-30T21:27:12+00:00
- Post Title: Splinter cell : conviction

looks a zlib crypted
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-01T00:04:26+00:00
- Post Title: Splinter cell : conviction

The game have two data files .ass and .umd using the same compression (or encryption)
And the header always it's:

> 45 50 43 4B 00 00 02
## Post #7
- Username: venomtrk
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 28, 2009 5:36 am
- Post datetime: 2010-05-29T20:46:18+00:00
- Post Title: Splinter cell : conviction

I want to translate this game to Turkish language, can anyone help me please ? I just need a tool to modify language files.
## Post #8
- Username: iservealot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 06, 2010 4:08 pm
- Post datetime: 2010-07-31T18:41:48+00:00
- Post Title: Splinter cell : conviction

Can anyone give a status update on this?

I was unsuccessful in trying to uncompress the ZLIB data. It was a hit or miss on certain chunks.

Does anyone have any further research for this, or could dedicate some time to looking into this?

Thanks!
## Post #9
- Username: omarbekdash
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 21, 2010 12:44 am
- Post datetime: 2010-10-20T16:48:33+00:00
- Post Title: Splinter cell : conviction

can anyone upload the file loc-int.umd please.
its located in Tom Clancy's Splinter Cell Conviction\src\system
## Post #10
- Username: iservealot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 06, 2010 4:08 pm
- Post datetime: 2010-11-05T17:36:55+00:00
- Post Title: Splinter cell : conviction

Is there any status update on this?

I'll get you the .UMD file when I get home. Do you need this to attempt decompression of ZLIB?
## Post #11
- Username: benzinjiq snake
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jul 18, 2011 10:07 pm
- Post datetime: 2013-09-01T12:47:24+00:00
- Post Title: Splinter cell : conviction

I'm interested in translating the game. I managed to extract "loc-int.umd", using @spinbot script "scc_conviction_data.bms". After that I used I Am Alive "iaa_unpacker.exe" to extract INT files from "dump_scc_data.bin". Now the problem is that I do not know how to repack modified files back to a "loc-int.umd". If anyone could help me I would be very grateful.
## Post #12
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-09-02T08:17:04+00:00
- Post Title: Splinter cell : conviction

I dont test all the following methods, so you can try which works properly.
Copy the unpacked files to gamedir\data folder.


Rename the loc-int.umd, then make an empty file, and name it to loc-int.umd.
or
Rename the dump file to loc-int.umd. Open it with hex editor.  Search and replace the .int extensions to .ina.

And the game will load the files from the data folder.
or
Rename the dump file to loc-int.umd. You can repack it with this script, if the file size is not bigger than original.

```
math asize -= 20
goto -16
get offset long
goto offset
get unk short
do
get namesz byte
getdstring name namesz
get offset long
get size long
get null long
savepos pos
log name offset size
while pos < asize
```


Im not sure this will work, but here is a method to edit ingame subtitles. They are in src\system\UMDS\01-11_xy.umd.
Unpack attached file to a folder and put there [spinbot's script](http://www.gildor.org/smf/index.php/topic,458.60.html), [aluigi's Quickbms](http://aluigi.altervista.org/quickbms.htm) and [xor](http://aluigi.altervista.org/mytoolz.htm), and only one umd at time.
Run export, pick a language and delete other xmls.
Import works only if the new xml size is not bigger than original. The created new umd is much bigger, because its uncompressed.
[scc_text.7z](https://xentaxbackup.github.io/file/6590_scc_text.7z)
## Post #13
- Username: benzinjiq snake
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jul 18, 2011 10:07 pm
- Post datetime: 2013-09-02T20:08:57+00:00
- Post Title: Splinter cell : conviction

Thank you, mate. I'll give it a try with your ways. Hope they (or atleast one of them) work out with the game.
## Post #14
- Username: benzinjiq snake
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jul 18, 2011 10:07 pm
- Post datetime: 2013-09-02T21:41:01+00:00
- Post Title: Splinter cell : conviction

> Reply from swuforce
>
> ...
Rename the dump file to loc-int.umd. You can repack it with this script, if the file size is not bigger than original.
Code: Select allget asize asize
math asize -= 20
goto -16
get offset long
goto offset
get unk short
do
get namesz byte
getdstring name namesz
get offset long
get size long
get null long
savepos pos
log name offset size
while pos < asize
Thank you. Works perfectly.

> Reply from swuforce
>
> ...
...
Im not sure this will work, but here is a method to edit ingame subtitles. They are in src\system\UMDS\01-11_xy.umd.
Unpack attached file to a folder and put there spinbot's script, aluigi's Quickbms and xor, and only one umd at time.
Run export, pick a language and delete other xmls.
Import works only if the new xml size is not bigger than original. The created new umd is much bigger, because its uncompressed.

This worked like a charm, too!
## Post #15
- Username: MCSOBA
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 06, 2014 4:27 am
- Post datetime: 2014-10-13T15:31:37+00:00
- Post Title: Splinter cell : conviction

hey all
I'm with: Splinter Cell Conviction and blacklist, need to decompress files umd/ass
how make this?
I just want decrypt and return to the game folder....not want to do mods...... 

I have done with tools unumd.exe by Gildor
but not work after returning to the game....

Pls
