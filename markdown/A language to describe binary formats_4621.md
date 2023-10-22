## Post #1
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2010-06-16T14:04:14+00:00
- Post Title: A language to describe binary formats?

For some time, I've been thinking about creating a language to describe binary formats and automatically generate code to read, write and calculate its size in some popular programming language.

I've noticed that when I implement some binary format, I spend most of the time creating duplicate and dumb code. For example, for a simple package binary format, I might do the following:

 Create some structures to describe the format.
 Create code to read the format. This is usually just calling some "read" function on each member of the structure.
 Create code to write the format. This is usually just calling some "write" function on each member of the structure.
 Sometimes, I also create code to calculate the size of parts of the format. Again, this is usually just calling some "size" function on each member of the structure.

Does something similar already exist? (I know that some hex. editors have a "structure viewer" feature that allows you to read and modify some formats, but all I know are pretty limited). Or did someone already think something about this, but gave up?
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-06-16T14:49:45+00:00
- Post Title: A language to describe binary formats?

I've thought about this quite some time ago.
A language like [http://www.sweetscape.com/010editor/templates.html](http://www.sweetscape.com/010editor/templates.html) is straightforward to write AND read.
But the big problem is generality: How do you tell the extractor tool which variable means what?

You either end up doing something like BMS by implementing every atomic possibility or you need to extend such a binary template language so you can code read and write functions in each template individually.
## Post #3
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2010-06-17T01:49:58+00:00
- Post Title: A language to describe binary formats?

I have already built something similar, instead of it actually being a language i built it more as a description.  To describe the format.
## Post #4
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2010-06-18T17:59:54+00:00
- Post Title: A language to describe binary formats?

> Reply from Rahly
>
> I have already built something similar, instead of it actually being a language i built it more as a description.  To describe the format.

Can you show/explain us how it is? I'm having some problems with some areas, specially about how to manage file offsets and synchronize array lengths.
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2011-01-20T01:08:47+00:00
- Post Title: A language to describe binary formats?

Figured it out?
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-01-20T23:40:18+00:00
- Post Title: A language to describe binary formats?

RAHLY!
## Post #7
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2011-01-22T20:57:46+00:00
- Post Title: A language to describe binary formats?

010 editor has come up with a pretty good system for doing this. They give you a way to describe the format and then they allow you to extend the basic read/write for structures so that you can edit them yourself without having to open the structure tree and edit each variable of the structure. There will be no "catch all" way of describing a format that allows for reading, writing (i assume inserting files or something), and for determining the size of an archive format without having at least a little code on each of the format's code files. 

My idea would be to provide a way of editing the basic types (byte, short, int, int64, float, double) and a way of providing or overriding the read/write functions for types. 010's C++ way is very simple to use when you get used to it and I have yet to come up against a file that I knew the structure of it and couldn't make a format description for. So I'd say go with that or something similar.
