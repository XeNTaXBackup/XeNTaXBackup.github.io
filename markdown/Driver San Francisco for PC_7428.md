## Post #1
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-27T21:36:35+00:00
- Post Title: Driver: San Francisco for PC

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-28T18:43:46+00:00
- Post Title: Driver: San Francisco for PC

I only had a look at the subtitles.astd.
Starting at 0x28 there is a table of offsets to the actual textdata.

```
4bytes: unknown (some kind of id)
4bytes: offset to the text
```

EDIT: 
I had a look at the global.fchunk too. Here is what I found out:
Little endian. Starting at 0x3080 comes a table with 8 bytes each row. The first 4 bytes are telling the offset (relative, starting at 0xBDD0) for a textchunk the other 4 bytes are unknown to me. After every textchunk the next one starts so you if you have the offset 0x0A and the next text comes at 0x16 the size of the textchunk is the difference between the two offsets.

Its not much but I wanted you to know.
## Post #3
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2011-09-29T16:21:47+00:00
- Post Title: Driver: San Francisco for PC

All the vehicles are in dngvehicles.sp, so it does worth more to unpack as it even has dds textures and the models.

Header is 'CHNK'.
## Post #4
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-10-01T04:37:22+00:00
- Post Title: Driver: San Francisco for PC

What i'm concerned with is car spawning. I want to make all cars spawn in the traffic. I'll assume the file that controls what vehicles spawn in what chapter is inside the dngvehicles.sp file.
## Post #5
- Username: XpucmoBG
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Apr 30, 2011 3:27 am
- Post datetime: 2011-10-02T17:15:33+00:00
- Post Title: Driver: San Francisco for PC

I really hope that someone will create a packer\unpacker for these files.
## Post #6
- Username: SoniKalien
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 13, 2011 11:02 am
- Post datetime: 2011-11-12T04:17:26+00:00
- Post Title: Driver: San Francisco for PC

There doesn't seem to be much looking at this from the pros, so I guess it's up to us noobs   

I've just been looking at dngvehicles.sp. These are my noobish observations using a hex editor:

-It's not encrypted (?)
-The end of file has filenames and directories eg 
```
R:\Resources\Vehicles\Vehicles\Chevrolet_Box_Van_1989_Ambulance\Model\Chevrolet_Box_Van_1989_Ambulance.gck.rimodel 17/06/11 10:59:16.104 
```

-There is some useless data? eg  blocks of "3E" (hex) = ">" ansi

-Dragon Unpacker can read and unpack the .dds files just fine in HyperRipper mode so there's a big clue!   

I'll add more clues as I go thru it more  I'm really interested in scoring the cars out
## Post #7
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2011-11-12T18:21:16+00:00
- Post Title: Driver: San Francisco for PC

Looks like we need some plugin or script to import .gck models
## Post #8
- Username: D1Racer
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 07, 2010 9:21 am
- Post datetime: 2011-12-26T10:01:13+00:00
- Post Title: Driver: San Francisco for PC

Using Game Extractor I extracted a bunch of .VEHC files and a few other files (.SSIC, .DMWK and .BINF) .BINF is clear text resource directory.

No idea if this helps I have no clue what I am doing, lol

Here is a sample of the .VEHC and other files.

[http://www.mediafire.com/?rhn6a3p15ggn965](http://www.mediafire.com/?rhn6a3p15ggn965)
## Post #9
- Username: StewMM
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 17, 2007 3:09 am
- Post datetime: 2012-01-08T10:51:21+00:00
- Post Title: Driver: San Francisco for PC

Really need more tool makers looking into this. I want to import my own cars. not just export.
## Post #10
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-01-08T13:30:46+00:00
- Post Title: Driver: San Francisco for PC

You could ask under another forumcategory. This post WAS for game localisation if i remember right.
## Post #11
- Username: StewMM
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 17, 2007 3:09 am
- Post datetime: 2012-01-08T13:38:29+00:00
- Post Title: Driver: San Francisco for PC

> Reply from Polefish
>
> You could ask under another forum category. This post WAS for game localisation if i remember right.
Pretty much the same thing. three threads. very little going on.
## Post #12
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-01-16T02:29:05+00:00
- Post Title: Driver: San Francisco for PC

1989 Chevrolet Box Van ambulance? There isn't even such a vehicle in DSF. Obvious beta vehicle.
