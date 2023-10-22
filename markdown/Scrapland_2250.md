## Post #1
- Username: diegoc
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 03, 2006 1:22 am
- Post datetime: 2006-12-07T03:35:45+00:00
- Post Title: Scrapland

Anyone know how to decompress this and get the datas?

Thanks
## Post #2
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-12-08T12:43:44+00:00
- Post Title: Scrapland

> Reply from diegoc
>
> Anyone know how to decompress this and get the datas?

Thanks
All *.packed archive files are not compressed.
Archive description:
[http://wiki.xentax.com/index.php/Scrapland_PACKED](http://wiki.xentax.com/index.php/Scrapland_PACKED)
## Post #3
- Username: diegoc
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 03, 2006 1:22 am
- Post datetime: 2006-12-08T17:12:07+00:00
- Post Title: Scrapland

Ok, Thanks
I use this code

ImpType Standard ; 
Goto 8 0 ; 
Get FNum Long 0 ; 
For n = 1 to FNum ; 
Get FNLen Long 0 ; 
GetDString FN FNLen 0 ; 
SavePos FOO 0 ; 
Get FO Long 0 ; 
SavePos FSO 0 ; 
Get FS Long 0 ; 
Log FN FO FS FOO FSO ; 
Next n ; 

And I can see the files, but i can't export. I have a error. 
Can you help me, please?
## Post #4
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-12-08T22:44:33+00:00
- Post Title: Scrapland

```
Goto 8 0 ;
Get FNum Long 0 ;
For n = 1 to FNum ;
Get FNLen Long 0 ;
GetDString FN FNLen 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FS FO FSO FOO ;
Next n ; 
```

False:
Log FN FO FS FSO FOO ;
Right:
Log FN FS FO FSO FOO ;
## Post #5
- Username: diegoc
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 03, 2006 1:22 am
- Post datetime: 2006-12-09T07:12:35+00:00
- Post Title: Scrapland

Thankssss
