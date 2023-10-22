## Post #1
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-11-16T20:33:22+00:00
- Post Title: ZLib library - Compression + Decompression

I need a zlib library that I can use in my C# program. I've tried zlib.net, but it has some wierd compression error, were my output stream can end up with a length of 2? So I need one that works 100%.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-17T19:38:59+00:00
- Post Title: ZLib library - Compression + Decompression

[http://datacompression.info/Zlib.shtml](http://datacompression.info/Zlib.shtml)
maybe there's something for you.
## Post #3
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-11-19T02:52:48+00:00
- Post Title: ZLib library - Compression + Decompression

Thanks, that led me to a xceed library that worked perfect!
## Post #4
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-29T13:25:06+00:00
- Post Title: ZLib library - Compression + Decompression

Is there a finished tool for it?
I cannot code but would really need a program to compress files with zlib. For some strange reason I cannot find any  

EDIT: ZOMG 2k8 topic x.x I'm sorry  But please help me anyway ^^"
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-08-29T15:51:42+00:00
- Post Title: ZLib library - Compression + Decompression

> Reply from eycaramba
>
> ... a program to compress files with zlib.

Maybe Rheini's zlibc is what you are looking for [viewtopic.php?p=20205#p20205](http://forum.xentax.com/viewtopic.php?p=20205#p20205)
## Post #6
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-29T16:27:31+00:00
- Post Title: ZLib library - Compression + Decompression

Yeah, this is exactly what I am looking for. Thank you, this is really nice 
The thing is I have to deal with a filesize limit. If I re-compress the original unmodified file, the filesize exactly matches.
If I compress the modified file, the filesize is way bigger oO
Is this due to how zlib's algorhythm works? The Size on disk is the same, however I need to put back that file in a binary dump hex file and so yah...

Is there no other possibility than finding and modifying the file table (if there is any)?
## Post #7
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-08-29T19:32:52+00:00
- Post Title: ZLib library - Compression + Decompression

I know nothing about compressing/programming etc., but did you try all 9 compression levels with zlibc?
## Post #8
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-30T07:19:52+00:00
- Post Title: ZLib library - Compression + Decompression

Yep. Mostly the same result, but never small like the original...
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-08-30T09:45:30+00:00
- Post Title: ZLib library - Compression + Decompression

Hmm I have no idea. Maybe Rheini or some "veteran" user could help you.
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-30T11:12:35+00:00
- Post Title: ZLib library - Compression + Decompression

> Reply from eycaramba
>
> If I compress the modified file, the filesize is way bigger oO
deflate basically works by exploiting repetitions in the code. It does so by using a history window that keeps track of the last x read bytes (e.g. 1KB). So if you modify the contents you get a different compression result.
## Post #11
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-08-31T19:09:38+00:00
- Post Title: ZLib library - Compression + Decompression

Here's a few things to help with zlib compression/decompression.  None of this is my creation, but the APL Zlib Tool can not be found anywhere on the internet anymore, so I uploaded it to my website for those that want to try it.  I can not remember who created the actual APL Zlib Tool, or I could give the original author credit for it.  I also have some source code that this tool was based on, and the source code according to the readme file is made by Mark Nelson, Tiny Software, markn@tiny.com, http://web2.airmail.net/markn, but I can no longer find this person on the internet, nor can I find a working website for him or his company.

Well anyway, here is the source code for the library:
[http://brienj.home.insightbb.com/zlibtool.zip](http://brienj.home.insightbb.com/zlibtool.zip)

And here is the installer for the APL Zlib Tool:
[http://brienj.home.insightbb.com/aplzltsetup.rar](http://brienj.home.insightbb.com/aplzltsetup.rar)

The APL Zlib Tool has the option to change the compression level from 0 to 9 and works with all zlib compression I've tried it on.  I was once going to make a program to do it, but why re-invent the wheel, as they say.  

Hope this is useful to some people.
