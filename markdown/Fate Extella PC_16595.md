## Post #1
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-07-26T04:35:54+00:00
- Post Title: Fate Extella PC

Hoping to get an extractor (and eventually model/texture tools) for this game. I've uploaded 2 .rar files as samples. 

The "Main" .rar has 4 files: the 2 files kicked out by filecutter.bms from the main archive (which was over 3 GB in size), a *.pfs file and *.pkh file. These are the only files aside from video files in *.usm format. The *.pfs file when viewed with a hex editor seems to have file names in plain text but the others are completely garbled. The "DLC" .rar has a couple DLC files which are in the same formats as the main files only smaller so I could upload them in their complete form. 

Main files
[https://www.mediafire.com/?3noigy49u9z5u45](https://www.mediafire.com/?3noigy49u9z5u45)

DLC files
[https://www.mediafire.com/?kxubd079k0h463q](https://www.mediafire.com/?kxubd079k0h463q)
## Post #2
- Username: xrevo
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-26T10:08:30+00:00
- Post Title: Fate Extella PC

your samples were bad.
but i got samples and its the same format as vita games.

```
# script for QuickBMS http://quickbms.aluigi.org
#made by chrrox
get name basename
endian big
Open FDDE PK 0
Open FDDE pfs 1
Open FDDE pkh 2
goto 8 1
get FOLDERS long 1
get TFILES long 1

for i = 0 < FOLDERS
   get FOLDERID long 1
   get FOLDERPARENT long 1
   get UNK long 1
   get SUBFLDR long 1
   get FILESTART long 1
   get FOLDERFILES long 1
   #print "%FOLDERID% %FOLDERPARENT% %UNK% %SUBFLDR% %FILESTART% %FOLDERFILES%"
   PutArray 3 i FOLDERPARENT
   PutArray 4 i FILESTART
   PutArray 5 i FOLDERFILES
next i

for i = 0 < FOLDERS
   get FOLDERNAMEOFF long 1
   PutArray 0 i FOLDERNAMEOFF
next i

for i = 0 < TFILES
   get FILENAMEOFF long 1
   PutArray 1 i FILENAMEOFF
next i

savepos NAMEBASE 1

for i = 0 < FOLDERS
   GetArray FOLDERNAMEOFF 0 i
   math FOLDERNAMEOFF += NAMEBASE
   goto FOLDERNAMEOFF 1
   get FOLDERNAME string 1
   #print "%FOLDERNAME%"
   string FOLDERNAME l FOLDERNAME
   PutArray 2 i FOLDERNAME
next i

for i = 0 < TFILES
   GetArray FILENAMEOFF 1 i
   math FILENAMEOFF += NAMEBASE
   goto FILENAMEOFF 1
   get FILENAME string 1
   #print "%FILENAME%"
   string FILENAME l FILENAME
   PutArray 7 i FILENAME
next i

set MEMORY_FILE binary ""

for i = 0 < FOLDERS
   GetArray FOLDERNAME 2 i
   GetArray FOLDERPARENT 3 i
   GetArray FILESTART 4 i
   GetArray FOLDERFILES 5 i
   math FOLDERFILES += FILESTART
   set FOLDERBASE ""
   #print "%FOLDERPARENT% %FILESTART% %FOLDERFILES%"
   if FOLDERPARENT > 0
   GetArray FOLDERBASE 6 FOLDERPARENT
   string FOLDERBASE += /
   #print "%FOLDERNAME%"
   endif
   string FOLDERBASE += FOLDERNAME
   PutArray 6 i FOLDERBASE
   #print "%FOLDERBASE%"
   if FOLDERFILES > 0
      for a = FILESTART < FOLDERFILES
         set NAME FOLDERBASE
         GetArray FILE 7 a
         string NAME += /
         string NAME += FILE
         #print "%NAME%"
         PutArray 8 a NAME
         #Put NAME LINE MEMORY_FILE
         # calculate checksum
         encryption crc 0x04c11db7 "32 -1 -1 1 0 0"
         string NAME E= NAME
         encryption "" ""
         #print "CRC %QUICKBMS_CRC|x%"
         string TEST p= "0x%08x " QUICKBMS_CRC
         string TEST += NAME
         #print "%TEST%"
         Put TEST LINE MEMORY_FILE
      next a
   endif
next i

goto 0 MEMORY_FILE

get FILES long 2
for i = 0 < FILES
   #GetArray NAME 8 i
   get NAME_CRC long 2
   get OFFSET long 2
   get SIZE long 2
   get ZSIZE long 2
   NameCRC NAME NAME_CRC MEMORY_FILE 32
   if ZSIZE == 0
      log NAME OFFSET SIZE
   else
      clog NAME OFFSET ZSIZE SIZE
   endif
next i

```
## Post #3
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2017-07-27T06:50:10+00:00
- Post Title: Fate Extella PC

[download/file.php?mode=view&id=13149](http://forum.xentax.com/download/file.php?mode=view&id=13149)

i got a message like that ,somebody help?
[001.png](https://xentaxbackup.github.io/file/13149_001.png)
## Post #4
- Username: imarceldoe
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 28, 2016 9:55 pm
- Post datetime: 2017-08-02T23:44:26+00:00
- Post Title: Fate Extella PC

> Reply from pgw00k
>
> download/file.php?mode=view&id=13149

i got a message like that ,somebody help?
Same result.

Any ideas?
## Post #5
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-08-05T22:17:45+00:00
- Post Title: Fate Extella PC

You can try my [extractor tool](https://github.com/kotcrab/fate-explorer/releases/download/pk-v1.0/pktools.zip). Java 8 required. 
Drag and drop PK archive on bat file. Files will be in 'out' folder. If you have many of them (aka 33 DLCs) run from cmd: 

```
pktools.bat extractAll "gamefiles\resource\target\win\pack\mount\retail"
```
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-08-06T03:24:43+00:00
- Post Title: Fate Extella PC

They used -1 for some packages and quickbms reads stuff as unsigned so added a quick fix.

```
# script for QuickBMS http://quickbms.aluigi.org
#made by chrrox
get name basename
endian big
Open FDDE PK 0
Open FDDE pfs 1
Open FDDE pkh 2
goto 8 1
get FOLDERS long 1
get TFILES long 1

for i = 0 < FOLDERS
   get FOLDERID long 1
   get FOLDERPARENT long 1
   get UNK long 1
   get SUBFLDR long 1
   get FILESTART long 1
   get FOLDERFILES long 1
  #print "%FOLDERID% %FOLDERPARENT% %UNK% %SUBFLDR% %FILESTART% %FOLDERFILES%"
   PutArray 3 i FOLDERPARENT
   PutArray 4 i FILESTART
   PutArray 5 i FOLDERFILES
next i

for i = 0 < FOLDERS
   get FOLDERNAMEOFF long 1
   PutArray 0 i FOLDERNAMEOFF
next i

for i = 0 < TFILES
   get FILENAMEOFF long 1
   PutArray 1 i FILENAMEOFF
next i

savepos NAMEBASE 1

for i = 0 < FOLDERS
   GetArray FOLDERNAMEOFF 0 i
   math FOLDERNAMEOFF += NAMEBASE
   goto FOLDERNAMEOFF 1
   get FOLDERNAME string 1
   #print "%FOLDERNAME%"
   string FOLDERNAME l FOLDERNAME
   PutArray 2 i FOLDERNAME
next i

for i = 0 < TFILES
   GetArray FILENAMEOFF 1 i
   math FILENAMEOFF += NAMEBASE
   goto FILENAMEOFF 1
   get FILENAME string 1
   #print "%FILENAME%"
   string FILENAME l FILENAME
   PutArray 7 i FILENAME
next i

set MEMORY_FILE binary ""

for i = 0 < FOLDERS
   GetArray FOLDERNAME 2 i
   GetArray FOLDERPARENT 3 i
   GetArray FILESTART 4 i
   GetArray FOLDERFILES 5 i
   math FOLDERFILES += FILESTART
   set FOLDERBASE ""
   #print "%FOLDERPARENT% %FILESTART% %FOLDERFILES%"
   if FOLDERPARENT > 0
   if FOLDERPARENT < 4294967295
   GetArray FOLDERBASE 6 FOLDERPARENT
   string FOLDERBASE += /
   #print "%FOLDERNAME%"
   endif
   endif
   string FOLDERBASE += FOLDERNAME
   PutArray 6 i FOLDERBASE
   #print "%FOLDERBASE%"
   if FOLDERFILES > 0
      for a = FILESTART < FOLDERFILES
         set NAME FOLDERBASE
         GetArray FILE 7 a
         string NAME += /
         string NAME += FILE
         #print "%NAME%"
         PutArray 8 a NAME
         #Put NAME LINE MEMORY_FILE
         # calculate checksum
         encryption crc 0x04c11db7 "32 -1 -1 1 0 0"
         string NAME E= NAME
         encryption "" ""
         #print "CRC %QUICKBMS_CRC|x%"
         string TEST p= "0x%08x " QUICKBMS_CRC
         string TEST += NAME
         #print "%TEST%"
         Put TEST LINE MEMORY_FILE
      next a
   endif
next i

goto 0 MEMORY_FILE

get FILES long 2
for i = 0 < FILES
   #GetArray NAME 8 i
   get NAME_CRC long 2
   get OFFSET long 2
   get SIZE long 2
   get ZSIZE long 2
   NameCRC NAME NAME_CRC MEMORY_FILE 32
   if ZSIZE == 0
      log NAME OFFSET SIZE
   else
      clog NAME OFFSET ZSIZE SIZE
   endif
next i

```
## Post #7
- Username: RikuKH3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 26, 2012 7:37 am
- Post datetime: 2017-08-12T20:52:08+00:00
- Post Title: Fate Extella PC

Program to rebuild PK/PKH from extracted files:
[https://github.com/RikuKH3/extella_pack/releases](https://github.com/RikuKH3/extella_pack/releases)
## Post #8
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2019-03-05T14:29:21+00:00
- Post Title: Fate Extella PC

> Reply from Kotcrab ↑Sun Aug 06, 2017 6:17 am at Sun Aug 06, 2017 6:17 am
>
> 
You can try my extractor tool. Java 8 required. 
Drag and drop PK archive on bat file. Files will be in 'out' folder. If you have many of them (aka 33 DLCs) run from cmd: 
Code: Select allpktools.bat extractAll "gamefiles\resource\target\win\pack\mount\retail"
can anybody reupload this? kotcrab's github page is gone
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-05T16:23:06+00:00
- Post Title: Fate Extella PC

> Reply from tone ↑Tue Mar 05, 2019 10:29 pm at Tue Mar 05, 2019 10:29 pm
>
> can anybody reupload this? kotcrab's github page is gone
still there just different url it seems.   
[https://github.com/kotcrab/fate-explorer/releases](https://github.com/kotcrab/fate-explorer/releases)

[https://github.com/kotcrab?tab=repositories](https://github.com/kotcrab?tab=repositories)
## Post #10
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-04-25T19:34:54+00:00
- Post Title: Fate Extella PC

does anyone know how to make the script for noesis to work. thought i don't no if this normals issue is with the script or the tool used for extracting the models. Kotcrab himself said that the script he posted had normal issues so i think its the former. if anyone can help that would be appreciated
