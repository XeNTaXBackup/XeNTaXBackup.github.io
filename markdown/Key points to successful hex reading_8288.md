## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T01:46:03+00:00
- Post Title: Key points to successful hex reading

This is not a tutorial. This is more of a "is this what your reality of format reversing is like?"
If you have comments on any of the points feel free to respond. If you disagree with something, that is even more interesting to read.

After talking to some people and reading various posts about it, I think there are a couple important points when it comes to reversing a binary format through hex reading that really doesn't get across, or is not given enough emphasis that people actually keep it in the back of their minds when reading any material about it.

If anything, I think these are what people should know before they even start reading about reversing (eg: [guide to file formats](http://wiki.xentax.com/index.php/DGTEFF#General_Introduction), etc)

I would summarize it in three points:

> 1: Know what you're looking at.
>
> 
>
> You can't begin to understand something if you don't know where to begin.
>
> 
>
> 2: See the big picture.
>
> 
>
> If you don't understand something, just skip it. Chances are, you'll either figure it out later, or realize it's not even important. Also, bytes are just bytes. Their values mean very little; you are only interested in what they represent and how they may be used.
>
> 
>
> 3: Start easy.
>
> 
>
> Some people are ambitious and want to just jump right into their favorite games. Unless it's really easy, you're probably not going to get anywhere, and you'll probably give up quickly. Don't waste your time, get a format out successfully and get a feel of what it's like
First

The first point may be obvious. In fact, it is totally obvious. So obvious that there really is no need to even mention it.
But the fact that some literature don't bother mentioning it creates a problem, because it is clearly wrong to assume people know what that really means.

If you don't know what you're looking at, how can you begin to try to understand what it is?

It is clear that the contents of an archive isn't the same as a 3D model or a picture.
So to reverse an archive, you should treat it like an archive.

That's obvious, so obviously it's clear that when I say "treat it like an archive," you're thinking "where are the archive-related values that I want?"
It's an archive. What kind of data do you think the values would represent?
If you don't know, then this is a good time to review [what an archive is](http://wiki.xentax.com/index.php/DGTEFF#General_Introduction).

Once you know what you're looking for, you should stick to that approach.
A 3D model contains 3D model data. So figure out what "3D model data" could be and start looking for it. (of course, figuring out what it is isn't an easy task)

Second

The second point is only relevant if you actually know what hex is.
If you don't know, then none of this will mean anything to you.

It typically takes 15 seconds to get an idea of what hex is.
It might take a little longer to understand what data types (ints, floats, chars, etc) are and how they are represented (4-bytes, 2-bytes, etc), but it probably takes at most an hour to realize that there are only so many of them and they only come in so many ways.

So then where is the problem? A binary format is just a bunch of data thrown together in some logical way, and all of it is just those data types and those hex values.

My impression is that somewhere along the way, people forget what they are looking at and simply dwell on bytes; I know I do that sometimes when a section makes no sense. Like they are fascinated by how many shorts they can count and not really thinking about what those shorts might represent.

If you were given a format in a nice, easy-to-read text file, I highly doubt people are going to get caught up on how many vowels there are and how often a word appears. So why does that happen with binary files?

Is it because you don't really understand the concept (eg: model, archive, etc)?
Or that you don't really know what you're looking for (eg: model data)?
Or that you don't actually know what the data might be in the first place (eg: it's a model?)?

This is quite mysterious to me.
While a 3D format in a nice text format might clearly say "Vertex: 1.0 1.0 1.0", I don't think seeing three floats in a row is that much different, aside from the absence of "this is a VERTEX".

How do I know 3 floats in a row are vertex coords? I don't.
I just guess that it is, and try it out. And if it looks right, then they're vertex coords.

Don't be afraid to experiment. If you don't like guessing, then you might be better off disassembling routines.

Third

"But I am not good with this sort of thing"

If you're not good at it because
1: you're lazy, or
2: you don't want to start from the basics, or
3: you don't want to learn, or

Then I would suggest giving up and finding something else to do. 

This is an obvious point: you start small, refine your skills, pick up techniques, and then proceed to bigger things.

Tools are available to make things easier, but that doesn't change the fact that you need to get a feel for what it's like before cracking a complex format. You also need to learn how to use the tool, so that just adds to the learning curve.

If you don't want to start easy because

1: you're too proud to bother yourself with trivial matters, or
2: why bother with something that's already been done, or
3: you follow some other philosophy that prevents you from starting from the beginning

Then you should also give up.

The point here is that you should start with the basics, whether it is part of your goal or not.
And your favorite games probably aren't the basics.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-15T14:24:56+00:00
- Post Title: Key points to successful hex reading

I have one tip to add. 

#1 use calc.exe.
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-02-18T01:53:29+00:00
- Post Title: Key points to successful hex reading

My tip, learn what zlib is (since it's free and can be used by ANY company) and the character "x" which is a key identifier of the compression.  The use of zlib seems to be diminishing, but it's still important to know, and easily spot.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-19T22:24:26+00:00
- Post Title: Key points to successful hex reading

when a game uses zlib everything becomes very easy during the reversing of its format:

offzip -S -x archive.dat 0 0
search the compressed and uncompressed sizes reported by offzip using the correct endianes, so if it's little endian and the compressed size is 0x1234 just search 34 12 00 00
check if there is also a relative/absolute offset and you have all the parameters for the extraction
yeah too easy :)
## Post #5
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-01T23:31:00+00:00
- Post Title: Key points to successful hex reading

My tip, write things down.
either with pencil and paper, notepad, or notepad++(has column select)
even if it's just writing down an offset near to something you think is some data, write it down.

If you write it down you can go back and do some more hex reading tomorrow.
## Post #6
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-15T17:44:09+00:00
- Post Title: Key points to successful hex reading

Once I find a function that looks to me like a vertex float, how do I probate that it is?
I don't get it.


and then how do I extract the entire model?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T18:17:37+00:00
- Post Title: Key points to successful hex reading

You use methods to read data and display them in a 3D viewer. This can be your own 3D viewer that you put together from scratch, or any of the existing 3D tools like blender, 3D max, metasequoia, or noesis

If you believe the are vertices, then figure out which one might be the coordinates and plot them.

That involves writing scripts in the appropriate language using the appropriate API provided.
Tutorials are available here for some of the tools, the rest you'll just have to search around.

[viewtopic.php?f=29&t=8319](http://forum.xentax.com/viewtopic.php?f=29&t=8319) - noesis model tutorial 1
[viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739) - noesis model tutorial 2
[viewtopic.php?f=29&t=6932](http://forum.xentax.com/viewtopic.php?f=29&t=6932) - Sanae3D format converter

I used Sanae3D for figuring out 3D stuff at the beginning cause I only knew MQO format at that time.
That was before noesis python API was available, and I'm not a fan of C++.
## Post #8
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-16T03:40:45+00:00
- Post Title: Key points to successful hex reading

Thank you I've read the noesis tutorials and this brings again more question:

1- How do I recognize a bytes integers that represents vertex floats?
2- And I see he is writing codes in a text editor that (from what I understood) he compiles then to import it in noesis.

How does he compile and use it?
## Post #9
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-21T00:45:12+00:00
- Post Title: Key points to successful hex reading

If you want pointers on Hex reading? Why toss about terms like Archives???
Why not talk about the basics before getting things complicated?

I know you're trying to do a good thing here but you've got me confused and things are going off topic as to what I see.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-21T10:02:44+00:00
- Post Title: Key points to successful hex reading

> Reply from Privateer
>
> If you want pointers on Hex reading? Why toss about terms like Archives???
Why not talk about the basics before getting things complicated?

I know you're trying to do a good thing here but you've got me confused and things are going off topic as to what I see.

Real examples hit home more than abstract theory. People want to learn hex because they want to figure out 3d, archives, graphics, and sound.

This is not "what is hex", it's "how you should be approaching it" because I don't think not understanding hex is the real problem.
