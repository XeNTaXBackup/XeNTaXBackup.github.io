## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-10-25T03:15:04+00:00
- Post Title: Dead Space Audio File.

U don't get this audio file, it seems that its compress, its certainly not a mus file.

[http://www.megaupload.com/?d=X0JN5VQ2](http://www.megaupload.com/?d=X0JN5VQ2)

Here is a sample.
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-10-29T11:28:16+00:00
- Post Title: Dead Space Audio File.

Very interested in this aswell, there are refrences to SBNK's in the str files, and I can't figure out if it's compressed or just an uncommon format.

btw, TrID says it's a generic xbase database, but I think it just doesnt have the right definitions for this type of file.
## Post #3
- Username: CUE
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 23, 2008 10:53 pm
- Post datetime: 2008-10-29T17:13:12+00:00
- Post Title: Dead Space Audio File.

I'm not sure, but looks like a TrueSpeech sound file.
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-10-29T22:36:14+00:00
- Post Title: Dead Space Audio File.

I highly doubt they would use true speech, it's primary use is very compact and "emotionless" speech.  it does some special thing with tones to make it smaller and sound bland.  it also is a very bad choice for a horror game where everybody's screaming and shooting.  i think it's more suited for text to speech apps and other things.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-10-30T17:41:37+00:00
- Post Title: Dead Space Audio File.

I got info from another member that the file is an interleaved EA ADPCM thats headerless. But again i don't know how to decode it.
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-03T07:00:21+00:00
- Post Title: Dead Space Audio File.

STR can refer to "Stream" and "SBNK" is most often a reference to "Sound Bank". I'll give a look-see.

I can hear music when trying to read it as raw music but it is too noisy. A little more would need to be done to convert this properly.
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-03T12:50:58+00:00
- Post Title: Dead Space Audio File.

Okay kataah told me it is basically a version of EA ADPCM_r3 thats headerless, its a codec that was used in Tiberium wars and nobody could decode it.
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-03T22:19:39+00:00
- Post Title: Dead Space Audio File.

```
01253     case CODEC_ID_ADPCM_EA_R2:
01254     case CODEC_ID_ADPCM_EA_R3: {
01255         /* channel numbering
01256            2chan: 0=fl, 1=fr
01257            4chan: 0=fl, 1=rl, 2=fr, 3=rr
01258            6chan: 0=fl, 1=c,  2=fr, 3=rl,  4=rr, 5=sub */
01259         const int big_endian = avctx->codec->id == CODEC_ID_ADPCM_EA_R3;
01260         int32_t previous_sample, current_sample, next_sample;
01261         int32_t coeff1, coeff2;
01262         uint8_t shift;
01263         unsigned int channel;
01264         uint16_t *samplesC;
01265         const uint8_t *srcC;
01266 
01267         samples_in_chunk = (big_endian ? bytestream_get_be32(&src)
01268                                        : bytestream_get_le32(&src)) / 28;
01269         if (samples_in_chunk > UINT32_MAX/(28*avctx->channels) ||
01270             28*samples_in_chunk*avctx->channels > samples_end-samples) {
01271             src += buf_size - 4;
01272             break;
01273         }
01274 
01275         for (channel=0; channel<avctx->channels; channel++) {
01276             srcC = src + (big_endian ? bytestream_get_be32(&src)
01277                                      : bytestream_get_le32(&src))
01278                        + (avctx->channels-channel-1) * 4;
01279             samplesC = samples + channel;
01280 
01281             if (avctx->codec->id == CODEC_ID_ADPCM_EA_R1) {
01282                 current_sample  = (int16_t)bytestream_get_le16(&srcC);
01283                 previous_sample = (int16_t)bytestream_get_le16(&srcC);
01284             } else {
01285                 current_sample  = c->status[channel].predictor;
01286                 previous_sample = c->status[channel].prev_sample;
01287             }
01288 
01289             for (count1=0; count1<samples_in_chunk; count1++) {
01290                 if (*srcC == 0xEE) {  /* only seen in R2 and R3 */
01291                     srcC++;
01292                     current_sample  = (int16_t)bytestream_get_be16(&srcC);
01293                     previous_sample = (int16_t)bytestream_get_be16(&srcC);
01294 
01295                     for (count2=0; count2<28; count2++) {
01296                         *samplesC = (int16_t)bytestream_get_be16(&srcC);
01297                         samplesC += avctx->channels;
01298                     }
01299                 } else {
01300                     coeff1 = ea_adpcm_table[ *srcC>>4     ];
01301                     coeff2 = ea_adpcm_table[(*srcC>>4) + 4];
01302                     shift = (*srcC++ & 0x0F) + 8;
01303 
01304                     for (count2=0; count2<28; count2++) {
01305                         if (count2 & 1)
01306                             next_sample = (int32_t)((*srcC++ & 0x0F) << 28) >> shift;
01307                         else
01308                             next_sample = (int32_t)((*srcC   & 0xF0) << 24) >> shift;
01309 
01310                         next_sample += (current_sample  * coeff1) +
01311                                        (previous_sample * coeff2);
01312                         next_sample = av_clip_int16(next_sample >> 8);
01313 
01314                         previous_sample = current_sample;
01315                         current_sample  = next_sample;
01316                         *samplesC = current_sample;
01317                         samplesC += avctx->channels;
01318                     }
01319                 }
01320             }
01321 
01322             if (avctx->codec->id != CODEC_ID_ADPCM_EA_R1) {
01323                 c->status[channel].predictor   = current_sample;
01324                 c->status[channel].prev_sample = previous_sample;
01325             }
01326         }
01327 
01328         src = src + buf_size - (4 + 4*avctx->channels);
01329         samples += 28 * samples_in_chunk * avctx->channels;
01330         break;
```


is this what you're talking about?  because according to the ffmpeg docs it supports it.
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-03T22:25:22+00:00
- Post Title: Dead Space Audio File.

Yes but the problem is that these type of R3 files are headerless, FFMPG only supports EA ADPCM with a header, but im not to sure,

```
00000010 04 1C BB 80 60 2E E0 00 00 00 00 00 00 00 00 00 ....`...........
00000020 00 00 07 28 00 00 01 80 A1 F8 05 00 A2 07 05 08 ...(............
00000030 B2 EF 26 EE 12 F8 16 FA 0F 10 3E 13 00 10 EF 22 ..&.......>...."
00000040 22 1F 00 FE 10 F1 DD 3E 0E 00 0E D0 FE 10 C0 22 "......>......."
00000050 DD FE 35 01 EE 01 FC 14 FF 0F DD 0C 01 13 00 CE ..5.............
00000060 12 EE FE 21 32 0F CE 0D 12 FF 43 24 32 0B 21 53 ...!2.....C$2.!S
00000070 34 F0 FF 33 F1 FC 06 00 32 07 76 08 02 F4 16 F3 4..3....2.v.....
00000080 82 04 F5 05 0F FF 04 0C 00 00 1E E3 22 1F 10 00 ............"...
00000090 10 D1 76 03 FF 50 1E 33 FF DB 43 FD FD 0E DE C2 ..v..P.3..C.....
000000A0 ED BC DF 32 DC FE 00 FE F2 FF 02 00 22 CD 11 21 ...2........"..!
000000B0 22 32 CD FF 13 50 35 03 56 E0 20 4E 47 2F CF F1 "2...P5.V. NG/..
000000C0 D0 FF 55 00 A1 00 C4 FF B1 FB F4 FE F1 FC 14 FF ..U.............
000000D0 0F 11 1E 12 E0 0D 21 FC F3 33 EF 42 5F D1 10 D1 ......!..3.B_...
000000E0 C0 00 E1 00 1F 0E 1E 10 0F F1 10 02 13 FF E2 1E ................
000000F0 DE 40 0B 10 2C E1 24 C2 D0 00 E0 2F F0 1F 1D 12 .@..,.$..../....
00000100 0B 02 C3 FF EE 1D 0E 20 F2 FE 10 01 81 FF 65 01 ....... ......e.
00000110 21 01 C4 00 41 00 75 FC E1 00 45 00 C1 21 E1 13 !...A.u...E..!..
00000120 D2 D1 1E E5 40 5C 03 3B FF E4 0B 01 10 FE 05 3F ....@\.;.......?
00000130 E0 0F C1 E0 2F 11 2B 30 0C F0 40 C4 11 0F B3 ED ..../.+0..@.....
00000140 B2 01 4E 50 01 11 01 F2 2C F0 D1 31 24 1F 0D F1 ..NP....,..1$...
00000150 E5 E0 22 02 DF D0 10 0B B1 FF D6 00 C2 00 E7 00 ..".............
00000160 02 01 78 00 22 F9 77 F9 DC 02 4E 20 02 E0 F7 31 ..x.".w...N ...1
00000170 23 0E C7 20 02 1E BE 02 FF 01 BC 0D FE 22 FF FC #.. ........."..
00000180 0D 11 20 D0 FE 30 FF D2 FF FF 11 00 01 C0 EA 2D .. ..0.........-
00000190 10 B2 CF 1E 10 12 A1 01 12 11 D0 2E 00 1F CC 2D ...............-
000001A0 11 1F E1 20 81 FF 36 01 42 FF 78 FF 82 FE F7 FD ... ..6.B.x.....
```
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-03T23:01:30+00:00
- Post Title: Dead Space Audio File.

I know, but is there any way to rebuild the header?  or any info on what it normally looks like?
## Post #11
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-03T23:25:44+00:00
- Post Title: Dead Space Audio File.

[http://wiki.multimedia.cx/index.php?tit ... udio_Codec](http://wiki.multimedia.cx/index.php?title=EA_Command_And_Conquer_3_Audio_Codec)


appearently it's XAS.  and headerless versions have the headers stored elsewhere in the data.
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-04T00:30:52+00:00
- Post Title: Dead Space Audio File.

HMM interesting.

Kataah a member that studied the file says that it has certain properties to ogg codec. and that the stream is also interleaved, its very complicated.
## Post #13
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-04T04:01:46+00:00
- Post Title: Dead Space Audio File.

should be similar to mp3, the files are normally ea layer3 (cant find much on it) when headerless.
## Post #14
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2008-11-04T21:08:19+00:00
- Post Title: Dead Space Audio File.

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-05T01:08:12+00:00
- Post Title: Dead Space Audio File.

lately i've just been looking through the game files for the headers, I've had shit luck, but I havent covered nearly all of it.  I'm sure the game has a method for loading the 16byte headers somewhere.

edit:  I know what you mean, XAS has 16 byte headers then 76byte data chunks alternating between the channels or something.
## Post #16
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-05T01:54:04+00:00
- Post Title: Re: Dead Space Audio File.

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-05T02:11:57+00:00
- Post Title: Re: Dead Space Audio File.

Maybe the headers could be hidden in the other files like the strs?
## Post #18
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-05T02:39:13+00:00
- Post Title: Re: Dead Space Audio File.

if you looked at what i posted, I have been searching the strs.  the frontend one seems most likely so i uploaded it.
## Post #19
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-05T04:40:40+00:00
- Post Title: Re: Dead Space Audio File.

Yeah i looked into that so it could be possible.
## Post #20
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2008-11-06T14:16:54+00:00
- Post Title: Re: Dead Space Audio File.

Hey guys, as darkfox has said. Processing it into RAW data gets you some music, but more high frequency ranges than I know what to do with. I've gone through most of the files from processing it as 8bit to 32bit. I found that 12, 16 and 24bit have the closest clarity sound to them. I don't really know if that will help but just thought I would mention it.

I've had the idea to gain access to dead space's audio for some time. I am just blown away by the sounds they use and the music. That said, I have gone through just about every single file reader app out there trying to get into the .snu and .str's. Everything from simple changes to the extension to importing it as raw data and processing it into different bits and resampling it. Nothing cuts it.

Btw has anyone gone through the C:\Program Files\Electronic Arts\Dead Space\global_assets\global_assets\ds_assets\audio_global\audio_streams for some with headers? When I extracted most of them, I kept finding txt reffering to a .sbk file that is locked away some where.
## Post #21
- Username: NeMetS
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 09, 2008 3:39 am
- Post datetime: 2008-11-08T23:24:42+00:00
- Post Title: Re: Dead Space Audio File.

Hello all. 

Sorry I am not a delevoper or something...  


Could you please say me how I can get some sound from *.str ?

I mean... what I must use to do it  


PS. Sorry for my english
## Post #22
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-09T02:00:46+00:00
- Post Title: Re: Dead Space Audio File.

that is what we are trying to figure out, we dont have a solution yet other then importing raw data and getting static-ish crap.

I would like someone good with ea audio formats to look at the file i posted at the top of this page.  it's an str containing multiple 04's after a sbk reference.  (04 = xas compressed adpcm)  I believe it contains the headers, but I have no idea how (what order) they relate to the files.
## Post #23
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-09T03:47:24+00:00
- Post Title: Re: Dead Space Audio File.

The static is whatever encryption/compression method being used I believe.
## Post #24
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-11-17T00:50:39+00:00
- Post Title: Re: Dead Space Audio File.

This is just like halo. There are no headers, you must create them. if you can get the number of channels and sample rate, I might be able to get you some working wavs out of these.
## Post #25
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-18T01:58:18+00:00
- Post Title: Re: Dead Space Audio File.

Kataah has sent me a tool by russian coders that decoded the dead space files successfully.
## Post #26
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2008-11-18T10:01:44+00:00
- Post Title: Re: Dead Space Audio File.

Successful rip of any/all audio? If at all possible can you send me the program? Desperate to give it a shot.

Grim... I would most likely assume its 4 channel if not 6 considering their defaults for audio are 5.1. I cannot provide more evidence due to my Audio analizer doesnt show me how many channels the raw data holds.
## Post #27
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-18T12:59:44+00:00
- Post Title: Re: Dead Space Audio File.

Very interested in this tool as well, and I doubt the sound files are anything more then stereo at most, normally games mix the sounds around the channels for higher speaker settings,  and don't need 6 channels for each sound effect.  rate is normally 44100 or 32000 khz.

again, would also love that program.
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-18T16:23:09+00:00
- Post Title: Re: Dead Space Audio File.

Okay here it is.
[SNU.rar](https://xentaxbackup.github.io/file/1748_SNU.rar)
## Post #29
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-18T16:23:30+00:00
- Post Title: Re: Dead Space Audio File.

Okay here it is.
[SNU.rar](https://xentaxbackup.github.io/file/1749_SNU.rar)
## Post #30
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-19T12:14:18+00:00
- Post Title: Re: Dead Space Audio File.

Nice!  it works perfectly.   all thats left are the audio asset str's.
## Post #31
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2008-11-20T10:13:12+00:00
- Post Title: Re: Dead Space Audio File.

avg found a trojan in the wav.exe. confirm?
## Post #32
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-20T15:31:45+00:00
- Post Title: Re: Dead Space Audio File.

Never had any problems.
## Post #33
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-20T19:31:55+00:00
- Post Title: Re: Dead Space Audio File.

AVG antivirus is shit.  it's way overprotective.
## Post #34
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2008-11-23T15:59:45+00:00
- Post Title: Re: Dead Space Audio File.

Running windows xp here. I cannot seem to get either of the items to run. Ive ran each program in compatibility mode. Also placed them inside the dead space folder with the .str files. Doesn't seem to work either way. Don't know if I am doing something wrong with them. If someone can tell me how to get them to do what they are suppose to I'd be greatful. Thanks.
## Post #35
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-11-25T02:33:51+00:00
- Post Title: Re: Dead Space Audio File.

had to figure this out too, put it in a folder with strs and run the non-wav one.
## Post #36
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2008-11-25T22:28:45+00:00
- Post Title: Re: Dead Space Audio File.

I must express my thanks. I finally paied attention enough to realize it was for the .snu files not the .str's. Works great and I am extremely greatful! You have made my year with this nifty converter!
## Post #37
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-01-11T18:10:39+00:00
- Post Title: Re: Dead Space Audio File.

I reconverted the audios and are great..but...i tried a few options to add the waved .nsu files in the game.

1-.Converted the wav to raw -> the game crashes
2-.Converted the wav with the tool sx, using all the methods, the game works but the sound is muted, no speech no musics...

In the 2nd case the game works...so..it's any tool to reconvert the waved audios to the "original" scheme? tool sx.exe it's outdated
## Post #38
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2009-09-15T17:59:10+00:00
- Post Title: Re: Dead Space Audio File.

so did anybody find any sort of wav2snu converter?
## Post #39
- Username: shaska
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 21, 2009 11:05 am
- Post datetime: 2009-09-23T15:12:23+00:00
- Post Title: Re: Dead Space Audio File.

help!!!! guy I SEARCH  a tool to convert SOUND EFFECT OF DEAD SPACE 

SOUND.STR to WAV or OGG

help!!! help!!!! help!!!!  

the SNU file no work in winxp o please send mi guide for tool
## Post #40
- Username: LoneTiger
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 16, 2010 3:51 am
- Post datetime: 2010-09-15T19:59:58+00:00
- Post Title: Re: Dead Space Audio File.

Most AV engines will detect convert and extract programs as trojans because of what they do, they scan the file and pull its content. Main reason it sometimes is stopped by your AV engine or put in quarantine. But since we know what the program is supposed to do just let it do its work to extract/convert audio.
## Post #41
- Username: aegisfangX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 22, 2010 11:21 am
- Post datetime: 2010-09-22T05:25:33+00:00
- Post Title: Re: Dead Space Audio File.

Hey guys, know a bit late on this thread, but have been trying to convert the dead space .snu's for a while now to no avail and saw that you guys were able to do it on this thread... sadly I don't have access to the converter that was posted earlier. Does anybody still have it around?
## Post #42
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-09-22T11:10:56+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from aegisfangX
>
> sadly I don't have access to the converter that was posted earlier. Does anybody still have it around?? You mean the SNU.rar posted by OrangeC? The download is still working...I just checked it.
## Post #43
- Username: aegisfangX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 22, 2010 11:21 am
- Post datetime: 2010-09-23T04:16:47+00:00
- Post Title: Re: Dead Space Audio File.

Yea apologies, must have been an issue with my account being verified. Tool works awesome, outstanding post! Anybody know if you can specify an output location or anything with this guy?
## Post #44
- Username: Climbatize
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 18, 2010 11:05 pm
- Post datetime: 2010-10-18T15:59:22+00:00
- Post Title: Re: Dead Space Audio File.

Downloaded Snu.rar
opened ConvAll.bat
"@wav.exe *.*"
what is this script for .bat file? Don't see any directory to output extracted seemingly unexisting sound/music files from .snu or .str pack, Searched all computer for extracts possibly done by command prompt, which only pops out for a second and disappeares with no trace of .wav that supposed to be created.
What am i missing here?
## Post #45
- Username: Isaac Clarke
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 07, 2010 2:33 am
- Post datetime: 2010-11-07T14:16:02+00:00
- Post Title: Re: Dead Space Audio File.

Hello,
I also have a problem with Avast tells me it is a trojan that I do? !

PS: I find all the tracks of dead space! But I do not know if it's the same thing with SNR as SNR is software somehow?
## Post #46
- Username: Ark5
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 26, 2010 4:11 pm
- Post datetime: 2010-11-26T09:24:32+00:00
- Post Title: Re: Dead Space Audio File.

bump, guys I need the sound effects really really bad. The link is down and I hope these are right ones too. Im looking for the sounds over the PA in the game. The computer AI lady that says stuff like "engines firing, please stand by"
## Post #47
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-11-26T12:20:58+00:00
- Post Title: Re: Dead Space Audio File.

Well, the snu tool link works aka towav, but it won't do snr which are basicly multiple sound files together with different header that would need splitting... not to mention no filenames seemingly anywhere of the contained numerious files, maybe elsewhere... pain in ass EA formats.
## Post #48
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-11-26T14:06:25+00:00
- Post Title: Re: Dead Space Audio File.

To give you the location of what to work on... Most of the ship's voice is inside the .snu's. All of the (assets) .str's are the foley's, weapons, necromorphs and ect, to which have not yet been researched or at least no real way to get to them. 

Nova's extractor and towav are what you need.
[http://www.volny.cz/nova-software](http://www.volny.cz/nova-software)

This forum might help the process of how to.
[http://www.tweaktown.com/articles/421/g ... ndex6.html](http://www.tweaktown.com/articles/421/game_music_extraction_page_6_mafia_nightfire/index6.html)
## Post #49
- Username: Ark5
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 26, 2010 4:11 pm
- Post datetime: 2010-11-27T02:08:48+00:00
- Post Title: Re: Dead Space Audio File.

No i dont even have the game for my PC nor is it powerful enough to play it. The closest ive gotten to any of the noises is at [http://www.entertonement.com/collection ... Dead-Space](http://www.entertonement.com/collections/qhybsjkkgh--Dead-Space) but i need to find some way to download off of the website because its not letting me
## Post #50
- Username: DarkStar88
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 16, 2011 12:32 am
- Post datetime: 2011-02-19T19:36:37+00:00
- Post Title: Re: Dead Space Audio File.

The extractor works perfectly. Problem is determining what sounds come from where - the folder names are either a half-decent hint (like the numbered ones which are by-chapter audio logs) or completely cryptic. I've played through the whole game twice and can at least place some of them now...like the voice of the guy just outside the door where you get your first weapon.

EDIT: So what would it take to at least crack the door on the .str files? 

Are there any programs that take an unknown file and run through a long list of known filetypes? Or will it have to be the old-fashioned way: opening them up in a hexeditor and trying to puzzle things out from square 1?

BTW - I managed to find a .str extractor for another game's soundfiles, I'll come back after I've tried it on DS. (Thank you Wayback Machine for rescuing me from another 404 link.) If I'm insanely lucky...
## Post #51
- Username: Arakune
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 07, 2011 5:56 am
- Post datetime: 2011-06-06T22:18:24+00:00
- Post Title: Re: Dead Space Audio File.

I hope this thread hasn't completely died... I was hoping someone could, maybe, upload the sound files. I own the game, but not on PC. I really want all the sounds the necromorphs make, and it seems the only way to get them is to open the sound files. I downloaded the program you guys used to open them..... but I need the sound files and can't get them from the game disc. Would anyone be so kind as to upload them somewhere?
## Post #52
- Username: spy007
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 06, 2012 3:02 am
- Post datetime: 2012-02-05T23:02:11+00:00
- Post Title: Re: Dead Space Audio File.

Can somebody please extract ds or ds2 menu action sounds for me?
## Post #53
- Username: deathkitten
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2012 12:32 pm
- Post datetime: 2012-06-24T04:53:50+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from OrangeC
>
> Kataah has sent me a tool by russian coders that decoded the dead space files successfully.

This is actually a virus:
Trojan TR/Gendal.1216653.11
virustotal.com/file/5c3385c1ded87221478346bacd9536cd3ce0e42c3c40195b23392647ab75f70b/analysis

Does anyone else know how to play/extract the dead space/dead space 2 SNU files? 


Or also interestingly the dead space 1/dead space 2 STR files? those seem to be like archives within the archives, the STR ones are extracted from the DAT files with the RickVisceral110423 extractor from the other thread [viewtopic.php?f=10&t=5881](http://forum.xentax.com/viewtopic.php?f=10&t=5881) ( download link [download/file.php?id=1749](http://forum.xentax.com/download/file.php?id=1749) ) but so far as I can find there is nothing to actually view the STR files so it's kind of useless?
## Post #54
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-21T21:16:27+00:00
- Post Title: Re: Dead Space Audio File.

someone get way to convert snu files is very important for me please thank's
## Post #55
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-08-27T19:19:46+00:00
- Post Title: Re: Dead Space Audio File.

This is quite old, but I've been trying without a single bit of success on decoding that .sbk(sbnk?) file, 
judging by the more experienced comments I ended up believing it's near impossible, but one can hope. :/

a chunk sample for those who might be able to figure it out:

[http://filetrip.net/dl?nzcXLS5xIL](http://filetrip.net/dl?nzcXLS5xIL)

if it helps, some files I noticed such as .smb inside show the actual sfx extensions are .exa , a compression within a compressioneption...
## Post #56
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2015-03-23T05:43:33+00:00
- Post Title: Re: Dead Space Audio File.

Bumping to revive!

Sadly lost a lot of my collected audio due to a hard drive failure and no backups made. Curious if anyone out there had any progress or luck on this finally.
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-25T15:56:32+00:00
- Post Title: Re: Dead Space Audio File.

Yes, everything can be extracted from DS1/2/3 now. If you need any info about audio in these games, feel free to ask me.
## Post #58
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-03-26T01:58:32+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from daemon1
>
> Yes, everything can be extracted from DS1/2/3 now. If you need any info about audio in these games, feel free to ask me.

Then, feel free to share what you know about it with us. Any help is welcomed at this point.
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-26T15:10:55+00:00
- Post Title: Re: Dead Space Audio File.

I've already done it yesterday. Here [viewtopic.php?f=10&t=10054](http://forum.xentax.com/viewtopic.php?f=10&t=10054) is the updated list of files, so all DS3 big audios can be extracted. And here [viewtopic.php?f=10&t=12716](http://forum.xentax.com/viewtopic.php?f=10&t=12716) I posted a tool to extract all small audio samples. I think its all information needed to extract 99% of audio from DS1/2/3.

Right now I'm working on modified version of ealayer3 that will allow to convert the remaining 1%.

Also maybe we need to summarize all the info in one place, and describe the formats themselves, maybe wiki, or a separate thread. I'm not familiar with xentax, suggestions are welcome.
## Post #60
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-03-27T08:59:03+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from daemon1
>
> I've already done it yesterday. Here viewtopic.php?f=10&t=10054 is the updated list of files, so all DS3 big audios can be extracted. And here viewtopic.php?f=10&t=12716 I posted a tool to extract all small audio samples. I think its all information needed to extract 99% of audio from DS1/2/3.

Right now I'm working on modified version of ealayer3 that will allow to convert the remaining 1%.

Also maybe we need to summarize all the info in one place, and describe the formats themselves, maybe wiki, or a separate thread. I'm not familiar with xentax, suggestions are welcome.

I think your thread "[Dead Space 2 .sbk file](http://forum.xentax.com/viewtopic.php?f=10&t=12716)" is enough to regroup all those informations. But, silly me, I didn't ask you if your way to do that include all versions of this game or only the PC version. It's important to know because the Xbox360 version, for example, use .xma sounds and it's impossible to unpack .str Xbox360 files with Rick's tools. I created a thread about it but without success...
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-27T16:04:26+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from Vosvoy
>
> It's important to know because the Xbox360 version, for example, use .xma sounds and it's impossible to unpack .str Xbox360 files with Rick's tools. I created a thread about it but without success...

That's possible. I already changed rick's strpack once because it couldn't pack some files. But why do you want xbox .strs unpacked? They probably contain the same sounds as on PC or not?

p.s. Is it really forbidden to upload any file samples here on xentax? Because I see people still upload them in new threads.
## Post #62
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-03-27T16:23:23+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from daemon1
>
> But why do you want xbox .strs unpacked? They probably contain the same sounds as on PC or not?

Oh, don't mind that mate. It's just because I always prefered to extract sounds from .xma files because it's pretty easier for me (it's my point of vue of course). I'm just curious to know if you ever modified Rick's StrUnpack.exe because if you did that I hope you could help me to unpack .str archives from Xbox360. Anyway... It's not the priority.

> Reply from daemon1
>
> Is it really forbidden to upload any file samples here on xentax? Because I see people still upload them in new threads.

Hum... I think it's forbidden to give/share direct content from games at some points. Personaly, I always give a hex view of a file to avoid any problem with moderators.

Last thing, I've got Dead Space 1,2,3 on my PC and I would help with filenames but I don't know how to proceed. Can you tell me how you did with more details? Plus, I don't know if filenames offsets are the same for PS3 and Xbox360 users.
## Post #63
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-27T16:37:39+00:00
- Post Title: Re: Dead Space Audio File.

ok, pm me one .str file so i can try it
## Post #64
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-27T18:39:07+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from Vosvoy
>
> It's important to know because the Xbox360 version, for example, use .xma sounds and it's impossible to unpack .str Xbox360 files with Rick's tools. I created a thread about it but without success...

Alright, here's why.

XBox version of .str stores some files with another compression method than on PC. Probably lzx. So to unpack it, we need to find out what the compression is, and add code to unpack it.

check here [viewtopic.php?p=82395#p82395](http://forum.xentax.com/viewtopic.php?p=82395#p82395)
## Post #65
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-03-27T18:49:53+00:00
- Post Title: Re: Dead Space Audio File.

I see but, however, your tool ds2_sbk.exe doesn't work on Xbox360 .sbk files so it's a lost cause because I doubt that many people would help about lzx compression. I'm sorry but I can't deal with compressions. I could help for filenames and .xma files but nothing more.
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-27T19:15:20+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from Vosvoy
>
> I see but, however, your tool ds2_sbk.exe doesn't work on Xbox360 .sbk files

I can make it work on them, but unless we can unpack them from .str, its useless.

There's no universal method for filenames. You just need to find them or guess them somehow. I was able to do that for sound files, because all their names were stored in .smb files. But I don't know where to search for the remaining names.
## Post #67
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-03-27T19:21:35+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from daemon1
>
> Vosvoy wrote:I see but, however, your tool ds2_sbk.exe doesn't work on Xbox360 .sbk files

I can make it work on them, but unless we can unpack them from .str, its useless.

There's no universal method for filenames. You just need to find them or guess them somehow. I was able to do that for sound files, because all their names were stored in .smb files. But I don't know where to search for the remaining names.

Alright, but I need the bigfile1,2,3,etc... filenames. How do I get them if I can't recognize a single file in those archives? (no .filenames file)
## Post #68
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2015-03-29T04:48:56+00:00
- Post Title: Re: Dead Space Audio File.

Most likely Xbox360 has the compression on all files including potential filenames file so there is very little that can be done until solve compression first.
## Post #69
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-29T06:31:17+00:00
- Post Title: Re: Dead Space Audio File.

Here are the current filelists. But I think there's no need to find anything more. The only names left unidentified are 19 videos (with no sound) and a couple of text files. I doubt they are even used in the game.
[ds3filelists.zip](https://xentaxbackup.github.io/file/8900_ds3filelists.zip)
## Post #70
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2016-06-23T02:07:23+00:00
- Post Title: Re: Dead Space Audio File.

Sorry to be bumping an old-ish topic, but I'm trying to extract music from a game (Godfather 2 PC) that uses the .STR file format, which I believe may be similar to what Dead Space is using. I tried Rick's Visceral tool, but the StrUnpacker reports that it's reading in too much header information. Did someone say they had a modified version of the tool?
## Post #71
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-24T15:08:35+00:00
- Post Title: Re: Dead Space Audio File.

That was about sound tool, not rick's tool.
## Post #72
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2016-06-24T15:16:43+00:00
- Post Title: Re: Dead Space Audio File.

Ah, ok. Well if anyone has any knowledge in these archive formats, I could really appreciate [the help](http://forum.xentax.com/viewtopic.php?f=10&t=14505).
## Post #73
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-08-01T22:23:37+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from daemon1
>
> Here are the current filelists. But I think there's no need to find anything more. The only names left unidentified are 19 videos (with no sound) and a couple of text files. I doubt they are even used in the game.
There are 2 unknown files in bigfile0 and 1. Are those sound files or just some useless text files?

Also I have 105 unknowns in the audiostreams folder of DS2.
## Post #74
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-02T16:48:14+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from MaZTeR
>
> There are 2 unknown files in bigfile0 and 1. Are those sound files or just some useless text files?

Also I have 105 unknowns in the audiostreams folder of DS2.

105 unknowns is because you used old filelists. I posted them somewhere dont remember where.

Those in 0 and 1 are NOT sounds.
## Post #75
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-08-02T17:23:40+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from daemon1
>
> MaZTeR wrote:There are 2 unknown files in bigfile0 and 1. Are those sound files or just some useless text files?

Also I have 105 unknowns in the audiostreams folder of DS2.

105 unknowns is because you used old filelists. I posted them somewhere dont remember where.

Those in 0 and 1 are NOT sounds.
Do you have them in your computer perhaps?
## Post #76
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-02T18:45:33+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from MaZTeR
>
> Do you have them in your computer perhaps?
[http://pastebin.com/c2AQqE9V](http://pastebin.com/c2AQqE9V)

yes, that's the missing names, but I'm sure just recently I posted them for someone.

63 will still be unknown, but those are german files which I think are just left there by accident. Since they are not used in game, you can't give them names.
## Post #77
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-08-02T19:59:07+00:00
- Post Title: Re: Dead Space Audio File.

> Reply from daemon1
>
> MaZTeR wrote:Do you have them in your computer perhaps?
http://pastebin.com/c2AQqE9V

yes, that's the missing names, but I'm sure just recently I posted them for someone.

63 will still be unknown, but those are german files which I think are just left there by accident. Since they are not used in game, you can't give them names.
nice thanks
## Post #78
- Username: reiherrera
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 01, 2018 4:19 am
- Post datetime: 2018-09-30T20:24:59+00:00
- Post Title: Re: Dead Space Audio File.

hey guys. where can i get de SNU or SRT files or directly the wav files? did anyone got them?
