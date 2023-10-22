## Post #1
- Username: R66FPlaysGames
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 30, 2022 8:55 pm
- Post datetime: 2022-10-31T06:53:00+00:00
- Post Title: How do I extract files from game archives that have damaged, or no, headers?

Is there any way to do this? The file that I am wanting to try this out on is this one: [https://www.dropbox.com/s/r0gduecsqt91i ... c.tlc?dl=0](https://www.dropbox.com/s/r0gduecsqt91isw/RoadLoc.tlc?dl=0)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-01T20:31:47+00:00
- Post Title: How do I extract files from game archives that have damaged, or no, headers?

First of all, you've already created a topic for this TLC file [viewtopic.php?f=10&t=25950](https://forum.xentax.com/viewtopic.php?f=10&t=25950)
So this topic is duplicate - we don't allow duplicates here.  


As for your question - this TLC file is not damaged. It's custom container for files (a.k.a. "archive file").
So not every archive has an obvious header. Some of them are encrypted/compressed or serialized in the weird way.
If you open this file in hex editor (e.g. hex workshop) and look closely at the end of the archive, you will see a directory (file entry list):



screenshot000192.png (18.55 KiB) Viewed 60 times



You can also spot an TGA footer just before start of the directory:



tga_footer.PNG (18.37 KiB) Viewed 60 times



And if you want to extract data, your main job is to figure out entries in the directory and parse them using quickbms script or some custom tool.

More info here: [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
