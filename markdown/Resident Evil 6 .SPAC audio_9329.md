## Post #1
- Username: ShinobiMao
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Sep 07, 2010 11:41 pm
- Post datetime: 2012-07-22T03:49:23+00:00
- Post Title: Resident Evil 6 .SPAC audio

Came across this while exploring the RE6 360 Demo files. 
I don't normally tinker with console files, so I don't know if this is common procedure, but, something worth noting for this file is everything is written backwards inside it. 
The header, "SPAC", becomes "CAPS", "RIFF" is "FFIR", "WAVE fmt" is now "EVAW tmf", etc. (As shown [here](http://i.imgur.com/ivbnS.jpg).) 

I'm a novice at things like this, so sorry in advance if I can't keep up with your replies.

I've included the sample below in it's entirety.
[snd_wp_cmn.rar](https://xentaxbackup.github.io/file/5587_snd_wp_cmn.rar)
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-07-22T03:55:58+00:00
- Post Title: Resident Evil 6 .SPAC audio

I decoded this before by hand editing out each xma steam, it's simply a header, but in the big endian format i'd assume. the xma starts a while in, and each spac i saw had anywhere from one stream to twenty five. You can normally find the start of a stream by searching for the hex values 00 01 00 with the stream's start being XX 00 01 00 0X where X= any whole number. then you should be able to decode with xmash and towav.
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-08-12T15:52:11+00:00
- Post Title: Resident Evil 6 .SPAC audio

I already made a tutorial to unpack all .SPC audio for the Xbox 360 version of Resident Evil 6.

See here:

[http://z6.invisionfree.com/Resident_Evi ... opic=22194](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=22194)
## Post #4
- Username: AndyAwe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 14, 2014 3:07 am
- Post datetime: 2015-03-01T16:08:46+00:00
- Post Title: Resident Evil 6 .SPAC audio

> Reply from Gh0stBlade
>
> I already made a tutorial to unpack all .SPC audio for the Xbox 360 version of Resident Evil 6.

See here:

http://z6.invisionfree.com/Resident_Evi ... opic=22194

You could upload SPC Tool v2.0 ?
## Post #5
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2015-04-23T06:22:38+00:00
- Post Title: Resident Evil 6 .SPAC audio

> Reply from AndyAwe
>
> Gh0stBlade wrote:I already made a tutorial to unpack all .SPC audio for the Xbox 360 version of Resident Evil 6.

See here:

http://z6.invisionfree.com/Resident_Evi ... opic=22194

You could upload SPC Tool v2.0 ?
Seconded. Could really use that tool, there doesn't seem to be another method of extracting the audio.
## Post #6
- Username: TheSorrow55
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 23, 2020 11:57 am
- Post datetime: 2020-02-25T04:48:10+00:00
- Post Title: Resident Evil 6 .SPAC audio

> Reply from ShinobiMao ↑Sun Jul 22, 2012 11:49 am at Sun Jul 22, 2012 11:49 am
>
> 
Came across this while exploring the RE6 360 Demo files. 
I don't normally tinker with console files, so I don't know if this is common procedure, but, something worth noting for this file is everything is written backwards inside it. 
The header, "SPAC", becomes "CAPS", "RIFF" is "FFIR", "WAVE fmt" is now "EVAW tmf", etc. (As shown here.) 

I'm a novice at things like this, so sorry in advance if I can't keep up with your replies.

I've included the sample below in it's entirety.

it's impossible to change weapons sounds even with tools
