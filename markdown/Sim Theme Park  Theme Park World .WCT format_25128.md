## Post #1
- Username: xezno
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 14, 2019 5:19 am
- Post datetime: 2022-03-09T01:25:21+00:00
- Post Title: Sim Theme Park / Theme Park World .WCT format

Hey all,

I'm currently working on a re-implementation project for Sim Theme Park, a game released by Bullfrog in 1999. The idea is that, since the game doesn't run very well on modern computers, it'd be a decent idea to re-write the game's "engine" and interface with assets that exist in a real copy of the game.

So far, I've done a decent amount of reverse-engineering on my own - but there's a couple of formats that I'm stumped on, namely the game's texture format: "WCT".

I know little about this file format. My initial ideas are as follows (based on attached blue.wct):

```
	- 13 - Unknown
	- 01 - Has alpha
	- 20 - Image bits per pixel
	- 04 - Compression flag?

40 00 - 2 bytes: Image width

40 00 - 2 bytes: Image height

14 00 - 2 bytes: Unknown

1e 00 - 2 bytes: Unknown
1e 00 - 2 bytes: Unknown

14 00 - 2 bytes: Unknown

7d 01 00 00 - 4 bytes: Length of first section
54 00 00 00 - 4 bytes: Length of second section

( First section )

00 - 1 byte: Padding

( Second section )

```


I think this is really as far as I can get on my own though - I've been stumped on this for a while, so I thought I'd ask around and see if anyone else has any ideas? Any help is very much appreciated.

As for examples, there's many within the archive files in the game, but I've attached few for people who don't want to go through the process of extracting them (with examples of what they should look like).
[WCTs.zip](https://xentaxbackup.github.io/file/21909_WCTs.zip)
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2022-03-09T12:22:53+00:00
- Post Title: Sim Theme Park / Theme Park World .WCT format

[https://gist.github.com/SirKane/27da340 ... feeeb42ed6](https://gist.github.com/SirKane/27da340aeeb9d73e7f8445feeeb42ed6)
## Post #3
- Username: xezno
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 14, 2019 5:19 am
- Post datetime: 2022-03-09T15:57:02+00:00
- Post Title: Sim Theme Park / Theme Park World .WCT format

Absolute legend, thanks for this!
## Post #4
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2022-03-14T11:22:08+00:00
- Post Title: Sim Theme Park / Theme Park World .WCT format

Got code/format info for some of the other file types as well somewhere, if you're interested.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-14T18:15:19+00:00
- Post Title: Sim Theme Park / Theme Park World .WCT format

> Reply from Sir Kane ↑Mon Mar 14, 2022 7:22 pm at Mon Mar 14, 2022 7:22 pm
>
> 
Got code/format info for some of the other file types as well somewhere, if you're interested.

You can add it to the wiki if you have some free time  [http://wiki.xentax.com/index.php/Category:Format_Image](http://wiki.xentax.com/index.php/Category:Format_Image)

Edit: I have just added this one [http://wiki.xentax.com/index.php/Theme_Park_World_WCT](http://wiki.xentax.com/index.php/Theme_Park_World_WCT)
## Post #6
- Username: xezno
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 14, 2019 5:19 am
- Post datetime: 2022-03-18T14:21:17+00:00
- Post Title: Sim Theme Park / Theme Park World .WCT format

> Reply from Sir Kane ↑Mon Mar 14, 2022 7:22 pm at Mon Mar 14, 2022 7:22 pm
>
> 
Got code/format info for some of the other file types as well somewhere, if you're interested.

Would very much appreciate any code or info you have for any of the other file types!
