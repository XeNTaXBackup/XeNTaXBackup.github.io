## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-04-07T22:18:05+00:00
- Post Title: I wrote some code for dealing with some EA audio stuff

As some people here might know, Electronic Arts has a tool called Sound Exchange (sx) that can convert between different audio formats and codecs. (a few different versions of this tool can be found out there).
Internally this tool uses a library from EA called SIMEX to handle all the different file formats and codecs.

I have (via various tricks including some things that are best described as "black magic") created some code that re-creates part of this SIMEX library and lets you manipulate some of the same formats and codecs as the sx tool does inside your own code.

It can decode from the following formats:
Microsoft WAV audio with s16l_int, u8_int and s24l_int codecs.
MPEG audio with MPEG Layer3 codec. (i.e. regular old MP3 files).
EA sndplayer files (snr/sns/sph/sps) with s16b_int, xas_int, ealayer3_int, ealayer3pcm_int and ealayer3spike_int codecs.

It can encode to the following formats:
Microsoft WAV audio with s16l_int and u8_int codecs.
EA sndplayer version 0 files (snr/sns not sph/sps) with xas_int, s16b_int, ealayer3pcm_int, ealayer3spike_int and ealayer3_int codecs.

This is not a tool for general use, its code for programmers to make use of in their own tools but hopefully there are people out there who want to be able to work with these formats and codecs and will get use out of my code (as messy as it is).

You can get the code from [https://github.com/jonwil/snrtool](https://github.com/jonwil/snrtool) and [https://github.com/jonwil/lame-3.96](https://github.com/jonwil/lame-3.96) contains the LAME MP3 encoding code being used for the EALayer3 stuff.

Documentation is non-existent (no comments or anything else either and the code is not the neatest out there) but feel free to hit me up here or on xentax discord with any questions or comments or feedback or feature requests (including other formats or codecs you want me to look into supporting).

My original intent for this code (and something I am still going to work on) is to produce a replacement for the BinaryAssetBuilder.AudioCompiler dlls from the C&C3 and RA3 Mod SDKs that can support the EALayer3 MP3-style compression (it was originally not supported in those SDKs because of patent issues but now that I have this new set of code that can encode to EALayer3 its possible to support it). Oh and I can continue my work reverse engineering the PathMusic stuff from RA3 as well (it contains embedded sndplayer data that contains EALayer3 audio).

Hopefully this is of use to someone out there who needs to work with these formats and codecs. You will need Visual Studio 2019 to mess with the code and it will only work on 32-bit x86 windows (why it can't be ported right now pertains to the "black magic" I alluded to above)

It can support changing various things about the audio as well (including re-sampling it to a different sample rate)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-07T22:46:40+00:00
- Post Title: I wrote some code for dealing with some EA audio stuff

Good job!

I have some questions though:
1. Do you plan to make any documentation for this in the future?
2. Do you plan to support also some video files from EA?
  Like for example MAD Video [http://wiki.xentax.com/index.php/Electr ... MAD_(MADV)](http://wiki.xentax.com/index.php/Electronic_Arts_MAD_%28MADV%29)
  or something similar?
3. Do you plan to add some GUI in the future?
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-04-08T00:50:45+00:00
- Post Title: I wrote some code for dealing with some EA audio stuff

Documentation may happen although I totally suck at writing documentation for the code I write...
Video formats is a no.
And this is just code for other people to make use of, not an actual tool so a GUI is a no.
## Post #4
- Username: bnnm
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Nov 10, 2017 6:43 am
- Post datetime: 2021-04-08T18:04:09+00:00
- Post Title: I wrote some code for dealing with some EA audio stuff

You may be interested in checking vgmstream's source code too, since it plays almost all known EA formats (including many edge cases) and has some documentation in-code.

Mainly:
[https://github.com/vgmstream/vgmstream/ ... /ea_schl.c](https://github.com/vgmstream/vgmstream/blob/master/src/meta/ea_schl.c)

[https://github.com/vgmstream/vgmstream/ ... /ea_eaac.c](https://github.com/vgmstream/vgmstream/blob/master/src/meta/ea_eaac.c)
## Post #5
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-04-09T05:28:44+00:00
- Post Title: I wrote some code for dealing with some EA audio stuff

I am well aware of vgmstream and have looked at its source code many times to help understanding things.
As for supporting more formats, its a matter of what formats people want me to support (preferably a format that is supported by one of the various versions of the EA SX tool that are out there so I can compare the results of my code with the results of the EA tool but doesn't need to be)

If you have a format or codec you want me to support, let me know (and preferably point me to an example) and I will look into it.
