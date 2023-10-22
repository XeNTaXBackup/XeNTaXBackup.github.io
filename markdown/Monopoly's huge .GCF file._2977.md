## Post #1
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-03-19T07:25:00+00:00
- Post Title: Monopoly's huge .GCF file.

The TikGames Monopoly and Monopoly Here and Now games use a very large file named game.gcf

The original Monopoly version uses game.gcf 14,372 KB, MonopolyPB.exe 10,908 KB and a single DLL MonPlg.dll 776 KB

For Here and Now, game.gcf 12,788 KB, Monopoly.exe 1,710 KB, MonPLG.dll, 780 KB, and MonRes.dll 98 KB

It tickles my curiosity why the original version game uses a much larger executable and why the Here and Now version uses two DLL's vs one for the other.

If the graphics can be ripped, I'm planning on making my own Monopoly board game that combines the old and new versions.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-20T21:31:54+00:00
- Post Title: Monopoly's huge .GCF file.

Can you use the FileCutter to cut some samples of this large file ?

[http://www.xentax.com/downloads/tools/filecutter.zip](http://www.xentax.com/downloads/tools/filecutter.zip)
## Post #3
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-03-22T19:09:15+00:00
- Post Title: Monopoly's huge .GCF file.

I don't know if that would do much good. I opened the files in notepad and the contents for the two versions are completely different. Here & Now's file shows up as mostly a bunch of inverted triangles while the original version's file looks more like what I've seen opening other binary files in notepad to see what, if anything, it has for header information that might identify it.

Here & Now version download. [http://downloads.gamehouse.com/pub/MonopolyInstall.exe](http://downloads.gamehouse.com/pub/MonopolyInstall.exe)

Original version download. [http://downloads.gamehouse.com/pub/Mono ... nstall.exe](http://downloads.gamehouse.com/pub/MonopolyPBInstall.exe)

Downloads are 22 and 20 megs. I got them on dialup.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-23T06:55:44+00:00
- Post Title: Monopoly's huge .GCF file.

The archive has an index table that is ZLib compressed.
## Post #5
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-23T20:44:13+00:00
- Post Title: Monopoly's huge .GCF file.

Okay, so this is the format

```
// Main Header

uint16	Uncompressed size of File info Header
uint16	Compressed size of File info Header
[data]	ZLib compressed file info header

	// Data

	Zlib compressed files

Uncompress the File info header and you will get a list of resources in this archive

// File info header

[1]	Version number?
uint16	Number of resources in the archive

	// Resource info
	
	[1]	Size of the filename string
	[n]	filename
	uint32	Compressed size of resource
	uint32	Uncompressed size of resource

```
## Post #6
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-10-14T01:08:16+00:00
- Post Title: Monopoly's huge .GCF file.

And that helps me how? I'm not a programmer, I just want to extract the graphics.
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-10-14T11:37:57+00:00
- Post Title: Monopoly's huge .GCF file.

We need much more programmers ^^
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-10-14T22:18:48+00:00
- Post Title: Monopoly's huge .GCF file.

> Reply from bizzybody
>
> And that helps me how? I'm not a programmer, I just want to extract the graphics.

Well, programming a tool that will help you out costs time. Time usually is money, but not here, unless you want to change that. In any event, by posting the format (and not having time myself at that instance) I had hoped that some coder would have picked it up and programmed a tool to extract the stuff using my info. No one did, probably due to lack of unpayed time
## Post #9
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-10-16T01:54:33+00:00
- Post Title: Monopoly's huge .GCF file.

If nobody else volunteers I might be able to whip something up (for free)…
## Post #10
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-10-16T02:04:48+00:00
- Post Title: Monopoly's huge .GCF file.

The reason I'm wanting to rip the graphics is I have an idea for combining the original and here & now Monopoly games.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-10-16T06:25:20+00:00
- Post Title: Monopoly's huge .GCF file.

> Reply from Zench
>
> If nobody else volunteers I might be able to whip something up (for free)…

By all means, please do !
## Post #12
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-10-21T13:59:43+00:00
- Post Title: Monopoly's huge .GCF file.

Sorry that it's a bit late, but here's an small extractor for the original Monopoly that I threw together. It's command line, I hope that's okay. Maybe I will write a MexCom plugin for it sometime. Call it with the input file:

```
GcfExtr game.gcf
```

[GcfExtr.zip](https://xentaxbackup.github.io/file/1693_GcfExtr.zip)
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-10-21T14:27:16+00:00
- Post Title: Monopoly's huge .GCF file.

Nice work! I feel a newspost coming up  , right?
## Post #14
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-10-21T20:12:42+00:00
- Post Title: Monopoly's huge .GCF file.

Yay! Extraction works. Appears to also work on the Here and Now version.

But now I need to find an extractor for Shockwave Flash.
## Post #15
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-10-21T21:05:31+00:00
- Post Title: Monopoly's huge .GCF file.

Found one that appears to work. Dcomsoft SWF Picture Extractor. [http://www.dcomsoft.com/](http://www.dcomsoft.com/) It's free, as in *free*, not a "free" download of a demo or trial version.

It found 2202 images in game.swf from the original version of Monopoly.

Thanks, Zench!

Edit: Well poop! SWF Picture Extractor 1.7 has a bug. It correctly displays .bmp and .jpg files with transparency but when extracting them it converts the alpha channel to solid black. I sent Dcomsoft a bug report. Now to find a different .swf ripper.
## Post #16
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-10-22T01:33:17+00:00
- Post Title: Re: Monopoly's huge .GCF file.

> Reply from Mr.Mouse
>
> Nice work! I feel a newspost coming up  , right?[Yep.](http://www.xentax.com/?p=188)
## Post #17
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2008-10-22T05:20:43+00:00
- Post Title: Re: Monopoly's huge .GCF file.

I found a freeware SWF extractor that doesn't screw up transparency. Fortop SWF Resources Extractor [http://www.fortop-digital.com/product/s ... extractor/](http://www.fortop-digital.com/product/swf-resources-extractor/)

Yesssss, now my plan of combining original and here & now Monopoly may begin! (Except for the bit of needing to find downloads of the H&N money like Hasbro/Parker Bros. has for the original.)

Edit: It appears that the Chance and Community Chest card images are very well hidden in the Here & Now version. Neither SWF extractor finds them in any of the SWF files.  I've been unable to find any pictures online of those cards or the money from this version of the game.
## Post #18
- Username: delgerdalai
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 05, 2008 5:45 pm
- Post datetime: 2008-12-06T02:48:22+00:00
- Post Title: Re: Monopoly's huge .GCF file.

Hi all,

uint16   Uncompressed size of File info Header

How i calculate Uncompressed size of File info Header. (orignal value 463, actually uncompress file info header size is 535  ). i want edit xml files after recompress game.gcf. 
but i can't calculate Uncompressed size of File info Header.   . 

Sorry my bad english.
## Post #19
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-12-09T02:45:43+00:00
- Post Title: Re: Monopoly's huge .GCF file.

The uncompressed size is the size before all of the file entries are compressed with zlib (and it would be the size after they are decompressed). So you basically construct the file info entries and the size of that is the uncompressed size, and then you compress it with zlib, and then that is the compressed size. If it actually uncompresses to a different size that what that value is, I don't know what to tell you. Re-compression should be okay, though.
## Post #20
- Username: delgerdalai
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 05, 2008 5:45 pm
- Post datetime: 2008-12-09T03:28:06+00:00
- Post Title: Re: Monopoly's huge .GCF file.

> Reply from Zench
>
> The uncompressed size is the size before all of the file entries are compressed with zlib (and it would be the size after they are decompressed). So you basically construct the file info entries and the size of that is the uncompressed size, and then you compress it with zlib, and then that is the compressed size. If it actually uncompresses to a different size that what that value is, I don't know what to tell you. Re-compression should be okay, though.
 , 

I think first 2 bytes are not a uncompressed file header size.
[MonoPoly-GameEditor.rar](https://xentaxbackup.github.io/file/1773_MonoPoly-GameEditor.rar)
## Post #21
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-12-10T13:57:12+00:00
- Post Title: Re: Monopoly's huge .GCF file.

> Reply from delgerdalai
>
> I think first 2 bytes are not a uncompressed file header size.You're right -- and I don't know else what they could be, unfortunately. You'll just have to experiment with it. By the way, neat tool.
## Post #22
- Username: andyloi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 29, 2010 4:42 am
- Post datetime: 2010-04-03T17:56:29+00:00
- Post Title: Re: Monopoly's huge .GCF file.

please!
how to edit the language file?
## Post #23
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2010-04-03T23:36:43+00:00
- Post Title: Re: Monopoly's huge .GCF file.

Has anyone been able to dig out the Chance and Community Chest card images in the Here & Now version?
## Post #24
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-08-28T17:20:58+00:00
- Post Title: Re: Monopoly's huge .GCF file.

Is there a way to recompile the .gcf file?
## Post #25
- Username: ZeoWorks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 22, 2016 8:36 am
- Post datetime: 2016-12-22T14:14:23+00:00
- Post Title: Re: Monopoly's huge .GCF file.

Any updates on this?
I'm trying to mod this game to have other editions with different boards and stuff.
When using the "Game editor" provided in this thread; the game will recompile ok, but when I click on the .exe to play I'll get an error and it wont boot.
I am simply changing image graphics.  Thanks!
## Post #26
- Username: ZeoWorks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 22, 2016 8:36 am
- Post datetime: 2017-01-22T01:14:13+00:00
- Post Title: Re: Monopoly's huge .GCF file.

I'm willing to pay someone to come forward and create a working recompile system (so images can be edited in an external program then recompiled back into a gcf file).
The tool in this topic does not allow this unfortunately, it causes crashes when you attempt to play the game with a gcf modified with the current tool on this topic.
## Post #27
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2017-01-22T04:12:38+00:00
- Post Title: Re: Monopoly's huge .GCF file.

Has anyone been able to find out where the Chance and Community Chest card images are hidden?
## Post #28
- Username: Moosicus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 19, 2017 8:50 pm
- Post datetime: 2017-04-19T13:29:45+00:00
- Post Title: Re: Monopoly's huge .GCF file.

I have wanted to see how the graphics for TikGames Monopoly are constructed for years, and was poking around the game files tonight, trying out various things (gcfscape, etc - none of which worked).  So I did a search on TikGames Monopoly game.gcf and found this thread.  

I can confirm that Zench's excellent GcfExtr tool works great to extract the the SWF files from game.gcf for TikGames Monopoly and that the SWF Picture Extractor works great to extract the images from the SWF file to JPB, BMP, and PNG.  (It took a while to run on my old laptop - maybe 5 minutes or so to do the extract and save).

Anyway, just registered here so I could post and say thanks.  


> Reply from bizzybody
>
> Has anyone been able to find out where the Chance and Community Chest card images are hidden?

Sorry, can't help with this.  I don't have Here and Now.  The links you provided on page 1 no longer work.  Have you looked in all of the extracted SWFs ?
## Post #29
- Username: matan2001
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 11, 2018 4:31 am
- Post datetime: 2018-08-10T20:51:07+00:00
- Post Title: Re: Monopoly's huge .GCF file.

Just registered an account for this forum in order to try and extract the catchy music from the Monopoly game, and I'm glad to say the GcfExtr tool works absolutely wonderful! Thank you so much Zench!

Also, I've found a tool which really helps editing the main game.swf. The program is called "JPEXS Flash Decomplier" and it allows extraction and editing of all sprites, images, texts, fonts, scripts and more. [https://github.com/jindrapetrik/jpexs-decompiler](https://github.com/jindrapetrik/jpexs-decompiler)

> Reply from bizzybody
>
> Has anyone been able to find out where the Chance and Community Chest card images are hidden?If you go into JPEXS and onto the "images" section in the "game.swf" file, you'll find there the Chance and Community Chest image (you'll need to scroll down a bit).
