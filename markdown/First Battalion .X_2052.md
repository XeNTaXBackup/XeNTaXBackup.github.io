## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-20T21:02:07+00:00
- Post Title: First Battalion *.X

Hello guys it's me again   PXR i now you help me    

[http://rapidshare.de/files/30143384/dialogs.x.zip.html](http://rapidshare.de/files/30143384/dialogs.x.zip.html)

PS : for some time past much to ask became but nevertheless I think you will help me , I am able nothing... OMG i lamer      

Many thanks guys
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-20T22:24:49+00:00
- Post Title: First Battalion *.X

MP3 Files!!!  , and lots of them.......
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-20T22:35:20+00:00
- Post Title: First Battalion *.X

No no no no no   I need all resources which in archives
## Post #4
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-21T18:25:41+00:00
- Post Title: First Battalion *.X

I've actually already taken a look at these archives... And there's two types:

```
IDString 0 xp10 ;
Get TEMP Long 0 ;
Get FILENUM Long 0 ;
GoTo 112 0 ;
For F = 1 To FILENUM ;
Get TEMP Long 0 ;
Get FNS Int 0 ;
GetDString FNAME FNS 0 ;
Get TEMP Int 0 ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos FSIZEX 0 ;
Get FSIZE Long 0 ;
Log FNAME FOFFSET FSIZE FOFFSETX FSIZEX ;
Next F ;
```

[x1.zip](https://xentaxbackup.github.io/file/818_x1.zip)
## Post #5
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-21T18:28:14+00:00
- Post Title: First Battalion *.X

```
Get TEMP Long 0 ;
Get FILENUM Long 0 ;
GoTo 108 0 ;
Get SUBS Long 0 ;
Math SUBS *= 2 ;
For S = 1 To SUBS ;
Get TEMP Int 0 ;
GetDString NAME TEMP 0 ;
Next S ;
For F = 1 To FILENUM ;
Get TEMP Long 0 ;
Get FNS Int 0 ;
GetDString FNAME FNS 0 ;
Get TEMP Int 0 ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos FSIZEX 0 ;
Get FSIZE Long 0 ;
Log FNAME FOFFSET FSIZE FOFFSETX FSIZEX ;
Next F ;
```


I'll add specifications later on (at the wiki i suppose) when I got more time on my hands. Also, these scripts should work, but I haven't really tested them. 
[x2.zip](https://xentaxbackup.github.io/file/819_x2.zip)
