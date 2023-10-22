## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-01T05:13:50+00:00
- Post Title: TXM to TGA?

I'm modding an old game (Die By The Sword) and planned to make a player variant of a training dummy just for fun to find out this fellow has TXMs instead of the regularly used TGA or BMP. TXM is a type of obsolete texture use for the old version of the game and is uncompressed. Would it be possible to convert the TXM format listed below to a format like the TGA it uses (also listed)?
[BLADE.zip](https://xentaxbackup.github.io/file/1045_BLADE.zip)
## Post #2
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-02-01T13:16:30+00:00
- Post Title: TXM to TGA?

Your picture easily oppens as 8 bit RAW 256x256 and 36 bytes header. I do not think I see any information about palette there.  Unless that hex 20 on the begining of the file stands for something? There must be in other files of the game some palette file.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-01T23:45:45+00:00
- Post Title: TXM to TGA?

Thank you for the info. I'll see if I can find the pallete data. If I do find it it should be very possible correct?
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-01T23:53:40+00:00
- Post Title: TXM to TGA?

Alright, I found palette data in the trainer stage. This is the one it uses I believe.
[palette.zip](https://xentaxbackup.github.io/file/1046_palette.zip)
## Post #5
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-02-02T01:52:05+00:00
- Post Title: TXM to TGA?

PMView [http://www.pmview.com/](http://www.pmview.com/) will do the trick.

Load TXB as RAW (256x256 8bit in Photoshop or other) then save to 24bit RGB, and then open it in PMView while loading IFF palette. It will save the result to TGA as desired. 

Not sure though if the palette indicated  by you  was the right one because the picture was not too colorful. But that was some old game, was it not ?
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-02T05:20:51+00:00
- Post Title: TXM to TGA?

Was it brownish?
## Post #7
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-02-02T13:19:53+00:00
- Post Title: TXM to TGA?

Brownish/bluish.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-03T03:17:37+00:00
- Post Title: TXM to TGA?

Open it as raw in PMView?
## Post #9
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-02-04T00:57:04+00:00
- Post Title: TXM to TGA?

> Open it as raw in PMView?
No. I am afraid,  PMView does not support this format. I use Photoshop to "open as" RAW. What other free and popular programs support RAW. Perhaps GIMP? If not u can always d/l trial version of Photoshop.

PMView suports IFF format with palette.
## Post #10
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-05T19:42:18+00:00
- Post Title: TXM to TGA?

XNView supports RAW images afaik. It's freeware
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-06T05:41:04+00:00
- Post Title: TXM to TGA?

And pallette files as well? Like IFF?
