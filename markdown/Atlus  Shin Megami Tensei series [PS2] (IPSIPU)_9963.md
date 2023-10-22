## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-12-21T03:11:44+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

I'm a huge Shin Megami Tensei / Devil Summoner fan. Well, in particular the Raidou Kuzunoha duology is among the most favorite ever.
This is why it would be great to extract and be able to view the videos from Devil Summoner: Raidou Kuzunoha 1 & 2 on PS2. However as it turns out Atlus used a proprietary format for several of their PS2 titles. 

IPS and IPU. I figured they were proprietary not only because of unusual file extension but because just about any video tool was unable to do anything to them. 
VGMToolbox with all its diverse functionality had no results scanning the files. 
Only CubeMediaPlayer can read audio stream as PCMRAW (PS2 PCM Audio) though it sounds very distorted. 

Here's a list of games that use IPS/IPU:

Shin Megami Tensei: Devil Summoner: Raidou Kuzunoha vs. The Soulless Army
Shin Megami Tensei: Devil Summoner 2: Raidou Kuzunoha vs. King Abaddon
Shin Megami Tensei: Digital Devil Saga
Shin Megami Tensei: Digital Devil Saga 2
Shin Megami Tensei: Nocturne

I understand that this is probably not an easy task even for those familiar with video formats, but I would be very appreciative and pay $100 to anyone who can figure this thing out. The goal is to extract raw video/audio streams and put them into a single MKV file via MKVmerge. 

Here are samples from Shin Megami Tensei: Devil Summoner 2: Raidou Kuzunoha vs. King Abaddon [PS2]:

E695_001.IPS (12.5mb) [http://www.sendspace.com/file/w5jb2n](http://www.sendspace.com/file/w5jb2n)
MOVIE00.IPU (51.9mb) [http://www.sendspace.com/file/mrom3t](http://www.sendspace.com/file/mrom3t)

You can PM me for any additional info.
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-12-23T03:55:04+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

I made a tool to get the audio out, you can find it here: [viewtopic.php?f=21&t=3054](http://forum.xentax.com/viewtopic.php?f=21&t=3054). Only tested with SMT Nocturne Maniax. It's slow, and could be improved, but it works.  Source is included.

The video encoding process is documented in the PS2 SDK a little bit.  I recall an MPEG  to  IPU converter included in some open source Dance Dance  Mania clone.

I have spent a  lot of time trying to figure out the headers, but never had any luck adding a demuxer to VGMToolbox for this format.
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-12-23T05:39:25+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

I see. That's too bad really. Your VGMToolbox is like the most advanced thing out there. They must have really wanted to encrypt/protect their stuff with these formats. 
Heck, if snakemeat couldn't do it, than who can? 

But hey, it's good to know you're a SMT fan too.
## Post #4
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-12-30T19:07:47+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

> Reply from MiLØ
>
> I see. That's too bad really. Your VGMToolbox is like the most advanced thing out there. They must have really wanted to encrypt/protect their stuff with these formats. 
Heck, if snakemeat couldn't do it, than who can? 

But hey, it's good to know you're a SMT fan too.

Thanks for the compliments, but I also get a lot of information from places like the [MultimediaWiki](http://wiki.multimedia.cx/index.php?title=Main_Page) and [MPUCoder's MPEG reference site](http://stnsoft.com/DVD/index.html).

The header doesn't seem encrypted or anything, just confusing   

Maybe someone else will have some luck?
## Post #5
- Username: truston
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 15, 2014 5:42 pm
- Post datetime: 2014-12-15T10:10:41+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

two years now... @snakemeat the hero, how's the en... this ipu / ips going????
really wanna know~~
## Post #6
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2015-03-16T03:16:10+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

I'd still be interested in this just as if it were yesterday. Raidou Kuzunoha games are my favorite for eva and eva
## Post #7
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-10-20T10:57:01+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

They're not proprietary as they're part of the ps2 sdk. Here's some info on it: [http://puu.sh/kQW3N.7z](http://puu.sh/kQW3N.7z)
## Post #8
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-02-18T06:12:12+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

Excuse me for reviving an old thread, but after coming across a few games that use this format, it's confirmed that the IPS/IPU formats aren't proprietary after all.

Thanks TGE for the info.
## Post #9
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2017-11-01T12:26:51+00:00
- Post Title: Atlus / Shin Megami Tensei series [PS2] (*IPS/IPU)

I've been working on a translation project recently, and while things have just started to wrap up nicely, I've found myself wanting to translate the text of a video file or two before releasing it.. Unfortunately the videos are in IPS format, which there seems to be little and less information about than I'd like.

As near as I can tell, IPS is essentially an IPU video interleaved with ADPCM audio.. The problem is that I see no particular pattern to the interleaving itself, and am not really an expert on video formats to begin with. Producing an IPU video and ADPCM audio themselves is simple enough, but inteleaving them together? Not really my field of expertise. If anyone has any idea about muxing this I'd be eternally grateful.
