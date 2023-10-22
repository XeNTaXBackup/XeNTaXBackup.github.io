## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-31T15:49:55+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-31T16:30:09+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

By the way, this video format is also used in the new Spider-Man: Shattered Dimensions (Xbox 360), so it could get used more often in the future.
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-09-27T02:06:22+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

Hey, I know this is kind of old, but have you tried usm_deinterleave (in the utf_tab suite)? I wasn't able to try it on your file since the link has died.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-09-28T07:55:40+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

> Reply from hcs
>
> Hey, I know this is kind of old, but have you tried usm_deinterleave (in the utf_tab suite)? I wasn't able to try it on your file since the link has died.
Oh, didn't notice that you actually wrote tools!  Will try when I get home.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-09-30T00:20:19+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

You know where found a tool/script to reconvert the USM to mpg? 
Or any USm tools? SFD tools are obsolete.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-01T11:42:53+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-10-01T12:08:59+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

Ah, as I'd expected might be possible, this has multiple audio streams in it.  Now that I have an example I'll try to add support for it.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-01T20:56:17+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

Cool, thanks a lot in advance!
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-15T10:45:12+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

Any progress?
## Post #10
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-03-26T22:57:54+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

Crysis 2 video files are all usm files 

Was anyone able to play them?
## Post #11
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2011-03-28T09:20:17+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

have someone to convert the USM-video files?
Format CryMovie
## Post #12
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2011-04-10T10:25:09+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

After a quick talk with hcs, he recommended that I try [VGMToolbox](http://sourceforge.net/projects/vgmtoolbox/) by snakemeat.
This worked well with most Crysis 2 videos but some audio streams, I think background music, wouldn't play in winamp. I don't know if this has something to do with the tool or the winamp plugin.
[](http://www.imagebam.com/image/402582127327504)
## Post #13
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2011-04-10T18:49:54+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

> Reply from Chipicao
>
> but some audio streams, I think background music, wouldn't play in winamp. I don't know if this has something to do with the tool or the winamp plugin.

Can you tell me a few of the names of files that won't play?  Also, bxaimc has mentioned that some of the extracted files have loop start and end set to zero.  You may want to try telling vgmstream to ignore loops and see if that works.
## Post #14
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2011-04-11T08:16:12+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

Most cinematic files: GameResolution_st.usm, fb1.usm, fb2.usm ([download](http://www.mediafire.com/?c944yl5d4qnc0az)), fb3.usm, fb4.usm
They contain several audio streams in adx format with speech in different languages (but identical size), and one larger audio stream which won't play and I presume contains background music/soundfx. This one is almost 3 times the size of one speech adx, give or take a few bytes.

There is one exception though: Prophets_Journey.usm. Its music stream  is also identical in size to the speech streams and is playable.

> Reply from snakemeat
>
> You may want to try telling vgmstream to ignore loops and see if that works.How do I do that, I couldn't find any settings... or maybe I'm not looking in the right place
## Post #15
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2011-04-11T14:25:34+00:00
- Post Title: extracting the audio of PS3 *.usm videos - NEED HELP!

> Reply from Chipicao
>
> fb2.usm

They contain several audio streams in adx format with speech in different languages (but identical size), and one larger audio stream which won't play and I presume contains background music/soundfx. This one is almost 3 times the size of one speech adx, give or take a few bytes.

Tested with your posted sample.  It's just as bxaimc described.  Loop points are set to 0.  To configure vgmstream to ignore loops, Right Click Winamp and Select Options > Preferences.  Go to Plug-ins > Input, and select vgmstream plugin from the list on the right and click the "Configure" button.  You'll see 3 radio buttons describing Loop behavior.  Choose "Ignore looping" and they should play.
## Post #16
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2011-04-11T17:48:44+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Thanks for your help, I'll try it.
## Post #17
- Username: Sniperello
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 08, 2011 7:26 am
- Post datetime: 2011-05-03T16:49:56+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Eah use vgm toolbox new version!
## Post #18
- Username: hbelouf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 8:43 am
- Post datetime: 2011-07-06T00:58:47+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

I would like to convert the usm videos from witcher 2. I can convert them using vgm toolbox, though when played back
it is highly pixelated. I have provided a sample video file which would help out why this is happen. Also I have tired using 
Movavi Video Converter 10 to convert it but it has same results.

[http://www.filesonic.com/file/1077674534/atari.usm](http://www.filesonic.com/file/1077674534/atari.usm)

Thanks
## Post #19
- Username: jess
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 11, 2011 3:24 pm
- Post datetime: 2011-07-11T07:27:24+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

thanx for info, but i usually use this prog [http://geovid.com/Video_mp3_Extractor_PRO/](http://geovid.com/Video_mp3_Extractor_PRO/)
## Post #20
- Username: hbelouf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 8:43 am
- Post datetime: 2011-07-13T23:14:57+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

> Reply from jess
>
> thanx for info, but i usually use this prog http://geovid.com/Video_mp3_Extractor_PRO/

What r u talking about??????? this has nothing related to USM VIdeo.
## Post #21
- Username: SkyDelete
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 28, 2011 10:05 pm
- Post datetime: 2011-09-28T14:22:02+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Hello guys, I would like to convert the usm videos from Deus EX Human Revolution. I also can convert them using vgm toolbox, though when played back it is totally artefacts. I have provided a sample video file which would help out why this is happen.

[http://rghost.ru/23396951](http://rghost.ru/23396951)

Thanks  
PS. Sorry for copying post, i'm not much well in English.
## Post #22
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2011-10-14T12:52:17+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Oh, really need avi to usm converter, hcs' utf only converts to avi and it's not clear avi.
## Post #23
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2011-11-06T23:19:21+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Any updates on how to demultiplex The Witcher 2 USM files correctly? Thus far I only got latest VGMToolbox to output video full of artifacts, unusable.
I mean, the shapes are there but the video is just garbage. Any ideas on how to overcome this. I think some Russian guy achieved it but he doesn't discuss any details in the forum I read, he posted some extracted videos on youtube though.
## Post #24
- Username: hbelouf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 8:43 am
- Post datetime: 2012-04-24T00:57:38+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Finally able to correctly convert USM file without any artifacts.

01. Demux USM file using VGMToolbox.
>>>> This will produce multiple files depending upon which USM file used.
>>>> One file will be the video file in M2V format.
>>>> One audio file containing music only.
>>>> Other will be audio files containing spoken languages. English, spanish,...
2A. Convert Video (M2V file) using Mediacoder
2B. Convert ADX Audio files (Mediacoder will do this also)
03. Remux files (MP4boxer or mkvmerge or whatever is your preference.)

I have tested this on serveral Witcher 2 USM files and the conversion process works without any artifacts.

Special thanks to all the developers for their great effort here.
## Post #25
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-04-24T07:51:33+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

> Reply from ner0
>
> Any updates on how to demultiplex The Witcher 2 USM files correctly? Thus far I only got latest VGMToolbox to output video full of artifacts, unusable.
I mean, the shapes are there but the video is just garbage. Any ideas on how to overcome this. I think some Russian guy achieved it but he doesn't discuss any details in the forum I read, he posted some extracted videos on youtube though.

For some reason, this is not true. I just failed to have the proper codecs or player.
Once I installed Potplayer, those files played without a hitch. Although conversion might be needed for other uses.
## Post #26
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-08-30T10:52:52+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

I am sorry if I asked this noob questions on a wrong place, but can someone tell me why the video extracted with vgmtoolbox look like this? The game is mugen souls (PS3) JPN, and the default video format is .USM
[vlcsnap-2012.JPG](https://xentaxbackup.github.io/file/5724_vlcsnap-2012.JPG)
## Post #27
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-08-30T12:00:21+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Have you tried playing them in PotPlayer?
It's freeware, [here](http://get.daum.net/PotPlayer/v2/PotPlayerSetup.exe)
## Post #28
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-08-30T18:09:49+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

@ner0 the potplayer played even worse with no shapes but boxes of solid colors and slowly, but I found out it play normally in MediaCoder, look like it definitely  caused by codec.
## Post #29
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-08-30T18:36:33+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

> Reply from tomatopasta
>
> @ner0 the potplayer played even worse with no shapes but boxes of solid colors and slowly, but I found out it play normally in MediaCoder, look like it definitely  caused by codec.
Yeah, I believe you. Although we are talking about a different game. I had had that problem with videos extracted from The Witcher 2 PC version. Every video player I tried would display a garaged image, but when I tried PotPlayer and was able to watch the picture clearly, I was then convinced that it was an issue related to codecs, but I didn't track it down, I'm sure you can if you want though.
## Post #30
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2012-09-02T10:52:46+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

> Reply from hbelouf
>
> Finally able to correctly convert USM file without any artifacts.

01. Demux USM file using VGMToolbox.
>>>> This will produce multiple files depending upon which USM file used.
>>>> One file will be the video file in M2V format.
>>>> One audio file containing music only.
>>>> Other will be audio files containing spoken languages. English, spanish,...
2A. Convert Video (M2V file) using Mediacoder
2B. Convert ADX Audio files (Mediacoder will do this also)
03. Remux files (MP4boxer or mkvmerge or whatever is your preference.)

I have tested this on serveral Witcher 2 USM files and the conversion process works without any artifacts.

Special thanks to all the developers for their great effort here.
And a mkv or mp4 to USM?
## Post #31
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2013-01-10T03:35:50+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

> Reply from hbelouf
>
> Finally able to correctly convert USM file without any artifacts.

01. Demux USM file using VGMToolbox.
>>>> This will produce multiple files depending upon which USM file used.
>>>> One file will be the video file in M2V format.
>>>> One audio file containing music only.
>>>> Other will be audio files containing spoken languages. English, spanish,...
2A. Convert Video (M2V file) using Mediacoder
2B. Convert ADX Audio files (Mediacoder will do this also)
03. Remux files (MP4boxer or mkvmerge or whatever is your preference.)

I have tested this on serveral Witcher 2 USM files and the conversion process works without any artifacts.

Special thanks to all the developers for their great effort here.
can anyone provide some details instructions. Demuxing and converting was fine but both mkvmerge or mp4box gave me error while remux them back.
## Post #32
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2013-02-02T03:39:36+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

any help
## Post #33
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2013-02-04T14:14:21+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Is it posible to write a muxer based on the usm_deinterleave from utf_tab07
## Post #34
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2013-05-29T15:06:20+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Hey guys, please help me,
with the method above i can extract the audio and video from Patrician IV but is there any way to convert it back to usm?
## Post #35
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2013-08-13T20:21:23+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

Dang it, the .usm files for witcher 2 were just those cartoon animations, so all the romance scenes were rednered ingame!! WTF
## Post #36
- Username: rambohazard
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 27, 2009 9:33 am
- Post datetime: 2014-03-11T17:17:09+00:00
- Post Title: Re: extracting the audio of PS3 *.usm videos - NEED HELP!

I found this on internet today, when i search for USM Encoder:
[http://pesedit.com/forums/showthread.ph ... -Tutorial)](http://pesedit.com/forums/showthread.php?19574-ScaleForm-VideoEncoder-For-Converting-Video-To-usm-%28-Tutorial%29)

Its a Scaleform Video Encoder. I Tested, making a usm file, but not testing into a game. Sorry for my bad english
