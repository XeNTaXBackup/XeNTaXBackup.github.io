## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-23T19:24:28+00:00
- Post Title: FINAL FANTASY VII Remake (*.LGP)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

get NULLS short
idstring "SQUARESOFT"
get FILES long

for i = 0 < FILES
	getdstring NAME 0x14
	get OFFSET long
	get DUMMY threebyte
	savepos TEMP
	math OFFSET += 0x14
	goto OFFSET
	get SIZE long
	math OFFSET += 0x4
	log NAME OFFSET SIZE
	goto TEMP
next i
```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-23T20:17:07+00:00
- Post Title: FINAL FANTASY VII Remake (*.LGP)

What, the game is out already?
Is it still low-poly Cloud? Or is it high-poly Cloud now LOL
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-23T20:57:39+00:00
- Post Title: FINAL FANTASY VII Remake (*.LGP)

> Reply from finale00
>
> What, the game is out already?
Yep

> Reply from finale00
>
> Is it still low-poly Cloud? Or is it high-poly Cloud now LOL
Dunno
## Post #4
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-08-24T16:59:42+00:00
- Post Title: FINAL FANTASY VII Remake (*.LGP)

I was under the assumption that it was just a revision of the PC game with some of the bugs fixed.  I looked into the achievements that you can accomplish and your account logs and they are not very impressive....
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-24T20:23:51+00:00
- Post Title: FINAL FANTASY VII Remake (*.LGP)

Honestly the game is not impressive
## Post #6
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-27T16:15:28+00:00
- Post Title: FINAL FANTASY VII Remake (*.LGP)

hey ekey have you found out where the script work is?
## Post #7
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-08-29T21:46:22+00:00
- Post Title: FINAL FANTASY VII Remake (*.LGP)

The LGP format is just the same as it has always been. Most of the formats are. So look for tools here:

[http://forums.qhimm.com/index.php](http://forums.qhimm.com/index.php)
