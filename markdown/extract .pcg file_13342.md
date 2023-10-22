## Post #1
- Username: appsVoyage
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 19, 2015 11:05 pm
- Post datetime: 2015-09-19T15:23:57+00:00
- Post Title: extract .pcg file

Hello.
Guys, there is a problem with unpacking resources game files are. "voyage century china"
I been to a topic the forum "[viewtopic.php?f=10&t=10853](http://forum.xentax.com/viewtopic.php?f=10&t=10853)"
But this theme did not helped me.
files from this game
[https://drive.google.com/file/d/0B6VS0H ... sp=sharing](https://drive.google.com/file/d/0B6VS0HhQOboURVBXZ0pDQ21US2M/view?usp=sharing)
[https://drive.google.com/file/d/0B6VS0H ... sp=sharing](https://drive.google.com/file/d/0B6VS0HhQOboUMHotVmgtbE45cGM/view?usp=sharing)
## Post #2
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-19T18:11:55+00:00
- Post Title: extract .pcg file

The files seem to be zlib compressed. 

This is a sound extracted from 1 file: [https://mega.nz/#!2QBiBYAD!_brRPzBweCyR ... fAazMavnms](https://mega.nz/#!2QBiBYAD!_brRPzBweCyR1smDNF2CvfITI7CZR5B1AfAazMavnms) .
## Post #3
- Username: appsVoyage
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 19, 2015 11:05 pm
- Post datetime: 2015-09-19T19:10:22+00:00
- Post Title: extract .pcg file

> Reply from ekanspt
>
> The files seem to be zlib compressed. 

This is a sound extracted from 1 file: https://mega.nz/#!2QBiBYAD!_brRPzBweCyR ... fAazMavnms .

Yes, but this one file.
The rest of what to do?
guyskbms helps, but bad.
## Post #4
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-19T20:02:15+00:00
- Post Title: extract .pcg file

This seems to be the MEX script to extract the files:

```

ComType ZLib1; 
IDString 0 "snail_package";

Get U1 Long 0;
Get NFiles Long 0;
GoTo 61 0;

For I = 1 To NFiles;

Get FNameSize Int 0;
GetDString FName FNameSize 0;
Get FUSize Long 0;
GetDString Hash 32 0;
Get FOffset Long 0;
Get FSize Long 0;

CLog FName FOffset FSize 0 0 FUSize 0;

SavePos HOffset 0;
Math HOffset += 72;
GoTo HOffset 0;

Next I;


```
## Post #5
- Username: appsVoyage
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 19, 2015 11:05 pm
- Post datetime: 2015-09-20T02:34:32+00:00
- Post Title: extract .pcg file

> Reply from ekanspt
>
> This seems to be the MEX script to extract the files:
Code: Select all#Voyage Century China *.pcg files

ComType ZLib1; 
IDString 0 "snail_package";

Get U1 Long 0;
Get NFiles Long 0;
GoTo 61 0;

For I = 1 To NFiles;

Get FNameSize Int 0;
GetDString FName FNameSize 0;
Get FUSize Long 0;
GetDString Hash 32 0;
Get FOffset Long 0;
Get FSize Long 0;

CLog FName FOffset FSize 0 0 FUSize 0;

SavePos HOffset 0;
Math HOffset += 72;
GoTo HOffset 0;

Next I;

Thank you.
He extract files sound.pcg (music), but they do not run and weighs 0 bytes
## Post #6
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-20T12:07:24+00:00
- Post Title: extract .pcg file

With the file sound.pcg I was able to get this: [http://imgur.com/6jH1my4](http://imgur.com/6jH1my4).
## Post #7
- Username: appsVoyage
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 19, 2015 11:05 pm
- Post datetime: 2015-09-20T16:58:28+00:00
- Post Title: extract .pcg file

> Reply from ekanspt
>
> With the file sound.pcg I was able to get this: http://imgur.com/6jH1my4.
Yes, it is those files.
You tried run files?

This script not helps, I cannot repack back files.

> # Game: HotDance / 5 Street 
>
> # by Fatduck 
>
> # script for QuickBMS http://aluigi.org/papers.htm#quickbms 
>
> 
>
> idstring "snail_package" 
>
> get DUMMY long 
>
> get NUMRES long 
>
> goto 61 
>
> 
>
> for i = 0 < NUMRES 
>
>     get STGLEN byte 
>
>     get NEGFLAG byte 
>
>     if NEGFLAG == 0xFF 
>
>         math STGLEN -= 256 
>
>         math STGLEN *= -1 
>
>     endif 
>
>     getdstring RESNAME STGLEN 
>
>     get RESSIZE long 
>
>     getdstring STGDUMMY 32 
>
>     get OFSRES long 
>
>     getdstring STGDUMMY 76 
>
> 
>
>     log RESNAME OFSRES RESSIZE 
>
> next i

This script helps, I cannot reimport files back.

> goto 0x11
>
> get FILES long
>
> goto 0x3d
>
> for i = 0 < FILES
>
>     get NAMESZ short
>
>     if NAMESZ >= 0x8000
>
>         xmath NAMESZ "0x10000 - NAMESZ"
>
>     endif
>
>     getdstring NAME NAMESZ
>
>     get SIZE long
>
>     getdstring HASH 32
>
>     get OFFSET long
>
>     get ZSIZE long
>
>     get DUMMY1 long
>
>     get DUMMY2 long # ZIP?
>
>     getdstring DUMMY 0x40
>
>     if DUMMY1 == 0
>
>         if ZSIZE == SIZE
>
>             log NAME OFFSET SIZE
>
>         else
>
>             clog NAME OFFSET ZSIZE SIZE
>
>         endif
>
>     endif
>
>     # the others with DUMMY1 != 0 are invalid!
>
> next i
Error
[http://imgur.com/rGZXhXu](http://imgur.com/rGZXhXu)
## Post #8
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-21T13:13:21+00:00
- Post Title: extract .pcg file

> Reply from appsVoyage
>
> 
Yes, it is those files.
You tried run files?

Yes, I tried to run the files and they are ok. I can listen to all the extracted sound files, I can send you if you want.

Of course you cannot repack back the files with this script, because it is not coded to repack back any files.
## Post #9
- Username: appsVoyage
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 19, 2015 11:05 pm
- Post datetime: 2015-09-21T15:42:58+00:00
- Post Title: extract .pcg file

> Reply from ekanspt
>
> appsVoyage wrote:
Yes, it is those files.
You tried run files?


Yes, I tried to run the files and they are ok. I can listen to all the extracted sound files, I can send you if you want.

Of course you cannot repack back the files with this script, because it is not coded to repack back any files.

Thank you for the explanation.
And do tell me, as the import files back?
## Post #10
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-21T17:04:42+00:00
- Post Title: extract .pcg file

The first try can be done using this script:

```
ImpType Standard;
ComType ZLib1; 
IDString 0 "snail_package";

Get U1 Long 0;
Get NFiles Long 0;
GoTo 61 0;

For I = 1 To NFiles;

Get FNameSize Int 0;
GetDString FName FNameSize 0;
SavePos FUSizeOffset 0;
Get FUSize Long 0;
GetDString Hash 32 0;
SavePos FOffsetOffset 0;
Get FOffset Long 0;
SavePos FSizeOffset 0;
Get FSize Long 0;

CLog FName FOffset FSize FOffsetOffset FSizeOffset FUSize FUSizeOffset;

SavePos HOffset 0;
Math HOffset += 72;
GoTo HOffset 0;

Next I;

```


However it is possible that the some of the fields not considered in the extraction of the files need some modification, so this script is not enough to solve the problem and a custom repacker needs to be done.

However try this first, test ingame an post here the results.
## Post #11
- Username: appsVoyage
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 19, 2015 11:05 pm
- Post datetime: 2015-09-22T01:55:44+00:00
- Post Title: extract .pcg file

> Reply from ekanspt
>
> The first try can be done using this script:
Code: Select all#Voyage Century China *.pcg files
ImpType Standard;
ComType ZLib1; 
IDString 0 "snail_package";

Get U1 Long 0;
Get NFiles Long 0;
GoTo 61 0;

For I = 1 To NFiles;

Get FNameSize Int 0;
GetDString FName FNameSize 0;
SavePos FUSizeOffset 0;
Get FUSize Long 0;
GetDString Hash 32 0;
SavePos FOffsetOffset 0;
Get FOffset Long 0;
SavePos FSizeOffset 0;
Get FSize Long 0;

CLog FName FOffset FSize FOffsetOffset FSizeOffset FUSize FUSizeOffset;

SavePos HOffset 0;
Math HOffset += 72;
GoTo HOffset 0;

Next I;


However it is possible that the some of the fields not considered in the extraction of the files need some modification, so this script is not enough to solve the problem and a custom repacker needs to be done.

However try this first, test ingame an post here the results.

An error has occurred

[http://prntscr.com/8j1viv](http://prntscr.com/8j1viv)
I sorry, all good. I'm use the quickbms and an error has occurred.
How to pack all those files back?
## Post #12
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-22T09:27:20+00:00
- Post Title: extract .pcg file

I coded the script with multiex, not with quickbms. In fact, this error occurs but I don't know actually why. 

I can try to code a quickbms script for you.
## Post #13
- Username: appsVoyage
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 19, 2015 11:05 pm
- Post datetime: 2015-09-22T13:30:30+00:00
- Post Title: extract .pcg file

> Reply from ekanspt
>
> I coded the script with multiex, not with quickbms. In fact, this error occurs but I don't know actually why. 

I can try to code a quickbms script for you.
If you are not difficult, it would be good.
Reimport back will be through the "quickbms"?
## Post #14
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-24T17:17:54+00:00
- Post Title: extract .pcg file

Here it is:

```

ComType zlib
Get U1 long 0
Get NFiles long 0

GoTo 61 0

For i = 0 < NFiles
	Get FNameSize Int 0
	GetDString FName FNameSize 0
	Get FUSize Long 0
	GetDString Hash 32 0
	Get FOffset Long 0
	Get FSize Long 0

	CLog FName FOffset FSize FUSize

	SavePos HOffset 0
	Math HOffset += 72
	GoTo HOffset 0
next i
```
## Post #15
- Username: appsVoyage
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 19, 2015 11:05 pm
- Post datetime: 2015-09-24T18:38:38+00:00
- Post Title: extract .pcg file

> Reply from ekanspt
>
> Here it is:
Code: Select allIDString "snail_package"

ComType zlib
Get U1 long 0
Get NFiles long 0

GoTo 61 0

For i = 0 < NFiles
	Get FNameSize Int 0
	GetDString FName FNameSize 0
	Get FUSize Long 0
	GetDString Hash 32 0
	Get FOffset Long 0
	Get FSize Long 0

	CLog FName FOffset FSize FUSize

	SavePos HOffset 0
	Math HOffset += 72
	GoTo HOffset 0
next i
Thank you very much!
A with the help of your script, i can repimport files ?
Or maybe you know how to create such an archive (.pcg), with my the files?
It would be cool
## Post #16
- Username: cxt
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 20, 2014 10:20 pm
- Post datetime: 2023-02-27T18:12:17+00:00
- Post Title: Re: extract .pcg file

> Reply from appsVoyage ↑Fri Sep 25, 2015 2:38 am at Fri Sep 25, 2015 2:38 am
>
> Thank you very much!
A with the help of your script, i can repimport files ?
Or maybe you know how to create such an archive (.pcg), with my the files?
It would be coolPacker and unpacker with C source codes:
[5street .PCG package tool v1.3](http://www.ctpax-x.org/index.php?goto=files&show=165&lang=en)
Correct QuickBMS script for unpacking since archive format unnecessary complex:
[5street .PCG QuickBMS unpacker code](https://www.extractor.ru/ipb/index.php?showtopic=2219&p=14359)
