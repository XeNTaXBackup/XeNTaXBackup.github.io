## Post #1
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-05-16T02:16:08+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

The format seems rather straight forward. It begins with a table of contents, then each file follows the ToC in succession, each with padding. It's something I could probably "hex sew" to mod new tracks in to MX vs ATV Unleashed on the Xbox and new content to Cars on the Xbox, but to be able to extract and rebuild an archive would be amazing. I've had a lot of experience modding Cars on the PC and I can say that, comparatively speaking, all the files are uncompressed. [Here](http://en.wikipedia.org/w/index.php?title=Rainbow_Studios&oldid=42712046) is a partial list of their games. XBR is the original Xbox's container, whereas PSR seems to be the PlayStation 2 version. I don't know whether .PSR is used for the PS3.
## Post #2
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-05-16T19:12:54+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

I've been able to extract cars.xbr and mxvsatv.xbr using the following BMS script found in [THIS](http://forum.xentax.com/viewtopic.php?f=10&t=3897) thread:

```
Get NUM_FILES long 0 ;
Get HEADER_UNK2 long 0 ;
Get HEADER_UNK3 long 0 ;
Get FILE_TABLE_SIZE long 0 ;
Get HEADER_UNK4 long 0 ;
For I = 0 To NUM_FILES ;
Get NAME_LEN long 0 ;
GetDString NAME NAME_LEN 0 ;
Get SIZE long 0 ;
Get OFFSET long 0 ;
Math OFFSET *= 2048 ;
Log NAME OFFSET SIZE 0 0 ;
Next I ;
```


*EDIT*

This works for both extraction and rebuilding.
## Post #3
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-05-19T03:14:19+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

I've encountered a new version of .PSR, used on Cars: Race-o-Rama. Unlike the previous two games in the Cars series that were developed by Rainbow, this was developed by Incinerator Studios. Incinerator helped with porting the first two games to the Wii.

Now as far as the format goes it doesn't have any quick-discernable tells to the naked eye. There is no little endian-based table of contents. I'm not sure whether it's compressed, big endian, or whatever. Any tips for scanning it?
## Post #4
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-04-03T23:28:02+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

After a bit of research (finally came back to this) the PSR/XBR used on Cars: Race-O-Rama is indeed little endian. This is what I know so far:

Table of contents starts at 499A8C30

Files seem to be padded with 00 bytes between. For example,
first padding starts at 02DF78 and ends at 02DFFF, with the next
file starting at 02E000

Files do not seem to be compressed (that I can tell). I've identified
several files that retain their original headers in the archive (much
was reused from previous Cars games)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-04-12T11:07:31+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

[http://aluigi.org/papers/bms/rainbow_studios.bms](http://aluigi.org/papers/bms/rainbow_studios.bms)
## Post #6
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-04-12T13:36:37+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

Thank you! It works on most items. The files in some RES containers are ZLIB compressed (maybe LZSS?) and the script fails on those, but most others work perfectly. I'll send you some samples.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-04-12T16:49:58+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

script update to version 0.1.1
## Post #8
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-04-12T21:22:25+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

Awesome. Thanks again. Is there a way to re-compress a text file so I can use a hex editor to copy/paste it back into the RES file? It would be under the block size of 0x6000 once compressed, but it's a necessary file to modify the game.
## Post #9
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-05-01T19:25:31+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

I've obtained the source code for the resource (RES) and streaming (STR) containers. I can't get them to compile under VS 2003, so I'm going to dig through and get my Visual Studio 6.0 discs out (the source is from early 2002). I will post here should I get the tools to compile, or should I need help.
## Post #10
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2013-11-05T18:56:13+00:00
- Post Title: Rainbow Studios .XBR, .PSR (Cars, MX vs ATV, etc)

I want to get the dialogue of Cars Race-O-Rama for personal uses, but I have no idea how to do it. I do have the script & the .xbr files, but quickbms was no help for me.
