## Post #1
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-04-21T22:42:32+00:00
- Post Title: Eador Masters of the Broken World .pac

How decompress these file : [http://mir.cr/0CKSJZRV](http://mir.cr/0CKSJZRV) 

- header : PACK 
- i have nothing found with sigsrch.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-22T00:42:23+00:00
- Post Title: Eador Masters of the Broken World .pac

it works on this file have no other files to compare with.

```
#quickbms script by chrrox
#extract .pac file
idstring "PACK"
get VER long
get TBLOFF longlong
get FILES longlong
goto TBLOFF
for i = 0 < FILES
filexor "0x98 0x83 0x84 0x8E 0x82 0x9F 0x83 0x92 0x9E 0x83 0x82 0x9A 0x8F 0x84 0x9F 0x89" TBLOFF
get OFFSET longlong
get SIZE longlong
get NSIZE long
get UNK long
getdstring NAME NSIZE
print "%NAME%"
filexor "0x98 0x83 0x84 0x8E 0x82 0x9F 0x83 0x92 0x9E 0x83 0x82 0x9A 0x8F 0x84 0x9F 0x89" OFFSET
log NAME OFFSET SIZE
next i


```
## Post #3
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-04-22T12:16:57+00:00
- Post Title: Eador Masters of the Broken World .pac

hi chrrox, and thx for bms, it works only on this file, so i cut few lines from data.000.pak (1.6Go)  [http://mir.cr/ZVQKTTMI](http://mir.cr/ZVQKTTMI) 

and update file data.002.pak v1.0.1 [http://mir.cr/1VGZRS5V](http://mir.cr/1VGZRS5V)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-22T20:01:20+00:00
- Post Title: Eador Masters of the Broken World .pac

fixed one line change.
## Post #5
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-04-23T05:03:21+00:00
- Post Title: Eador Masters of the Broken World .pac

Hi master Chrrox
Would you please tell how did you find xor key?(a tutorial maybe  )
thanks
## Post #6
- Username: deepshit
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-23T10:42:20+00:00
- Post Title: Eador Masters of the Broken World .pac

There is no tutorial I can give for this game.
I was able to find the xor key with just looking at the pac file.
It just comes with experience I did not reverse engineer the exe to get this key.
I look at the file table at the end of these and find patterns and use that to get the xor key.
step1. Be very bored.
step2. stare at the data for a while.
step3. find the pattern and start xoring with luigi's xor program to test.
step4. profit?
## Post #7
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-05-16T19:10:59+00:00
- Post Title: Eador Masters of the Broken World .pac

Hi, chroxx works like a charm, thx.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-06-13T05:53:06+00:00
- Post Title: Eador Masters of the Broken World .pac

Hi chroxx can you please post key as string ?

Also can you give me a bit explanation how exactly command filexor works please ? I'm new to xoring thing so i would need some kick  Do you think it is possible to build repacker pls?

From what i readed that you should save the file before you start decoding right ? Your script doing everything on the fly unfortunately i dont know the size of the files coz this longs are also xored 

thx
