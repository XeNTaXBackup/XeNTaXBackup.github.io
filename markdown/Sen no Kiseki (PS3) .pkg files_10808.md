## Post #1
- Username: taezou
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 26, 2013 4:21 am
- Post datetime: 2013-09-26T15:00:00+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

The data in this game is first stored in a very large .psarc file, which I was able to extract using existing tools. Inside that are a lot of different files, with the data I'm personally interested in (the game's script) stored in .pkg files.

Here are some images of one of the files. First one shows the header and what is clearly a file list, and the second one is scrolled down to where I believe the data starts.

[](http://imgur.com/vRuxS3H) [](http://imgur.com/7SMG79x)

And here's a much smaller one with fewer files:

[](http://imgur.com/WlrWY0Y)

A cursory glance at the script makes me think that the files could possibly be compressed, but if they are, it's lightly if at all, since a lot of the script is viewable in shift-JIS, with just some oddities.

Any help anyone can give with this would be greatly appreciated.
## Post #2
- Username: taezou
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 26, 2013 4:21 am
- Post datetime: 2013-09-27T00:25:54+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

Well, I managed to figure out a bit about the format of the .pkg file itself and extract each file. Here's the crappy QuickBMS script I wrote for that.

```

get FILES long

for i = 0 < FILES
	getdstring FILENAME 0x40
	get UNCSIZE long
	get SIZE long
	get DUMMY long
	get DUMMY long
	PutArray i 0 FILENAME
	PutArray i 1 SIZE
	PutArray i 2 UNCSIZE
next i

math OFFSET = FILES
math OFFSET * 80
math OFFSET + 8
math OFFSET + 0x2F # 0x2F works for scena.pkg and talk.pkg, 0x2B needed for ui.pkg for some reason

for i = 0 < FILES
	GetArray FILENAME i 0
	GetArray SIZE i 1
	GetArray UNCSIZE i 2
	log FILENAME OFFSET SIZE
	math OFFSET + SIZE
next i
```


Unfortunately, the individual files seem to be very lightly compressed. The file table in the header seems to include two size fields, one for the compressed size, and one for the uncompressed size.

I tried using comtype_scan2 with no useful results, at least at first-glance. I really have no idea how to go about determining compression methods. I know I can't link any of the actual files from the game here, so I'm not sure what to do next in seeking assistance. :\
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-27T12:45:02+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

Very similar on series of LZ
## Post #4
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-27T14:11:49+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

There are errors.

Error: incomplete input file number 0, can't read 47 bytes.
## Post #5
- Username: taezou
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 26, 2013 4:21 am
- Post datetime: 2013-09-27T14:41:48+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

That error is just because I was lazy and it tries to seek past the end of the file. You still get all of the files out of it.

As for the compression being LZ-related, is that affected by whether the header is on the files or not? I wonder if I need to run the compression finder on the files without the filename header each file has in order to get correct results. I really know basically nothing at all about compression. :\
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-27T19:46:30+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

Well you can send me 2-3 example pkg's ?
## Post #7
- Username: taezou
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 26, 2013 4:21 am
- Post datetime: 2013-09-27T22:08:47+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

Let me know if you find anything, Ekey.

I am pretty sure my QuickBMS script is slightly wrong, starting the file extraction at the wrong place. I'm not sure exactly where the start of the first file is supposed to be.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-28T08:18:22+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

Simple script.. About compression currently is unknown.

```
#
# Written by Ekey (h4x0r)
# http://forum.xentax.com
#
# script for QuickBMS http://quickbms.aluigi.org

goto 0x4
get FILES long

for i = 0 < FILES
    getdstring NAME 0x40
    get SIZE long
    get ZSIZE long
    get OFFSET long
    get TYPE long
    log NAME OFFSET ZSIZE
next i
```
## Post #9
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-28T10:02:10+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

> Reply from Ekey
>
> Simple script.. About compression currently is unknown.
Code: Select all# Sen no Kiseki (PS3) (PKG format) 0.1
#
# Written by Ekey (h4x0r)
# http://forum.xentax.com
#
# script for QuickBMS http://quickbms.aluigi.org

goto 0x4
get FILES long

for i = 0 < FILES
    getdstring NAME 0x40
    get SIZE long
    get ZSIZE long
    get OFFSET long
    get TYPE long
    log NAME OFFSET ZSIZE
next i

Exactly, what is WQSG..? I can't understand chinese..
I requested the unpacked file from chinese hacker. And download it.
The post thread is.. [http://www.pujiahh.com/topic/1745/](http://www.pujiahh.com/topic/1745/)
He uses Python code. But don't know about the  compression.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-28T12:42:23+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

If you can get the code i am sure it can be added to quickbms.
The current decompressors that produce close results are
COMP_TDCB_lzw15v,
COMP_SCUMMVM34
COMP_COMPRLIB_RLE4
COMP_COMPRLIB_RLE1
so its most likely some kind of RLE
## Post #11
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-28T13:06:42+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

> Reply from chrrox
>
> If you can get the code i am sure it can be added to quickbms.
The current decompressors that produce close results are
COMP_TDCB_lzw15v,
COMP_SCUMMVM34
COMP_COMPRLIB_RLE4
COMP_COMPRLIB_RLE1
so its most likely some kind of RLE

I try to persuade him.. But I'm not sure if he would release the Python code.
## Post #12
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-28T13:41:43+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

> Reply from chrrox
>
> If you can get the code i am sure it can be added to quickbms.
The current decompressors that produce close results are
COMP_TDCB_lzw15v,
COMP_SCUMMVM34
COMP_COMPRLIB_RLE4
COMP_COMPRLIB_RLE1
so its most likely some kind of RLE

Would it be help..?

For example,
1) font.pkg file(1,833,491byte) contains font.itf, sjisutf8.dat, utf8sjis.dat
2) Extracted by quickbms => 1,833,243byte = font.itf + sjisutf8.dat + utf8sjis.dat
3) Extracted by chinease programmer => 2,310,138byte = font.bin + sjisutf8.bin + utf8sjis.bin

Image is too large..

<Extracted by quickbms> - sjisutf8.dat
[http://postimg.org/image/kvacnk1u9/](http://postimg.org/image/kvacnk1u9/)

<Delete> 24 87 00 00 E3 72 00 00 01 00 00 00
[http://postimg.org/image/h06ykzioh/](http://postimg.org/image/h06ykzioh/)

<Extracted by chinease programmer> - sjisutf8.bin
[http://postimg.org/image/4vlwqb2lx/](http://postimg.org/image/4vlwqb2lx/)
## Post #13
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-29T01:20:03+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

I get the code. But would it be possible write python code in quickbms..? And write repacking bms script..?
The python code only uncompressed *.dat files to *.bin files.
## Post #14
- Username: taezou
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 26, 2013 4:21 am
- Post datetime: 2013-09-29T02:33:25+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

What Python code?
## Post #15
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-29T04:00:06+00:00
- Post Title: Sen no Kiseki (PS3) .pkg files

..
## Post #16
- Username: taezou
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 26, 2013 4:21 am
- Post datetime: 2013-09-29T05:35:08+00:00
- Post Title: Re: Sen no Kiseki (PS3) .pkg files

Oh, excellent, that takes care of all of the compression.
Did you get that from caoyang? I was trying to get him to give it to me but he wouldn't respond to me.
## Post #17
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-09-29T15:39:25+00:00
- Post Title: Re: Sen no Kiseki (PS3) .pkg files

> Reply from taezou
>
> Oh, excellent, that takes care of all of the compression.
Did you get that from caoyang? I was trying to get him to give it to me but he wouldn't respond to me.

Yes, I am.  
But python code won't repack *.bin files to *.dat files.
## Post #18
- Username: mailwl
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 18, 2014 4:20 pm
- Post datetime: 2015-04-15T15:48:40+00:00
- Post Title: Re: Sen no Kiseki (PS3) .pkg files

sorry for necropost, but how to decompress files in .pkg? Algo ID 1 and 3
## Post #19
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2015-04-15T22:54:48+00:00
- Post Title: Re: Sen no Kiseki (PS3) .pkg files

Here is my pkg tool for sen no kiseki...it will also decompress.
if you need the code let me know 
[senpkg.rar](https://xentaxbackup.github.io/file/9031_senpkg.rar)
## Post #20
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-04-17T19:12:24+00:00
- Post Title: Re: Sen no Kiseki (PS3) .pkg files

Was anyone ever able to view the extracted models/textures from the .pkg files or was it still not possible?
