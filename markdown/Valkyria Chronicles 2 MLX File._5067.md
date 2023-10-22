## Post #1
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2010-09-21T21:50:34+00:00
- Post Title: Valkyria Chronicles 2 MLX File.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-21T21:55:43+00:00
- Post Title: Valkyria Chronicles 2 MLX File.

you would need to post a sample or the start of the file the first 10 mb
## Post #3
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2010-09-21T22:06:59+00:00
- Post Title: Valkyria Chronicles 2 MLX File.

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-09-24T01:15:01+00:00
- Post Title: Valkyria Chronicles 2 MLX File.

Never seen one like this, looks quite probably encrypted.

[edit]
Though if it is encrypted, it looks likely to be half-assed, there's lots of patterns here and there is a TOC marker. Maybe only compressed?

[edit2]
The main CPK header and the TOC header both start off the same way and have a lot of bytes in common. I'll bet these are are both XOR'd with an LCG, same as encrypted ADX, and it looks to be the same one in each case.  I'll try to use the same techniques and see if I can recover the key from the cyphertext.

[edit3]
Yep, par for the wacky CRI course. It's an LCG with initial value 0x5F and multiplier 0x15.  I'll try to put together a modified cpk_unpack that will handle this, and do the guessing (as there should be enough information to narrow it down automatically).

[edit4]
Ok, not entirely automatic, but the builds of cpk_unpack here should at least be able to do the basic utf_tab reading correctly:
[http://hcs64.com/files/utf_tab07b4_special.zip](http://hcs64.com/files/utf_tab07b4_special.zip)
I wasn't able to figure out if the payload is actually encrypted, the .MSB files come out random either way, I assume they might be compressed.
## Post #5
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2010-09-24T13:03:00+00:00
- Post Title: Valkyria Chronicles 2 MLX File.

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: gta1211
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 14, 2011 2:30 am
- Post datetime: 2011-05-19T17:21:16+00:00
- Post Title: Valkyria Chronicles 2 MLX File.

Sorry to bump this topic, but nobody knows how to open MLX files ? Or NPC, HLX, HTX ?

I wanted to extract pictures of characters from VC II, I think it's a compressed/encrypted image file but I don't know what extension it is, and much less how to open it. I suppose that it's many " big " files, so that's why I thought of these four extensions.

If someone has an idea or have time and motivation to work on it, please answer
