## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-06-14T22:41:46+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

Does anyone know how to edit this .pak file? I suspect it contains the text files of the game.
I can't even find info on it as what engine the game uses.
[http://www57.zippyshare.com/v/68212829/file.html](http://www57.zippyshare.com/v/68212829/file.html)

Any help is greatly appreciated.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-14T22:55:35+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

Seems encrypted

Edited: just xored zip

```
get SIZE asize
log "decrypted_file.dat" 0 SIZE 
```
## Post #3
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-06-15T06:58:48+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

> Reply from Ekey
>
> Seems encrypted

Edited: just xored zip
Code: Select allfilexor "\x29\x61\x53\x33"
get SIZE asize
log "decrypted_file.dat" 0 SIZE
So I should use aluigi's xor to decrypt and then just unzip with eg. 7-zip?

Like this?
xor.exe scripts.pak scripts2.pak \x29\x61\x53\x33
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-06-15T11:57:38+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

Use Aluigi's QuickBMS.

I made similar script. Can be used to pak -> zip and vice versa.

```
filexor "\x29\x61\x53\x33"
get SIZE asize
get NAME basename

if SIGN == "PK"
 string NAME += ".pak_new"
elif SIGN == "y*"
 string NAME += ".zip"
else
 cleanexit
endif

log NAME 0 SIZE
```
## Post #5
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-06-15T18:09:57+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

Thank you, works perfectly
## Post #6
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-08-29T12:13:43+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

> Reply from merlinsvk
>
> Use Aluigi's QuickBMS.

I made similar script. Can be used to pak -> zip and vice versa.
Code: Select allgetdstring SIGN 2
filexor "\x29\x61\x53\x33"
get SIZE asize
get NAME basename

if SIGN == "PK"
 string NAME += ".pak_new"
elif SIGN == "y*"
 string NAME += ".zip"
else
 cleanexit
endif

log NAME 0 SIZE

works, even as a repack. made my very first mod, and I think the first mod for the game, with this
## Post #7
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-09-08T15:56:07+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

took the liberty of [quoting](http://steamcommunity.com/app/256030/discussions/3/616187204169609608/) you
## Post #8
- Username: Slappy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 17, 2012 5:28 pm
- Post datetime: 2016-06-19T06:39:55+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

> Reply from Devilot
>
> took the liberty of quoting you

Hey guys.

Did something change?

In new version of game I cannot open the unpacked .zip files (with xor x29x61x53x33 from above)?

Am I doing something wrong? Here is file from new game (.zip extension is only so I can upload the file, this is .pak file!):
[lair_save.pak.zip](https://xentaxbackup.github.io/file/11077_lair_save.pak.zip)
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-06-19T09:09:42+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

New XOR key: 
```
\x33\x29\x61\x53
```
## Post #10
- Username: duysharp1998
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 09, 2016 6:37 pm
- Post datetime: 2016-07-09T11:24:30+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

> Reply from merlinsvk
>
> New XOR key: Code: Select all\x33\x29\x61\x53
Thanks for the useful code   . I've unpacked the scripts.pak and edited some details. But i don't know how to pack it the script folder into .pak   
any ideas ?
## Post #11
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-07-09T19:57:41+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

You used BMS script for decrypt .pak to .zip.
Then you extracted that zip file.

Pack all extracted files into new zip, and use the same BMS script on it.
## Post #12
- Username: duysharp1998
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 09, 2016 6:37 pm
- Post datetime: 2016-07-11T12:32:21+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

> Reply from merlinsvk
>
> You used BMS script for decrypt .pak to .zip.
Then you extracted that zip file.

Pack all extracted files into new zip, and use the same BMS script on it.

ty   it's work.
## Post #13
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2019-10-29T02:08:19+00:00
- Post Title: Shadows: Heretic Kingdoms [.pak]

> Reply from Slappy ↑Sun Jun 19, 2016 2:39 pm at Sun Jun 19, 2016 2:39 pm
>
> 
Devilot wrote:took the liberty of quoting you 

Hey guys.

Did something change?

In new version of game I cannot open the unpacked .zip files (with xor x29x61x53x33 from above)?

Am I doing something wrong? Here is file from new game (.zip extension is only so I can upload the file, this is .pak file!):
New version = Shadows Awakening?
