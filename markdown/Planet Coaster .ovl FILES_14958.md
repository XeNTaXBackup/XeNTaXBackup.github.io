## Post #1
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-08-28T08:34:42+00:00
- Post Title: Planet Coaster *.ovl FILES

Hello,
can someone please help me with extracting texts from *.ovl files?

[https://mega.nz/#!HAdAkC4L!Z0J_a7_8u2dw ... nJCF8ALOWg](https://mega.nz/#!HAdAkC4L!Z0J_a7_8u2dwQi7q4L0nNmz7ZJaorfgPwnJCF8ALOWg)

Thank you
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-28T11:13:53+00:00
- Post Title: Planet Coaster *.ovl FILES

I think you got the wrong link. That link looks like its something for a different game (and not an ovl file from Planet Coaster)

That said, it looks like Planet Coaster is from the same people who did Rollercoaster Tycoon 3 and I bet the .ovl files in Planet Coaster are the same format as the ones in that game were. In which case, good luck trying to reverse engineer them, you will definitely need it. I wrote the custom scenery import tools for Rollercoaster Tycoon 3 back in the day and figuring out the .ovl files was a nightmare, they were some of the hardest formats I have ever done any work on (and no I dont know of anything out there that would cover the formats of RCT3 nor do I have any old stuff from back then so any reverse engineering would basically need to be done from scratch)
## Post #3
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-08-28T11:28:15+00:00
- Post Title: Planet Coaster *.ovl FILES

> Reply from jfwfreo
>
> I think you got the wrong link. That link looks like its something for a different game (and not an ovl file from Planet Coaster)

That said, it looks like Planet Coaster is from the same people who did Rollercoaster Tycoon 3 and I bet the .ovl files in Planet Coaster are the same format as the ones in that game were. In which case, good luck trying to reverse engineer them, you will definitely need it. I wrote the custom scenery import tools for Rollercoaster Tycoon 3 back in the day and figuring out the .ovl files was a nightmare, they were some of the hardest formats I have ever done any work on (and no I dont know of anything out there that would cover the formats of RCT3 nor do I have any old stuff from back then so any reverse engineering would basically need to be done from scratch)

Sorry, I've edited the link.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-08-28T12:28:15+00:00
- Post Title: Planet Coaster *.ovl FILES

taken a quick look - the format is a bit wierd. theres a chunk of zlib "STATIC" data at the end which contains the actual text values.

5min version:

```
uint pool[140/4];

byte str_data[pool[3]];;

uint pool2[24];

struct
{
  uint a, b, c;
} dd[ pool2[17] ]<bgcolor=0xeeaa00>;

char static[8];

uint hdr[19];

// zlib data
byte zlib[ hdr[11] ] <bgcolor=0xffff00>;


Assert(FEof());

```
## Post #5
- Username: mattd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 07, 2015 3:37 am
- Post datetime: 2017-01-11T20:01:10+00:00
- Post Title: Planet Coaster *.ovl FILES

Same engine (home-grown "Cobra Engine") as Elite Dangerous, which also has OVL files with a zlib section.
