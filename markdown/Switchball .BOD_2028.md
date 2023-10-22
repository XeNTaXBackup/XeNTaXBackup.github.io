## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-08T19:13:39+00:00
- Post Title: Switchball *.BOD

Mr.Mouse i now you can help me  

Cuted archive download here :
[http://rapidshare.de/files/28674563/swi ... d.zip.html](http://rapidshare.de/files/28674563/switchball.bod.zip.html)

Many thanks
## Post #2
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-08T22:31:10+00:00
- Post Title: Switchball *.BOD

Attach bigger parts, 1 or even 2MB if possible, please. These files simply give us too little information in this case.
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-08T23:04:49+00:00
- Post Title: Switchball *.BOD

Okey no problem .... i now guys you can help me 100%    

[http://rapidshare.de/files/28699353/swi ... d.zip.html](http://rapidshare.de/files/28699353/switchball.bod.zip.html)
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-09T22:55:39+00:00
- Post Title: Switchball *.BOD

No news ?
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-12T17:02:04+00:00
- Post Title: Switchball *.BOD

A topic can be closed to help not whoever wants!
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-13T00:51:02+00:00
- Post Title: Switchball *.BOD

Things are slow here for now so things may take quite a while.

Activity may kick up in the next update.
## Post #7
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-13T02:40:36+00:00
- Post Title: Switchball *.BOD

Sorry for the late response, I kinda forgot about the thread/forum. 

```
001 - Unknown (46)
032 - null
004 - Number of files (774)

// for each file

	256 - File Name
	004 - File Offset
	004 - File Length

x - null padding

// for each file 

	x - file data
```


And a BMS-script:

```
IDString 0 This ;
Set TEMP Long 64 ;
GoTo TEMP 0 ;
Get FILENUM Long 0 ;
For F = 1 To FILENUM ;
GetDString FNAME 256 0 ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos FSIZEX 0 ;
Get FSIZE Long 0 ;
Log FNAME FOFFSET FSIZE FOFFSETX FSIZEX ;
Next F ;
```


I'll also attach a zipped compiled script.
[bod.zip](https://xentaxbackup.github.io/file/788_bod.zip)
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-13T03:17:16+00:00
- Post Title: Switchball *.BOD

Wow thank you for help PXR worked
