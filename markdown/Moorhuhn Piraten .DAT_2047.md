## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T15:24:00+00:00
- Post Title: Moorhuhn Piraten *.DAT

Hi guys help me plz    

2.12MB
[http://rapidshare.de/files/29991091/dat ... t.zip.html](http://rapidshare.de/files/29991091/datafile.dat.zip.html)

Thanks
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-19T16:11:56+00:00
- Post Title: Moorhuhn Piraten *.DAT

hehe, Some tasty BMPs, a JPEG, and lots of Oggy Poggy audios =D
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T16:17:45+00:00
- Post Title: Moorhuhn Piraten *.DAT

lolz  Strobe you can help me ?
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-19T16:27:24+00:00
- Post Title: Moorhuhn Piraten *.DAT

Well. all you have to do to rip them out is using Jaeder Naub,
and set options on BMP, JPEG, Ogg. and voila, the files are out.

=D, but if you plan to reinsert/modify them, then i suggest you wait until someone makes a BMS script or something :X

[http://jaedernaub.ath.cx](http://jaedernaub.ath.cx)

g0g0g0g0g0!
## Post #5
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-19T17:41:49+00:00
- Post Title: Moorhuhn Piraten *.DAT

And here's my notes + BMS-script... 

```
 57 - null
  4 - first file offset
  4 - unknown (1)
  8 - null

// for each file
	64 - filename (null)
	 4 - file offset
	 4 - file length
	 8 - null

  4 - end of directory sign? (****)
 60 - null
  4 - first file offset
124 - null

// for each file

	 x - file data
	 x - null padding

  4 - footer (:ET.)
```


```
IDString 0 MHP ;
Set ENDDIRSTRING String **** ;
GoTo 64 0 ;
Get DATAX Long 0 ;
GoTo 80 0 ;
Do ;
GetDString FNAME 64 0 ;
If FNAME = ENDDIRSTRING ;
CleanExit ;
EndIf ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos FSIZEX 0 ;
Get FSIZE Long 0 ;
Get TEMP Long 0 ;
Get TEMP Long 0 ;
Log FNAME FOFFSET FSIZE FOFFSETX FSIZEX ;
SavePos CHECK 0 ;
While CHECK < DATAX ;
```

[dat.zip](https://xentaxbackup.github.io/file/801_dat.zip)
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T19:30:19+00:00
- Post Title: Moorhuhn Piraten *.DAT

Thanks PXR
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-19T21:00:30+00:00
- Post Title: Moorhuhn Piraten *.DAT

> Reply from PXR
>
> And here's my notes + BMS-script...

Awesome. You're gonna be in the About section of MexCom, by the way. As co-author.
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-19T22:03:48+00:00
- Post Title: Moorhuhn Piraten *.DAT

I agree with Mr Mouse, really nice/good job
## Post #9
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-20T07:56:57+00:00
- Post Title: Moorhuhn Piraten *.DAT

I'll be looking forward to seeing that.
