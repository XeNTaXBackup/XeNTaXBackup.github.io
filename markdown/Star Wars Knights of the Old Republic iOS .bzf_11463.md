## Post #1
- Username: Shurtugal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 04, 2013 1:38 am
- Post datetime: 2014-04-28T23:54:56+00:00
- Post Title: Star Wars Knights of the Old Republic iOS ".bzf"

I would like to request support for the "bzf" file format for this game. I believe it contains either .bif or .2da files. I am unsure of what the files were on the PC version atm. The bzf files are located in the data folder just like in the PC version. I have source code  for an old Linux project meant to extract these files. I was able to port it to iOS but unfortunately it does not recognize these bzf files. However I came across an open source implementation of the Bioware Aurora engine. and one of the headers deals with decompressing the zip files. I however am not knowledgeable enough to make use of it. Perhaps you might be able to.

Linux Project: [http://sourceforge.net/projects/biounzi ... /biounzip/](http://sourceforge.net/projects/biounzip/files/biounzip/)
OpenSource Reimplementation of Bioware  Aurora Engine: [https://github.com/xoreos/xoreos/blob/m ... /zipfile.h](https://github.com/xoreos/xoreos/blob/master/src/common/zipfile.h)
One of the bzf files: [https://www.mediafire.com/?75jo6pzgaatior1](https://www.mediafire.com/?75jo6pzgaatior1) [119KB]

That's currently all the information I have. If I find anything new that might help I shall add it here.

Edit: forgot to include sample file.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-01T06:43:20+00:00
- Post Title: Star Wars Knights of the Old Republic iOS ".bzf"

Simple script

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype LZMA_DYNAMIC

idstring "BIFFV1\x20\x20"
get FILES long
get NULLS long
get DUMMY long
get PACKSIZE ASIZE
set j FILES
math j -= 1

for i = 0 < FILES
    get FILEID long
    get OFFSET long
    get SIZE long
    get DUMMY long
    savepos TEMP
	
	if i == j
	   set ZSIZE PACKSIZE
	   math ZSIZE - OFFSET
	   clog "" OFFSET ZSIZE SIZE
	else
	   get FILEID2 long
	   get OFFSET2 long
	   get SIZE2 long
	   get DUMMY2 long
	
	   math OFFSET2 -= OFFSET
	   set ZSIZE OFFSET2
	   clog "" OFFSET ZSIZE SIZE
	endif
	goto TEMP
next i
```
## Post #3
- Username: Shurtugal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 04, 2013 1:38 am
- Post datetime: 2014-05-01T12:54:07+00:00
- Post Title: Star Wars Knights of the Old Republic iOS ".bzf"

> Reply from Ekey
>
> Simple script
Code: Select all# Star Wars Knights of the Old Republic (iOS) (BZF format)
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype LZMA_DYNAMIC

idstring "BIFFV1\x20\x20"
get FILES long
get NULLS long
get DUMMY long
get PACKSIZE ASIZE
set j FILES
math j -= 1

for i = 0 < FILES
    get FILEID long
    get OFFSET long
    get SIZE long
    get DUMMY long
    savepos TEMP
	
	if i == j
	   set ZSIZE PACKSIZE
	   math ZSIZE - OFFSET
	   clog "" OFFSET ZSIZE SIZE
	else
	   get FILEID2 long
	   get OFFSET2 long
	   get SIZE2 long
	   get DUMMY2 long
	
	   math OFFSET2 -= OFFSET
	   set ZSIZE OFFSET2
	   clog "" OFFSET ZSIZE SIZE
	endif
	goto TEMP
next i
Thank you so much. I am unfamiliar with this tool however so I have a question. It does work great, but is it possible to extract the files with their actual names or am i mistaken and that these are their real names?
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-01T19:23:37+00:00
- Post Title: Star Wars Knights of the Old Republic iOS ".bzf"

Archives not contain real names, only ID's.
