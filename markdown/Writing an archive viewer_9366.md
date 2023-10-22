## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-28T21:04:39+00:00
- Post Title: Writing an archive viewer

So I'm using C# to write a simple archive viewer GUI.
I have it working and it loads up my archive and displays all of the file paths in a nice tree view structure.

But I don't have any references to my list of file entries to actually get the offsets and sizes!



Anyone have ideas on how I could reference my entries?
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-07-29T09:17:54+00:00
- Post Title: Writing an archive viewer

[http://msdn.microsoft.com/en-us/library ... (v=vs.100)](http://msdn.microsoft.com/en-us/library/system.windows.forms.treenode.tag%28v=vs.100%29)
## Post #3
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-07-30T20:07:01+00:00
- Post Title: Writing an archive viewer

I've done something similar in VGMToolbox, see the source for the ISO Extractor form [here](http://vgmtoolbox.svn.sourceforge.net/viewvc/vgmtoolbox/VGMToolbox/forms/extraction/IsoExtractorForm.cs?revision=828&view=markup).  Drop me a PM if you have any questions.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-31T00:33:35+00:00
- Post Title: Writing an archive viewer

I guess using that tag property is the easiest way to go. I'll go with that for now.
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-10T19:40:11+00:00
- Post Title: Writing an archive viewer

i'm not familiar with c# in any way, but you only need store all the file data in an array(or vector or similar) and have the tree items hold an index so the file data array.
## Post #6
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-16T21:26:02+00:00
- Post Title: Writing an archive viewer

Finale00 great job.
Could you please give me a link to some toturials where to start from ? what you did is just what i wanted to do also in c#.
But i want to learn to do it. 

If its not so hard to learn and understand could you give me some guide so i can get at least to the point you did ?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-17T17:21:24+00:00
- Post Title: Writing an archive viewer

I already knew what I wanted to do so it was a matter of looking at how to write it in C#.

1: you start by figuring out the archive format
2: then you write an unpacker script (to verify the format is correct)
3: then you make the GUI and have it run the unpacker script (you might re-write the script in C# if you didn't already)
4: the unpacker script doesn't actually unpack anything in GUI mode; instead, it parses it and returns a list of file entries, which you can draw on the GUI
5: users then choose what to unpack: everything, selected items, selected folders, etc.

Everything I needed was on stackoverflow and microsoft's online docs.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-08-25T05:12:55+00:00
- Post Title: Writing an archive viewer

> Reply from finale00
>
> I already knew what I wanted to do so it was a matter of looking at how to write it in C#.

1: you start by figuring out the archive format
2: then you write an unpacker script (to verify the format is correct)
3: then you make the GUI and have it run the unpacker script (you might re-write the script in C# if you didn't already)
4: the unpacker script doesn't actually unpack anything in GUI mode; instead, it parses it and returns a list of file entries, which you can draw on the GUI
5: users then choose what to unpack: everything, selected items, selected folders, etc.

Everything I needed was on stackoverflow and microsoft's online docs.

Or you could skip having to write a GUI and just write a MexScript.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-25T19:03:43+00:00
- Post Title: Writing an archive viewer

> Reply from Dinoguy1000
>
> 
Or you could skip having to write a GUI and just write a MexScript.

Usually I would expect an unpacker eventually becomes a re-packer, and support specific functionality for the particular format.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-08-26T01:47:34+00:00
- Post Title: Writing an archive viewer

> Reply from finale00
>
> Dinoguy1000 wrote:
Or you could skip having to write a GUI and just write a MexScript. 

Usually I would expect an unpacker eventually becomes a re-packer, and support specific functionality for the particular format.

MultiEx Commander allows for repacking archives, though I don't understand very well how it decides whether it can or can't repack a given archive format (and I definitely have no comment on format-specific functionality).
