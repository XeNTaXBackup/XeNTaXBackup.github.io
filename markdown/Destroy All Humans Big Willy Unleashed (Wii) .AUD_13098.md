## Post #1
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-24T13:14:01+00:00
- Post Title: Destroy All Humans: Big Willy Unleashed (Wii) *.AUD

Hello! I need some help converting the .AUD music files from DAH! BWU (Xbox 360). The samples are included.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-25T00:35:10+00:00
- Post Title: Destroy All Humans: Big Willy Unleashed (Wii) *.AUD

EDIT: It's Nintendo ADPCM (Not from Xbox 360 but Nintendo Wii)

Rename to .dsp and vgmstream can play it back but it isn't interleaved properly or something.
## Post #3
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-25T08:33:29+00:00
- Post Title: Destroy All Humans: Big Willy Unleashed (Wii) *.AUD

You're right, it works for some DSPs (which are mono, so without interleave) but doesn't work for interleaved DSPs.
## Post #4
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-25T15:45:09+00:00
- Post Title: Destroy All Humans: Big Willy Unleashed (Wii) *.AUD

I'm affraid I'll need to know the right interleave. Any clues on how do that please?
## Post #5
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-28T20:09:43+00:00
- Post Title: Destroy All Humans: Big Willy Unleashed (Wii) *.AUD

> Reply from brendan19
>
> EDIT: It's Nintendo ADPCM (Not from Xbox 360 but Nintendo Wii)

Rename to .dsp and vgmstream can play it back but it isn't interleaved properly or something.

Thanks, it works with the mono tracks but not with stereo tracks because they're interleaved and they need coeffs... Thanks anyway
