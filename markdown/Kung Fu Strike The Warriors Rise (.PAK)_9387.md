## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-01T15:32:00+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.PAK)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PAK"
get DUMMY long
get FILES long

for i = 0 < FILES
	get NSIZE byte
	getdstring NAME NSIZE
	get DUMMY byte
	get OFFSET long
	get SIZE long
	log NAME OFFSET SIZE
next i
```
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-05T19:35:12+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.PAK)

Made a quick user friendly exe file , so you don't need Quick BMS, just start it up, select any dat file from the game and it will extract it.

Next stop is unraveling the .a3d files that contain the 3D model ( I think)

Textures are dds, and are stored uncompressed in the texture.dat file

Cheers

T.
[DatTool.rar](https://xentaxbackup.github.io/file/5639_DatTool.rar)
## Post #3
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-08-06T23:31:54+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.PAK)

Someone found the localization files of the game?
## Post #4
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-08T12:16:45+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.PAK)

> Reply from delutto
>
> Someone found the file location of the game?

What??

T.
## Post #5
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-08-08T23:44:45+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.PAK)

> Reply from TaylorMouse
>
> delutto wrote:Someone found the file location of the game?

What??

T.

Ops.
Localization files, texts of the game.
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-14T18:47:10+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.PAK)

I've noticed that there are a lot of ppl looking for these localisation files ( not specificly for this game) 

Why? The game is in English, what else do you need?

Any progress on the .a3d files yet ?

T.
## Post #7
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-08-14T21:44:04+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.PAK)

> Reply from TaylorMouse
>
> I've noticed that there are a lot of ppl looking for these localisation files ( not specificly for this game) 

Why? The game is in English, what else do you need?

Any progress on the .a3d files yet ?

T.
I want to translate into Brazilian Portuguese.
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-14T22:14:25+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.PAK)

> Reply from delutto
>
> TaylorMouse wrote:I've noticed that there are a lot of ppl looking for these localisation files ( not specificly for this game) 

Why? The game is in English, what else do you need?

Any progress on the .a3d files yet ?

T.
I want to translate into Brazilian Portuguese.

Heu, ok...
