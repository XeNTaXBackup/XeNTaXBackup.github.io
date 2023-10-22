## Post #1
- Username: TheLynx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 27, 2014 4:52 pm
- Post datetime: 2014-09-27T09:04:16+00:00
- Post Title: [Help] How to get started in unpacking game files?

I want to start unpacking and repacking game files. I have a great understanding of C++, and a mediocre background in rev engineering with Cheat Engine / Olly / IDA, but I'm not anywhere near good and I have no idea where to even begin to get better.

A lot of the resources on here specifically refer to models but I'm interested in everything about the game, such as hard coded information like the shader scripts found in Watch_Dogs. Thanks for any help on this, I really just want to get better at reverse engineering.
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-28T01:08:38+00:00
- Post Title: [Help] How to get started in unpacking game files?

The DGTEFF over at the Xentax Wiki is a great place to start learning about reverse engineering game archives. If you can follow that guide, you've learned the most basic skills needed for figuring out archives. [http://wiki.xentax.com/index.php?title=DGTEFF](http://wiki.xentax.com/index.php?title=DGTEFF)

Something else to keep in mind are common file format headers and compression algorithms. With those in mind you can quickly identify common file formats packed within archives. For example if you see 78 DA or 7C DA, you know the data is Zlib compressed.
