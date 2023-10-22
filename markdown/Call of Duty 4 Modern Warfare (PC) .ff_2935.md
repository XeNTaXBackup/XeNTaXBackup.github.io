## Post #1
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2008-02-12T14:16:16+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2008-02-13T07:57:05+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

The .ff compressed with zlib.
Cut out the first 12byte, and all zlib can decompress/compress the .ff.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-13T08:20:43+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

Well I don't know the purpose of the first 3 dwords, but the rest of the file is zlib'ed data.
Here's the decompressed data:
[http://uploaded.to/?id=vin0he](http://uploaded.to/?id=vin0he)
If link is broken you may also try here:
[http://xirror.com/spread/99500868/data.rar.html](http://xirror.com/spread/99500868/data.rar.html)

EDIT: You may use my zlibc tool to decompress zlib streams. Get it here:
[viewtopic.php?p=20205#p20205](http://forum.xentax.com/viewtopic.php?p=20205#p20205)
## Post #4
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2008-02-13T13:03:15+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

> Reply from Rheini
>
> Well I don't know the purpose of the first 3 dwords, but the rest of the file is zlib'ed data.
Here's the decompressed data:
http://uploaded.to/?id=vin0he
If link is broken you may also try here:
http://xirror.com/spread/99500868/data.rar.html

EDIT: You may use my zlibc tool to decompress zlib streams. Get it here:
viewtopic.php?p=20205#p20205

thanks a lot, but as I use this program?
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-13T13:10:10+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

use it like this:
zlibc -d inputfile outputfile

(so you have to cut off the first 12 bytes and saving only the compressed data into a new file before you can use zlibc)
## Post #6
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2008-02-13T13:29:23+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

> Reply from Rheini
>
> 
(so you have to cut off the first 12 bytes and saving only the compressed data into a new file before you can use zlibc)

how I make for cuts the archive?
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-13T19:56:21+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

You can do this with most hex editing tools.
## Post #8
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2008-02-13T20:07:10+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

> Reply from Darkfox
>
> You can do this with most hex editing tools.

tks  

but no I obtained to open the archive.

[](http://img219.imageshack.us/my.php?image=imagemoj1.jpg)
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-13T20:33:11+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

Huh? Think you might have missed what I was saying. All that screenshot shows is an error on trying to open the archive with MC.
## Post #10
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2008-02-13T23:42:31+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

Hi, but I did not obtain to cut the archive, can help me?
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-14T10:25:23+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

Well even if you manage to cut the file and decompress it, you still have to figure out the data's format.
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-14T10:25:23+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

Well even if you manage to cut the file and decompress it, you still have to figure out the data's format.

btw what about those modtools you obviously have installed? Aren't they able to create ff files?

EDIT: Yeah they are! Read this topic:
[http://www.infinityward.com/community/f ... pic=4926.0](http://www.infinityward.com/community/forum/index.php?topic=4926.0)

Some additional information can be found here:
[http://www.infinityward.com/community/f ... ic=11188.0](http://www.infinityward.com/community/forum/index.php?topic=11188.0)

EDIT2: Here's another forum dealing with modding:
[http://iwnation.com/forums/index.php?showforum=153](http://iwnation.com/forums/index.php?showforum=153)
## Post #13
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2008-02-14T12:24:08+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

Thanks, but in the truth I wanted I was to find the archive where they will count the subs-heading, I to be able to translate the game for the Portuguese, and that am part of a team of translation of games in Brazil here.
## Post #14
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-14T20:48:31+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2008-02-14T22:16:22+00:00
- Post Title: Call of Duty 4 Modern Warfare (PC) *.ff

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-14T22:20:34+00:00
- Post Title: Re: Call of Duty 4 Modern Warfare (PC) *.ff

I could decipher all your posts, but this one is really hard to understand.
Please don't upload it to rapidshare, I'd personally prefer something like xirror.com
## Post #17
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2008-02-15T02:15:47+00:00
- Post Title: Re: Call of Duty 4 Modern Warfare (PC) *.ff

These archives that are in the address for download were extracted with the Paulus ' CoDDump (v1.1) but I do not know if it can modify these archives, it looks at and it says me if I can modify and to compress using zlibc for the format *.ff I am wanting really and to modify the subs-heading for the Portuguese language.

[http://xirror.com/spread/15424262/Files.rar.html](http://xirror.com/spread/15424262/Files.rar.html)
## Post #18
- Username: jedimaster
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 04, 2008 1:36 am
- Post datetime: 2008-03-30T14:25:48+00:00
- Post Title: Re: Call of Duty 4 Modern Warfare (PC) *.ff

Well...
## Post #19
- Username: CoDEmanX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 12, 2009 1:39 pm
- Post datetime: 2009-11-12T23:27:42+00:00
- Post Title: Re: Call of Duty 4 Modern Warfare (PC) *.ff

aintnomeinteam wrote a tool to decompress CoD4/5 fastfiles, which can also scan the dumps and extract ascii strings (=all gsc scripts etc.)

Note that the stuff in the ui folders is useless, menus are compiled to binary data but his tool extracts some unuseable stuff like ÿÿÿÿ

You may alter the scripts and use the official mod tools to compile a mod.ff in order to change them (you can use CoD4\mods\ModWarfare\ as example)

RGN Wiki » [Fast File Decompiler Tool](http://wiki.modsrepository.com/index.php/Call_of_Duty_5:_FastFile_Decompiler)


A friend (Daevius) and me are currently working on a tool to extract non-plaintext data from fastfiles.
» [Call of Duty 4: FastFile Format](http://wiki.modsrepository.com/index.php/Call_of_Duty_4:_FastFile_Format)

If you want to support us, add me on Xfire (codemanx) or send me a PM
