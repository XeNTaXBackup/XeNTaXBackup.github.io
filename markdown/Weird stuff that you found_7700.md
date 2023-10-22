## Post #1
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-16T21:45:53+00:00
- Post Title: Weird stuff that you found

This thread is for stories that are about the (sometimes) fun things you find while
diving into game files. 




0x0D0A or 'Why I hate typewriters'

What is 0x0D0A to you? Two bytes like 15 and 12? You would read them as two separate chars?

Let me tell you a short story: (.arc = archive for Tales of the World: Radiant Mythology 1+2+3)
When I was trying to decompress a GZIP compressed .arc file that was inside an .arc file that was GZip compressed beforehand (talk about overkill)
I wondered why sometimes the header (and the data part) were misaligned by one byte.
After many searches and misunderstandings I realized that the header parts use a PER CHAR calculation and the offsets are also on a PER CHAR basis.
"But", you would say, "there is no character that is longer than one byte, right?"

That depends.

(I would suggest you to read this http://www.perlmonks.org/index.pl?node_id=68687 it's about newline characters and explains the problem pretty well)

Apparently the "real" and "complete" windows newline (\n) (when reading in binary) is 0x0D0A, AFAIK those two bytes are handled like
a single char (="\n") by the game.

Based on this knowledge I could successfully implement a .dgn extractor for the second installment of the aforementioned series
because as soon as the file format reaches the 0D (16th) node it doesn't write the uint32_le as 0x0D000000 = 4 bytes  but instead as 0x0D0A000000 = 5 bytes.

This is seriously messed up.

P.S.: I also found a (somewhat) working .psd (YES, Photoshop, it has the right header) file inside one of the archives.
P.P.S.: And a Thumbs.db that seems legit (I only took a glimpse at the specs) but can't be opened by anything that reads Thumbs.db files. Maybe it's a little endian version
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-11-18T20:25:26+00:00
- Post Title: Weird stuff that you found


## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-02-13T18:36:32+00:00
- Post Title: Weird stuff that you found

I didn't find it myself, but [this](http://i42.tinypic.com/t0qcg3.jpg) seems to be a series of test images or something in one of the Yu-Gi-Oh! Tag Force games (some background on image extraction for the game(s) can be found [here](http://yugioh.wikia.com/wiki/User_talk:Falzar_FZ#TF_image_extraction)).
