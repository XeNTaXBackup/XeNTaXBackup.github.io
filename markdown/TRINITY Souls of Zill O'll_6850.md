## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-25T17:37:13+00:00
- Post Title: TRINITY: Souls of Zill O'll

This will extract the idx and bin files.

```
#TRINITY: Souls of Zill O'll
#from chrrox

endian big

open FDDE BIN 0
open FDDE IDX 1

savepos offset
set counter 0

for
set name counter
math counter + 1
goto offset
get size long 1
get zsize long 1
get zip long 1
if zip == 1
string name + .pak
else
string name + .unc
endif
if zsize != 0
if size == zsize
log name offset zsize
else
log name offset zsize
endif
math offset + zsize
goto offset
Padding 0x800
savepos offset

endif
next

```
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-25T23:40:27+00:00
- Post Title: TRINITY: Souls of Zill O'll

Its the same format as Dynasty Warriors 7
[trinity.png](https://xentaxbackup.github.io/file/4380_trinity.png)
## Post #3
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-07-15T03:25:40+00:00
- Post Title: TRINITY: Souls of Zill O'll

hi chrrox,what about the pak and unc files? thanks
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-15T11:05:02+00:00
- Post Title: TRINITY: Souls of Zill O'll

all you need to do is use the same methods used on dynasty warrior 7
## Post #5
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-07-15T16:26:55+00:00
- Post Title: TRINITY: Souls of Zill O'll

the LINKDATA.bin is extract  pak and unc files but not the one big archive file like DW7,so i don't know which script could use on both of them,more details?thanks
## Post #6
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2012-03-02T17:37:36+00:00
- Post Title: TRINITY: Souls of Zill O'll

Hi everyone.

I been try to extract the model of this game a few days now, But I could't get anything but four .g1t files. Please help me and tell me what I did wrong.

First, I extract the contents of the DVD using Xbox Image Browser and got: EBOOT.BIN, LINKDATA.BIN and LINKDATA.IDX.
Then use quickbms script that posted at the top onto the LINKDATA.BIN or LINKDATA.IDX and got 4513 files of .pak and .unc (But mostly .pak)

Next, I download the "DW7 Files.7z" from Dynasty Warriors 7 / Warriors Legends of Troy topic (on the first post) and use the G1TG0060.BMS onto the 4513 files and I got 4 .g1t files extracted which are 1.g1t, 2.g1t, 3.g1t and i.g1t. For the G1M_0034.BMS script, I did not get anything extracted from the 4513 files I got. 

After I use the dds.BMS on the four .g1t files that extracted, I get some texture of ground about 256*256 size and some normal maps and also some Icons but so far no model is found. I am wondering if I did the right way please help.
## Post #7
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-01-30T16:03:41+00:00
- Post Title: TRINITY: Souls of Zill O'll

Script dont work with quickbms version 0.5.1 and high.

Very early avaliable on aluigi.org versions got "myfopen no such file or directory".
Latest version got error with line "open FDDE BIN 0" or "open FDDE IDX 1".

Be glad for explanations what need to do or script modification variant for modern versions of quickbms.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-30T21:12:13+00:00
- Post Title: TRINITY: Souls of Zill O'll

1) You need to update QuickBMS to latest version
2) Upload files (posible changes in format)
## Post #9
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-02-09T01:35:27+00:00
- Post Title: TRINITY: Souls of Zill O'll

i got ps3 version from BLES01184.
2 files called LINKDATA.BIN size 3,455,571,968 bytes
                 LINKDATA.IDX size 72,684 bytes

this is dynasty warrior 7 model file extraction bms script from chrros's post.

 G1M_0034.bms
  
```
for i
findloc start string "G1M_0034"
goto start
print "%start%"
savepos offset
getdstring null 0x8
get size long
set name i
string name + ".g1m"
log name offset size

next i
  
```


the files i extracted by script in this post give me 2 types of files extentions,.pak,.ukn.
I looked the content of it's hex data,can't find any string called "G1M_0034"
so,i'm thinking the some .pak files may be the model files,i'm testing some of them by chrros's DW7 maxscript atm.

and another ps3 game
Bladestorm: Nightmare
[http://koei.wikia.com/wiki/Bladestorm:_Nightmare](http://koei.wikia.com/wiki/Bladestorm:_Nightmare)
It's archieve data's extention is the same as this title. .BIN and .IDX.
