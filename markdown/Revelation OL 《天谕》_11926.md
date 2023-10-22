## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-09T19:16:37+00:00
- Post Title: Revelation OL 《天谕》

Hello guys, well with small help of Ekey and Aluigi I got unpacked files from this game, after checking them, the native format ofc can't figure out, but stored in .dat 3D format, so well maybe somebody can take a look into files? ok many thanks for try and hope somebody can take a look into that.

[http://puu.sh/bsm5i/d7bfc98d09.7z](http://puu.sh/bsm5i/d7bfc98d09.7z)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-09-09T20:11:17+00:00
- Post Title: Revelation OL 《天谕》

Same format as Dragon Sword(龙剑).
Similar to Legendary Champions.

the 3d model(geometry) is in .primitives extension (header 0x42A14E65)
bones, material etc are in .visual extension (header 0x62A14E45)
animation should be in .anca extension

without the name, it's almost impossible to match them automatically.
I worked a bit and then given up!
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-10T02:38:36+00:00
- Post Title: Revelation OL 《天谕》

well many thanks, but as see, no way to got file names, just dumping it from .exe but is really hard got them for me, I think need put in the garbage this game  thanks a lot for try fat, grateful, take care.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-09-12T06:11:48+00:00
- Post Title: Revelation OL 《天谕》

The 3D Object Converter supports the BigWorld Technology .primitives format 3 years ago, so just rename your *.dat file to *.primitives and use the batch converter module in registered mode to get all models in one step.
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-09-15T17:41:55+00:00
- Post Title: Revelation OL 《天谕》

Where is unpack?  I made a thread but nothing there:

[viewtopic.php?f=10&t=11892&hilit=revelation](http://forum.xentax.com/viewtopic.php?f=10&t=11892&hilit=revelation)

Here is character customization to see models:

[https://www.youtube.com/watch?v=eVvsuH8-K2I](https://www.youtube.com/watch?v=eVvsuH8-K2I)
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-16T08:11:58+00:00
- Post Title: Revelation OL 《天谕》

> Reply from pixellegolas
>
> Where is unpack?  I made a thread but nothing there:

viewtopic.php?f=10&t=11892&hilit=revelation

Here is character customization to see models:

https://www.youtube.com/watch?v=eVvsuH8-K2Iok here we go, special thanks to aluigi and ekey.

> # 1gab / 2gab / bag
>
> #   Dragon Sword, JianLong, Revelation
>
> #   thanks Ekey 
>
> # script for QuickBMS http://quickbms.aluigi.org
>
> 
>
> comtype lzo1x
>
> 
>
> get MAGIC long
>
> get dwTotalFiles long
>
> get dwTableOffset long
>
> if MAGIC == 0x62616731
>
>     math XOR_FILES = 0xe7356461
>
>     math XOR_OFFSET = 0xcb449442
>
>     math XOR1 = 0x698346BD
>
>     math XOR2 = 0x867389FE
>
>     math XOR3 = 0xABEDC59D
>
> elif MAGIC == 0x62616732
>
>     math XOR_FILES = 0x27252421
>
>     math XOR_OFFSET = 0x3b343432
>
>     math XOR1 = 0x5953565D
>
>     math XOR2 = 0x6663696E
>
>     math XOR3 = 0x7B7D757D
>
> else
>
>     print "Error: unsupported magic signature %MAGIC|x%"
>
>     cleanexit
>
> endif
>
> math dwTotalFiles ^ XOR_FILES
>
> math dwTableOffset ^ XOR_OFFSET
>
> 
>
> goto dwTableOffset
>
> for i = 0 < dwTotalFiles
>
>     savepos ENTRY_OFF
>
> 
>
>     get NAME_CRC long
>
>     xmath NAME_CRC "NAME_CRC ^ ENTRY_OFF ^ XOR1"
>
> 
>
>     if MAGIC == 0x62616732
>
>         get NAME_CRC2 long  # ???
>
>     endif
>
> 
>
>     get OFFSET long
>
>     xmath OFFSET "OFFSET ^ ENTRY_OFF ^ XOR2"
>
> 
>
>     get ZSIZE long
>
>     xmath ZSIZE "ZSIZE ^ ENTRY_OFF ^ XOR3"
>
> 
>
>     savepos TMP
>
>     goto OFFSET
>
>     getdstring DUMMY 0x18
>
>     get ZIP long
>
>     if ZIP == 0x5a5a5a5a
>
>         get SIZE long
>
>         savepos OFFSET
>
>         clog "" OFFSET ZSIZE SIZE
>
>     else
>
>         log "" OFFSET ZSIZE
>
>     endif
>
>     goto TMP
>
> next i
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-09-16T19:05:51+00:00
- Post Title: Revelation OL 《天谕》

Thanks!
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-16T19:55:16+00:00
- Post Title: Revelation OL 《天谕》

> Reply from pixellegolas
>
> Thanks!u welcome, have a nice day buddy.
## Post #9
- Username: ALYX
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Apr 08, 2010 2:33 am
- Post datetime: 2014-10-04T18:01:52+00:00
- Post Title: Revelation OL 《天谕》

CriticalError, can you share a link to download client?
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-04T18:18:52+00:00
- Post Title: Revelation OL 《天谕》

> Reply from ALYX
>
> CriticalError, can you share a link to download client?well here is the webpage, don't remember where is download link xD

[http://tianyu.163.com/](http://tianyu.163.com/)
## Post #11
- Username: ALYX
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-10-04T23:24:13+00:00
- Post Title: Revelation OL 《天谕》

> Reply from CriticalError
>
> ALYX wrote:CriticalError, can you share a link to download client?well here is the webpage, don't remember where is download link xD

http://tianyu.163.com/

[http://tianyu.163.com/download/](http://tianyu.163.com/download/)
## Post #12
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-01-25T15:38:14+00:00
- Post Title: Revelation OL 《天谕》

I try the QuickBMS script, but it's not working
[QQ图片20150125233607.png](https://xentaxbackup.github.io/file/8561_QQ图片20150125233607.png)
## Post #13
- Username: OutSide
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 12, 2013 9:39 pm
- Post datetime: 2016-06-07T09:48:48+00:00
- Post Title: Revelation OL 《天谕》

Bump on this. @Ekey. Any news with your unpacker?
