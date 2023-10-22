## Post #1
- Username: Mali
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 27, 2010 5:22 pm
- Post datetime: 2010-03-28T22:13:24+00:00
- Post Title: RSD Madness

I've looked through the forum on what they are, but am still trouble by how to extract the wav files out of them. 

Crash: Tag Team Racing for the Gamecube.

Looking through the character viewer in GameExtractor it displays filename ending in wav. I feel that i have tried every program imaginable, but have come up with nothing but a few of the non-wav files that contained .dds files through the use of jaeder. There are multiple instances of directories to these rsd files.

root/english.rcf/sound/rsd/english/0/filename.rsd
root/adefault/sound/rsd/0
root/advent1.rcf/sound....

Any solution. The previous topics had to do with either rsd2ogg or use fileripper. Unless I missed an important step, then I'm stumped.
Edit1: 
[http://www.megaupload.com/?d=32O6QJG6](http://www.megaupload.com/?d=32O6QJG6)
[http://www.megaupload.com/?d=0EJ78KPN](http://www.megaupload.com/?d=0EJ78KPN)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-03-31T11:11:18+00:00
- Post Title: RSD Madness

These .rsd use "Radical ADPCM", which is an IMA ADPCM variant.  I added support to [vgmstream](http://hcs64.com/vgmstream.html) a while back.  For this particular game, in fact.
## Post #3
- Username: Mali
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 27, 2010 5:22 pm
- Post datetime: 2010-04-01T01:10:52+00:00
- Post Title: RSD Madness

> Reply from hcs
>
> These .rsd use "Radical ADPCM", which is an IMA ADPCM variant.  I added support to vgmstream a while back.  For this particular game, in fact.

You sir are my hero and I can't believe how I overlooked vgmstream. I had the program, but I must of goofed somewhere.
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-04T03:10:45+00:00
- Post Title: RSD Madness

Does it work on prototype files?

[http://www.filefront.com/16019851/credits.p3d](http://www.filefront.com/16019851/credits.p3d)

couldnt seem to get this to play in vgmstream.
## Post #5
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-04-04T04:57:20+00:00
- Post Title: RSD Madness

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-04-04T05:48:50+00:00
- Post Title: RSD Madness

The p3d has two interleaved mono RADP streams (rather than one stereo stream).  I'll look into adding support for it.

@gamehead:
I suggest you try vgmstream, it seems to work.  Otherwise use start offset 0x800, interleave 0x10.
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-04-10T12:08:58+00:00
- Post Title: RSD Madness

Added .p3d support in 773, don't know if it will work with all files but it works with the sample.
Fun fact: when it's interleaved mono like this, RADP is exactly the same as MS ADPCM would be.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-10T17:18:15+00:00
- Post Title: RSD Madness

[http://www.mediafire.com/file/manwww3dv ... combat.p3d](http://www.mediafire.com/file/manwww3dvx2/e01m01_combat.p3d)

seems the credits one only will work.

Here is another sample from prototype.
## Post #9
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-04-10T18:19:43+00:00
- Post Title: RSD Madness

Last night I was going thru the Scarface the world is yours RSD files on the PS2 disk that I extracted and converting the songs I wanted and I went into the subtitles folder and there was another complete set of folders 0-9 and a-j they have a bunch of .P3D files in them those are also audio files. I found that loading them in MFAudio most of the ones like the songs use 24000hz sample rate and interleave 10 and offset 800. every time you load a p3d file up it will default to 20000 interleave but change it to 10 bytes. the RSD files have built-in support using the settings above. please set the default ADPCM sample rate to 24000hz in MFAudio's settings, that will make things easier.  some of the RSD or P3d files are mono change the channels to 1 if it sounds messed up and they should play right. there are some files that dont play right at all and they are gunfire sounds or whatever don't worry about those (I didnt, I just wanted the music) Hope this helps. I will try that attached P3d file that someone above me posted.
## Post #10
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-04-10T21:03:59+00:00
- Post Title: RSD Madness

OrangeC: fixed in 775, there's a value I was checking that has some unknown meaning, I'm leaving it alone now.  Unfortunately this track is clipped to hell, is that how it's supposed to be?
## Post #11
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-10T21:07:56+00:00
- Post Title: RSD Madness

If the source is clipped then i guess yes, developers clip them i guess to boost the volume ingame.

but thx anyway.
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-28T11:30:35+00:00
- Post Title: RSD Madness

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-28T11:47:06+00:00
- Post Title: RSD Madness

Huh? i thought the xbox version was canceled?
