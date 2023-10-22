## Post #1
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-11-24T09:24:14+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

Hello everyone!
I'm Happy to create pre-release topic for this game that possibly release in 10 December 2020.
This topic is about Cyberpunk 2077 game and extracting files from it.
I have pre-ordered this game and waiting for release since first trailer.
As game not released yet feel free post any rumors/thoughts/useful info for all forum members. 
All i know right now:
1.Game use REDengine 4
2.DRM Free version
3.(Rumor) someone already have PS4 version apk.

If anyone wanna help with creating export tools after release feel free use this topic to get useful info.
I'll update this topic with additional useful info when i get it.
Thank you for attention and keep well!

(Rumor) Here screenshot of apk file for PS4


UPD1: Release!
Here list of tools that recently added/updated by our greatest members  

Official BMS script by aluigi
[http://aluigi.org/bms/cyberpunk_2077.bms](http://aluigi.org/bms/cyberpunk_2077.bms)

rfuzzo updated cp77Tools to support decompression of extracted files from .archives.
Also included is a very experimental first read-only File viewer for some of the files (CR2W file format from CDPR).
[https://github.com/rfuzzo/CP77Tools/releases/tag/0.1.1](https://github.com/rfuzzo/CP77Tools/releases/tag/0.1.1)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-11-24T16:09:09+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

This PKG is encrypted?
## Post #3
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-11-30T07:40:27+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

> Reply from Ekey ↑Wed Nov 25, 2020 12:09 am at Wed Nov 25, 2020 12:09 am
>
> 
This PKG is encrypted?

Im not sure because everything i found in this 4ch topic is screenshot only. 
Another rumor that for some guys on PS4 Cyberpunk 2077 pre-load started on last Friday and total weight of files was 56GB
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-12-02T11:17:15+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

Developers have confirmed that in Cyberpunk 2077 there will be tools for modifications will avaible later after release
## Post #5
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2020-12-04T16:16:55+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

> Reply from Ekey ↑Wed Dec 02, 2020 7:17 pm at Wed Dec 02, 2020 7:17 pm
>
> 
Developers have confirmed that in Cyberpunk 2077 there will be tools for modifications will avaible later after release

Doesn't mean they'll give access to edit base files though.
## Post #6
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2020-12-07T15:20:05+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

This seems to be the container format. I did not find filenames yet not was i able to validate checksums, the compression etc. But its a start 
This is a 010 editor template.

```
    int64 unk1; // checksum?
    FILETIME fileTime;
    int unk2; // 0 1 2 5 6 - Maybe a type? Bitmask? Attributes?
    int unk3; // startDataChunk? file unique, starts where previous ended.
    int unk4; // endDataChunk?
    int unk5; // startUnk3? groups some files, ascending.
    int unk6; // endUnk3
    int unk7; // checksum?
    int unk8; // checksum?
    int unk9; // checksum?
    int unk10; // checksum?
    int unk11; // checksum?
};

struct DataChunk {
    int64 offset;
    int compressedSize;
    int uncompressedSize;

    local int64 pos = FTell();
    FSeek(offset);

    if (compressedSize == uncompressedSize)
       byte file[uncompressedSize];
    else
    {
        char KARK[4];
        int uncompressedSize;
        // File Data!
    }

    FSeek(pos);
};

struct FileSystem {
    int unk1; // 8
    int chunkSize;
    int64 unk2; // checksum?
    int numDataChunkGroups;
    int numDataChunks;
    int numUnk3;
    DataChunkGroup dataChunkGroup[numDataChunkGroups];
    DataChunk dataChunk[numDataChunks]<optimize=false>;
    int64 unk3[numUnk3]; // checksums? filenames? folders? paths?
};

struct Header {
    char RDAR[4];
    int version; // 12
    int64 fileSystemOffset;
    int64 fileSystemSize;
    int64 unk2; // 0
    int64 fileSize;
    int unk3[33]; // 0
};


Header header;
FSeek(header.fileSystemOffset);
FileSystem fileSystem;

```
## Post #7
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2020-12-07T16:10:44+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

[](https://funkyimg.com/i/39cuh.png)
Sample:
[http://sendfile.su/1586990](http://sendfile.su/1586990)
[https://mega.nz/file/fn4imDYT#F6Y8OF73G ... esPak_9C6w](https://mega.nz/file/fn4imDYT#F6Y8OF73GyiZ9Kz8qUbBFFhNiSWIM2AoVesPak_9C6w)
Signature: RDAR
## Post #8
- Username: karliky
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 26, 2012 7:46 pm
- Post datetime: 2020-12-07T17:18:48+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

Is KARK [4B 41 52 4B] the start of every entry?
## Post #9
- Username: derinhalil2015
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 11, 2019 4:23 am
- Post datetime: 2020-12-07T18:39:35+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

> Reply from Ekey ↑Wed Dec 02, 2020 7:17 pm at Wed Dec 02, 2020 7:17 pm
>
> 
Developers have confirmed that in Cyberpunk 2077 there will be tools for modifications will avaible later after release

What's your source on that?
## Post #10
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2020-12-08T01:10:22+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

I have started experimenting with the preload files and we have put together a basic extractor([https://github.com/rfuzzo/CP77Tools](https://github.com/rfuzzo/CP77Tools)).
We would like to integrate it in long term to our cdpr modding tool ([https://github.com/Traderain/Wolven-kit/issues/286](https://github.com/Traderain/Wolven-kit/issues/286))
## Post #11
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2020-12-08T03:07:05+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

Hmm it doesnt seem to work on the audio banks.
## Post #12
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2020-12-08T04:10:53+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

Oodle compress for KARK

```
get Version long
get offset_table longlong

goto offset_table

getdstring unk 16
get numChunk1 long
get numChunk2 long
get unk long
savepos OffsetChunk1
xmath sizeChunk1 "56*numChunk1"
getdstring Chunk1 sizeChunk1
savepos OffsetChunk2
goto OffsetChunk1
for j = 0 < numChunk1
	getdstring unk 20
	get startId long
	get endId long
	getdstring unk 28
	savepos OffsetChunk1Next
	set name string j
	string name + ".data"

	for i = startId < endId
		xmath OffsetCurrentId "OffsetChunk2 + i*16"
		goto OffsetCurrentId
		get offset longlong
		get zsize long
		get size long
		append
		if zsize == size
			log name offset zsize
		else
			goto offset
			idstring "KARK"
			GET size long
			math zsize - 8
			savepos offset_compressed
			comtype oodle
			clog name offset_compressed zsize size
		endif
		append
	next i
	goto OffsetChunk1Next
next j
```
## Post #13
- Username: rfuzzo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 08, 2020 3:02 pm
- Post datetime: 2020-12-08T07:04:54+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

here is a KAITAI ksy file for .archives
[https://gist.github.com/rfuzzo/2b4e366b ... ead5b36744](https://gist.github.com/rfuzzo/2b4e366b6551934337d804ead5b36744)

interesting are the three tables in the back. Not sure how to decompress KARK chunks yet (even though they don't look compressed actually)

does anyone have an oodle kraken decompression tool?
## Post #14
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2020-12-08T09:47:01+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

> Reply from rfuzzo ↑Tue Dec 08, 2020 3:04 pm at Tue Dec 08, 2020 3:04 pm
>
> does anyone have an oodle kraken decompression tool?
You should call decompress/compress functions from oo2core_"version"_win64.dll

[https://github.com/Crauzer/OodleSharp](https://github.com/Crauzer/OodleSharp)
[https://zenhax.com/viewtopic.php?t=7292](https://zenhax.com/viewtopic.php?t=7292)
## Post #15
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2020-12-08T13:33:22+00:00
- Post Title: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

Audio is Wwise WEM (RIFF). Can be decrypted by [ww2ogg](https://github.com/hcs64/ww2ogg). Video (bk2) is can be played by Rad Video Tools.
## Post #16
- Username: shade
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2020-12-08T17:02:26+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

Thanks, guys!
What about filenames?
And where game texts? )
---
Here music (RAW) to OGG to MP3 converter
[https://mega.nz/file/TvRCmLjS#bXmyMfLsr ... nfNYp2tHmA](https://mega.nz/file/TvRCmLjS#bXmyMfLsrV5arI-buBthCh1JKryqz-fLZnfNYp2tHmA)
## Post #17
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2020-12-08T18:16:55+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

> Reply from Haoose ↑Wed Dec 09, 2020 1:02 am at Wed Dec 09, 2020 1:02 am
>
> 
What about filenames?
And where game texts? )

It use some hash for file names just like Watch Dogs, Hitman, RE engine, etc.
So we must hook filenames. Maybe Ekey will do it.
## Post #18
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2020-12-08T18:36:24+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

Official BMS script by aluigi
[http://aluigi.org/bms/cyberpunk_2077.bms](http://aluigi.org/bms/cyberpunk_2077.bms)

Also would be great to see a fresh version of CR2WTools by rfuzzo
This not support this version of files.
[https://github.com/rfuzzo/CR2WTools](https://github.com/rfuzzo/CR2WTools)
## Post #19
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2020-12-08T19:08:47+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

How did you guys even open the files? Are you using the PS4 version or Steam one?
## Post #20
- Username: rfuzzo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 08, 2020 3:02 pm
- Post datetime: 2020-12-08T19:23:56+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

Hi!

I updated my cp77Tools to support decompression of extracted files from .archives.

Also included is a very experimental first read-only File viewer for some of the files (CR2W file format from CDPR).

[https://github.com/rfuzzo/CP77Tools/releases/tag/0.1.1](https://github.com/rfuzzo/CP77Tools/releases/tag/0.1.1)
## Post #21
- Username: rfuzzo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 08, 2020 3:02 pm
- Post datetime: 2020-12-08T19:31:20+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

> Reply from Haoose ↑Wed Dec 09, 2020 2:36 am at Wed Dec 09, 2020 2:36 am
>
> 
Also would be great to see a fresh version of CR2WTools by rfuzzo
This not support this version of files.
https://github.com/rfuzzo/CR2WTools

Most up-to date cr2w.dll for witcher 3 is found here: [https://github.com/Traderain/Wolven-kit ... enKit.CR2W](https://github.com/Traderain/Wolven-kit/tree/master/WolvenKit.CR2W)
And this is the repo we are actively devolping. The file format afaik is the same, but it seems that most classes are out of date, as well as new classes.
## Post #22
- Username: rfuzzo
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2020-12-08T20:04:54+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

> Reply from dimis9138 ↑Wed Dec 09, 2020 3:08 am at Wed Dec 09, 2020 3:08 am
>
> 
How did you guys even open the files? Are you using the PS4 version or Steam one?
GOG preload )
## Post #23
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2020-12-10T07:08:06+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

How can we deal with the .dat file or anyother type of files extracted from quickbms?
It will be nice if someone can make tools for this.
## Post #24
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2020-12-10T09:45:01+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

> Reply from cjdung ↑Thu Dec 10, 2020 3:08 pm at Thu Dec 10, 2020 3:08 pm
>
> 
How can we deal with the .dat file or anyother type of files extracted from quickbms?
It will be nice if someone can make tools for this.
[https://github.com/rfuzzo/CP77Tools](https://github.com/rfuzzo/CP77Tools)
## Post #25
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2020-12-10T16:53:13+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

I was able to decrypt the .dat files
[](https://ibb.co/52Zx8X2)

[https://zenhax.com/viewtopic.php?f=5&t=14572](https://zenhax.com/viewtopic.php?f=5&t=14572)

Need some kind of drop and drag ripper for the .dat files if possible.
## Post #26
- Username: rfuzzo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 08, 2020 3:02 pm
- Post datetime: 2020-12-10T16:58:42+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

> Reply from cjdung ↑Thu Dec 10, 2020 3:08 pm at Thu Dec 10, 2020 3:08 pm
>
> 
How can we deal with the .dat file or anyother type of files extracted from quickbms?
It will be nice if someone can make tools for this.

I updated my tools to extract archives with correct filenames and paths (almost all files).
[https://github.com/rfuzzo/CP77Tools/releases](https://github.com/rfuzzo/CP77Tools/releases)
## Post #27
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2020-12-11T14:55:46+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

Here's my hook for filenames.
If you want to contribute to [Cyberpunk 2077 modding tool](https://github.com/rfuzzo/CP77Tools), please use this.

[Download](https://discord.gg/NTA2t5GngV)

Currently missing filenames is about 50.000 / 600.000 knowed filenames.
You can download knowed filenames [here](https://github.com/rfuzzo/CP77Tools/tree/main/CP77Tools/Resources).
## Post #28
- Username: Synrvrer3
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 13, 2020 2:17 pm
- Post datetime: 2020-12-13T06:19:05+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

Is/ will there be a tutorial? I'd really like to get Johnny's model if possible
## Post #29
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-12-13T13:51:59+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

Second this.
## Post #30
- Username: spennser
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 30, 2016 1:12 pm
- Post datetime: 2020-12-14T05:19:59+00:00
- Post Title: Re: [ENG] [STEAM] Cyberpunk 2077 Pre-release

would this work for sound effects?
## Post #31
- Username: k1tteh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 20, 2017 9:26 pm
- Post datetime: 2020-12-17T22:23:58+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

so i've done some digging into the sound files, they're wwise's WEM files (glorified wav files from what i can tell). however, there are at least 3 different types (in audio_2_soundbanks.archive): some of them have a wFormatTag of 0x0001 (normal PCM), some are 0xFFFE (WAVE_EXTENSIBLE) and some are 0xFFFF (ogg vorbis, which isn't standard to microsoft's spec). 

the ones with 0xFFFF can be converted to vorbis using ww2ogg, and the other two can be converted using [WEMConverter](https://github.com/EtiTheSpirit/WEMConverter).
for some reason however some files have a riff/wav header, format tag for pcm but opus data (3DB1EB9C11E1A414.bin for example) and all the vorbis files don't even open in the official wwise tools, so 0xFFFF isn't standard to wwise either as it seems.

if that's not confusing enough some files aren't even sound files but something entirely different. even the ones with the same header have different contents, some have 0x48 long chunks that start with SMP2 (AC3BA5BDDAB3D92B.bin for example) and some others that make no sense to me at all (94D354EE54E0A03F.bin for example).

the file names might be different on other versions, these are from v1.04
maybe this helps someone
## Post #32
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-12-19T17:57:38+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

My project list (Multi-Language). Current state 1307466

```
audio_2_soundbanks.archive -> 2427 of 2751 (88%)
basegame_1_engine.archive -> 1541 of 1840 (83%)
basegame_2_mainmenu.archive -> 68 of 68 (100%)
basegame_3_nightcity.archive -> 122248 of 122502 (99%)
basegame_3_nightcity_gi.archive -> 22792 of 22792 (100%)
basegame_3_nightcity_terrain.archive -> 21257 of 21257 (100%)
basegame_4_animation.archive -> 4645 of 5221 (88%)
basegame_4_appearance.archive -> 1001 of 4597 (21%)
basegame_4_gamedata.archive -> 76536 of 120287 (63%)
basegame_5_video.archive -> 429 of 546 (78%)
lang_ar_text.archive -> 3222 of 3222 (100%)
lang_cs_text.archive -> 3222 of 3222 (100%)
lang_de_text.archive -> 3222 of 3222 (100%)
lang_de_voice.archive -> 90274 of 90769 (99%)
lang_en_text.archive -> 3222 of 3222 (100%)
lang_en_voice.archive -> 92544 of 92593 (99%)
lang_es-es_text.archive -> 3222 of 3222 (100%)
lang_es-es_voice.archive -> 90418 of 91784 (98%)
lang_es-mx_text.archive -> 3222 of 3222 (100%)
lang_fr_text.archive -> 3222 of 3222 (100%)
lang_fr_voice.archive -> 91858 of 91877 (99%)
lang_hu_text.archive -> 3222 of 3222 (100%)
lang_it_text.archive -> 3222 of 3222 (100%)
lang_it_voice.archive -> 90332 of 91461 (98%)
lang_ja_text.archive -> 3222 of 3222 (100%)
lang_ja_voice.archive -> 87807 of 87893 (99%)
lang_ko_text.archive -> 3222 of 3222 (100%)
lang_ko_voice.archive -> 87075 of 87382 (99%)
lang_pl_text.archive -> 3222 of 3222 (100%)
lang_pl_voice.archive -> 89417 of 91498 (97%)
lang_pt_text.archive -> 3222 of 3222 (100%)
lang_pt_voice.archive -> 90548 of 92141 (98%)
lang_ru_text.archive -> 3222 of 3222 (100%)
lang_ru_voice.archive -> 91923 of 91945 (99%)
lang_th_text.archive -> 3222 of 3222 (100%)
lang_tr_text.archive -> 3222 of 3222 (100%)
lang_zh-cn_text.archive -> 3222 of 3222 (100%)
lang_zh-cn_voice.archive -> 90371 of 90602 (99%)
lang_zh-tw_text.archive -> 3222 of 3222 (100%)
```

[Mirror 1](https://www49.zippyshare.com/v/d3r1DVKK/file.html)
[Mirror 2](https://dropmefiles.com/blM8f)
[Mirror 3](https://www.dropbox.com/s/xmdzclyfuc9v0wg/cp77_project_u1.rar?dl=0)
## Post #33
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-12-19T20:21:11+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

Thanks!
Do you know how convert it for cp77tools?
strings like this (how I can get hash?)
String,Hash
15002372041655897180.app,572357581749055550
1925576907472423714.app,3490732375385782047
2003268365561002008.app,2220310316197503567
9955918664674453963.app,8630345567418466109
base/weather/24h_basic/luts/hdri/cp2077_ar_hdr_acess_v001.xbm,8596959477450492744
base/weather/24h_basic/luts/hdri/cp2077_ar_v001.xbm,13642651560116929829

or I need use bms script?
## Post #34
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-12-19T22:04:29+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

@erik945 - This list will be merged soon > [https://github.com/WolvenKit/CP77Tools/issues/27](https://github.com/WolvenKit/CP77Tools/issues/27)
## Post #35
- Username: k1tteh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 20, 2017 9:26 pm
- Post datetime: 2020-12-23T18:49:02+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

> Reply from k1tteh ↑Fri Dec 18, 2020 6:23 am at Fri Dec 18, 2020 6:23 am
>
> some files have a riff/wav header, format tag for pcm but opus data (3DB1EB9C11E1A414.bin for example)
if anyone wants to write a script for these, one can identify these checking for a hex sequence of 4F 67 67 53 at 0x2C and turn them into a functional .opus file by removing everything before that
## Post #36
- Username: k1tteh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 20, 2017 9:26 pm
- Post datetime: 2020-12-29T15:24:36+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

i wrote a python script that splits the soundbanks into (mostly) usable opus files with proper names [you can get it here](https://mega.nz/file/pptURDrI#H48IHwwcjqSsjK8RkIEVL4Js2lnqko9Jsvicbk98s1U)
## Post #37
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-01-15T07:49:33+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

I've redrawn a couple of textures, does anyone know how to import a texture into the game?
## Post #38
- Username: Felldude
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 30, 2009 2:34 am
- Post datetime: 2021-01-25T10:44:54+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

> Reply from DENver666 ↑Fri Jan 15, 2021 3:49 pm at Fri Jan 15, 2021 3:49 pm
>
> 
I've redrawn a couple of textures, does anyone know how to import a texture into the game?

Did you extract with a quick BMS, I might have missed if someone posted one. * I found the bms but not sure where your getting textures from*

I can tell you a long..long time ago the method I used to "trick" the first witcher game (By CD REd) was simply to place the texture in the same folder as the archive called for.

As I was looking at the Ram in a memory viewer I noticed some of the texures seem to have folder locations identified. Example:

base\materials\mesh_decal_blendable.mt�base\characters\main_npc\silverhand\textures\t0_001_ma_body__silverhand_tattoo_d01.xbm 

Others seem to have either header info possibly.
## Post #39
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-01-26T03:56:47+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

> Reply from Felldude ↑Mon Jan 25, 2021 6:44 pm at Mon Jan 25, 2021 6:44 pm
>
> 
DENver666 wrote: ↑Fri Jan 15, 2021 3:49 pm
I've redrawn a couple of textures, does anyone know how to import a texture into the game?


Did you extract with a quick BMS, I might have missed if someone posted one. * I found the bms but not sure where your getting textures from*

I can tell you a long..long time ago the method I used to "trick" the first witcher game (By CD REd) was simply to place the texture in the same folder as the archive called for.

As I was looking at the Ram in a memory viewer I noticed some of the texures seem to have folder locations identified. Example:

base\materials\mesh_decal_blendable.mt�base\characters\main_npc\silverhand\textures\t0_001_ma_body__silverhand_tattoo_d01.xbm 

Others seem to have either header info possibly.

I extract textures thanks to the cp77tools utility, but I don't understand how to push the changed texture back so that it works in the game.
## Post #40
- Username: Felldude
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 30, 2009 2:34 am
- Post datetime: 2021-01-26T12:46:33+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

> Reply from DENver666 ↑Fri Jan 15, 2021 3:49 pm at Fri Jan 15, 2021 3:49 pm
>
> 
I extract textures thanks to the cp77tools utility, but I don't understand how to push the changed texture back so that it works in the game.

Ok I am playing with the CP77tools it seems to have a pack feature, I would think you would have to repackage the whole file. Experimenting now.

*Edit* I tried to unpack, and then repack an archive without making changes or uncooking it. I had no errors or missing files on the extract or the compress but the game crashes before loading the start screen.
## Post #41
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-01-27T07:23:41+00:00
- Post Title: Re: [RELEASE] [ENG] [STEAM] Cyberpunk 2077

The developers have released the official modding toolkit for unpacking and packing textures. I think now it will trample.
