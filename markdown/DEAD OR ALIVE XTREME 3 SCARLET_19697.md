## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-03-22T15:33:57+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

Here is a quickbms script to extract this game.


```
#use quickbms
#http://aluigi.altervista.org/quickbms.htm
open FDSE "package_data.bin" 1
comtype zlib_noerror
goto 0x68 1
get FILES long 1
goto 0x80 1
get NSTART1 long 1
get LNKNAME1 long 1
get UNK long 1
get SEC3START long 1
math LNKNAME1 + 0x90
savepos TMP 1
goto LNKNAME1 1
get REMOVE string 1
string REMOVE + /
get LNKFILE string 1
string LNKFILE R REMOVE ""
open FDSE LNKFILE
goto TMP 1
for i = 0 < FILES
set MEMORY_FILE2 binary ""
set MEMORY_FILE3 binary ""
goto TMP 1
get HASH long 1
get UNK1 long 1
get NOFF long 1
get UNK2 long 1
get UNK3 long 1
get FLAG long 1
get UNK4 longlong 1
get UNK5 long 1
get UNK5 long 1
get FBASE long 1
savepos TMP 1
math NOFF + 0x90 1
math NOFF + NSTART1 1
goto NOFF 1
get NAME string 1
#print "%NAME%"
math FBASE * 0x20
math FBASE + 0x20
    goto FBASE
    get OFFSET longlong
    get SIZE longlong
    get ZSIZE longlong
    get COMP longlong
    #print "1 %OFFSET% %SIZE% %ZSIZE% %COMP%"
    if SIZE > ZSIZE
      log MEMORY_FILE2 OFFSET ZSIZE
      append
      do
        get CSIZE long MEMORY_FILE2
        savepos COFF MEMORY_FILE2
        #print "Yay %SIZE% %COFF% %CSIZE%"
        if SIZE > 0x4000
          math CSIZE & 0x7FFF
          #print "%COFF% %CSIZE%"
          clog MEMORY_FILE3 COFF CSIZE 0x4000 MEMORY_FILE2
          math SIZE - 0x4000
          math COFF + CSIZE
          goto COFF MEMORY_FILE2
          padding 16 MEMORY_FILE2
        else
          math CSIZE & 0x7FFF
          clog MEMORY_FILE3 COFF CSIZE SIZE MEMORY_FILE2
          math SIZE - SIZE
        endif
      while SIZE > 0
    append
    get TSIZE asize MEMORY_FILE3
    log NAME 0 TSIZE MEMORY_FILE3
    else
      log NAME OFFSET ZSIZE
    endif
next i

```
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-03-23T15:37:01+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

Here is a script to extract the ktss files from the xhs files.
You can then play them with vgmstream

```
#use quickbms
#http://aluigi.altervista.org/quickbms.htm
get ARC basename
goto 0x14
get FILES long
savepos TMP
for i = 0 < FILES
goto TMP
get OFFSET long
savepos TMP
goto OFFSET
get NULL long
get SIZE long
set NAME ARC
string NAME + i
string NAME + .ktss
log NAME OFFSET SIZE
next i

```
## Post #3
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2019-03-23T17:32:27+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

Hi chrrox, these scripts work on which version, ps4 or Switch?
## Post #4
- Username: TerryXX
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-03-23T18:56:19+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

switch version there is no way to get ps4 files.
## Post #5
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2019-03-23T23:00:17+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

Hi chrrox, so the version I have of the game the file ends with .nsp I extracted the files with a python script "nspx.py", but the files are not .bin I tried to rename but obviously your script gave me an error, I need to do some specific procedures to create these .bin files?
Thx.
## Post #6
- Username: TerryXX
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-03-24T10:49:12+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

You need to use hactool to extract to raw files.
just google extract nsp and the first result will give you tools.
you want version 1.6 of the bat file
NCA-NSP-XCI_TO_LayeredFS.bat
## Post #7
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2019-03-24T15:36:48+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

Sorry if I still bother you chrrox but I found yet another error  so I extracted the .bin file and renamed to package_data.bin, load quickbms_4gb_files select our script etc etc but this error happens: 

error in src\file.c line 487: fdnum_open()
Error= No such file or directory

Last script line before the error or that produced the error:
 20 open FDSE LNKFILE

Definitely I skip something but I don't know what
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-03-24T16:38:45+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

You should never need to rename any files they will show up when you extract the nca correctly
## Post #9
- Username: TerryXX
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 12, 2014 8:26 pm
- Post datetime: 2019-03-24T21:31:50+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

Eureka, after several attempts I understood what I was wrong I used the command Romfs.bin instead of Romfs Folder, I am trying to extract also the various dlc and for now everything seems to work, thx again chrrox.
## Post #10
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2019-03-26T12:35:58+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

@chrrox
How to open tmc/tmcl files of the game?
## Post #11
- Username: game01er
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 27, 2012 7:05 pm
- Post datetime: 2020-05-03T12:06:15+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

@chrrox: your scripts works fine, thank you. But how did you get the models in 3d program?
thanks
## Post #12
- Username: spiderjames
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 26, 2016 3:04 pm
- Post datetime: 2021-02-20T06:15:23+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

Sorry for necroing thread. Does any one has any ideas how to extract animation from .mpm files? Here is sample plus .tmcl
[http://www.mediafire.com/file/pbpjwalw5 ... e.rar/file](http://www.mediafire.com/file/pbpjwalw58epfsz/DOAX3mpmsample.rar/file)
## Post #13
- Username: MARK2580
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 13, 2014 2:29 pm
- Post datetime: 2022-06-12T13:17:24+00:00
- Post Title: DEAD OR ALIVE XTREME 3: SCARLET

I apologize that it is a little not about that game or platform but nevertheless.
I downloaded the "Dead Or Alive Xtreme 3: Fortune" files, unpacked the PS4 archives and got the familiar tmc/tmcl files. I was delighted and thought that a familiar script for Noesis (for doa5) would open them. But the script gives only an error and does not open anything. Am I doing something wrong? What version of DOAX3 can be fully "opened" and get levels from it, like a bedroom, a pool, an island, etc. ???
