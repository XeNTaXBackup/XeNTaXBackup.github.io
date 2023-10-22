## Post #1
- Username: JesseMitsuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 16, 2011 6:58 pm
- Post datetime: 2012-06-24T23:00:30+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

Hi,
I need help opening files extracted from the game Muramasa: Demon Blade, a game released on the WII. Description is here:
[http://en.wikipedia.org/wiki/Muramasa:_The_Demon_Blade](http://en.wikipedia.org/wiki/Muramasa:_The_Demon_Blade)

The primary files I'm interested in opening are the ftx and the mbs files. I've included some of these files in the attached archive. I can only make out the headers of the files but the rest confuses me (I'm still new to this).

Hope you can help; thanks in advance!

Archive Download:
* snip * NO COPYRIGHTED FILES!
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-24T23:54:33+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

How did you extract them? the files look compressed.
## Post #3
- Username: JesseMitsuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 16, 2011 6:58 pm
- Post datetime: 2012-06-25T02:04:52+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

I extracted them originally from the game's iso by using the Wii emulator, Dolphin.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-25T02:33:08+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

quickbms script.
its standard wii compression used in the sdk they just added a 12 byte header.

```
get name filename
string name + .ext
get zsize asize
math zsize - 12
set size zsize
math size * 4
clog name 12 zsize size
```
## Post #5
- Username: JesseMitsuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 16, 2011 6:58 pm
- Post datetime: 2012-06-25T20:35:12+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

Thanks!
I was able to decompress the files with the script you provided. However, I'm not sure where to go from here. I can see the .tpl files. What sort of script or extractor will I have to run?
Sorry for the trouble~
## Post #6
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-25T22:55:08+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

Unfortunately i failed to extract those FTX files, the size that is specified is incorrect resulting in the files being extracted incorrectly, i may have missed something but it's unlikely. Can someone fix this script and tell me where i went wrong?

Thanks

```
# By MrNightmareTM
# Version 0.1a

get SIGN long
get UNK1 long
get OFFSET long
get FILES long

goto 0x20
savepos OFFSET2

for i = 0 < FILES
getdstring NAME 0x24
get SIZE long
get UNK1 long
get UNK2 long

log NAME OFFSET SIZE
math OFFSET2 += 0x30
goto OFFSET2
math OFFSET += SIZE
next i

```
## Post #7
- Username: JesseMitsuru
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-26T00:50:30+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

the extractor works fine you just have to read the sub headers that give the real size and offset.
the size given is not used in the wii extraction process it uses its own size based on the data it reads like the dynamic zlib.
they seem to be normal tpl files.
## Post #8
- Username: JesseMitsuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 16, 2011 6:58 pm
- Post datetime: 2012-06-26T20:46:08+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

I think I see it.
Sorry COOL12345, I made changes to your script >_< Hope that's okay.

```
# By MrNightmareTM
# Version 0.1a

get SIGN long
get UNK1 long
get OFFSET long
get FILES long

goto 0x20
savepos OFFSET2

for i = 0 < FILES
getdstring NAME 0x24
get UNK0 long
get UNK1 long
get UNK2 long

goto OFFSET
get UNK3 long
get SIZE long
get OFFSET3 long
goto OFFSET2

log NAME OFFSET SIZE
math OFFSET2 += 0x30
goto OFFSET2
math OFFSET += SIZE
math OFFSET += OFFSET3
next i

```


Would these changes then extract the files at their correct sizes and offsets?

I managed to extract them fine, but the tools I try open the tpl files all give errors still. Can you guys look at this please?
## Post #9
- Username: JesseMitsuru
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-26T21:47:29+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

^ No that won't fix it. I have re looked over the script and have managed to fix it, i forgot something important here's your working script.

Click the thanks button   

```
# By MrNightmareTM
# Version 0.2b

get SIGN long
get UNK1 long
get OFFSET long
get FILES long

goto 0x20
savepos NMEBNK

for i = 0 < FILES
getdstring NAME 0x24
get SIZE2 long
get UNK2 long
get UNK3 long

goto OFFSET
get SIGN2 long
get SIZE long
get HSIZE long
math SIZE += HSIZE

log NAME OFFSET SIZE
math NMEBNK += 0x30
math OFFSET += SIZE
goto NMEBNK
next i

```
## Post #10
- Username: JesseMitsuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 16, 2011 6:58 pm
- Post datetime: 2012-06-27T01:45:27+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

Ah! Thanks so much COOL12345. Same to you chrrox. I see where I messed up.
You guys really helped a lot!

I'm curious though, since I don't recognize the header, or rather, the format of these tpl files. I've compared them to the .tpl samples I created using a png to tpl converter, but the formats are entirely different. Are there any usable apps or codes I can implement to view these files?

Thanks again ^^
## Post #11
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-27T06:24:18+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

> Reply from JesseMitsuru
>
> Ah! Thanks so much COOL12345. Same to you chrrox. I see where I messed up.
You guys really helped a lot!

I'm curious though, since I don't recognize the header, or rather, the format of these tpl files. I've compared them to the .tpl samples I created using a png to tpl converter, but the formats are entirely different. Are there any usable apps or codes I can implement to view these files?

Thanks again ^^
chrrox said they were normal .tpl files, i suggest searching for a .tpl texture opener to open the files.
## Post #12
- Username: JesseMitsuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 16, 2011 6:58 pm
- Post datetime: 2012-06-28T06:42:06+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

After spending a little time looking at it I figured out what was wrong. The script isn't working correctly, entirely. chrrox is right on all counts: They are normal TPL files (I read and compared them to documentation, found here ). And it needs to use the correct sizes and offsets. However, the second offset is there to offset from the subheader before each file.

Normally, TPL headers start like this with the 0x20AF30 signature:


However, with the current script they begin with the subheader instead.


The 0x40 offset value that comes after and the size is supposed to offset to the location of the TPL header and extract from there. Also, the original extraction process does bleed into the next file.

Once again, I apologize; I took the liberties of editing the script lol.

```
get UNK1 long
get OFFSET long
get FILES long

goto 0x20
savepos NMEBNK

for i = 0 < FILES
getdstring NAME 0x24
get SIZE2 long
get UNK2 long
get UNK3 long

goto OFFSET
get SIGN2 long
get SIZE long
get OFFSET2 long

math OFFSET += OFFSET2

log NAME OFFSET SIZE
math NMEBNK += 0x30
math OFFSET += SIZE
goto NMEBNK
next i
```


Another thing I noticed while going through the files was that the format was CI8 (indicated by 0x9) and the tools I was using only supported TPL formats up to RGBA8, neither CI4 or CI8. That was a mistake on my part.

I got it working and extracted a few more images for fun:




Anyway, thanks again to both of you for helping me out! I learned a lot. I might just write a small app for the extraction process.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-06-29T06:14:37+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

JesseMitsuru, read the damn rules.
## Post #14
- Username: JesseMitsuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jul 16, 2011 6:58 pm
- Post datetime: 2012-06-30T03:24:21+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

My apologies. It won't happen again.
## Post #15
- Username: maoxianfly
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 08, 2014 12:38 am
- Post datetime: 2014-11-12T02:27:36+00:00
- Post Title: Murama: Demon Blade ftx and mbs Files

> Reply from JesseMitsuru
>
> After spending a little time looking at it I figured out what was wrong. The script isn't working correctly, entirely. chrrox is right on all counts: They are normal TPL files (I read and compared them to documentation, found here ). And it needs to use the correct sizes and offsets. However, the second offset is there to offset from the subheader before each file.

Normally, TPL headers start like this with the 0x20AF30 signature:


However, with the current script they begin with the subheader instead.


The 0x40 offset value that comes after and the size is supposed to offset to the location of the TPL header and extract from there. Also, the original extraction process does bleed into the next file.

Once again, I apologize; I took the liberties of editing the script lol.
Code: Select allget SIGN long
get UNK1 long
get OFFSET long
get FILES long

goto 0x20
savepos NMEBNK

for i = 0 < FILES
getdstring NAME 0x24
get SIZE2 long
get UNK2 long
get UNK3 long

goto OFFSET
get SIGN2 long
get SIZE long
get OFFSET2 long

math OFFSET += OFFSET2

log NAME OFFSET SIZE
math NMEBNK += 0x30
math OFFSET += SIZE
goto NMEBNK
next i

Another thing I noticed while going through the files was that the format was CI8 (indicated by 0x9) and the tools I was using only supported TPL formats up to RGBA8, neither CI4 or CI8. That was a mistake on my part.

I got it working and extracted a few more images for fun:




Anyway, thanks again to both of you for helping me out! I learned a lot. I might just write a small app for the extraction process.

You can share code and app?
