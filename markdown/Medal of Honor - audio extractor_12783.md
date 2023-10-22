## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-21T13:18:08+00:00
- Post Title: Medal of Honor - audio extractor

Audio extractor for Medal of Honor

Currently only tested on "Medal of Honor: Airborne" and "Medal of Honor 2010" but may work with other EA games with Unreal Engine.

Medal of Honor: Airborne

If you unpack .xxx packages with Gildor's extractor you get a lot of files of type .SoundRiotRawAsset. Some of them are soundbanks, and you can extract sounds from them with moha_snb [bank file]

Please note it will not work with "audio", "mix", "plugin" and other files, which are different types of audio assets. In this case the tool will give you an error "unknown file type". 

There are some external stream banks, which is needed to decode big stream .xxx files, which are not UE packages, but just a raw data for XAS streams. These banks are all named "stream.SoundRiotRawAsset", but they are all just headers for different big streams. To unpack those, place the corresponding .xxx stream to the same directory.

There are also music banks, also named .xxx each containing about 100-200 audio files. Some are complete music pieces, but most are short fragments, combining which you can compile music tracks, or loop them infinitely. Extract them with moha_music [music bank]

Then you can decode files with xas_decode [exa file]

Some files were 3-channel and 5-channel, which is strange, and some players don't play such files. 

This tool currently only support EA XAS format for this game, but later I plan to make it a universal XAS decoder.

Medal of Honor 2010

All sounds and music here contained in similar sound banks. They are not unreal packages anymore, you can extract sounds from them with moh_snb [bank file]

Some of them are external stream banks (those containing the word "stream"). These must be handled like explained before for Airborne game. For example, to extract Aud_MP_SoundRIOT_ui_stream_stb.xxx you need to run moh_snb Aud_MP_SoundRIOT_ui_stream.xxx and it will use headers from "...stream" and data from "...stream_stb"

After extracting the files you can convert them using xas_decode or ealayer3, depending on codec. There's no way to detect it automatically yet. Also ealayer3 is unable to detect their headers, so you need to use "-i 8" switch for most of files, and "-i 16" for files that have loops.
[moh_audio_extr.rar](https://xentaxbackup.github.io/file/9207_moh_audio_extr.rar)
## Post #2
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-21T13:25:10+00:00
- Post Title: Medal of Honor - audio extractor

For the Unreal Packages extractor, go see Gildor's website guys: [http://www.gildor.org](http://www.gildor.org)
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-21T13:32:29+00:00
- Post Title: Medal of Honor - audio extractor

> Reply from Vosvoy
>
> PS: I don't think you can post stream info file mate but I'm not 100% sure of that.

Ok, I removed them.
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-21T14:52:42+00:00
- Post Title: Medal of Honor - audio extractor

let me know when music is supported so i can test MOH reboot pc.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-21T15:26:58+00:00
- Post Title: Medal of Honor - audio extractor

> Reply from OrangeC
>
> let me know when music is supported so i can test MOH reboot pc.

The format in that "reboot" may be totally different, so you better send me a sample of its music bank.
## Post #6
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-21T15:30:56+00:00
- Post Title: Medal of Honor - audio extractor

I didn't know that Medal Of Honor 2010 was also called "Reboot". I was looking to test it too.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-21T17:51:09+00:00
- Post Title: Medal of Honor - audio extractor

I've got the music decoded. In each music bank there are about 100-200 audio files. Some are complete music pieces, but most are short fragments, combining which you can compile music tracks, or loop them infinitely. There must be some script in the game to do this, but currently I can't find it or analyze it. Anyway I think you can easily find what pieces do you need.

Tools updated.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-21T18:14:15+00:00
- Post Title: Medal of Honor - audio extractor

Here is a bank from moh 2010.

[https://mega.co.nz/#fm/wMUnSRLS](https://mega.co.nz/#fm/wMUnSRLS)
## Post #9
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-04-21T18:36:49+00:00
- Post Title: Medal of Honor - audio extractor

> Reply from daemon1
>
> I've got the music decoded. In each music bank there are about 100-200 audio files. Some are complete music pieces, but most are short fragments, combining which you can compile music tracks, or loop them infinitely.

I saw that in the Xbox360 version but it was very messy. Each samples didn't have the right sample rate and the loop was cut before the end. I'm happy you figured out.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-21T18:38:55+00:00
- Post Title: Medal of Honor - audio extractor

> Reply from Vosvoy
>
> I saw that in the Xbox360 version but it was very messy. Each samples didn't have the right sample rate and the loop was cut before the end. I'm happy you figured out.

Yes, if I combine these pieces one by one, can hear a perfect music file.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-22T08:57:16+00:00
- Post Title: Medal of Honor - audio extractor

The format in Medal of Honor 2010 reboot is similar, but different headers, and most sounds are in Ealayer3 version 5. Yet some are still in XAS. I can decode them all I think.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-17T13:12:36+00:00
- Post Title: Medal of Honor - audio extractor

Tools updated, Medal of Honor 2010 now supported.

Old airborne tools renamed.
## Post #13
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-05-23T03:24:19+00:00
- Post Title: Medal of Honor - audio extractor

incredible work daemon thank you so much for this tool. Works like a charm.
## Post #14
- Username: victor639514
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 01, 2015 1:33 am
- Post datetime: 2016-02-05T16:06:57+00:00
- Post Title: Medal of Honor - audio extractor

> There are some external stream banks, which is needed to decode big stream .xxx files, which are not UE packages, but just a raw data for XAS streams. These banks are all named "stream.SoundRiotRawAsset", but they are all just headers for different big streams. To unpack those, place the corresponding .xxx stream to the same directory.

Mind if I ask, which directory to be more specific?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-05T17:55:47+00:00
- Post Title: Medal of Honor - audio extractor

> Reply from victor639514
>
> There are some external stream banks, which is needed to decode big stream .xxx files, which are not UE packages, but just a raw data for XAS streams. These banks are all named "stream.SoundRiotRawAsset", but they are all just headers for different big streams. To unpack those, place the corresponding .xxx stream to the same directory.

Mind if I ask, which directory to be more specific?

It means that "stream.SoundRiotRawAsset" and the corresponding .xxx stream must be in the same directory to unpack it.
