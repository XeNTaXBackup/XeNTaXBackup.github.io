## Post #1
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2004-08-20T02:21:26+00:00
- Post Title: Doom 3??  Far Cry??

Any chance of adding these two to the list?

  Thanks!
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-20T03:00:35+00:00
- Post Title: Doom 3??  Far Cry??

> Reply from flaz
>
> Any chance of adding these two to the list?

  Thanks!

lol, doom3 is a zip file, just use 7zip or winzip to uncompress.  Easy as pie.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-20T10:52:49+00:00
- Post Title: Doom 3??  Far Cry??

> Reply from flaz
>
> Any chance of adding these two to the list?

  Thanks!
 Er... Far Cry is already supported and Doom 3 .PK4 files are, as Rahly said, your basic .ZIP files. Just open them with your basic unzipper. 
They will be supported in MultiEx Commander though.
## Post #4
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2004-08-20T16:36:57+00:00
- Post Title: Doom 3??  Far Cry??

Thanks!
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-21T14:58:07+00:00
- Post Title: Doom 3??  Far Cry??

Yep, just as they said - they are just zip files.

There is also 1 other format used in FarCry that I kinda know about - its a complicated one though.

```
| Far Cry *.cgf *.cga |
+---------------------+

6	Header (CryTek)
2	Unknown
2	null
2	Unknown
4	Unknown
4	Directory Offset (can be all 255's, not sure what to do here if not a real value!)

// go to dirOffset
4	Number Of Files

// for each file
2	ID?
2	Unknown (both 204)
1	Group ID?
1	File Type (0 = Archive Description, 9 = Root Directory?, 8 = Directory, 7 = File)
2	null
4	File Offset
4	File Number (starting at 0)

// at each file offset

// IF TYPE = 0
X	Description (read until the next field = 14)
2	ID? (14) (same as ID in dirEntry)
4	Unknown
2	Unknown
4	File Offset (same as in dirEntry)
4	File Number (same as in dirEntry)

// IF TYPE = 9
2	ID? (same as ID in dirEntry)
4	Unknown
2	Unknown
4	File Offset (same as in dirEntry)
4	File Number (same as in dirEntry)

// IF TYPE = 8
2	ID? (same as ID in dirEntry)
4	Unknown
2	Unknown
4	File Offset (same as in dirEntry)
4	File Number (same as in dirEntry)
4	File Type / Extension?
4	Unknown (160)
12	Description (GlobalRange + null)
4	File Number (same as in dirEntry)
4	Offset?
4	Unknown
4	Unknown
8	null
8	Size?

// IF TYPE = 7
2	ID? (same as ID in dirEntry)
4	Unknown
2	Unknown
4	File Offset (same as in dirEntry)
4	File Number (same as in dirEntry)
128	Description of item (null)
X	File
```


I don't think it's 100% perfect, but it'll do. Don't know if anyone wants to try and implement this in MexCom   

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)

PS - this was from a demo - so hopefully this archive type still exists in the full game
