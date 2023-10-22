## Post #1
- Username: Jubb
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 18, 2006 12:45 pm
- Post datetime: 2008-11-08T05:35:26+00:00
- Post Title: Game Ripper/extractor tutorials?

I've been lurking around game modding forums for a very long time but never really contributed anything before. I would really like to, and I'm at a point where I know a decent amount of programming, so I figured I could try writing a program to extract data out of game files. 

I know deciphering the structure of the file is the hardest part, but I was wondering if there are any tutorials on how to write programs to interpret that data and then actually convert it into a known format for everyone to edit and have fun with. Is it simply just parsing the file looking for predetermined patterns of how the data is stored and then writing that out to individual files? None of these rippers usually come with source code so I'm a little uneducated on the subject. 

Any help would be appreciated
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-08T09:07:56+00:00
- Post Title: Game Ripper/extractor tutorials?

Well, you could start with our tutorial on Game Resource Archive Formats : [http://wiki.xentax.com/index.php?title=DGTEFF](http://wiki.xentax.com/index.php?title=DGTEFF)

That would give you an idea how archives work. MultiEx Commander uses a special script language for many formats. ( [http://wiki.xentax.com/index.php?title=BMS](http://wiki.xentax.com/index.php?title=BMS) ). But basically, yes, you collect the information in the archive that concerns offsets, compression, sizes of individual resources in that archive. Then you can save those resources as separate files.
## Post #3
- Username: Jubb
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 18, 2006 12:45 pm
- Post datetime: 2008-11-08T17:17:47+00:00
- Post Title: Game Ripper/extractor tutorials?

Thanks Mr. Mouse you always seem to be the most helpful. When I'm done with that tutorial hopefully I'll be able to contribute some great things.
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-11-10T02:23:47+00:00
- Post Title: Game Ripper/extractor tutorials?

> Reply from Jubb
>
> None of these rippers usually come with source code so I'm a little uneducated on the subject.Which rippers do you want to know more about? I can provide you with some source examples of how to make a ripper/extractor, just to demonstrate the theory of it. And definitely do look into BMS too.
## Post #5
- Username: Jubb
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 18, 2006 12:45 pm
- Post datetime: 2008-11-10T03:49:44+00:00
- Post Title: Game Ripper/extractor tutorials?

any, actually haha i'm interested in any code you got
## Post #6
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-11-12T02:26:42+00:00
- Post Title: Game Ripper/extractor tutorials?

First of all, which programming language(s) are you comfortable with? And also, perhaps you can be a little bit more specific about what you want to learn. Do you want to make MexCom plugins? The source code to Game Extractor by Watto is available [here](http://downloads.sourceforge.net/gameextractor/source_20.zip) (in Java). If you want to know how to write a ripper like Jaeder Naub I can explain the theory behind that. A lot of the source I've written in the field of game extraction hasn't been released (because it was useful only for my experimentation). Besides that I don't have any source that hasn't been released to everyone.

Hmmm... I guess I didn't release the source of GEPlugins. Just PM me if you (or anyone) want(s) it.
## Post #7
- Username: Jubb
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 18, 2006 12:45 pm
- Post datetime: 2008-11-12T15:41:41+00:00
- Post Title: Game Ripper/extractor tutorials?

Wow thanks I can't believe that was written in Java haha is it really slow? I've never used that extractor before. 

To answer your questions I am most comfortable with Java and C++ but i'm sure I could pick up whatever other language these things may be written in. Also I'm not really looking to make mexcom plugins but I might at some point in the future. So, yes I am looking to write a ripper like Jaeder Naub and a little more information on the subject would be lovely.
## Post #8
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-11-12T20:03:38+00:00
- Post Title: Game Ripper/extractor tutorials?

The (old) source for MultiEx Commander is available at [http://sourceforge.net/projects/mexcom/](http://sourceforge.net/projects/mexcom/) as well, if you're interested.
## Post #9
- Username: Jubb
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 18, 2006 12:45 pm
- Post datetime: 2008-11-13T22:48:57+00:00
- Post Title: Game Ripper/extractor tutorials?

Cool, I'll be sure to check that one out too. Would you say there have been a lot of major changes to the structure since that release?
## Post #10
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-11-14T00:56:07+00:00
- Post Title: Game Ripper/extractor tutorials?

The basic strategy of writing a ripper is to load a block of the file into memory, and then search for signatures of media files or whatever kind of file you want to extract. After a signature is found, it reads this sub-file to make sure that it is indeed that particular kind of file. It also must calculate the size of this sub-file. Here is a little source code fragment of my ripper. I wrote it quite some time ago. It might be a bit complicated, since there are a bunch of other things it does too. I hope you can get something out of it anyways.
[RipperCodeFragment.zip](https://xentaxbackup.github.io/file/1741_RipperCodeFragment.zip)
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-14T12:05:25+00:00
- Post Title: Game Ripper/extractor tutorials?

> Reply from Jubb
>
> Cool, I'll be sure to check that one out too. Would you say there have been a lot of major changes to the structure since that release?

Well,yes, actually. And it's been a lot more organized since . Nevertheless, the basic method of the scripting process is there, the way multiex.dll works is not changed a lot.
## Post #12
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-11-14T18:54:34+00:00
- Post Title: Game Ripper/extractor tutorials?

You really ought to update the SourceForge project with some newer code, Mr. Mouse...
