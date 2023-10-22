## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-17T12:02:07+00:00
- Post Title: The Testament of Sherlock Holmes (*.PAK)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

goto -0x4
get TABLEOFFSET long
goto TABLEOFFSET
get VERSION byte
get TABLEZSIZE long
get TABLESIZE long
savepos TABLENEWOFFSET

clog MEMORY_FILE TABLENEWOFFSET TABLEZSIZE TABLESIZE

get FILES long MEMORY_FILE
math FILES *= 2

for i = 0 < FILES
     get TYPE long MEMORY_FILE
     get NSZIE short MEMORY_FILE
     getdstring NAME NSZIE MEMORY_FILE
     get OFFSET long MEMORY_FILE
     get SIZE long MEMORY_FILE
     get FLAG long MEMORY_FILE
     get TIMESTAMP longlong MEMORY_FILE
     log NAME OFFSET SIZE
next i
```
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-11-07T08:54:37+00:00
- Post Title: The Testament of Sherlock Holmes (*.PAK)

This script does not work for PC and also not for X360....
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-07T12:40:46+00:00
- Post Title: The Testament of Sherlock Holmes (*.PAK)

> Reply from michalss
>
> This script does not work for PC
Explain! Errors ? or what ?
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-11-07T13:33:27+00:00
- Post Title: The Testament of Sherlock Holmes (*.PAK)

> Reply from Ekey
>
> michalss wrote:This script does not work for PC
Explain! Errors ? or what ?

Sorry Ekey. Getting this:

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file xxxxxxxxxxxxxxxxxxxxx\en.pak
- open script sherlock.bms
- set output folder Extr

  offset   filesize   filename
------------------------------
  00000000 190544     locale
  00000026 0          t4@loc♠

- it's not possible to create that file due to its filename or related
  incompatibilities (for example already exists a folder with that name), so
  now you must choose a new filename for saving it.
  - old: t4@loc♠
  - new: tttttt

- 2 files found in 4 seconds
```


SImple start ask me for a new filename and the close...... Also sent you to PM 2 pak files. Please have a look. Thx
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-11-08T20:54:16+00:00
- Post Title: The Testament of Sherlock Holmes (*.PAK)

can you please fix it ?
## Post #6
- Username: AntonyS
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 28, 2012 3:11 am
- Post datetime: 2013-01-20T16:07:27+00:00
- Post Title: The Testament of Sherlock Holmes (*.PAK)

Hello! I've just kinda fixed Ekey's script, now it extracts all the files in archive. Here's the code:

```
#
# Written by Ekey (h4x0r)
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org

# script remade by AntonyS

goto -0x4
savepos LAST_TABLE_END
get TABLEOFFSET long
goto TABLEOFFSET


do
  get VERSION byte
  get TABLEZSIZE long
  get TABLESIZE long
  savepos TABLENEWOFFSET
  clog  MEMORY_FILE TABLENEWOFFSET TABLEZSIZE TABLESIZE
//  clog  "111.dmp" TABLENEWOFFSET TABLEZSIZE TABLESIZE
  set CURTABLEOFFSET TABLENEWOFFSET
  print "%CURTABLEOFFSET%"

  set CUR_POS  0
  do 
    set DIR_NAME string ""
    set NAME string ""
    set EXTENSION string ""
    get FILES long MEMORY_FILE
    savepos CUR_POS MEMORY_FILE
    for i = 0 < FILES
      callfunction GetFileInfo 1
    next i
    callfunction GetDirAndExtInfo 1
    goto CUR_POS MEMORY_FILE
    for i = 0 < FILES
      callfunction GetFileInfo 1
      set FULL_NAME string ""
      if DIR_NAME != ""
        string FULL_NAME = DIR_NAME
        string FULL_NAME += \
      endif
      string FULL_NAME += NAME
      if EXTENSION != ""
        string FULL_NAME += EXTENSION
      endif
      log FULL_NAME OFFSET SIZE
//    log NAME OFFSET SIZE
    next i
    callfunction GetDirAndExtInfo 1   
    savepos CUR_POS MEMORY_FILE
  while CUR_POS != TABLESIZE
  math CURTABLEOFFSET += TABLEZSIZE
  goto CURTABLEOFFSET
while CURTABLEOFFSET != LAST_TABLE_END

startfunction GetFileInfo 
      get DUMMY1 short MEMORY_FILE
      get DUMMY2 short MEMORY_FILE
      get NSZIE short MEMORY_FILE
      getdstring NAME NSZIE MEMORY_FILE
      get OFFSET long MEMORY_FILE  
      get SIZE long MEMORY_FILE
      get FLAG long MEMORY_FILE
      get TIMESTAMP longlong MEMORY_FILE
endfunction

startfunction GetDirAndExtInfo 
    get DUMMY_SIZE short MEMORY_FILE
    getdstring DUMMY_EXT_DIR DUMMY_SIZE MEMORY_FILE
    get EXT_SIZE short MEMORY_FILE
    getdstring EXTENSION EXT_SIZE MEMORY_FILE
    get DIRNAME_SIZE short MEMORY_FILE
    getdstring DIR_NAME DIRNAME_SIZE MEMORY_FILE
    get DUMMY short MEMORY_FILE
endfunction

```
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-01-21T15:18:11+00:00
- Post Title: The Testament of Sherlock Holmes (*.PAK)

thank you. Can you also pls have a look on loc_en.pakx files ? It is for Xbox360 ??? I can send it over PM if would like to help.

thank you
## Post #8
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2013-01-30T13:44:54+00:00
- Post Title: The Testament of Sherlock Holmes (*.PAK)

For the PC version, you can use Bacter tools.

[viewtopic.php?f=10&t=3453&start=15&hili ... ock+Holmes](http://forum.xentax.com/viewtopic.php?f=10&t=3453&start=15&hilit=Sherlock+Holmes)
