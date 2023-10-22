## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-11-10T18:19:15+00:00
- Post Title: does anyone have a QSound API overview?

I try to find out where the audio files in Beasts & Bumpkins are decoded.
Maybe it could be helpful to know which functions are used in QSound to play back a sound.
Is anybody familiar with the QSound API?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-10T18:59:18+00:00
- Post Title: does anyone have a QSound API overview?

qsound is mixing and positional stuff, I have never heard of proprietary codecs used in it
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-11-10T19:03:19+00:00
- Post Title: does anyone have a QSound API overview?

Yeah but you somehow have to hand over your sound data to QSound, if I find the function where this is done, I maybe also find the function that decodes it before that.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-10T19:25:10+00:00
- Post Title: does anyone have a QSound API overview?

it's a EA game so for it uses for sure one of the EA codecs.
have you tried all the related codecs available in ffmpeg?

ffmpeg is a nightmare to use even for doing a so easy job like decoding a raw data block, the last time I needed to do a similar test I got its codecs one by one and decoded the raw block by hand with a simple tool written and updated each time... blah bad memories.

for qsound it's enough to see what functions are imported, and those to which you can be interested are QSWaveMixPlay and QWaveMixOpenWave
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-11-10T23:45:52+00:00
- Post Title: does anyone have a QSound API overview?

Yeah an EA in-house audio library is used. As I pointed out [here](http://forum.xentax.com/viewtopic.php?p=26411#p26411) it uses some kind of EA format without a proper header and with an unknown codec number.
Could be Microtalk 1:10 because of the .m10 file extension, but some tests with Sound eXchange (adding a proper header and converting) didn't yield any results. It's the only tool supporting that one and the codec hasn't been reversed ever.

I've looked into ffmpeg merely to find out some more header value meanings. It IS a PITA.

It uses Play and OpenWave functions as well as OpenChannel etc. but in a kind of strange way. I gotta dig deeper into that when I get some time.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-11T11:44:20+00:00
- Post Title: does anyone have a QSound API overview?

if can be of any help, yesterday I tried a bit using an experimental tool I wrote some months (years?) ago which is a collection of the same algorithms used in ffmpeg and is usable with raw data but got no results, ever noisy data even when using the EA algorithms.
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-11-11T15:59:37+00:00
- Post Title: does anyone have a QSound API overview?

Thanks for trying.
I just found some source code using QMixer, sheds some light on the structures and parameters used!

[http://svn.gna.org/svn/warzone/tags/1.1 ... d/qmixer.h](http://svn.gna.org/svn/warzone/tags/1.10a/lib/sound/qmixer.h)
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2019-07-25T14:49:34+00:00
- Post Title: does anyone have a QSound API overview?

For the record can now be found at [https://github.com/Warzone2100/warzone2 ... d/qmixer.h](https://github.com/Warzone2100/warzone2100/blob/v1.10a/lib/sound/qmixer.h)
