## Post #1
- Username: dodther
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-15T10:08:06+00:00
- Post Title: (Ps3) White Knight Chronicles

After you extract the psarc file you can use these scripts to extract the assets.

HPK extractor

```
get idstring long
endian big
get files long
get arcsize long
get nameend long
get namestart long
get baseoff long
get version long
get null long
savepos filestart
print %filestart%
for i = 0 < files
goto filestart
getdstring hash 0x10
get offset long
math offset + baseoff
get size long
get null1 long
get null2 long
savepos filestart
goto namestart
get name string
savepos namestart
log name offset size
next i


```


Image to dds converter

```
Open FDDE p3igg 0
Open FDDE p3img 1
endian big
get idstring long 1
get unk long 1
get arcsize long 1
get null1 long 1
get baseoff long 1
getdstring unk01 0x14 1
get files long 1
get null long 1
get skip long 1
math skip + baseoff
goto skip 1
savepos filepos 1
for i = 0 < files
goto filepos 1
get nameoff long 1
get offset long 1
math nameoff + baseoff
get size long 1
get null long 1
get type byte 1
get unk021 byte 1
get unk022 byte 1
get unk023 byte 1
get unk03 long 1

get width1 byte 1
get width2 byte 1
get height1 byte 1
get height2 byte 1
getdstring null03 0x14 1

putVarChr MEMORY_FILE 0x11 width1 byte
putVarChr MEMORY_FILE 0x10 width2 byte
putVarChr MEMORY_FILE 0xD height1 byte
putVarChr MEMORY_FILE 0xC height2 byte
savepos filepos 1
goto nameoff 1 
get name string 1
string name + ".dds"

   callfunction addDDSheader
   math SIZE + 0x80
   log NAME 0 SIZE MEMORY_FILE

next i

startfunction addDDSheader
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x11 width1 byte
putVarChr MEMORY_FILE 0x10 width2 byte
putVarChr MEMORY_FILE 0xD height1 byte
putVarChr MEMORY_FILE 0xC height2 byte

if type == 136
putVarChr MEMORY_FILE 0x57 0x35
endif
if type == 135
putVarChr MEMORY_FILE 0x57 0x33
endif
if type == 134
putVarChr MEMORY_FILE 0x57 0x31
endif

   append
   log MEMORY_FILE OFFSET SIZE
   append
endfunction




```
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-09-17T14:06:17+00:00
- Post Title: (Ps3) White Knight Chronicles

What is the format of the assets? Unknown 3D or chrrox ready?
## Post #3
- Username: jcarl904
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 12, 2010 11:08 pm
- Post datetime: 2010-09-18T04:27:02+00:00
- Post Title: (Ps3) White Knight Chronicles

Great work chrrox. The models in this game are awesome, Could you tell us how to extract the psarc file?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-19T14:55:13+00:00
- Post Title: (Ps3) White Knight Chronicles

The contents of this post was deleted because of possible forum rules violation.
[PSARC.zip](https://xentaxbackup.github.io/file/3457_PSARC.zip)
## Post #5
- Username: jcarl904
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 12, 2010 11:08 pm
- Post datetime: 2010-12-17T05:37:58+00:00
- Post Title: (Ps3) White Knight Chronicles

Chrrox, How did you open d00h.psarc.sdat? Do I need to rename it? I manage to extract d03b.psarc and d04b.psarc without a hitch, but they contain mostly sounds.
I'm stuck trying to figure out the other files that end with .sdat.
Any assistance is much appreciated.
## Post #6
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-12-17T16:29:18+00:00
- Post Title: (Ps3) White Knight Chronicles

.sdat at PS3 encrypted files, you'll need to write a tool to run on your PS3 with the appropriate key information to decrypt the file.
## Post #7
- Username: jcarl904
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 12, 2010 11:08 pm
- Post datetime: 2010-12-17T19:30:32+00:00
- Post Title: (Ps3) White Knight Chronicles

I see, thank you Rick for pointing that out. 
I read about decrsdat.cpp, v1 over at asmodean's.
Bummer! I really wanted to access and hopefully convert actual model and texture data with the scripts provided.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-17T20:28:18+00:00
- Post Title: (Ps3) White Knight Chronicles

I am not sure what you are talking about there are plenty of model files.
extract d04h.psarc there is an event folder filled with models.
## Post #9
- Username: jcarl904
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 12, 2010 11:08 pm
- Post datetime: 2010-12-17T21:06:28+00:00
- Post Title: (Ps3) White Knight Chronicles

You're absolutely right chrrox, my search was not thorough. Thank you!
## Post #10
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-06-01T05:12:41+00:00
- Post Title: (Ps3) White Knight Chronicles

pls help!the HPK extracted  P3mmg,P3mms and P3msh.no max script? how could i import the model into max?
## Post #11
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-15T04:24:21+00:00
- Post Title: (Ps3) White Knight Chronicles

i use "Image to dds converter" for game "ni no kuni".
ni no kuni and White Knight Chronicles use the same format.
 but converted image a strange
[](http://imageshack.us/photo/my-images/842/pause01.png/)

bad script? or used compression? how to make a normal picture?
## Post #12
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-18T02:39:29+00:00
- Post Title: (Ps3) White Knight Chronicles

no use DXT1
 need use 8 L 8 bpp | luminance

[](http://imageshack.us/photo/my-images/259/pause02.png/)
## Post #13
- Username: ureshiiiiii
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 22, 2017 9:14 am
- Post datetime: 2018-02-22T09:08:01+00:00
- Post Title: (Ps3) White Knight Chronicles

Sorry to revive such an old thread, but I kinda wish there were more guidelines on this process.

I've extracted the psarc file and have all the .hpk archives, but I'm at a loss how to use HPK Extractor
I've read Crypton's posts about the tool, but I still don't know how to use it to extract the assets

Sorry, I'm very noobish at this. (obviously)
I'm mainly focused on extracting the model files from the game...
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-22T14:59:21+00:00
- Post Title: (Ps3) White Knight Chronicles

> Reply from ureshiiiiii
>
> I've extracted the psarc file and have all the .hpk archives, but I'm at a loss how to use HPK Extractor
the 2 scripts in the first post are for QuickBMS, copy the first one to a text file and run it with the program.
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

quick instruction
1. launch QuickBMS.exe
2. select the script you want to run
3. select the file you want to process with the script 
4. select the destination for processed files and done!
## Post #15
- Username: ureshiiiiii
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 22, 2017 9:14 am
- Post datetime: 2018-02-23T00:50:44+00:00
- Post Title: (Ps3) White Knight Chronicles

Thank you, AceWell! (And chrrox for the scripts) That worked like a charm.

I'm assuming model data is stored in .p3mmg or .p3mms files? Are there any scripts available to convert this file type?
## Post #16
- Username: ureshiiiiii
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 22, 2017 9:14 am
- Post datetime: 2018-02-28T10:40:16+00:00
- Post Title: Re: (Ps3) White Knight Chronicles

> Reply from 652845095
>
> pls help!the HPK extracted  P3mmg,P3mms and P3msh.no max script? how could i import the model into max?
Yeah, I'm having the same problem, too. :/ Can't find any answers.
## Post #17
- Username: shxp
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 01, 2021 7:55 pm
- Post datetime: 2021-10-01T12:11:34+00:00
- Post Title: Re: (Ps3) White Knight Chronicles

> Reply from chrrox ↑Wed Sep 15, 2010 6:08 pm at Wed Sep 15, 2010 6:08 pm
>
> 
After you extract the psarc file you can use these scripts to extract the assets.

HPK extractor
Code: Select all
get idstring long
endian big
get files long
get arcsize long
get nameend long
get namestart long
get baseoff long
get version long
get null long
savepos filestart
print %filestart%
for i = 0 < files
goto filestart
getdstring hash 0x10
get offset long
math offset + baseoff
get size long
get null1 long
get null2 long
savepos filestart
goto namestart
get name string
savepos namestart
log name offset size
next i



Image to dds converter
Code: Select all
Open FDDE p3igg 0
Open FDDE p3img 1
endian big
get idstring long 1
get unk long 1
get arcsize long 1
get null1 long 1
get baseoff long 1
getdstring unk01 0x14 1
get files long 1
get null long 1
get skip long 1
math skip + baseoff
goto skip 1
savepos filepos 1
for i = 0 < files
goto filepos 1
get nameoff long 1
get offset long 1
math nameoff + baseoff
get size long 1
get null long 1
get type byte 1
get unk021 byte 1
get unk022 byte 1
get unk023 byte 1
get unk03 long 1

get width1 byte 1
get width2 byte 1
get height1 byte 1
get height2 byte 1
getdstring null03 0x14 1

putVarChr MEMORY_FILE 0x11 width1 byte
putVarChr MEMORY_FILE 0x10 width2 byte
putVarChr MEMORY_FILE 0xD height1 byte
putVarChr MEMORY_FILE 0xC height2 byte
savepos filepos 1
goto nameoff 1 
get name string 1
string name + ".dds"

   callfunction addDDSheader
   math SIZE + 0x80
   log NAME 0 SIZE MEMORY_FILE

next i

startfunction addDDSheader
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x11 width1 byte
putVarChr MEMORY_FILE 0x10 width2 byte
putVarChr MEMORY_FILE 0xD height1 byte
putVarChr MEMORY_FILE 0xC height2 byte

if type == 136
putVarChr MEMORY_FILE 0x57 0x35
endif
if type == 135
putVarChr MEMORY_FILE 0x57 0x33
endif
if type == 134
putVarChr MEMORY_FILE 0x57 0x31
endif

   append
   log MEMORY_FILE OFFSET SIZE
   append
endfunction

Been itching to get my hands on models from wkc2 gonna be looking into this major big thanks for pointing me where I need to go
## Post #18
- Username: shxp
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 01, 2021 7:55 pm
- Post datetime: 2021-10-01T19:27:34+00:00
- Post Title: Re: (Ps3) White Knight Chronicles

Ok the scripts don't do anything, it spits out a small file that's all 0's 
the psarc app opens and closes itselfI tried dragging files to it but nothing.
am I doing something wrong?
