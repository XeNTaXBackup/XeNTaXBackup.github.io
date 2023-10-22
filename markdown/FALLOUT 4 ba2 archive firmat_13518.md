## Post #1
- Username: sucubus2049
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 23, 2015 8:23 am
- Post datetime: 2015-11-10T00:04:04+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

I'm sorry if the topic is not created where needed, but would like to appeal to the masters from this forum help unpack ba2 archives
Example game archive
[https://mega.nz/#!TIdEDaSL!Gq84-jzjD073 ... i9dn8K4WHE](https://mega.nz/#!TIdEDaSL!Gq84-jzjD073CBatOX2nuSgU1TxL3f9cji9dn8K4WHE)
## Post #2
- Username: sucubus2049
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 23, 2015 8:23 am
- Post datetime: 2015-11-10T00:40:12+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

tnx Ekey for that, qbms file here

```
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "BTDX"
get VERSION long
idstring "GNRL"
get FILES long
get NAMES_TABLE_OFFSET long
get NULL long
savepos TEMP

goto NAMES_TABLE_OFFSET
for i = 0 < FILES
  get NSIZE short
  getdstring NAME NSIZE
  putarray 0 i NAME
next i

goto TEMP
for i = 0 < FILES
    get DUMMY long
    getdstring EXT 4
    get DUMMY long
    get DUMMY long
    get OFFSET long
    get NULL long
    get ZSIZE long
    get SIZE long
    get DUMMY long
    getarray NAME 0 i
   
    if ZSIZE == SIZE
       log NAME OFFSET ZSIZE
    else
       clog NAME OFFSET ZSIZE SIZE
    endif
next i

```
## Post #3
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-11-10T04:58:16+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

Thanks for this, it works fine with .ba2 files of sounds but it doesn't works with .ba2 files of textures, so can someone pls fix this script to work with textures files as well ?
## Post #4
- Username: Eiwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 21, 2011 10:06 am
- Post datetime: 2015-11-10T08:08:42+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

Yes, thanks. Fallout 4 doesn't seem to read loose files though so I'm being an idiot trying to figure out how to repack
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-10T10:17:45+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

Also im gonna work on repacker i guess
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-10T14:18:50+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

> Reply from TheRanger
>
> Thanks for this, it works fine with .ba2 files of sounds but it doesn't works with .ba2 files of textures, so can someone pls fix this script to work with textures files as well ?

change

```
idstring "GNRL"
```


to 

```
get MAGIC long
```
## Post #7
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-11-10T15:54:19+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

> Reply from Ekey
>
> TheRanger wrote:Thanks for this, it works fine with .ba2 files of sounds but it doesn't works with .ba2 files of textures, so can someone pls fix this script to work with textures files as well ?

change
Code: Select allidstring "GNRL"

to 
Code: Select allget MAGIC long

Still doesn't works bro, :-



I am trying something but if you can solve it then please do it.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-10T16:46:16+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

Use this script [http://aluigi.altervista.org/bms/filecutter.bms](http://aluigi.altervista.org/bms/filecutter.bms) and upload cutted parts.
## Post #9
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-11-10T16:56:02+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

> Reply from Ekey
>
> Use this script http://aluigi.altervista.org/bms/filecutter.bms and upload cutted parts.

Here it is :-

```
http://www.solidfiles.com/d/5f4d660881/
```


That file had .ba2 extension.
## Post #10
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-10T17:17:08+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

im working on correct repacker, unpack is completely done, problem is ekey that textures has a bit different structure.
## Post #11
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-11-10T17:33:19+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

> Reply from michalss
>
> im working on correct repacker, unpack is completely done, problem is ekey that textures has a bit different structure.

Please make command-line tools as well.
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-10T20:32:40+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

Here is my beta Unpacker : 
```
https://dl.dropboxusercontent.com/u/38234344/F4%20Tools%20V1.rar
```

Should work with all types, except Textures = will be tommorow + basic repack.. 

> Reply from TheRanger
>
> im working on correct repacker, unpack is completely done, problem is ekey that textures has a bit different structure.

Please make command-line tools as well.
Yes i can do that as well...
## Post #13
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-11-11T07:12:43+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

> Reply from michalss
>
> Here is my beta Unpacker : Code: Select allhttps://dl.dropboxusercontent.com/u/38234344/F4%20Tools%20V1.rar
Should work with all types, except Textures = will be tommorow + basic repack.. 
TheRanger wrote:im working on correct repacker, unpack is completely done, problem is ekey that textures has a bit different structure.

Please make command-line tools as well.
Yes i can do that as well...

That's so kind of you, waiting for command-line tools.
## Post #14
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-11T22:22:53+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

New Version supporting Texture files (yet without the header)

```
https://dl.dropboxusercontent.com/u/38234344/F4%20Tools%20v2.0.rar
```

[F4 Tools v2.0.rar](https://xentaxbackup.github.io/file/9997_F4 Tools v2.0.rar)
## Post #15
- Username: TheRanger
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-12T14:43:11+00:00
- Post Title: FALLOUT 4 ba2 archive firmat

A new version V3, can extract all archives, also Textures include headers 
[F4 ToolsV3.rar](https://xentaxbackup.github.io/file/9999_F4 ToolsV3.rar)
## Post #16
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-11-12T15:39:06+00:00
- Post Title: Re: FALLOUT 4 ba2 archive firmat

> Reply from michalss
>
> A new version V3, can extract all archives, also Textures include headers

Waiting for repacker
## Post #17
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-12T16:07:35+00:00
- Post Title: Re: FALLOUT 4 ba2 archive firmat

is there any program that can open/convert those .nif files? they wont load into nifskope :/
## Post #18
- Username: TheRanger
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-12T16:32:28+00:00
- Post Title: Re: FALLOUT 4 ba2 archive firmat

> Reply from TheRanger
>
> michalss wrote:A new version V3, can extract all archives, also Textures include headers 

Waiting for repacker

I guess tommorow for GNRL files..
## Post #19
- Username: TheRanger
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-11-12T20:12:51+00:00
- Post Title: Re: FALLOUT 4 ba2 archive firmat

pipboy.jpg (8.33 KiB) Viewed 204 times
## Post #20
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-13T12:46:13+00:00
- Post Title: Re: FALLOUT 4 ba2 archive firmat

I have add specific thread for my tool in here: [viewtopic.php?f=32&t=13531](http://forum.xentax.com/viewtopic.php?f=32&t=13531)

BTW added support for repacker of GNRL files    still WIP!!
## Post #21
- Username: coolkid
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-21T08:34:33+00:00
- Post Title: Re: FALLOUT 4 ba2 archive firmat

These NIF files are practically the same as Skyrim, it only took a couple of hours with one to get it loading in Noesis. Only real difference is that geo is now embedded in BSTriShape instead of having a data link.

I'll probably put a build out sometime this weekend that supports it. (dumping archives+textures and loading up the DX10-fourcc dds's with the models is also working)
## Post #22
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-21T10:49:18+00:00
- Post Title: Re: FALLOUT 4 ba2 archive firmat

> Reply from MrAdults
>
> These NIF files are practically the same as Skyrim, it only took a couple of hours with one to get it loading in Noesis. Only real difference is that geo is now embedded in BSTriShape instead of having a data link.

I'll probably put a build out sometime this weekend that supports it. (dumping archives+textures and loading up the DX10-fourcc dds's with the models is also working)

You are awesome!
