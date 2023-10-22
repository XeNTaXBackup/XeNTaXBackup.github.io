## Post #1
- Username: withmorten
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 28, 2012 11:03 pm
- Post datetime: 2013-08-24T21:22:35+00:00
- Post Title: LEGO Lord of the Rings *.pac

Hi!

I just used aluigi's tt quickbms script to extract the LEGO LotR *.DAT files. In the audio folder I discovered the following files that seem to include the sfx stuff I was after:



They seem to be an uncompressed RIFF WAVE fmt container that also include some sort of file system structure before any of the files.





I searched far and wide and couldn't find any extractor or anything for those files. I also don't really know how to put together a quickbms script that would successfully extract this and include the FS structure. If anybody here would be able to so, I can upload a sample. The file starts with "zV4" if that's any help in identifying what kind of container this is.

Thanks for any help!
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-24T23:32:11+00:00
- Post Title: LEGO Lord of the Rings *.pac

And where samples?
## Post #3
- Username: withmorten
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 28, 2012 11:03 pm
- Post datetime: 2013-08-25T19:03:32+00:00
- Post Title: LEGO Lord of the Rings *.pac

I can't share them publicly, so that needs to happen privately
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-25T20:35:24+00:00
- Post Title: LEGO Lord of the Rings *.pac

Done

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "zV4\x12"
get FILES long
goto 0x18

for i = 0 < FILES
   get NOFFSET long
   get OFFSET long
   get SIZE long
   get UNKNOWN long
   get NULL long
   get DUMMY longlong
   savepos TEMP
   goto NOFFSET
   get NAME string
   log NAME OFFSET SIZE
   goto TEMP
next i
```
## Post #5
- Username: withmorten
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 28, 2012 11:03 pm
- Post datetime: 2013-08-26T01:38:20+00:00
- Post Title: LEGO Lord of the Rings *.pac

Works absolutley great on all 6 files, thank you so much!
## Post #6
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-03-27T07:34:29+00:00
- Post Title: LEGO Lord of the Rings *.pac

Hi, how to repack *.pac file?
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-27T11:12:57+00:00
- Post Title: LEGO Lord of the Rings *.pac

Read section 3 in QuickBMS readme.
## Post #8
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-03-27T13:12:31+00:00
- Post Title: LEGO Lord of the Rings *.pac

> Reply from Ekey
>
> Read section 3 in QuickBMS readme.
Thanks you very much!
