## Post #1
- Username: OmegaThree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2004 5:06 am
- Post datetime: 2010-05-23T18:58:37+00:00
- Post Title: LEGO Universe

Hey guys.

I'm waiting to hear back from NetDevil regarding the TOS for LEGO Universe closed beta (of which I am part).  In an act of gross oversight, the TOS is not available anywhere on the site, in the closed forum, in the game folder. or in any of the e-mails I've received re: LU.  As such, I can't make any public posts regarding this, but . . .

I wrote a tool to extract all files from LU .pk archives.  It's actually very simple:  the archive index is stored at the end of the file, with the item count at the very end.  The index contains hash ID's for each item.  The hash ID's are defined in a separate set of plain-text (*.txt) files in another folder.  You just need to read in the hash set, stuff it in a dictionary, read the archive contents, extract the files (based on size and location, which are given in the index), get filenames from your hash dictionary, and write out the files with their actual name and directory structure.  Piece of cake.

Again, since I don't have the TOS and don't know NetDevil or Xentax's stance on beta information, I won't post the source, but if you want it, PM me.  It's VS2008, .NET 2.0, console application with embedded command-line interface.  When I figure out the TOS, if it's okay for me to post the source here, I'll do that.

By the way, since LU uses the NetDevil engine, the models are in NIF/KF format and can be read/modified by NifTools and NifSkope, etc.

EDIT:  After verifying that it's safe, I've added the extractor C# solution.  As of 17-Aug-2010, I have not confirmed that it works with the absolute latest version of LEGO Universe.  If it doesn't, you at least have a good starting point for updating it.  A few of the files won't extract (namely levels); I don't know why, nor do I particularly care because I really just wanted the Lua scripts.

Usage:  run the program, follow the on-screen instructions.  If you installed LU to the default location, you don't have to type a path; just press enter (this works for 32- and 64-bit versions of Windows).  Dots mean a file was extracted; X's mean it wasn't; question marks (?) mean the hash record wasn't found.  File/folder compression is still experimental; it may or may not work for you.  (It works for me.)

If you don't have VS2008 (or 2010, or 2005 for that matter), you can download an Express edition for free (C#).  Requires .NET 2.0.
[LUPKExtractor.zip](https://xentaxbackup.github.io/file/3339_LUPKExtractor.zip)
## Post #2
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2010-09-07T15:29:45+00:00
- Post Title: LEGO Universe

I checkrd it. It works with the actual files but some (in the Maps section are double-packed (in an unknown format). With my special patcher i bypassed thisproblem and get some mysterious raw files.
I zipped the avant garden diectory and uploaded it.

[http://www.speedyshare.com/files/241525 ... ardens.zip](http://www.speedyshare.com/files/24152562/avant_gardens.zip)
## Post #3
- Username: bartvbl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 27, 2010 7:28 am
- Post datetime: 2010-11-27T12:24:23+00:00
- Post Title: LEGO Universe

Thanks a lot for that extractor!
I tried it one my last backup of lego universe; the one I made the day before the beta ended, and it all extracted fine. It had some problems with a part of the textures, though, but it didn't seem too serious. 
Me and a friend have already been looking into the LU files for some time now, and we have been digging up some nice concept art, like the file I attached. Until now we have only had access to the files of my earliest beta backup; as that one didn't contain any pk files yet. Let's hope there are hidden some more interesting files in the later versions 
So thank you for helping out with that =)
[minifig_factory_task.png](https://xentaxbackup.github.io/file/3644_minifig_factory_task.png)
## Post #4
- Username: bm1
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2011-11-04T21:55:35+00:00
- Post Title: LEGO Universe

> Reply from OmegaThree
>
> Hey guys.

I'm waiting to hear back from NetDevil regarding the TOS for LEGO Universe closed beta (of which I am part).  In an act of gross oversight, the TOS is not available anywhere on the site, in the closed forum, in the game folder. or in any of the e-mails I've received re: LU.  As such, I can't make any public posts regarding this, but . . .

I wrote a tool to extract all files from LU .pk archives.  It's actually very simple:  the archive index is stored at the end of the file, with the item count at the very end.  The index contains hash ID's for each item.  The hash ID's are defined in a separate set of plain-text (*.txt) files in another folder.  You just need to read in the hash set, stuff it in a dictionary, read the archive contents, extract the files (based on size and location, which are given in the index), get filenames from your hash dictionary, and write out the files with their actual name and directory structure.  Piece of cake.

Again, since I don't have the TOS and don't know NetDevil or Xentax's stance on beta information, I won't post the source, but if you want it, PM me.  It's VS2008, .NET 2.0, console application with embedded command-line interface.  When I figure out the TOS, if it's okay for me to post the source here, I'll do that.

By the way, since LU uses the NetDevil engine, the models are in NIF/KF format and can be read/modified by NifTools and NifSkope, etc.

EDIT:  After verifying that it's safe, I've added the extractor C# solution.  As of 17-Aug-2010, I have not confirmed that it works with the absolute latest version of LEGO Universe.  If it doesn't, you at least have a good starting point for updating it.  A few of the files won't extract (namely levels); I don't know why, nor do I particularly care because I really just wanted the Lua scripts.

Usage:  run the program, follow the on-screen instructions.  If you installed LU to the default location, you don't have to type a path; just press enter (this works for 32- and 64-bit versions of Windows).  Dots mean a file was extracted; X's mean it wasn't; question marks (?) mean the hash record wasn't found.  File/folder compression is still experimental; it may or may not work for you.  (It works for me.)

If you don't have VS2008 (or 2010, or 2005 for that matter), you can download an Express edition for free (C#).  Requires .NET 2.0.

There is no exe file in the zip. I can't figure out how to extract it. PLEASE HELP!
## Post #5
- Username: Rokreder
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 18, 2012 11:01 pm
- Post datetime: 2012-04-16T17:51:42+00:00
- Post Title: LEGO Universe

> Reply from masterX244
>
> I checkrd it. It works with the actual files but some (in the Maps section are double-packed (in an unknown format). With my special patcher i bypassed thisproblem and get some mysterious raw files.
I zipped the avant garden diectory and uploaded it.

http://www.speedyshare.com/files/241525 ... ardens.zip
Hi! 
Could you explain how you bypassed the problem? 
I have been wondering about those files myself and if you could tell me how you got the raw files, That would be great.
I would like to have those raw files as because I belive i know how to use them...  

Thank you in advance!

Rokreder
## Post #6
- Username: Rokreder
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 18, 2012 11:01 pm
- Post datetime: 2012-04-16T17:55:17+00:00
- Post Title: LEGO Universe

Oh, and is there anything that can be done with the X-es? 
Some way of manually extracting those the program did not?

It annoys me that there where more then 100 of them.

Thanks!

Rokreder
