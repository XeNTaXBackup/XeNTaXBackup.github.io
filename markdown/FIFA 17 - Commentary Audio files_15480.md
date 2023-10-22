## Post #1
- Username: rocket7900
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 05, 2015 5:19 am
- Post datetime: 2016-11-11T17:50:11+00:00
- Post Title: FIFA 17 - Commentary Audio files

hi to all, i would ask help to decode audio files from FIFA 17 Commentary, i have made some hex research in the past and have found some information if useful:

1) Audio container/codec i think must be a EALayer3 ( Hex audio frame begin with 0x48 )
2) codec has been changed from fifa 16 with new coding in Frostbite engine ( From 0x19 - Speex  to 0x1C i suppose Opus Codec )
3) Sample to 48000 Hz from old speex 32000 hz  ( hex show 0xBB 0x80  = 48000 )
4) after sample Ealayer3 structure 0x40 - code for lenght of audio file 
5) after that Ealayer3 structure 0x44 - code for think a pitch time
6) after that 0x28 0x08 is the same for all streams and think is the begin of frame packet
7) Ealayer3 container closing with same 0x45 follow by 0x04 or 0x05 or 0x06 used by Ea to recognize type of audio 

From Demo of old ignite fifa 16 i have seen some file with debug inside from ea and audio master audio file was simple .wav and .aiff and ea encoded with speex format ( was the .sbr .sbs archive for all fifa version from 2011 to 2016 )


Ask for expert an help to decode this stream as wav or mp3






i have extract the first audio file from .cas commentary ( cut and paste from demo file not encrypted with hex viewer)
i have put an extension .eal3 but its not real

[https://mega.nz/#!mU8D1DpY!nyv-qZJTy8eD ... YwMhijDUkg](https://mega.nz/#!mU8D1DpY!nyv-qZJTy8eDLOELbILRHxUFl4e6Rk2yFYwMhijDUkg)
[hex.gif](https://xentaxbackup.github.io/file/11900_hex.gif)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-11T19:01:11+00:00
- Post Title: FIFA 17 - Commentary Audio files

> Reply from rocket7900
>
> 1) Audio container/codec i think must be a EALayer3 ( Hex audio frame begin with 0x48 )
2) codec has been changed from fifa 16 with new coding in Frostbite engine ( From 0x19 - Speex  to 0x1C i suppose Opus Codec )
3) Sample to 48000 Hz from old speex 32000 hz  ( hex show 0xBB 0x80  = 48000 )
4) after sample Ealayer3 structure 0x40 - code for lenght of audio file 
5) after that Ealayer3 structure 0x44 - code for think a pitch time
6) after that 0x28 0x08 is the same for all streams and think is the begin of frame packet
7) Ealayer3 container closing with same 0x45 follow by 0x04 or 0x05 or 0x06 used by Ea to recognize type of audio

1) ealayer3 is not a container, its codec. This file is not ealayer3
2) why do you think its opus?
5) 0x44 is frame size
7) its not type of audio, just end of file. And you cut off some bytes from it in the end
## Post #3
- Username: rocket7900
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 05, 2015 5:19 am
- Post datetime: 2016-11-11T20:51:05+00:00
- Post Title: FIFA 17 - Commentary Audio files

Sorry for not technical english, but i have attached the first stream inside .cas was an example found for the commentary of the demo games, after that ( it's finished with 0x45 0x00 0x00 0x05 ) begin another streams and so on ( i cant attach 800mb of entire .cas file )

i have opened the .exe of the game and searching in the hex viewer there are some reference to soma audio codec tha the game use, ACC audio for the video, speex, opus, EA use some free codec for their audio files so they changed from fifa 16 was used speex to the best quality of opus ( same free ) to improve the audio quality ( i have compared soma portion of opus sample audio to this stream and there are some similitudes...

in fifa 16 i have tried to change the value of the bytes after 0x44 and the voice in the game was acclereted after that, because ea using a system of pitch predicition to combine some portion of dialogues togheter during the game commenatry ( portion of dialogues that have different pitch time )

why it's not a ealayer3 ??? refering from zench page for the header b type
[https://bitbucket.org/Zenchreal/ealayer ... ew-default](https://bitbucket.org/Zenchreal/ealayer3/src/6bd060055708bc874b41501a7214adbbf077b64c/src/Writers/HeaderBWriter.cpp?at=default&fileviewer=file-view-default) Ea changed ealayer3 and modify that when passed to speex compression but the basic structure is the same perhaps a variant of ealayer3

i'm not expert but this is what i have found studing on it... i think it's a bit of base to know better for found or create an decoder
## Post #4
- Username: rocket7900
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 05, 2015 5:19 am
- Post datetime: 2016-11-11T21:02:10+00:00
- Post Title: FIFA 17 - Commentary Audio files

attach some piece of hex viewer on th main .exe where there are reference to audio codec used in the game...
[opus.gif](https://xentaxbackup.github.io/file/11903_opus.gif)
## Post #5
- Username: rocket7900
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 05, 2015 5:19 am
- Post datetime: 2016-11-11T21:03:03+00:00
- Post Title: FIFA 17 - Commentary Audio files

another
[audio.gif](https://xentaxbackup.github.io/file/11904_audio.gif)
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-11T21:41:46+00:00
- Post Title: FIFA 17 - Commentary Audio files

> Reply from rocket7900
>
>  ( it's finished with 0x45 0x00 0x00 0x05 )

It must be finished with 0x45 0x00 0x00 0x05 0x00, so you cut off 1 byte in this case

> Reply from rocket7900
>
> in fifa 16 i have tried to change the value of the bytes after 0x44 and the voice in the game was acclereted after that

Its because you ruined the file structure which can lead to unpredictable results. After 0x44 is FRAME SIZE.

> Reply from rocket7900
>
> why it's not a ealayer3 ???

Because ealayer3 is MP3 audio. This is not MP3 audio. This is another codec, maybe OPUS as you said. But in this case to decode it we need to build proper OPUS header for the raw data contained in this file. Do you know how to do this?
## Post #7
- Username: rocket7900
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 05, 2015 5:19 am
- Post datetime: 2016-11-11T21:58:07+00:00
- Post Title: FIFA 17 - Commentary Audio files

i suppose that is opus because the quality of the audio in the game is better than old fifa 16  ( 0x19 speex codec ) and found some reference to opus in the exe and after see this comparision

[http://opus-codec.org/comparison/](http://opus-codec.org/comparison/)

so i think that EA for fifa 17 using Frostbite change in better with this codec but its only what i suppose...if is opus there is above site that share all for encoder and decoder audio libreries for opus format ( use ogg container but for me EA - DICE on their audio engine use a raw opus packet payload inside the eayaler3 )

after the 0x44 frame size for all stream is common this code 0x28 0x08 in the fifa form 2012 to 2016 was 0x19 0x83 i dont know if audio packet start from there or not...
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-12T06:33:48+00:00
- Post Title: FIFA 17 - Commentary Audio files

> Reply from rocket7900
>
> raw opus packet payload inside

ok, this must be the case, but stop calling it ealayer3, because it sounds like "they use mp3 inside ogg"

Also 0x2808 is number of samples in a frame. Then goes raw data.
## Post #9
- Username: rocket7900
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 05, 2015 5:19 am
- Post datetime: 2016-11-12T13:39:34+00:00
- Post Title: FIFA 17 - Commentary Audio files

Here are the opus libraries:

[http://opus-codec.org/downloads/](http://opus-codec.org/downloads/)

Are you able to decode the raw data if is opus audio ?
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-12T14:22:42+00:00
- Post Title: FIFA 17 - Commentary Audio files

> Reply from rocket7900
>
> Are you able to decode the raw data if is opus audio ?

I tried decoding it and it failed. As I expected.

I don't think decoding raw data is that easy. This is ogg, and you can't decode it just like that. It requires some complex manipulations and good knowledge of this codec. I don't have time for this.
## Post #11
- Username: rocket7900
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 05, 2015 5:19 am
- Post datetime: 2016-11-27T21:11:43+00:00
- Post Title: FIFA 17 - Commentary Audio files

> Reply from daemon1
>
> rocket7900 wrote:Are you able to decode the raw data if is opus audio ?

I tried decoding it and it failed. As I expected.

I don't think decoding raw data is that easy. This is ogg, and you can't decode it just like that. It requires some complex manipulations and good knowledge of this codec. I don't have time for this.

i dont know if usefull, but i have found this code to convert simple rtp opus audio payload to ogg

[https://git.xiph.org/?p=opus-tools.git; ... .c;hb=HEAD](https://git.xiph.org/?p=opus-tools.git;a=blob;f=src/opusrtp.c;hb=HEAD)

if EA have their special audio container perhaps after code ( 2880 ) start the payload...
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-28T15:42:19+00:00
- Post Title: FIFA 17 - Commentary Audio files

this is a part of their official tools. And it can't be compiled as a single file. I don't have time to mess with their code and learn the codec.

p.s. what is RTP?
## Post #13
- Username: rocket7900
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 05, 2015 5:19 am
- Post datetime: 2016-11-30T22:22:26+00:00
- Post Title: FIFA 17 - Commentary Audio files

> Reply from daemon1
>
> this is a part of their official tools. And it can't be compiled as a single file. I don't have time to mess with their code and learn the codec.

p.s. what is RTP?

is useful [https://en.wikipedia.org/wiki/RTP_audio_video_profile](https://en.wikipedia.org/wiki/RTP_audio_video_profile)
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-01T16:23:25+00:00
- Post Title: FIFA 17 - Commentary Audio files

ok then this RTP will not help us

you need someone who have time to CODE opus stuff for you, or find a tool that can handle raw opus stuff. I dont have time for this
## Post #15
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-12-01T20:29:18+00:00
- Post Title: FIFA 17 - Commentary Audio files

> Reply from daemon1
>
> I dont have time for this
You already said that.
