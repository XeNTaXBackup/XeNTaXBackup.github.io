## Post #1
- Username: nobyboy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 02, 2010 3:25 am
- Post datetime: 2010-11-03T18:53:34+00:00
- Post Title: Afrika PS3 (.ARC)

hi guys first sorry for my bad english 
ok here is my problem i tried to extract files from the ps3 game afrika but these files are inside the .arc file (exept videos and music these files are in seperate folders) i tried to extract this file with all the plugins and extractors i found for .arc files but without success and now i ask you guys to help me out please the .arc file is 2gb in size and split to 4 parts with winrar and hosted on zippyshare a very fast service 2 downloads at the same time 

this are all the files that are inside the folder


a.arc part1   [http://www38.zippyshare.com/v/76107865/file.html](http://www38.zippyshare.com/v/76107865/file.html)
a.arc part2   [http://www38.zippyshare.com/v/41292924/file.html](http://www38.zippyshare.com/v/41292924/file.html)
a.arc part3   [http://www38.zippyshare.com/v/57442018/file.html](http://www38.zippyshare.com/v/57442018/file.html)
a.arc part4   [http://www38.zippyshare.com/v/24661665/file.html](http://www38.zippyshare.com/v/24661665/file.html)
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-04-14T16:15:49+00:00
- Post Title: Afrika PS3 (.ARC)

> Reply from nobyboy
>
> hi guys first sorry for my bad english 
ok here is my problem i tried to extract files from the ps3 game afrika but these files are inside the .arc file (exept videos and music these files are in seperate folders) i tried to extract this file with all the plugins and extractors i found for .arc files but without success and now i ask you guys to help me out please the .arc file is 2gb in size and split to 4 parts with winrar and hosted on zippyshare a very fast service 2 downloads at the same time 

this are all the files that are inside the folder


a.arc part1   http://www38.zippyshare.com/v/76107865/file.html
a.arc part2   http://www38.zippyshare.com/v/41292924/file.html
a.arc part3   http://www38.zippyshare.com/v/57442018/file.html
a.arc part4   http://www38.zippyshare.com/v/24661665/file.html

Here is a quickbms script to extract A.ARC.
You can get quickbms here:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Here is the script

```
Get files Short 0 ;
GoTo 0x8 0 ;
Get jump Long 0 ;
GoTo 0x14 0 ;
SavePos base 0 ;
For f = 1 To files ;
GoTo base 0 ;
Get com Long 0 ;
If com != 0 ;
Print unknown ;
EndIF ;
Get compressedsize Long 0 ;
Get decompressedsize Long 0 ;
Get toname Long 0 ;
Get fileoffset Long 0 ;
SavePos base 0 ;
Math fileoffset += jump ;
GoTo toname 0 ;
Get name String 0 ;
Log name fileoffset compressedsize 0 ;
Next f ;
```


I will be working on the mesh format. The DDS textures come out fine.
