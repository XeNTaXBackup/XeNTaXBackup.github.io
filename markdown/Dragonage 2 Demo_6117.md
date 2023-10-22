## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-21T17:33:20+00:00
- Post Title: Dragonage 2 Demo

Here is an extractor for the files in dragon age 2 its not perfect yet i need to add more extensions but it gets the job done.

```
get off long
get files long
get unk09 long
set mainoff 0x30
math mainoff + off
goto mainoff
comtype inflate
for i = 0 < files
set name i
get null01 long
get unk01 long
get unk02 long
get ext long
if ext == 1131896374
set ext PHY
endif
if ext == 663550188
set ext MMI
endif
if ext == 746452407
set ext MESH
endif
if ext == 1048449626
set ext XML
endif
if ext == 1067198654
set ext ANBT
endif
if ext == 1114824674
set ext RML
endif
if ext == 1115560169
set ext MMH
endif
if ext == 395652716
set ext DDS
endif
if ext == 579662031
set ext GAD
endif
if ext == 932389276
set ext EVT
endif
if ext == 1067198645
set ext ANI
endif

string name + .
string name + ext
get offset long
get zsize long
get size long
if zsize == size
log name offset size
else
math offset + 1
math zsize - 1
clog name offset zsize size
endif
next i

```
## Post #2
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2011-02-21T18:28:54+00:00
- Post Title: Dragonage 2 Demo

Awesome Chrrox , but just curius the demo its from 360 or PS3 version?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-21T18:53:55+00:00
- Post Title: Dragonage 2 Demo

PC
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-22T10:41:48+00:00
- Post Title: Dragonage 2 Demo

updated script to add model name support makes it much easier looking at the model names.

```
get off long
get files long
get unk09 long
set mainoff 0x30
math mainoff + off
goto mainoff
comtype inflate
for i = 0 < files
set name i
get null01 long
get unk01 long
get unk02 long
get ext long
if ext == 1131896374
set ext PHY
endif
if ext == 663550188
set ext MMI
endif
if ext == 1048449626
set ext XML
endif
if ext == 1067198654
set ext ANBT
endif
if ext == 1114824674
set ext RML
endif
if ext == 1115560169
set ext MMH
endif
if ext == 395652716
set ext DDS
endif
if ext == 579662031
set ext GAD
endif
if ext == 932389276
set ext EVT
endif
if ext == 1067198645
set ext ANI
endif

string name + .
string name + ext
get offset long
get zsize long
get size long
if ext == 746452407
math offset + 1
math zsize - 1
clog MEMORY_FILE offset zsize size
goto 0x1A0 MEMORY_FILE
get nameoff long MEMORY_FILE
math nameoff + 0x1A0
goto nameoff MEMORY_FILE
get nsize long MEMORY_FILE
math nsize * 2
getdstring UNAME nsize MEMORY_FILE
set NAME unicode UNAME
endif
if zsize == size
log name offset size
else
if ext == 746452407
else
math offset + 1
math zsize - 1
endif
clog name offset zsize size
endif

next i

```

[test3.jpg](https://xentaxbackup.github.io/file/3969_test3.jpg)
## Post #5
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2011-02-22T21:22:28+00:00
- Post Title: Dragonage 2 Demo

Nice update Chrrox , but just curius ¿In wich files are the models?
i found some CRF and other files? and this script it for bms or max?

Thanks in advance.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-22T21:46:10+00:00
- Post Title: Dragonage 2 Demo

the one big archive its like 700mb
