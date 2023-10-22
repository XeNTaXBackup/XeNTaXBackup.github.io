## Post #1
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-16T16:34:45+00:00
- Post Title: vorb4 wav?

hi i have the new harry potter here, well the audio are in a container but its a little strange

after dbpoweramp

```
Original Size 29,74 MB
Length 2 minutes 56 seconds
Channels 2  (stereo)
Sample Rate 44,1 KHz{CR}
Sample Size 16 bit
Bit Rate 220 kbps
Encoder 
Encoder Settings Unknown ACM ID: 65535 (ACM decoder not installed)
Audio Quality Low  (Lossy)
Contains 
Channel Mapping Left, Right
File DH1_Streamed00F35800
Type Microsoft Wave Soundformat    [.wav]

```


First bytes of header

```
RIFF.CJ.WAVEfmt ........D....k..............cue ................data............LIST$...adtllabl........Snatcher Industrial.vorb4....<v.................B.I..u..rv...... L...N..........data]BJ.................................
```


i have not direct a idea, was first thinking about any kind of wav vobis but its worked not
[http://www.xup.in/dl,14101421/DH1_Streamed00F35800.wav/](http://www.xup.in/dl,14101421/DH1_Streamed00F35800.wav/)
## Post #2
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-11-16T16:48:54+00:00
- Post Title: vorb4 wav?

This is Wwise Vorbis use ww2ogg to convert this into playable ogg vorbis.
## Post #3
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-16T16:55:13+00:00
- Post Title: vorb4 wav?

> Reply from Barnaby
>
> This is Wwise Vorbis use ww2ogg to convert this into playable ogg vorbis.
thx works


btw is here anyway to create this wwise vobis format?
## Post #4
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-11-16T17:04:37+00:00
- Post Title: vorb4 wav?

Well there is but I believe the Wwise cost a very large sum of money. Not sure if there is any other way.
## Post #5
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-11-17T00:20:53+00:00
- Post Title: vorb4 wav?

well if ww2ogg exists, it should be possible to reverse engineer ww2ogg, figure out the format of these files and produce an ogg2ww tool or similar.
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-17T21:09:01+00:00
- Post Title: vorb4 wav?

> Reply from jfwfreo
>
> well if ww2ogg exists, it should be possible to reverse engineer ww2ogg, figure out the format of these files and produce an ogg2ww tool or similar.
Well or you can download a FREE demo sdk from here (you need to register):
[http://www.audiokinetic.com/en/downloads](http://www.audiokinetic.com/en/downloads)

Works great, but no always, normally wwise vorbis have parameters like action scenes, lips or if the audio it's SFX, voices or music, etc..it's a bit complex (for me) but sure someone can make a nice tool with this SDK.

In the example of the last harry potter the audio files have internal data with the name of the sequence/s if you reconvert to ogg and then to wwvorbis again you can't hearth anything..missing data=missing audio.

Example:

```
      Ú data        Ú    ›& data        ›&    an
 data        an
    ¸5 data        ¸5    ˜¦ data        ˜¦    . data        .    , data        ,    œø data        œø 	   ¯» data        ¯» 
   ©| data        ©| LIST0  adtllabl      S7_05662A_GEO_ALL labl      S7_05663A_FRE_ALL labl      S7_05664A_GEO_ALL labl      S7_05665A_FRE_ALL labl      S7_05666A_GEO_ALL labl      S7_05667A_FRE_ALL labl      S7_05668A_GEO_ALL labl      S7_05669A_FRE_ALL labl   	   S7_05670A_GEO_ALL labl   
   S7_05671A_FRE_ALL vorb4   ¯k% Z!      ê   î   Úa     ê   °   L  N  ç½¤  dataáa ä     +»Pö‚2®$

```

You can try with "The saboteur" too, it uses wwise vorbis with a lot of data inside.

The problem is not the extraction/conversion to wwvise, the problem it's how to save the internal data and add after the final conversion.
Maybe wwvorbis it's "killing" Fmod/FSB?
## Post #7
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-18T21:28:06+00:00
- Post Title: vorb4 wav?

> Reply from Savage
>
> jfwfreo wrote:well if ww2ogg exists, it should be possible to reverse engineer ww2ogg, figure out the format of these files and produce an ogg2ww tool or similar.
Well or you can download a FREE demo sdk from here (you need to register):
http://www.audiokinetic.com/en/downloads

Works great, but no always, normally wwise vorbis have parameters like action scenes, lips or if the audio it's SFX, voices or music, etc..it's a bit complex (for me) but sure someone can make a nice tool with this SDK.

In the example of the last harry potter the audio files have internal data with the name of the sequence/s if you reconvert to ogg and then to wwvorbis again you can't hearth anything..missing data=missing audio.

Example:
Code: Select allRIFF}d WAVEfmt    ÿÿ €»  1„           cue ô   
      Ú data        Ú    ›& data        ›&    an
 data        an
    ¸5 data        ¸5    ˜¦ data        ˜¦    . data        .    , data        ,    œø data        œø 	   ¯» data        ¯» 
   ©| data        ©| LIST0  adtllabl      S7_05662A_GEO_ALL labl      S7_05663A_FRE_ALL labl      S7_05664A_GEO_ALL labl      S7_05665A_FRE_ALL labl      S7_05666A_GEO_ALL labl      S7_05667A_FRE_ALL labl      S7_05668A_GEO_ALL labl      S7_05669A_FRE_ALL labl   	   S7_05670A_GEO_ALL labl   
   S7_05671A_FRE_ALL vorb4   ¯k% Z!      ê   î   Úa     ê   °   L  N  ç½¤  dataáa ä     +»Pö‚2®$

You can try with "The saboteur" too, it uses wwise vorbis with a lot of data inside.

The problem is not the extraction/conversion to wwvise, the problem it's how to save the internal data and add after the final conversion.
Maybe wwvorbis it's "killing" Fmod/FSB?

hope not, well i think both are sensles, its sensles to fill audio as wav pcm i remember a game 3 gb wav, when its used in fsb its senles 2, i dont know why they dont want to use vobis, support chans and more

i think here is anyway, people make it also can people fuck it , but its still ur question about exact and reinject it
## Post #8
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2010-11-22T15:25:43+00:00
- Post Title: vorb4 wav?

> Reply from Barnaby
>
> This is Wwise Vorbis use ww2ogg to convert this into playable ogg vorbis.
Will the the file stay lossless, after using ww2ogg or become lossy?

> Reply from Cryptonia
>
> hi i have the new harry potter here, well the audio are in a container but its a little strange
How did you extract the music files out of the *.pck file, by the way? Couldn't find a working script.
## Post #9
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-11-22T18:02:58+00:00
- Post Title: vorb4 wav?

All ww2ogg does is change the file headers etc. to make it playable as a normal ogg file. It doesn't convert it. All Wwise ogg is is normal vorbis in a wwise container.
## Post #10
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-23T15:51:32+00:00
- Post Title: vorb4 wav?

@funny normal filescanner, scanning after wav

@Barnaby u sure i cant belive it realy thaht the container eat 400 kb and the time what the tool need is not realy short
## Post #11
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-11-23T16:41:50+00:00
- Post Title: vorb4 wav?

Not entirely sure. Ask hcs if you want to be certain.
## Post #12
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-11-24T00:59:28+00:00
- Post Title: vorb4 wav?

ww2ogg shouldn't lose any audio data. It throws away some stuff in the header, the stuff that doesn't go into a normal Ogg Vorbis file, as was discussed further up in this thread, but that is very small.  I'm not sure what you're asking about with the 400k... all of the changes that Audiokinetic made were to save space, and ww2ogg only does one Vorbis frame per page which is somewhat wasteful, so it is normal for the converted file to be a bit bigger.  But if the converted file is smaller, there's probably another RIFF/RIFX somewhere in the middle of the file that you're trying to convert, ww2ogg will only read from the beginning of the file so you'll need to split it up.
## Post #13
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-24T01:36:08+00:00
- Post Title: vorb4 wav?

> Reply from hcs
>
> ww2ogg shouldn't lose any audio data. It throws away some stuff in the header, the stuff that doesn't go into a normal Ogg Vorbis file, as was discussed further up in this thread, but that is very small.  I'm not sure what you're asking about with the 400k... all of the changes that Audiokinetic made were to save space, and ww2ogg only does one Vorbis frame per page which is somewhat wasteful, so it is normal for the converted file to be a bit bigger.  But if the converted file is smaller, there's probably another RIFF/RIFX somewhere in the middle of the file that you're trying to convert, ww2ogg will only read from the beginning of the file so you'll need to split it up.

ah kay i changed some facts in my brain, ur rigth i mean the fact thaht  the ogg file was bigger
## Post #14
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2010-11-27T08:10:16+00:00
- Post Title: vorb4 wav?

Epic Mickey (Wii) uses this Wwise format, too.
## Post #15
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-29T02:44:49+00:00
- Post Title: vorb4 wav?

> Reply from FunnyML
>
> Epic Mickey (Wii) uses this Wwise format, too.

its like a pest, i start to hate it ....
