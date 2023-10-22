## Post #1
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-14T17:02:09+00:00
- Post Title: Taz Wanted (PS2) .str

Hello! Is it possible to help me? .STR files from the PS2 version of Taz Wanted are using the PS ADPCM codec (with .STH header attached) but I can't play them properly. The interleave seems to be 0x8000 while some bigfiles are multichannel. Samples are included.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-15T03:54:37+00:00
- Post Title: Taz Wanted (PS2) .str

The interleave is 0x8000 but it is not a 6 channel file, it's three different stereo files interleaved together.
## Post #3
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-15T08:05:12+00:00
- Post Title: Taz Wanted (PS2) .str

Can I use VGMToolbox to make a GENH header?
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-15T12:25:49+00:00
- Post Title: Taz Wanted (PS2) .str

This is unusual, it has a 0x8000 block followed by a 0x18000 block.
## Post #5
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-15T12:35:02+00:00
- Post Title: Taz Wanted (PS2) .str

So how can I convert the files please?
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-15T13:15:57+00:00
- Post Title: Taz Wanted (PS2) .str

I'm not entirely sure, you might need a custom BMS script to deinterleave the files into their proper parts.
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-15T13:37:09+00:00
- Post Title: Taz Wanted (PS2) .str

I worked out a way 

Use Alpha23's File Deinterleave script with the following options set

```
set PRESERVE 0
set ADJUST 0
set BLOCKSIZE 0 # size of one complete block
set INTSIZE 0x20000 # size of one single interleave block. Set Blocksize to zero to take this value instead.
set LAYERS 3
set SKIP 0 # area at start of each block to skip
```


Then use HCS' VGMToolbox to add a GENH header to the files with the following settings

Input File Format: PlayStation 4-bit ADPCM
Header skip: 0
Interleave: 0x8000
Channels: 2
Frequency: 44100
No Loops
## Post #8
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-15T13:58:40+00:00
- Post Title: Taz Wanted (PS2) .str

Amazing! Thank you.
## Post #9
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-15T15:23:06+00:00
- Post Title: Taz Wanted (PS2) .str

Does it work for other games that use .STR?
## Post #10
- Username: AwesomeMarioFan
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 05, 2015 10:56 am
- Post datetime: 2015-08-17T04:12:17+00:00
- Post Title: Taz Wanted (PS2) .str

> Reply from brendan19
>
> I worked out a way 

Use Alpha23's File Deinterleave script with the following options set
Code: Select allset HEADER 0 # zero if skip is at end of block, otherwise = first skip at start
set PRESERVE 0
set ADJUST 0
set BLOCKSIZE 0 # size of one complete block
set INTSIZE 0x20000 # size of one single interleave block. Set Blocksize to zero to take this value instead.
set LAYERS 3
set SKIP 0 # area at start of each block to skip

Then use HCS' VGMToolbox to add a GENH header to the files with the following settings

Input File Format: PlayStation 4-bit ADPCM
Header skip: 0
Interleave: 0x8000
Channels: 2
Frequency: 44100
No Loops
Hey, I sent you a PM, I had a similar game which I was trying to convert audio from and was wondering if you could help me out (Details are in the PM).
## Post #11
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-17T08:23:19+00:00
- Post Title: Taz Wanted (PS2) .str

It would be amazing to see that script working for CFTKK.
## Post #12
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-17T10:52:43+00:00
- Post Title: Taz Wanted (PS2) .str

AwesomeMarioFan sent me a file from Spongebob SquarePants: Creature From the Krusty Krab on PS2 and these are the settings I changed to make it work:

Alpha23's File Deinterleave Script

```
set PRESERVE 0
set ADJUST 0
set BLOCKSIZE 0x20000 # size of one complete block
set INTSIZE 0 # size of one single interleave block. Set Blocksize to zero to take this value instead.
set LAYERS 4
set SKIP 0 # area at start of each block to skip
```


VGMToolbox GENH Header:

Input File Format: PlayStation 4-bit ADPCM
Header skip: 0
Interleave: 0x4000
Channels: 2
Frequency: 44100
No Loops
## Post #13
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-17T10:58:42+00:00
- Post Title: Taz Wanted (PS2) .str

It seems to simple for you! Thank you!
## Post #14
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-10-14T12:49:10+00:00
- Post Title: Taz Wanted (PS2) .str

Maybe other Blitz Games games use the same format, but I'm affraid it could slightly change.
## Post #15
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-23T10:25:55+00:00
- Post Title: Taz Wanted (PS2) .str

Is there a way to support the Wii version of CFTKK? We need to find the coefficients first.
## Post #16
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-08-23T12:05:44+00:00
- Post Title: Re: Taz Wanted (PS2) .str

I don't know how to find co-efficients in Wii ADPCM either sorry.
## Post #17
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-23T12:22:42+00:00
- Post Title: Re: Taz Wanted (PS2) .str

Ok, no problem, you already helped us a lot. Thank you again.
## Post #18
- Username: AwesomeMarioFan
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 05, 2015 10:56 am
- Post datetime: 2016-09-02T14:35:49+00:00
- Post Title: Re: Taz Wanted (PS2) .str

Hello again,

I could not find the audio coefficients for the GameCube or Wii ADPCM either. I decided to use the PS2 version since we figured out how to convert the format.

Just as a side note, the PS2 ADPCM has different values for each file, since some contain 3 tracks, and some contain 1 or 2, which complicates things a bit. I managed to get all of the soundtrack converted correctly though.

Basically though, you need to find the interleave and track count for each file (MFAudio is helpful here), then use the file deinterleaver with the track count and interleave value (found using hex editor), then create a GENH for it, and finally convert it.

Edit: If you are having trouble with a specific file, you can PM either me or brendan and we can help you out. Also as a side note, all of the .str soundtrack in THQ PS2 games use the same format, so the same process would apply to other games too.
