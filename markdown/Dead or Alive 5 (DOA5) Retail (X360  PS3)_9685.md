## Post #1
- Username: dragbody
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-28T00:57:03+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Ok I want to get this out before the model script so people are ready when the time comes.
These are the tools to extract and decrypt the new format.
This will not be the fastest thing in the world but you only need to extract the game one time so.
first you must extract the .lnk and .bin files

```
open FDDE LNK 0
open FDDE BIN 1
goto 0x8 1
get files long 1
goto 0x28 1
savepos offset 1
for i = 0 < files
goto offset 1
get arcnum long 1
get id long 1
get noff long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 i name
next i
getarray name 0 0
putarray 0 files name
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
set id i
getarray name 0 id
string name + .dat
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i

```


Ok then on the files that are put out you will want to run this 2nd script called doa5extract.bms.
use this command to batch process
quickbms -F "*.dat" c:\doa5extract.bms c:\DOA5\datfiles c:\output
now you will have a directory with a bunch of ext files
you will want to run doa5decrypt.bms
you can run it the same way
quickbms -F "*.ext" c:\doa5decrypt.bms c:\DOA5\extfiles c:\output2
(This will take a while)
ok so now you have a bunch of files with funky names that are extracted and decrypted.
the names they give will tell you how to find the characters models
for instance

```
2S763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_002.TMC
2T763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_003.TMC
2U763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_004.TMC
2V763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_005.TMC
2W763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_006.TMC
2X763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_007.TMC
2Y763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_008.TMC

BR873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_001.TMCL
BS873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_002.TMCL
BT873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_003.TMCL
BU873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_004.TMCL
BV873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_005.TMCL
BW873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_006.TMCL
BX873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_007.TMCL
BY873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_008.TMCL

```

you can clearly see the pattern in the name

```
2S151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_002.TMC
2T151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_003.TMC
2U151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_004.TMC
2V151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_005.TMC
2W151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_006.TMC

BR161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_001.TMCL
BS161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_002.TMCL
BT161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_003.TMCL
BU161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_004.TMCL
BV161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_005.TMCL
BW161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_006.TMCL

```


```
2S052@1S100@BF1G]]724B21G1PQ87710M10{R821F - MILA_COS_002.TMC
2T052@1S100@BF1G]]724B21G1PQ87710M10{R821F - MILA_COS_003.TMC
2U052@1S100@BF1G]]724B21G1PQ87710M10{R821F - MILA_COS_004.TMC
2V052@1S100@BF1G]]724B21G1PQ87710M10{R821F - MILA_COS_005.TMC
2W052@1S100@BF1G]]724B21G1PQ87710M10{R821F - MILA_COS_006.TMC

BR062@1S100@C71]H]723C212G1PQ87610M10{R821F - MILA_COS_001.TMCL
BS062@1S100@C71]H]723C212G1PQ87610M10{R821F - MILA_COS_002.TMCL
BT062@1S100@C71]H]723C212G1PQ87610M10{R821F - MILA_COS_003.TMCL
BU062@1S100@C71]H]723C212G1PQ87610M10{R821F - MILA_COS_004.TMCL
BV062@1S100@C71]H]723C212G1PQ87610M10{R821F - MILA_COS_005.TMCL
BW062@1S100@C71]H]723C212G1PQ87610M10{R821F - MILA_COS_006.TMCL

2R0K2@1S100@CG212H]2]B8341QA1I1DNA8H0100M{PQ1A = MILA_HAIR_001.TMC
2S0K2@1S100@CG212H]2]B8341QA1I1DNA8H0100M{PQ1A = MILA_HAIR_002.TMC
BR0K2@1S100@D7212]I1]C8300QA15I1DNA8H0100M{PQ1A = MILA_HAIR_001.TMCL
BS0K2@1S100@D7212]I1]C8300QA15I1DNA8H0100M{PQ1A = MILA_HAIR_002.TMCL

```

the first 2 characters tell what costume it is and the last 4 or 5 tell you what the model is.
so its very simple to match them up
I will try to make a wiki page and fill in the costume names and people can feel free to help 
if you look at the tmc files in a hex editor the model name is clearly visible
[doa5.7z](https://xentaxbackup.github.io/file/5843_doa5.7z)
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-28T04:49:54+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

LOL You're the boss here.

Thanks Chrrox.

Edit:

The scripts also work with the dlc files.
## Post #3
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-28T06:50:49+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Thanks a lot Chrrox, this is good to learn from your scripts also. I Appreciate all the work you do!
## Post #4
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-28T10:42:50+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I get this when using doa5extract.bms:
[Untitled.png](https://xentaxbackup.github.io/file/5844_Untitled.png)
## Post #5
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-28T11:49:44+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

it cant be a folder in the area you are extracting.
works
c:\original files
c:\new files

not working
c:\coriginal files
c:\coriginal files\new files
## Post #6
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-28T13:25:59+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from chrrox
>
> it cant be a folder in the area you are extracting.
works
c:\original files
c:\new files

not working
c:\coriginal files
c:\coriginal files\new files
Huh? Im confused xD I made a folder named "new files" in my D: Drive to have the ext files extract there, but that didnt work either.
## Post #7
- Username: olylanboy
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-28T14:19:26+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

in your example do this
make a new folder
d:\quickbms
install the newest quickbms there.
now open a command prompt and change to that directory
cd d:\quickbms
now do
quickbms.exe -F "*.dat" d:\doa5extract.bms d:\dat_file_folder d:\new_dat_file_folder
and put quotes around all your paths to be sure
## Post #8
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-28T14:42:34+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from TRDaz
>
> chrrox wrote:it cant be a folder in the area you are extracting.
works
c:\original files
c:\new files

not working
c:\coriginal files
c:\coriginal files\new files
Huh? Im confused xD I made a folder named "new files" in my D: Drive to have the ext files extract there, but that didnt work either.

He means there can't be any spaces between words.
## Post #9
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-28T14:48:42+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

good script work!  
I'm Defrosting was completed. 
but noesis fmt_DOA5_NG3_tmc.py Load failure  
1.4ver is old?
## Post #10
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-28T16:31:01+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from chrrox
>
> in your example do this
make a new folder
d:\quickbms
install the newest quickbms there.
now open a command prompt and change to that directory
cd d:\quickbms
now do
quickbms.exe -F "*.dat" d:\doa5extract.bms d:\dat_file_folder d:\new_dat_file_folder
and put quotes around all your paths to be sure
Thanks! This worked! Its extracting them right now  I cant wait for the noesis script btw 

EDIT: What happened? D:
[Untitled.png](https://xentaxbackup.github.io/file/5846_Untitled.png)
## Post #11
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-28T16:52:49+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I am not sure not nearly enough information to know.
you should have about 700 or more files extracted.
## Post #12
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-28T17:07:27+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from chrrox
>
> I am not sure not nearly enough information to know.
you should have about 700 or more files extracted.
I have 454 files extracted D:
## Post #13
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-09-28T17:26:42+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

chrrox
thanks for the decrypting scripts - i thought my brains will start boiling because of all these pawerpc mnemonics 

i think the script that exports lnk has an error. you should skip the names that belongs to attached lnk archives. these bin's have only one lnk attached, you don't have to calculate the offset, just skip 4 bytes.

```
open FDDE LNK 0
open FDDE BIN 1
goto 0x8 1
get files long 1
goto 0x24 1  // you should fix it here to: "goto 0x28 1", else you'll use the archive name for the first file, and each next file will use the name of the precedent one

```
## Post #14
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-28T17:27:17+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I had that error because I wasn't using the latest version of quickbms, but i think you are so I'm not sure, maybe try redownloading it just in case?
## Post #15
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-28T17:42:14+00:00
- Post Title: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from rman2
>
> I had that error because I wasn't using the latest version of quickbms, but i think you are so I'm not sure, maybe try redownloading it just in case?
Nah, that didnt work D:
## Post #16
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-28T18:03:28+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Thank's again Chrrox !!

Does it will work with the X360 demo of the game ?
## Post #17
- Username: zaykho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-28T18:54:51+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

for the demo just use the script here
[viewtopic.php?f=16&t=8867](http://forum.xentax.com/viewtopic.php?f=16&t=8867)
its not encrypted or anything in the demo.
## Post #18
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-28T19:00:32+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Any help with my problem? D: I want to get these extracted before the script is released...
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-28T19:37:38+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

you are doing something wrong with the command line.
open a command prompt and drag all the files into the box instead of typing the names.
this will put them in quotes automatically.
you can try one file at a time using the script as normal to see it work.
## Post #20
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-28T19:51:02+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from chrrox
>
> you are doing something wrong with the command line.
open a command prompt and drag all the files into the box instead of typing the names.
this will put them in quotes automatically.
you can try one file at a time using the script as normal to see it work.
I did everything correct afaik.
Still has an error with this command line:
[Untitled.png](https://xentaxbackup.github.io/file/5847_Untitled.png)
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-28T19:55:18+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

try just one file then.
double click quickbms
click the extractor bms
then click on one dat file
then click the output folder see if it works.
if that failed something went wrong during the first script.
or something is wrong with the game rip.
## Post #22
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-28T21:58:17+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> for the demo just use the script here
>
> viewtopic.php?f=16&t=8867
>
> its not encrypted or anything in the demo.

Thank's !

I will test this in some minutes.
## Post #23
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-09-28T22:01:41+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

While doing the extractions, did you happen to come across audio (music) files, chrrox?

I've been looking for them and so far only extracted rtm_common and stage_rtm. A lot of files that don't look like any common X360/PS3 audio format, but who knows they might be encrypted. 

Also  any idea what are the files in DATA and DATA2 folder? Thanks for sharing your work on this.
## Post #24
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-28T23:30:41+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Seto from the best manga of the universe: I''s
## Post #25
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-09-29T02:33:15+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Correct ^_^
## Post #26
- Username: divStar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 22, 2010 6:46 am
- Post datetime: 2012-09-29T04:57:43+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I'm also very curious about the music. I have bought the collector's edition, but this soundtrack CD is a joke.. I'm angry kinda, because in the game I at least heard some original Bass (Armstrong) music, so I guess it has far more music in it .. so it'd be awesome if there was a way to extract it o_o;; I've got the files and will try tomorrow, but I'm keeping track on here =).
## Post #27
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-09-29T06:08:11+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from b0ny
>
> chrrox
thanks for the decrypting scripts - i thought my brains will start boiling because of all these pawerpc mnemonics 

i think the script that exports lnk has an error. you should skip the names that belongs to attached lnk archives. these bin's have only one lnk attached, you don't have to calculate the offset, just skip 4 bytes.
Code: Select allendian BIG
open FDDE LNK 0
open FDDE BIN 1
goto 0x8 1
get files long 1
goto 0x24 1  // you should fix it here to: "goto 0x28 1", else you'll use the archive name for the first file, and each next file will use the name of the precedent one
wow, my bad here. sorry... the above will not fix the problem.
to fix it, the values order should be fixed - to read the name offset last.(noff-arcnum-id -> arcnum-id-noff)

> endian BIG
>
> open FDDE LNK 0
>
> open FDDE BIN 1
>
> goto 0x8 1
>
> get files long 1
>
> goto 0x28 1
>
> savepos offset 1
>
> for i = 0 < files
>
> goto offset 1
>
> 
>
> get arcnum long 1
>
> get id long 1
>
> get noff long 1
>
> savepos offset 1
>
> goto noff 1
>
> get name string 1
>
> putarray 0 i name
>
> next i
>
> getarray name 0 0
>
> putarray 0 files name
>
> goto 0xC
>
> get files long
>
> get unk01 longlong
>
> get unk02 longlong
>
> for i = 0 < files
>
> get offset longlong
>
> get zsize longlong
>
> get size longlong
>
> get arc longlong
>
> set id i
>
> math id + 1
>
> getarray name 0 id
>
> string name + .dat
>
> if zsize == size
>
> log name offset size
>
> else
>
> clog name offset zsize size
>
> endif
>
> next i
## Post #28
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-09-29T06:25:31+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

hi 
i m having some problem extracting .lnk files


edit: fixed.  sorry
## Post #29
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T06:33:12+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from khanbot
>
> hi 
i m having some problem extracting .lnk files


edit: fixed.  sorry

did you try chara_common.bin? instead?
## Post #30
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-09-29T06:56:35+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

i think it was some problem with file paths.  i didn't type the whole thing and just dragged the script and file and folders onto command window lol.   
.bin file outputs the same files as .lnk file


so for now, can we just extract these files?  is there a way to view them models atm?
## Post #31
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-29T06:59:26+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from chrrox
>
> try just one file then.
double click quickbms
click the extractor bms
then click on one dat file
then click the output folder see if it works.
if that failed something went wrong during the first script.
or something is wrong with the game rip.
Trying one file works perfectly, is it because I am extracting too many dat's at the same time? Should I try and split them into different folders?
I think the rip was perfect, I used PowerISO and Noesis to extract em, did the same with TTT2 and that was fine.

EDIT: Just tested the file from the error, it seems to be corrupted I think, it isnt extracting with your script at all D: im gonna test the others see if they are fine.
## Post #32
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T07:11:08+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from khanbot
>
> i think it was some problem with file paths.  i didn't type the whole thing and just dragged the script and file and folders onto command window lol.   
.bin file outputs the same files as .lnk file


so for now, can we just extract these files?  is there a way to view them models atm?

you may not want to use that original script for bms extraction. you should use bonys.

umm I am not sure yet but I think there is a link to an noesis import script somewhere and chroxx is working on it. wait a couple of days =)
## Post #33
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-29T07:16:14+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Yep, just that 1 file that seems to not extract, others worked perfectly. 
The one that wont extract is:

BRL73@1S100@D]I]623G1K165F1QEE1100M10{RL72317.dat

I have 647 files from extracting every other file.
## Post #34
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T07:29:49+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from TRDaz
>
> Yep, just that 1 file that seems to not extract, others worked perfectly. 
The one that wont extract is:

BRL73@1S100@D]I]623G1K165F1QEE1100M10{RL72317.dat

I have 647 files from extracting every other file.

I have 710 files from the chara_common.bin/lnk I have tried to search for
files that chroxx had put up to match costumes and cannot find them :S
I looked at the files with a hex editor and found that it was decrypted.

I used Bonys BMS script with the fix and the two scripts in decrypt, and extract.
## Post #35
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-29T07:38:59+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Wierd how I have less than you. One file cant give another 63 ext's D: Im gonna re extract it with b0ny's edit, maybe that will help.
## Post #36
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T07:51:23+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from TRDaz
>
> Wierd how I have less than you. One file cant give another 63 ext's D: Im gonna re extract it with b0ny's edit, maybe that will help.

yeah let me know how many files you have a feeling that the bms script that charoxx posted in the first post along with bonys post maybe incorrect.
## Post #37
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-09-29T08:36:50+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Mobuis
>
> 

I have 710 files from the chara_common.bin/lnk I have tried to search for
files that chroxx had put up to match costumes and cannot find them :S
I looked at the files with a hex editor and found that it was decrypted.

I used Bonys BMS script with the fix and the two scripts in decrypt, and extract.

I also have 710 files after running the decrypt script.  I also used b0ny's script in first step, then extract and decrypt.  I can't find some of the files chroxx posted in first post.  where are we wrong?


also, the supposed .tmc and .tmcl files extracted dont match.  like i have this file 2T151@....S75131G.dec ending with 131G.  but its matching file that should start with BT151@.. is not there.
## Post #38
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-09-29T08:57:32+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

So which is the correct script?

1. Wrote by "chrrox" in the first post.

or

2. Fixed by "b0ny" in the 27th post.
## Post #39
- Username: blackfoxeye
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-29T11:21:10+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

i have been using my script with no problem you can try both but i know the model files extracted using what i posted work fine.
## Post #40
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-09-29T11:42:03+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from chrrox
>
> i have been using my script with no problem you can try both but i know th emodel files extracted using what i posted work fine.

Thank you very much chrrox for the information.
I am currently downloading the game, so I can check after 2/3 days, till then I have to wait.

And can you please just let me know, what is the "emodel" please
## Post #41
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T15:49:57+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from blackfoxeye
>
> So which is the correct script?

1. Wrote by "chrrox" in the first post.

or

2. Fixed by "b0ny" in the 27th post.

I had tried both.

They both produce 710 files after its been through the whole process but,
First file 
2A0J2_AKA1F13031]2]A1]30OJ1818561DMHJ221B1L{O061 is only 2kb for bonys script where as 506kb for charrox script. and on inspection with a hex editor they are different files.
BUT on closer inspection when you line up the files by sizes and open with a hex editor they are different.
So file 

BWA73@1S100@D]H]623D5446125PQM131410210{F1R5211.dec from bony's script is 11,112kb
BU1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I.dec from charrox's script is 11,112kb and its file contents are different.

try and find this on charrox's or bony's script and you will find they are completely different files.
BU1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I.dec 

Just to be safe I would go with charrox's script. Since he has extracted models from his =)
## Post #42
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-09-29T15:53:45+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Mobuis
>
> blackfoxeye wrote:So which is the correct script?

1. Wrote by "chrrox" in the first post.

or

2. Fixed by "b0ny" in the 27th post.

I had tried both.

They both produce 710 files after its been through the whole process but,
First file 
2A0J2_AKA1F13031]2]A1]30OJ1818561DMHJ221B1L{O061 is only 2kb for bonys script where as 506kb for charrox script. and on inspection with a hex editor they are different files.
BUT on closer inspection when you line up the files by sizes and open with a hex editor they are different.
So file 

BWA73@1S100@D]H]623D5446125PQM131410210{F1R5211.dec from bony's script is 11,112kb
BU1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I.dec from charrox's script is 11,112kb and its file contents are different.

try and find this on charrox's or bony's script and you will find they are completely different files.
BU1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I.dec 

Just to be safe I would go with charrox's script. Since he has extracted models from his =)

Ya, you are right.
## Post #43
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-09-29T16:00:31+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

it's possible to restore automatically the names for the tmc files by reading the inside names, and then find the tmcl associated by searching it by size wich is indicated in LHeader section in the tmc file(and then maybe checking if it's the right one by checking some value in some section). 

right now i'm more interested in restoring the directory tree. we have it in the demo, so i think it can be possible to find the associations inside the executable - like pointers to the names of all files that belongs to some costume or character...
## Post #44
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-09-29T19:04:42+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Ok I think I did something wrong, I ended up with this:

1st srcript:

8 lnk files
8 bin files

2nd script:

5,177 dat files (I got several overwrite messages so there could be more files just duplicated)

3d script:

1,101 ext files (at least 3 of the dat files were either corrupt or something, because I got the same message TRDaz got about zlib/deflate but with -3,-4 and -5)

I'm decrypting them now, will tell you if I get any more error messages
## Post #45
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T19:36:18+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from b0ny
>
> it's possible to restore automatically the names for the tmc files by reading the inside names, and then find the tmcl associated by searching it by size wich is indicated in LHeader section in the tmc file(and then maybe checking if it's the right one by checking some value in some section). 

right now i'm more interested in restoring the directory tree. we have it in the demo, so i think it can be possible to find the associations inside the executable - like pointers to the names of all files that belongs to some costume or character...

I would help with this but.... there is no map of the binaries of the TMC and the TMCL what is the TMC composed of anyways? and the TMCL must be the full character model.
## Post #46
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T19:38:44+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from GDL
>
> Ok I think I did something wrong, I ended up with this:

1st srcript:

8 lnk files
8 bin files

2nd script:

5,177 dat files (I got several overwrite messages so there could be more files just duplicated)

3d script:

1,101 ext files (at least 3 of the dat files were either corrupt or something, because I got the same message TRDaz got about zlib/deflate but with -3,-4 and -5)

I'm decrypting them now, will tell you if I get any more error messages

Update to the latest version of BMS and then try it again. ensure you have charrox script for bms to extract the LNK and BIN files, for only chara_common. or else you will get a mess of files.

So in command prompt
quickbms charroxbmssript.bms c:\path\to\chara_common.bin c:\path\destination\chara_common_out
## Post #47
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-09-29T20:14:50+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I downloaded the latest version of quickbms before extracting/decrypting the files, and from the chara_common.bin extracted files the only one that gives me an error message with chrrox bms is this one:

BSF73@1S100@D]I]623D54B14PQPM100510331000{R7211.dat

after I delete that one I get 709 ext files
## Post #48
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-29T22:41:16+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I followed the steps to extract the files .dec...

What are have do now?
## Post #49
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T22:54:39+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from GDL
>
> I downloaded the latest version of quickbms before extracting/decrypting the files, and from the chara_common.bin extracted files the only one that gives me an error message with chrrox bms is this one:

BSF73@1S100@D]I]623D54B14PQPM100510331000{R7211.dat

after I delete that one I get 709 ext files  

By the way I created a .bat file to rename the decrypted files using chrrox model list:

ahaha I just wrote a python script to do the renaming based on the correct dictionary. ill post it in a bit =P
## Post #50
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-29T23:26:56+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Mobuis
>
> GDL wrote:I downloaded the latest version of quickbms before extracting/decrypting the files, and from the chara_common.bin extracted files the only one that gives me an error message with chrrox bms is this one:

BSF73@1S100@D]I]623D54B14PQPM100510331000{R7211.dat

after I delete that one I get 709 ext files  

By the way I created a .bat file to rename the decrypted files using chrrox model list:

ahaha I just wrote a python script to do the renaming based on the correct dictionary. ill post it in a bit =P

I am wait so.
## Post #51
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-30T11:55:29+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Some of the files are giving errors with b0ny's script. I really dont know why this is happening, I want these models so bad D:
## Post #52
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-30T12:15:14+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

All I can really think of is an error with your iso :s have you tried re-ripping it?
## Post #53
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-30T12:48:31+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Ill try, tho, someone is kind enough to be sending me the models I need (on Tomb Raider Forums because I port to XNALara)
## Post #54
- Username: Cziter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 05, 2011 2:47 am
- Post datetime: 2012-09-30T17:27:47+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I extracted char_common.bin from full version, but when im trying to use 2nd script im ending up with empty output folder. Am i doing something wrong?

Edit. Maybe full ver. scripts require some changes.
[Untitled-1.jpg](https://xentaxbackup.github.io/file/5865_Untitled-1.jpg)
## Post #55
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-30T18:21:21+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Cziter
>
> I extracted char_common.bin from full version, but when im trying to use 2nd script im ending up with empty output folder. Am i doing something wrong?

Edit. Maybe full ver. scripts require some changes.

For me happen the same, if you find results tell me please.
## Post #56
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-09-30T18:32:03+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

my 'fixed' script didn't work well - sorry.

here's a simple doa5 unpacker

put it in the doa5 directory where the bin and lnk files are. it will unpack/decrypt them in separate folders. use chrrox's method from his first post in this thread to find the tmcl files. the tmc file names are reversed for your convenience, the internal name is added if it exists and a tmc extension is added. at least test it...
## Post #57
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-30T19:09:56+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from b0ny
>
> my 'fixed' script didn't work well - sorry.

here's a simple doa5 unpacker

put it in the doa5 directory where the bin and lnk files are. it will unpack/decrypt them in separate folders. use chrrox's method from his first post in this thread to find the tmcl files. the tmc file names are reversed for your convenience, the internal name is added if it exists and a tmc extension is added. at least test it...

@BONY thanks for tool!

I use this and nice, extract all.

and after i use outher scripts for .dat and ok.

but when i used script for give .ext, appear a few files.

whats wrong?
## Post #58
- Username: Cziter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 05, 2011 2:47 am
- Post datetime: 2012-09-30T19:12:08+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Unpacker looks good, every "discovered" tmc is nicely renamed.I think it requires few upgrades to noesis script now, cause the old dosent work at all or something went wrong with unpacker.
## Post #59
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-09-30T19:29:37+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

The noesis script is not working for me either and it didn't work from the begining, nothing gets loaded but then again I don't get any error message just an empty screen :-/
## Post #60
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-01T02:35:47+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from GDL
>
> The noesis script is not working for me either and it didn't work from the begining, nothing gets loaded but then again I don't get any error message just an empty screen :-/

Have you updated your noesis script?? The fma_ng3/doablablablah doesn't work on DOA5 files, you need the script posted in the 3d model forum.

See ya.
## Post #61
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-01T02:43:42+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Try different noesis script, I know that:
>
> 
>
> For best export face character I use 1.4.1
>
> For best export costume character I use 1.5.0
>
> For best export stage I use 1.5.0 & 1.3.0
>
> 
>
> I know the demo is different from the retail, but give a try :p
>
> 
>
> I have indexed all interesting tools for DOA 5 here:
>
> http://www.mediafire.com/?ihz7d86bd2erh (then go to --> Tool)
>
> or directly here:
>
> http://www.mediafire.com/?sbd2c9r8ok3u3
EDIT: now this folder is THE ULTIMATE TOOL FOLDER for Dead Or Alive & Ninja Gaiden, enjoy !!

[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)

***If I have missed some tool, let me know !
## Post #62
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-10-01T03:43:30+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Darko
>
> GDL wrote:The noesis script is not working for me either and it didn't work from the begining, nothing gets loaded but then again I don't get any error message just an empty screen :-/

Have you updated your noesis script?? The fma_ng3/doablablablah doesn't work on DOA5 files, you need the script posted in the 3d model forum.

See ya.

Yes I'm using the 1.4.1 script, and nothing, when I use the 1.5 script I get an error message, I have the tmc and tmcl in the same folder :-/
## Post #63
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-01T03:54:49+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Yes I'm using the 1.4.1 script, and nothing, when I use the 1.5 script I get an error message, I have the tmc and tmcl in the same folder :-/

Try with this one, its the ayane face from the DEMO VERSION, and see if it work:

[http://www.mediafire.com/download.php?2bwvtakssqcmg7w](http://www.mediafire.com/download.php?2bwvtakssqcmg7w)

If not, then we can assume that its your noesis the problem.

For me its Noesis v392 + DOA5 1.5.0.

PS: Don't forget to clean your Py_cache and/or delete all old DOA5 plugin (like doa5_360, fmt_doa5 etc...), or more, get a fresh new noesis.
## Post #64
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-10-01T04:55:19+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from zaykho
>
> Yes I'm using the 1.4.1 script, and nothing, when I use the 1.5 script I get an error message, I have the tmc and tmcl in the same folder :-/

Try with this one, its the ayane face from the DEMO VERSION, and see if it work:

http://www.mediafire.com/download.php?2bwvtakssqcmg7w

If not, then we can assume that its your noesis the problem.

For me its Noesis v392 + DOA5 1.5.0.

PS: Don't forget to clean your Py_cache and/or delete all old DOA5 plugin (like doa5_360, fmt_doa5 etc...), or more, get a fresh new noesis.

Ok, that one works, the ones I extracted from the game are the ones not working
## Post #65
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-01T05:10:05+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Ok, that one works, the ones I extracted from the game are the ones not working

In this case, try re-ripping you Game, or try another Script for extract data, try to see if you don't have some
hardware problem (like memory error or old HDD.....).
## Post #66
- Username: Cziter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 05, 2011 2:47 am
- Post datetime: 2012-10-01T11:31:06+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Which files are tmc and tmcl then, cause file names changed and i cant find anything that matches.
For example i got H149B5S{01N000RQ01C528]17]H1TC@001S1@36BR2++ZACK_COS_001.TMC after using b0ny's extractor. Now what i should look for to find .tmcl to that? Because i dont see anything similar in first post.

Edit: now i get it. why is this reversed?

in the 1st post:
2R052@1S100@BF1G]]724B21G1PQ87710M10{R821F - MILA_COS_001.TMC

after b0ny extractor:
F128R{01M01778QP1G12B427]]G1FB@001S1@250R2++MILA_COS_001.TMC

its impossible to find anything.
## Post #67
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-01T21:08:04+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Cziter
>
> Which files are tmc and tmcl then, cause file names changed and i cant find anything that matches.
For example i got H149B5S{01N000RQ01C528]17]H1TC@001S1@36BR2++ZACK_COS_001.TMC after using b0ny's extractor. Now what i should look for to find .tmcl to that? Because i dont see anything similar in first post.

Edit: now i get it. why is this reversed?

in the 1st post:
2R052@1S100@BF1G]]724B21G1PQ87710M10{R821F - MILA_COS_001.TMC

after b0ny extractor:
F128R{01M01778QP1G12B427]]G1FB@001S1@250R2++MILA_COS_001.TMC

its impossible to find anything.

has succeeded in opening some model with noesis?
## Post #68
- Username: Cziter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 05, 2011 2:47 am
- Post datetime: 2012-10-01T22:03:57+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Ya with 1.5 py most of the models are working somehow.
## Post #69
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-01T22:11:53+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Cziter
>
> Ya with 1.4.1 py. No errors but blank preview and non exportable, i think im going to pass.  I see Darko succesfully extracted the model from full version. but i dont think he will share his knowledge with newbes like us.

Yes, you and me newbies.
## Post #70
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-01T22:42:38+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Wait until i get the retail Game, I will make a tutorial on how to extract and open in Noesis.
## Post #71
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-01T23:02:02+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from zaykho
>
> Wait until i get the retail Game, I will make a tutorial on how to extract and open in Noesis.

Great hear this zaykho!
## Post #72
- Username: Cziter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 05, 2011 2:47 am
- Post datetime: 2012-10-02T00:17:51+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I got everything now. I used b0ny extractor cause batch bms was giving me errors. b0ny extractor reverse filenames so i was confused and i messed tmlcs . Started from scratch and now everything works. My lazy bad.
## Post #73
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-02T09:58:23+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Thank you very much "chrrox" for your great help.

Your all tools and scripts are awesome, finally I got the mesh and textures, you are great
## Post #74
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-10-02T15:26:07+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

thanks for testing my "simple doa5 unpacker". it needs some fixes and improvements. use something else(chrrox scripts) to unpack the game till i'll manage to make it work properly. don't have enough time for this right now.
## Post #75
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-03T06:32:51+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

OK here my script for extract-decrypt-rename files for DOA5:
(It's a simple .bat file, you just need to choose what do you want to extract and to wait until the script finish his work)
(only selection 1 is enabled for now !!!)
[http://www.mediafire.com/download.php?prugcc49akr9p8a](http://www.mediafire.com/download.php?prugcc49akr9p8a)

If you just want to rename lot of files, take this script:
[http://www.mediafire.com/download.php?ogqnwt4wr8b5b03](http://www.mediafire.com/download.php?ogqnwt4wr8b5b03)

And if you want the Ultimate Tool Folder for DOA/NG:
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)
***If I have missed some tool, let me know !

PS: I have just make a simple .BAT, others things come from different users, thx chroxx & others Xentax user...
## Post #76
- Username: divStar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 22, 2010 6:46 am
- Post datetime: 2012-10-03T10:03:33+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Hm - is there a way to extract all the music? I have the DoA5 CE, but I think the soundtrack doesn't contain all the music played in the game :/ would that script help me? Thanks in advance .
## Post #77
- Username: sophist82
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 21, 2012 11:39 pm
- Post datetime: 2012-10-03T13:04:21+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I can't manage to find joints/animation data from all the extracted files. Could anyone give me an advice? 
I think it's in chara_common file. Since Doa 5 beta had model and joints data in same file.
## Post #78
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-10-03T13:52:58+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

simple doa5 unpacker version2

if anyone still need this 
will unpack correctly the doa5 files except some files that are encrypted but not compressed like "LEIFANG_COS_002"(i think chrrox scripts isn't handling these too. use the script to unpack them separately).

you still should find the tmcl files manually. maybe next version will use the list used to batch rename the files.  

an extension is added for many doa5 formats
## Post #79
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-03T14:12:13+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> simple doa5 unpacker version2
>
> 
>
> if anyone still need this 
>
> will unpack correctly the doa5 files except some files that are encrypted but not compressed like "LEIFANG_COS_002"(i think chrrox scripts isn't handling these too. use the script to unpack them separately).
>
> 
>
> you still should find the tmcl files manually. maybe next version will use the list used to batch rename the files.
>
> 
>
> an extension is added for many doa5 formats

Thx B0ny, I will pick a try :p
## Post #80
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-04T02:04:34+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

DOA5 - Model Renamer v1.2.zip  *UPDATE - 04/10/2012 - 04:05 AM - GTM+2*
----------------------------------------------------------------------------------------------------------
the v1.2 give you: 
- The latest names from the GoogleDOC page --> https://docs.google.com/spreadsheet/ccc ... eHc#gid=27 (- 04/10/2012 - 04:05 AM - GTM+2-)
- Support now: Characters, Stages and DLC

This tool will rename all unknown model names from extracted files of DOA5 by an updated list of real names.
You just need to put the .bat file in the folder corresponding to the type of files you have extracted from DOA5 (Characters, Stages or DLC)


Link to the tool -->
[http://www.mediafire.com/?61z7llb902fabu1](http://www.mediafire.com/?61z7llb902fabu1)

Link to the ultimate folder tool of DOA/NG -->
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)

EDIT: Link to folder corrected 

PS: This tool contains work from chroxx & others Xentax user too.
## Post #81
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-10-04T04:54:41+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

The link to the folder takes me to the MF hompage D:
## Post #82
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-04T09:57:06+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> The link to the folder takes me to the MF hompage D:

Link corrected :p
## Post #83
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-10-05T15:36:23+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Just had a few questions here:

-When I import to 3dsmax2010 using Neosis's .obj export the .mtl doesn't work. I have to rotate each texture 180 degrees, flip it horizontally and then place it manually for it to apply correctly to the model. Am I missing a step there?

-Is there a texture that contains the pupils for the eyes? I apply the 'eye' looking texture but all I get are black spheres.

Other than that everything worked perfectly! You guys are brilliant, especially that Chrrox fellow
## Post #84
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-05T15:45:15+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from skyvenom
>
> Just had a few questions here:

-When I import to 3dsmax2010 using Neosis's .obj export the .mtl doesn't work. I have to rotate each texture 180 degrees, flip it horizontally and then place it manually for it to apply correctly to the model. Am I missing a step there?

-Is there a texture that contains the pupils for the eyes? I apply the 'eye' looking texture but all I get are black spheres.

Other than that everything worked perfectly! You guys are brilliant, especially that Chrrox fellow

While Exporting from Neosis, there is a checkbox "Flip UV's".
You should check that to get the correct rotated textures.

And I think the UV of eye mesh is not there, so you have to correct the UV's manually of the eyes. You can find the eye texture with face texture.
## Post #85
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-05T16:02:26+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

No, there are two eyeballs, one should be deleted, the other has the correct uv's for the eyes.
## Post #86
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-10-05T16:06:24+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from blackfoxeye
>
> 

While Exporting from Neosis, there is a checkbox "Flip UV's".
You should check that to get the correct rotated textures.

And I think the UV of eye mesh is not there, so you have to correct the UV's manually of the eyes. You can find the eye texture with face texture.

The "Flip UV's" box did the trick, thanks! The only problem now is they still don't auto apply when I import to max. Normally I can deal with a little extra work but when it comes to the hair textures I'm completely lost. They all look the same to me and I have no idea where they are supposed to go...

Thank you rman2, I found the second set of eyes and now the pupils are showing up properly
## Post #87
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-05T16:14:39+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from skyvenom
>
> 

The "Flip UV's" box did the trick, thanks! The only problem now is they still don't auto apply when I import to max. Normally I can deal with a little extra work but when it comes to the hair textures I'm completely lost. They all look the same to me and I have no idea where they are supposed to go...

Thank you rman2, I found the second set of eyes and now the pupils are showing up properly

Select the hair mesh in Max, then apply a Unwrap UVW Modifier.
Then open the UV Editor, have a look into how the UVs are, then you can get an idea which is the correct hair texture for that mesh.
## Post #88
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-10-05T16:57:55+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from blackfoxeye
>
> 

Select the hair mesh in Max, then apply a Unwrap UVW Modifier.
Then open the UV Editor, have a look into how the UVs are, then you can get an idea which is the correct hair texture for that mesh.

Giving that a shot, it's slowly starting to make sense. Thanks again
## Post #89
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-08T01:13:52+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

DOA5 - Model Renamer v1.5  *UPDATE - 08/10/2012 - 03:05 AM - GTM+2*
----------------------------------------------------------------------------------------------------------
the v1.5 give you: 
- The latest names from the GoogleDOC page --> https://docs.google.com/spreadsheet/ccc ... eHc#gid=27 
- Support now: Characters, Stages and DLC in only one file

This tool will rename all unknown model names from extracted files of DOA5 by an updated list of real names.
You just need to put the .bat file in the folder where you have extracted files from DOA5 (Characters, Stages or DLC)

DOA5 - Ripping Tool v1.5  *UPDATE - 08/10/2012*
----------------------------------------------------------------------------------------------------------
the v1.5 give you: 
- Support now: Characters and DLC
- Automatically renaming files after finish
- Renaming.bat as been cleared and optimized   

This tool will extract and decrypt all chosen files of DOA5 and automatically rename them with an updated list of real names.
You just need to put the folder ( doa5_ripping_tool ) in the doa5 folder OR the dlc "root" folder (where .bin and .lnk are) 



Link to DOA5 - Model Renamer v1.5 -->
[http://www.mediafire.com/?rd3g3i234w8x84r](http://www.mediafire.com/?rd3g3i234w8x84r)

Link to DOA5 - Ripping Tool v1.5 -->
[http://www.mediafire.com/?h5xcs5zdj29jahi](http://www.mediafire.com/?h5xcs5zdj29jahi)

Link to the ultimate folder tool of DOA/NG -->
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)



PS: These tools contains work from chroxx & others Xentax user too.
## Post #90
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-10-08T20:17:05+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I looked around for a bit but couldn't find the info so I figured I would just shoot another question.

I can't find where the DLC costumes come from. Is it in the files from the original rip or is it from a separate download?
## Post #91
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-10-08T20:44:37+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

DLC models are from the actual DLC downloads, I use a program called Le Fluffie App (only works on 360 dlc) which extracts the .bin from the DLC file, then you can go on with the tools Chrrox made from there
## Post #92
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-10-08T22:10:05+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from TRDaz
>
> DLC models are from the actual DLC downloads, I use a program called Le Fluffie App (only works on 360 dlc) which extracts the .bin from the DLC file, then you can go on with the tools Chrrox made from there

Thanks for the quick response =) I take it finding the DLC downloads isn't exactly easy. The only thing I can think of is extracting it from a 360 HDD?
## Post #93
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-09T06:30:42+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I am also confused, where to find the Bunny Girl Swimsuits DLC.

I know that, first costume pack is free, and one can download from xbox live.
And Collector's Edition DLC is only comes with the Collector's Edition Box pack.
And I read that, Bunny Girl Swimsuits DLC comes with some retailer's Preorder pack.

So, any body knows that any download link or something else, where I can download the Bunny Girl Swimsuits DLC?
## Post #94
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-09T06:35:27+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from blackfoxeye
>
> I am also confused, where to find the Bunny Girl Swimsuits DLC.

I know that, first costume pack is free, and one can download from xbox live.
And Collector's Edition DLC is only comes with the Collector's Edition Box pack.
And I read that, Bunny Girl Swimsuits DLC comes with some retailer's Preorder pack.

So, any body knows that any download link or something else, where I can download the Bunny Girl Swimsuits DLC?

[http://www.mediafire.com/?ihz7d86bd2erh](http://www.mediafire.com/?ihz7d86bd2erh)
(choose DLC 0 for bunny)
## Post #95
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-09T06:40:01+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from zaykho
>
> 
http://www.mediafire.com/?ihz7d86bd2erh
(choose DLC 0 for bunny)

Awesome buddy 

You are super great... Thank you very very much zaykho.
## Post #96
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-09T08:21:04+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from blackfoxeye
>
> zaykho wrote:
http://www.mediafire.com/?ihz7d86bd2erh
(choose DLC 0 for bunny)

Awesome buddy 

You are super great... Thank you very very much zaykho.

no problem.   

Thanks @Mobuis for this, he's the one who have buy this DLC.
## Post #97
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-09T08:35:48+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Thank you very much "Mobuis" and "zaykho" for the great help.
## Post #98
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-10-09T14:00:45+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Wow wasn't expecting that! Huge thanks to zaykho and Mobuis!
## Post #99
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-10-09T17:05:16+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

here's the simple doa5 unpacker version 3
automatically will rename all tmc/tmcl pairs.
sadly the long names are shortened - an '@' letter(and a number if the name repeats) is added to these names.
extension for all known file types is added(and decryption if they are encrypted but not zipped)
sources inside - requires zlib(sorry for the mess inside  )

P.S. a lot of skins in "rtm.lnk". just wondering if the game can be hacked somehow to make these skins playable...
## Post #100
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-10-10T04:58:12+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

What I realized is that they intersect the clothing with the primary body mesh and take the difference quite sad for those people who wanted an alpha based nude hack =P. Oh well! but I do enjoy the new faces the old faces were so generic !
## Post #101
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-10T05:33:23+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Mobuis
>
> What I realized is that they intersect the clothing with the primary body mesh and take the difference quite sad for those people who wanted an alpha based nude hack =P. Oh well! but I do enjoy the new faces the old faces were so generic !

Well, it's easy to make a nude hack here, just take the the bikkini one, delete the bikkini part (or modify if you want) then re-create some polygons here and here :p

[](http://www.hostingpics.net/viewer.php?id=241742Sanstitre2.jpg)

I don't have the time to do that now, but for sure I will do this :p

I'm officially working for a perverted world
## Post #102
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-10T06:56:47+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

The Japanese already have something going;
## Post #103
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-10T07:14:55+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from rman2
>
> The Japanese already have something going;

Yeahhh    !!  any link to provide ?
## Post #104
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-10T08:49:18+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

[](http://www.hostingpics.net/viewer.php?id=535331Sanstitre3.jpg)

DOA5 - Model Tool v2.0 * UPDATE - 10/10/2012 *
----------------------------------------------------------------------------------------------------------
the v2.0 contain: 
- The Renamer Tool and the Rip Tool in only one file
the v2.0 give you: 
- The latest names from the GoogleDOC page --> https://docs.google.com/spreadsheet/ccc ... eHc#gid=27 (- 08/10/2012 - 04:05 AM - GTM+2-)
- Support now: Characters, Stages, DLC and User-Prompt update

This tool will extract/decrypt files of DOA5 and rename them automatically or manually
You just need to put the folder ( doa5_tool ) in the DOA5 folder OR the dlc "root" folder (where .bin and .lnk are) OR to just "browse" your folder for updating unknown names


Link to the tool -->
[http://www.mediafire.com/?7t1kdsy9t421h9n](http://www.mediafire.com/?7t1kdsy9t421h9n)

Link to the ultimate folder tool of DOA/NG -->
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)

Edit:The ultimate folder tool of DOA/NG have been actualized and optimized

PS: This tool contains work from chroxx & others Xentax user too.
## Post #105
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-10-11T02:54:35+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Anyone know which one is this? or if it's available in the US store yet?
## Post #106
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-11T03:34:47+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from GDL
>
> Anyone know which one is this? or if it's available in the US store yet?

[Hello !](http://en.wikipedia.org/wiki/Adobe_Photoshop)

[](http://en.wikipedia.org/wiki/Adobe_Photoshop)
## Post #107
- Username: kokuto
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 31, 2011 1:26 am
- Post datetime: 2012-10-11T23:01:19+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

>LISA_DLC_004.TMC Remove Swimsuit
>000001E0:  00 00 10 C0  00 00 00 03  00 00 00 03  00 00 00 00 
>00000230:  00 00 03 F0  00 00 09 10  00 00 0E 30  00 00 00 00 
>00000630:  00 00 01 99  00 00 02 B7  00 00 01 02  00 00 01 3E
## Post #108
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-12T01:29:01+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from kokuto
>
> >LISA_DLC_004.TMC Remove Swimsuit
>000001E0:  00 00 10 C0  00 00 00 03  00 00 00 03  00 00 00 00 
>00000230:  00 00 03 F0  00 00 09 10  00 00 0E 30  00 00 00 00 
>00000630:  00 00 01 99  00 00 02 B7  00 00 01 02  00 00 01 3E

Nice !

[](http://www.hostingpics.net/viewer.php?id=568443Sanstitre2.jpg)
## Post #109
- Username: wdw89
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Apr 07, 2012 4:10 pm
- Post datetime: 2012-10-12T17:35:10+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from b0ny
>
> here's the simple doa5 unpacker version 3
automatically will rename all tmc/tmcl pairs.
sadly the long names are shortened - an '@' letter(and a number if the name repeats) is added to these names.
extension for all known file types is added(and decryption if they are encrypted but not zipped)
sources inside - requires zlib(sorry for the mess inside  )

I think you should use the google doc list to rename the broken names. At least this works for chara_common.
## Post #110
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-10-15T06:11:27+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from zaykho
>
> kokuto wrote:>LISA_DLC_004.TMC Remove Swimsuit
>000001E0:  00 00 10 C0  00 00 00 03  00 00 00 03  00 00 00 00 
>00000230:  00 00 03 F0  00 00 09 10  00 00 0E 30  00 00 00 00 
>00000630:  00 00 01 99  00 00 02 B7  00 00 01 02  00 00 01 3E

Nice !

Is this a transparency hack? does it work for other characters?
## Post #111
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-10-17T11:18:35+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Mobuis
>
> zaykho wrote:kokuto wrote:>LISA_DLC_004.TMC Remove Swimsuit
>000001E0:  00 00 10 C0  00 00 00 03  00 00 00 03  00 00 00 00 
>00000230:  00 00 03 F0  00 00 09 10  00 00 0E 30  00 00 00 00 
>00000630:  00 00 01 99  00 00 02 B7  00 00 01 02  00 00 01 3E

Nice !



Is this a transparency hack? does it work for other characters?

meshes cut off, my be works
## Post #112
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-10-18T19:53:36+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

tagging this topic, checking back later.
## Post #113
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-20T22:54:27+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from chrrox
>
> in your example do this
make a new folder
d:\quickbms
install the newest quickbms there.
now open a command prompt and change to that directory
cd d:\quickbms
now do
quickbms.exe -F "*.dat" d:\doa5extract.bms d:\dat_file_folder d:\new_dat_file_folder
and put quotes around all your paths to be sure

I tried and I still got the same error as here

>
## Post #114
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-21T20:24:50+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Kamillho
>
> chrrox wrote:in your example do this
make a new folder
d:\quickbms
install the newest quickbms there.
now open a command prompt and change to that directory
cd d:\quickbms
now do
quickbms.exe -F "*.dat" d:\doa5extract.bms d:\dat_file_folder d:\new_dat_file_folder
and put quotes around all your paths to be sure

I tried and I still got the same error as here

Your paths are too long, try to use simple names for your folders ie: ext, dat, decrypt.

See ya.
## Post #115
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-22T10:13:53+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Darko
>
> Kamillho wrote:chrrox wrote:in your example do this
make a new folder
d:\quickbms
install the newest quickbms there.
now open a command prompt and change to that directory
cd d:\quickbms
now do
quickbms.exe -F "*.dat" d:\doa5extract.bms d:\dat_file_folder d:\new_dat_file_folder
and put quotes around all your paths to be sure

I tried and I still got the same error as here


Your paths are too long, try to use simple names for your folders ie: ext, dat, decrypt.

See ya.

I tried and I got the same error ;/
## Post #116
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-22T17:12:45+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Go here --> [viewtopic.php?f=16&t=8867&p=80185#p80185](http://forum.xentax.com/viewtopic.php?f=16&t=8867&p=80185#p80185)
## Post #117
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-10-25T04:23:27+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Oh boy, the thread had become not safe for work with those pics
## Post #118
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-25T11:00:01+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

[](http://www.hostingpics.net/viewer.php?id=352850iioioiof.jpg)

I agree that's different of FFshrine here :p
## Post #119
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-10-29T08:30:48+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Ahaha, good one
## Post #120
- Username: divStar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 22, 2010 6:46 am
- Post datetime: 2012-11-16T10:31:20+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Wow is that I's (from the creator of Video Girl Ai?)?

Anyway: is there a way to extract music/sound from DoA5? Preferably from the PS3 version?
## Post #121
- Username: synce
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 01, 2012 2:26 pm
- Post datetime: 2012-12-31T20:36:04+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I'm seeing a lot of costume swapping and nude mods, is this all being done on 360 or has anyone had success on PS3 too? I assume extracting the models is possible on both consoles
## Post #122
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-01T01:48:12+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

its not possible on ps3 until someone removes the file check-sum for the models.
## Post #123
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2013-01-09T15:56:30+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

I am getting this error in Noesis



I am new to this so I have no idea what this means.
## Post #124
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-01-10T15:25:30+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from farakh
>
> I am getting this error in Noesis



I am new to this so I have no idea what this means.

Are your files correctly renamed?
## Post #125
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2013-01-10T16:44:26+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Darko
>
> farakh wrote:I am getting this error in Noesis



I am new to this so I have no idea what this means.

Are your files correctly renamed?

Repeated the whole process or extracting, decrypting and renaming and its working now. 

Now how do I get the model skeleton? There is a script from this topic

[viewtopic.php?f=16&t=8867&hilit=dead+or+alive](http://forum.xentax.com/viewtopic.php?f=16&t=8867&hilit=dead+or+alive)

on which file do I use this script on?
## Post #126
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-01-11T02:26:51+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from farakh
>
> Darko wrote:farakh wrote:I am getting this error in Noesis



I am new to this so I have no idea what this means.

Are your files correctly renamed?

Repeated the whole process or extracting, decrypting and renaming and its working now. 

Now how do I get the model skeleton? There is a script from this topic

viewtopic.php?f=16&t=8867&hilit=dead+or+alive

on which file do I use this script on?

Use the script posted here:

[viewtopic.php?f=16&t=8867&hilit=dead+or+alive&start=105](http://forum.xentax.com/viewtopic.php?f=16&t=8867&hilit=dead+or+alive&start=105)
## Post #127
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2013-01-12T15:01:59+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Darko
>
> 

Use the script posted here:

viewtopic.php?f=16&t=8867&hilit=dead+or+alive&start=105

I downloaded the script and placed in the python folder in noesis and opened the TMC file and extracted to and FBX format but Im not getting the bones.
## Post #128
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2013-01-12T17:20:14+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from farakh
>
> Darko wrote:

Use the script posted here:

viewtopic.php?f=16&t=8867&hilit=dead+or+alive&start=105

I downloaded the script and placed in the python folder in noesis and opened the TMC file and extracted to and FBX format but Im not getting the bones.
If I remember correctly, the chroxx's script will not support the bones (at this moment). 
But I believe that it is someday implemented by him.
(or search "TMC Praser")
## Post #129
- Username: ratero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 23, 2013 9:18 am
- Post datetime: 2013-07-29T02:09:42+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Thanks to the authors of the tools!
I started yesterday... today running some renders while trying to fix some eyelashes textures...
[Ayane_Iray_03.jpg](https://xentaxbackup.github.io/file/6535_Ayane_Iray_03.jpg)
## Post #130
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-09-03T00:13:35+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

DOA5 scripts don't work on DOA5U files.
## Post #131
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2013-09-03T22:11:39+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from Darko
>
> DOA5 scripts don't work on DOA5U files.
aaawww damn it...
## Post #132
- Username: synce
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 01, 2012 2:26 pm
- Post datetime: 2013-09-19T01:27:17+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Any hope for some 5U scripts? Want dat Rachel
## Post #133
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-09-19T07:36:33+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from synce
>
> Any hope for some 5U scripts? Want dat Rachel

Memory dump from a jtagged 360 for the mean time.
## Post #134
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2013-11-09T12:04:22+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Would someone care to post this tool on this site, some of us can't access mediafire. Thanks!
also need the latest DOA5_360 python script, the version I found kept throwing script errors


p.s. I used the simple DOA5 unpacker v44 if that means anything

UPDATE: I'm such a doofus, I've been working on the DOA5Unlimited files... so I guess I need the Ultimate Folder tools below posted on this site, if you please !  ...note to self: caffeine is not equal to sleep...
++++++++++++++++++

> Reply from zaykho
>
> 

DOA5 - Model Tool v2.0 * UPDATE - 10/10/2012 *
----------------------------------------------------------------------------------------------------------
the v2.0 contain: 
- The Renamer Tool and the Rip Tool in only one file
the v2.0 give you: 
- The latest names from the GoogleDOC page --> https://docs.google.com/spreadsheet/ccc ... eHc#gid=27 (- 08/10/2012 - 04:05 AM - GTM+2-)
- Support now: Characters, Stages, DLC and User-Prompt update

This tool will extract/decrypt files of DOA5 and rename them automatically or manually
You just need to put the folder ( doa5_tool ) in the DOA5 folder OR the dlc "root" folder (where .bin and .lnk are) OR to just "browse" your folder for updating unknown names


Link to the tool -->
http://www.mediafire.com/?7t1kdsy9t421h9n

Link to the ultimate folder tool of DOA/NG -->
http://www.mediafire.com/?sbd2c9r8ok3u3

Edit:The ultimate folder tool of DOA/NG have been actualized and optimized

PS: This tool contains work from chroxx & others Xentax user too.
## Post #135
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-11-09T14:30:58+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

In this case, it's better to PM me, since I'm the owner of this folder on MEDIAFIRE and the owner of this tool.  =)


Problem is, I can't upload the tool here since the maximum allowed size is 256 KiB.


Here your mirror: --> [http://www.sendspace.com/file/8an0m7](http://www.sendspace.com/file/8an0m7)
## Post #136
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2013-11-10T02:37:41+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

thanks, will that work on DOA5 Ultimate or do I need the other version ?
## Post #137
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-10T03:05:23+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from rmezatang
>
> thanks, will that work on DOA5 Ultimate or do I need the other version ?

Check the DOA5 models thread for the method of extraction.
## Post #138
- Username: synce
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 01, 2012 2:26 pm
- Post datetime: 2014-05-22T07:38:07+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Does anyone know if it's possible to extract and play any of the audio files from DOA5/5U? I'm interested in the voice data
## Post #139
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-05-22T17:33:01+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

> Reply from synce
>
> Does anyone know if it's possible to extract and play any of the audio files from DOA5/5U? I'm interested in the voice data

Are reffering to the XWS files?? I tried last week with some tools and I got nothing.
## Post #140
- Username: Mizukichi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 14, 2014 3:57 am
- Post datetime: 2014-11-06T19:20:14+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Hello all. Anyone know, where there may be files that are responsible for the text? I want extract text from the game and translate him for other language.
## Post #141
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2023-07-06T07:51:15+00:00
- Post Title: Re: Dead or Alive 5 (DOA5) Retail (X360 / PS3)

Hi,
I'm trying to decrypt doa5lr ps4 version.
I cant extract files from bin/lnk archive and I think that the decryption method is different...
can someone help?
here there is a screenshot of the first bytes of the first file in chara_common.lnk
@chrrox
[Capture.PNG](https://xentaxbackup.github.io/file/24025_Capture.PNG)
