## Post #1
- Username: ryukakashi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 23, 2011 3:03 am
- Post datetime: 2011-11-30T04:53:59+00:00
- Post Title: Bionic Commando Rearmed 2

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-30T23:32:50+00:00
- Post Title: Bionic Commando Rearmed 2

See [http://www.daubnet.com/en/file-format-riff](http://www.daubnet.com/en/file-format-riff) for more info on RIFX
There is even a RIFF reader ([http://www.daubnet.com/ftp/riff13.zip](http://www.daubnet.com/ftp/riff13.zip)) that would flag it as valid.

The file contains the following: Two loop points (defined through chunks), JUNK (name of the chunk) to get it to a specific file size(?)
Will look into it and write an easy guide how to hex your way through. (it seem's fairly easy)
## Post #3
- Username: ryukakashi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 23, 2011 3:03 am
- Post datetime: 2011-12-01T08:26:28+00:00
- Post Title: Bionic Commando Rearmed 2

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-02T06:48:55+00:00
- Post Title: Bionic Commando Rearmed 2

It seems to work just fine for me when importing raw in audacity (1.3.12).  It is just 16-bit big endian PCM.

In fact, if you just write 00 01 to offset 0x14, it is a perfectly standard big endian wav, and many things will open it normally.
## Post #5
- Username: ryukakashi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 23, 2011 3:03 am
- Post datetime: 2011-12-02T08:10:13+00:00
- Post Title: Bionic Commando Rearmed 2

Writing 00 01 to 0x14 didn't seem to do anything for me.

I found that my problem was audacity couldn't find certain .wav's in that folder for some reason. Moving it to the root of my c:\ fixed it.

Thanks.

I'm still curious as to why some of the 4mb+ files are just static.

Edit: Also just importing with audacity isn't getting the full track of the sound file. Is there no program that can logically read the chunks of the .wav and properly encode it into an mp3?
## Post #6
- Username: DuderDuder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 10, 2010 10:12 pm
- Post datetime: 2012-02-28T00:05:33+00:00
- Post Title: Bionic Commando Rearmed 2

Sorry for the minor bump, but I figured I'd mention this in case someone else had the same issue.

> Reply from ryukakashi
>
> I'm still curious as to why some of the 4mb+ files are just static.
I was wondering this too until I looked at the hex and searched a bit.
A good pile of those "static" files (perhaps all of them?) are AudioKinetic Wwise RIFX Vorbis files, [hcs' ww2ogg](http://hcs64.com/vgm_ripping.html) utility seems to work great on those.


Toodles.
