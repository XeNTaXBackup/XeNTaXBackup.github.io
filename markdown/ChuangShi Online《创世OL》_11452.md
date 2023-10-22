## Post #1
- Username: lumis
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Dec 01, 2013 4:32 am
- Post datetime: 2014-04-24T17:53:05+00:00
- Post Title: ChuangShi Online《创世OL》

Client unpacked with help of luigi's quick bms script, maybe someone would take a look at those files.


Game trailer
[https://www.youtube.com/watch?v=4zFf3MiubTU](https://www.youtube.com/watch?v=4zFf3MiubTU)

File samples
[http://www.multiupfile.com/f/500fe8d4](http://www.multiupfile.com/f/500fe8d4)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-24T20:34:24+00:00
- Post Title: ChuangShi Online《创世OL》

using hex2obj (view link in my sig):



ChuangShi.JPG (115.61 KiB) Viewed 148 times



h2o file for 2nd submesh of 00000a1b.dat:

0x5C20 1272
Vb1
29 16
0x375C 322
020000
0x0 255

A VB size of 29 is somewhat strange. Never seen this before...
(For the weapon it's 32.)
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-04-25T07:01:44+00:00
- Post Title: ChuangShi Online《创世OL》

Where to find the unpack BMS script!?
## Post #4
- Username: lumis
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Dec 01, 2013 4:32 am
- Post datetime: 2014-04-25T17:15:51+00:00
- Post Title: ChuangShi Online《创世OL》

> Reply from fatduck
>
> Where to find the unpack BMS script!?

```
get OFFSET long
get FILES long
get DUMMY long
getdstring FOLDER 0x40
goto OFFSET
for i = 0 < FILES
	get DUMMY threebyte
	get TYPE byte
	get DUMMY long
	get OFFSET long
	get SIZE long
	savepos TMP
	goto OFFSET
	if TYPE & 0x10
		get DUMMY byte
		get XSIZE long
		reverselong XSIZE
		savepos OFFSET
		comtype lzo1x
		clog "" OFFSET SIZE XSIZE
	else
		log "" OFFSET SIZE
	endif
	goto TMP
next i
```
