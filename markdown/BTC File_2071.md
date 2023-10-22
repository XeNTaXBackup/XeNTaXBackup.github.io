## Post #1
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2006-09-03T19:27:03+00:00
- Post Title: BTC File?

In the game Links 2003 there is a BTC file used as the overhead sky texture.

  Anyone know anything about this format?

  Thanks.

  Here's a link to the image: [http://upload4.postimage.org/sports/gol ... /golf.html](http://upload4.postimage.org/sports/golf/linkscorner/423246/golf.html)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T16:57:30+00:00
- Post Title: BTC File?

I cannot tell much about the BTC format when its shown as a JPEG =D

maybe you have the BTC file to upload somewhere?
## Post #3
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2006-10-23T20:21:30+00:00
- Post Title: BTC File?

A little more info..

In Links the sky consists of 2 files...A TGA file which is used to display a preview of the sky within the course design tool and a BTC file (as it is called) of which I have no idea.. Both files are compressed into a data library using ZLib compression.

I can easily extract the compressed TGA and decompress it using a zlib decompressor tool..The outcome is a very nice 1280x85 TGA file of a sky..

I can also extract the BTC file and decompress it...what comes out is I think the question being asked..

Here is the header information for the so called BTC file

796B 7300 C012 0000 4001 0000  1300 0000 0200 0000
6465 7375 0280 0000 D121 941B

796B 7300 is I assume some sort of file identifier...(it is not the file length)  C012000 and 4001 0000 appear to be the file dimensions 4800x320 pixels

1300 0000 is = 19 I was assuming that this probably describes the length of the header / start of graphics data and 0200 000 is obviously 2 

Another view could be 1300 is 19 and 0000 0200 0000 is like the start of a TGA file..

Anyway any help on what this graphics file format might be is greatly appreciated...

Andrew
## Post #4
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2006-10-23T20:29:15+00:00
- Post Title: BTC File?

Here is the full uncompressed BTC file and the uncompressed TGA file

Sky01decomp is the BTC and skyo2.tga is obviously the TGA file

Both files in zip

[http://www.apcd2003.com/img/btcfile.zip](http://www.apcd2003.com/img/btcfile.zip)
## Post #5
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2006-10-23T20:49:49+00:00
- Post Title: BTC File?

Of course it is quite possible that this in itself is not a graphics file but yet another layer of compression.  It could be that the BTC is really some sort of block truncation coding of the base graphics file...

If that is the case any one know of a tool to decompress and recompress...A
## Post #6
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2006-10-27T19:39:07+00:00
- Post Title: BTC File?

Okon further investigation the 19 refers to the number of chunks for want of a better word...It appears that the large TGa has been broken into a number of chunks...I am assuming that this is because it only needs to render a piece of it at a time....

But who knows..
## Post #7
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-12T15:30:24+00:00
- Post Title: BTC File?

I have now completed an application that converts these btc files into tga files.  If anyone is still interested ( 5 years later) PM me.
