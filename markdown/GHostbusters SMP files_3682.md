## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-30T20:08:51+00:00
- Post Title: GHostbusters SMP files

hello guys i have here the music files of the pc version of ghostbusters, looks like either voxware or some adpcm. here are some files.

[http://www.megaupload.com/?d=HIX2L2JO](http://www.megaupload.com/?d=HIX2L2JO)

Thanks.
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-04-25T10:59:24+00:00
- Post Title: GHostbusters SMP files

Here is what I have figured out about the SMP files (so far all of them seem to follow this format)

0 version (always 6, the game will reject files which are not version 6)
4 unknown (seems to be part of a generic asset header, not relavent to sound at this point)
8 unknown (seems to be part of a generic asset header, not relavent to sound at this point)
C unknown (seems to be part of a generic asset header, not relavent to sound at this point)
10 unknown (seems to be part of a generic asset header, not relavent to sound at this point)
14 unknown (seems to be part of a generic asset header, not relavent to sound at this point)
18 unknown
1C unknown, never seen a value other than 160 so far
20 total size of sample data (i.e. all bytes after the headers)
24 unknown, never seen a value other than 4 so far
28 number of channels (seen 1 for mono and 2 for stereo so far)
2C unknown, never seen a value other than 4 so far
30 sample rate
then all items from 34 to A0 are unknown. This data here seems to be a different bit and is not part of the main file header.
At position A0 the audio data begins.
It is compressed with MS ADPCM compression.
Some of the unknowns clearly related to the size of the sample data or the number of samples or whatever but I dont know which ones.

Can any of the sound gurus here fill in the blanks so we can build a converter for this format?
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-25T11:45:01+00:00
- Post Title: GHostbusters SMP files

The latest vgmstream by hcs supports it now
## Post #4
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-04-25T12:24:14+00:00
- Post Title: GHostbusters SMP files

Thanks for the info, works great.
Can anyone tell me which audio file contains the GB theme tune?
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-25T19:59:12+00:00
- Post Title: GHostbusters SMP files

Its not in an smp file, its embbeded in the intro movie.
