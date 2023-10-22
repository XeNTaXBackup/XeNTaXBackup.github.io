## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-01T23:39:06+00:00
- Post Title: tutorial on tutorials

This is mainly for people that read tutorials
As someone that knows something that others may not and may want to learn as well, it's hard for me to write from the perspective of someone that doesn't know anything about it.

What are ways to write effective tutorials? Especially concerning the nature of the kinds of topics this community deals with. It is quite technical and can very easily assume you know a whole lot about whatever it's talking about.

Some things that would help are things like clearly defining any sort of technical term used and taking care not to gloss over any steps cause people might not understand the rationale.

Though there aren't that many tutorials so hard to say whether improvements can be made lol
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-06T23:28:47+00:00
- Post Title: tutorial on tutorials

I think I've gotten worse at writing tutorials as I've gotten older. It's easy to forget that all of the little things that now come to you innately are still unknown to most of your readers.

That said, though, I think it's unreasonable to try to encapsulate too much information in a single tutorial. At some point it stops being a tutorial and becomes a novel. Especially when it comes to reversing 3D model formats, there's just too much ground to cover everything. So it's pretty reasonable to write tutorials to target a certain level of knowledge and experience.

I think a series of tutorials covering everything up to the point of being reasonably well-prepared to write Noesis scripts to handle new (and previously-unspec'd) model formats would be something like:

1) Linear algebra and vector/matrix math, and how it applies to 3D games. (this assumes that the reader has something at least resembling a highschool-level math education to start)
2) Low-level computing concepts, including data storage and processing.
3) 3D rendering semantics and implementation, and how it applies to modern GPU pipelines.
4) Understanding raw binary on a higher level, and common high-level data types. Covers interpreting binary data as understandable structures and values, and gives examples of common things to look for, from tables/offsets to actual primitive data and common forms of mesh/draw structures.
5) The Noesis framework, and how it relates to all 4 of the other topics.

Putting all of that in 1 tutorial would be a bad idea. A series of tutorials could work nicely, though.
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-03-06T23:41:45+00:00
- Post Title: tutorial on tutorials

I am not very good at writing tutorials, but when I do, I always try to include as many screenshots as I can, or even make it a video tutorial.  Years ago I would write text only tutorials, and looking back at them and reading them now, they could have been made so much better by just adding a few screenshots to them.

As an example, I've seen tutorials that deal with the values and offsets inside a file, yet they write everything out, instead of taking a screenshot of the info as viewed in a hex editor.  People absorb information visually a lot more easily than just reading it.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-03-15T20:42:23+00:00
- Post Title: tutorial on tutorials

Keeping in mind that I've never written a tutorial myself, it seems a good method to writing one is considering the full scope of what you're trying to teach, and breaking it down into its parts. Write a separate tutorial on each individual part, and focus on making that specific part as well-written as you can before moving on to the next (though you shouldn't hesitate to go back and update parts you've already completed as you go). If you find a part you're writing about is more complicated then you expected, break it down further.

Yes, this is the same approach many programmers use to write programs. That's not a coincidence.  

As far as writing tutorials for our own use, we have [the wiki](http://wiki.xentax.com/index.php?title=Main_Page) (though we're having a few problems with it that can't currently be resolved); do not underestimate the power of wiki software used as a collaborative tutorial-writing tool.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-03-15T20:44:05+00:00
- Post Title: tutorial on tutorials

> Reply from Dinoguy1000
>
> Keeping in mind that I've never written a tutorial myself, it seems a good method to writing one is considering the full scope of what you're trying to teach, and breaking it down into its parts. Write a separate tutorial on each individual part, and focus on making that specific part as well-written as you can before moving on to the next (though you shouldn't hesitate to go back and update parts you've already completed as you go). If you find a part you're writing about is more complicated then you expected, break it down further.

And actually, thinking about it, this was a good chunk of the problem with the [Definitive Guide to Exploring File Formats](http://wiki.xentax.com/index.php?title=DGTEFF): it was far too ambitious in scope, meaning after it was written, it was very hard to update it.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-03-15T21:38:55+00:00
- Post Title: tutorial on tutorials

Hey, Dino, what's that? It's DEFINITIVE! No need to update!
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-03-15T21:55:29+00:00
- Post Title: tutorial on tutorials

Aah, but of course! What could I possibly have been thinking?!
