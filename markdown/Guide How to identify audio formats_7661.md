## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-11-10T09:56:52+00:00
- Post Title: Guide: How to identify audio formats

Hi there!

Over the years of game music ripping I've gathered some experience in audio format hex structures. I'd like to share my knowledge here as some persons may find it helpful.
I will update the first post from time to time.
Basically there are a few different possibilities how to identify a certain audio format. The ones I normally use are:
file size
hex structure
character distribution
wave form

I'll post a list with the most commonly used audio formats and how to recognize them. Sometimes there will be pictures of HEX views, character distributions, wave forms or spectral analysis.
The extensions in brackets are only the standard ones. All info basically is for headless files or files with a header variant.


PCM, 16bit (*.wav)
[](http://imageshack.us/photo/my-images/694/pcml.jpg/)
Note: The distribution is the same with interleaved, big endian or multichannel wave files. Further identification is done via wave form.


PCM, 8bit, unsigned (*.wav)
[](http://imageshack.us/photo/my-images/822/pcm8bitunsignedj.jpg/)


Microsoft ADPCM (*.wav)
[](http://imageshack.us/photo/my-images/715/msadpcm.jpg/)
Note the characteristic peaks at the last three curves.


Xbox ADPCM / IMA ADPCM (*.wav, *.xadp)
Divided into blocks of 0x24 bytes (mono) or 0x48 bytes (stereo') respectively. Channel interleave is 4 bytes. Of course each stream ends with a full block. 
Manually splitting containers with more than one xadp file is really easy.

[](http://imageshack.us/photo/my-images/257/imaadpcm.jpg/)
[](http://imageshack.us/photo/my-images/263/xadpmono.jpg/)
[](http://imageshack.us/photo/my-images/163/xadpstereo.jpg/)


CRI ADPCM (*.adx)
[](http://imageshack.us/photo/my-images/269/adxy.jpg/)


Playstation CDXA (*.xa)
Files are normally RAW extracts (e.g. with ISO Buster) and have the typical 0x930 bytes blocks (starting with 0x00FFFFFFFFFFFFFFFFFFFF00 each).
The stream is divided in 0x80 byte blocks, the RAW identifier is \x64\x01.
[](http://imageshack.us/photo/my-images/7/psxcdxa.jpg/)
[](http://imageshack.us/photo/my-images/210/psxcdxahex.jpg/)


PS2 ADPCM (*.ss2)
Block size of 0x10 bytes, really easy to recognize. Stereo files have multiples of 0x10 bytes interleave. Last interleave block may be incomplete (evenly split) and not playable right, so always use my 0x10 bytes reinterleave script for those streams!
[](http://imageshack.us/photo/my-images/810/ps2adpcmhex.jpg/)


Sony Atrac (*.wav, *.at3)
Only available configurations are 66kbps, 105kbps and 132kbps, stereo. Even character distribution.


Sony Atrac3+ (*.aa3, *.oma, *.at3)
Blocks of 0x230 bytes, each block starts with byte 0x3A. Even character distribution.


More to come.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-11-10T16:19:18+00:00
- Post Title: Guide: How to identify audio formats

Very cool, I've been meaning to do something like this.  One thing that's interesting is to look at the distribution of nibbles, that makes the differences between the various 4-bit ADPCMs in a particular group (1's vs 2's complement) much more striking.

And if you get a fairly even distribution (like your XWMA), you're probably looking at something Huffman coded, like MP3 or Vorbis, but at that point it's hard to tell just from the frequency distribution.  Padding preferentially used by some encoders (like XMA's extreme use of FFs) can stand out there.

Another interesting thing to look at, though I haven't seen a tool that does this yet besides a few special case ones I've hacked together, is the distribution across slices (so you'd generate graphs for every 6, 8, 10, 12, etc bytes, skipping those between) to determine whether there are different classes of behavior at regular spacing (headers and other per-frame features).  This is generally something you can pick up just by looking at the hex, but not always, especially if there aren't a lot of zeros.

One other quick thing that I've found helpful, Audacity is really good at detecting different types of PCM.  When you try to open a raw file it will guess whether you're looking at 8/16-bit, big/little endian, signed/unsigned, mono/stereo PCM.  I assume this is done with some quick autocorrelation tests given different settings.
## Post #3
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2011-11-14T16:29:25+00:00
- Post Title: Guide: How to identify audio formats

can you help me identify this?
## Post #4
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-15T22:44:10+00:00
- Post Title: Guide: How to identify audio formats

I made a HTML out of it, will mirror any changes.

Do you give me permission to host it?

EDIT: URL gone
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-11-21T09:48:03+00:00
- Post Title: Guide: How to identify audio formats

> Reply from 0xFAIL
>
> I made a HTML out of it, will mirror any changes.

Do you give me permission to host it?
I'd rather have people go to this very thread. Thanks anyway.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-11-21T11:11:24+00:00
- Post Title: Guide: How to identify audio formats

Updated with some other formats.
## Post #7
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-10-22T07:46:47+00:00
- Post Title: Guide: How to identify audio formats

The images are gone.
Can you update them?
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-28T01:04:18+00:00
- Post Title: Guide: How to identify audio formats

> Reply from deepshit
>
> The images are gone.

needed them too. luckily the wayback machine caught some:
