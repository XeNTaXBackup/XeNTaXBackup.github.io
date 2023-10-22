## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-16T08:19:32+00:00
- Post Title: AirborneTroops

hello

please see pak file

thanks
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-16T08:27:54+00:00
- Post Title: AirborneTroops

Hey Sajad, how's life in Iran? 

We will take a look at your pack file.
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-16T08:36:10+00:00
- Post Title: AirborneTroops

mr mouse 
no good no bad !!!

thanks
## Post #4
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-16T09:36:50+00:00
- Post Title: AirborneTroops

mr mouse 

use dune game arrchive *.dun

DUN Frank Herbert's Dune pack Frank Herbert's Dune
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-16T09:43:01+00:00
- Post Title: AirborneTroops

You are right! That's it! Good work!   

I guess you did not send me the whole global.pak archive huh? I could extract individal .DUN archives from the piece you sent me, and the DUN approach worked. 

Nice !
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-16T09:50:06+00:00
- Post Title: AirborneTroops

```
Archive.	GLOBAL.PAK
Requestee.	Sajad, http://forum.xentax.com 
Archive Full.	No
Format.	The format consists of separate archives in the main archive. 
	Each separate archive (not the global one) has a list of 
	all the files in the right order first, but this is something the
	game handles ("addresource"command). The info about the offsets and
	sizes of the individual files is saved in a tail in each archive. 
	Note that this is the same format as used in Frank Herbert's Dune .PAK!

Mainformat.

Offset	Value	Description
0	7210EAF4	ID value of new header
4	32-bit	Unknown
8	32-bit	Offset of tail in current archive (i.e. of archive-in-archive-in archive)
12 	32-bit	Number of files (or archives) in current archive
[commandchunk]	n bytes	command file for the game
tailoffset	tailformatsize	set of tailinfo about each file

TailInfo

Filename	String	0x0a-terminated string depicting the complete path of the original file
Offset	32-bit	offset of file in the archive (note: this is the relative offset in the current archive)
size	32-bit	size of the file in the archive

```


(Tab-delimited format file)
## Post #7
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-16T15:15:40+00:00
- Post Title: AirborneTroops

mr mouse

when work on *.pak show error message "corrupted file info" 

after show all files in arrchive show error message or for extract files
of arrchive
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-16T15:22:28+00:00
- Post Title: AirborneTroops

Yes, please go to Options and deselect "Check file info ascending". That will fix that.
## Post #9
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-04-12T20:43:00+00:00
- Post Title: AirborneTroops

Mr.Mouse how to fix this problem ?[/b]
[Scr.jpg](https://xentaxbackup.github.io/file/173_Scr.jpg)
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-12T22:15:30+00:00
- Post Title: AirborneTroops

Well, can you tell me your Operating System, and computer configuration?
