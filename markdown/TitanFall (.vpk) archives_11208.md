## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-15T10:02:21+00:00
- Post Title: TitanFall (.vpk) archives

TitanFall

.VPK archives hold the game assets

```
{
	int32 m_nHeaderMarker;
	int32 m_nVersion;
	int32 m_nDirectorySize;
	int32 m_nEmbeddedChunkSize;
	int32 m_nChunkHashesSize;
	int32 m_nSelfHashesSize;
	int32 m_nSignatureSize;

	VPKDirHeader_t( void )
	{
		m_nHeaderMarker = VPK_HEADER_MARKER;
		m_nVersion = VPK_CURRENT_VERSION;
		m_nDirectorySize = 0;
		m_nEmbeddedChunkSize = 0;
		m_nChunkHashesSize = 0;
		m_nSelfHashesSize = 0;
		m_nSignatureSize = 0;
	}

};

```


The _dir.vpk files seem to have no compression however the contents do.


Tool Release


[](http://cra0kalo.com/public/Titanfall_VPKTool3_Portable.zip)
[](http://cra0kalo.com/public/Titanfall_VPKTool3_Installer.zip)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-15T12:23:21+00:00
- Post Title: TitanFall (.vpk) archives

Share link for download client.
## Post #3
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-02-15T21:08:01+00:00
- Post Title: TitanFall (.vpk) archives

after installing (running through the audio decompression phase) the 8gb vpk holds the sounds as raw big endian riff data. that's as much as I can figure out.
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2014-02-16T02:44:49+00:00
- Post Title: TitanFall (.vpk) archives

I did some digging and found that the compression it uses is [lzham](http://code.google.com/p/lzham/) Alpha 8 (you need to get it from svn). Set the dictionary size to 20. Some files aren't compressed (e.g. audio tracks).
## Post #5
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-17T05:01:41+00:00
- Post Title: TitanFall (.vpk) archives

So nice that op and other ones are lookin into this game ! I tried your program just to look around, if we are lucky depinding on your extract/pack/unpack additions we can change scripts, modify models, change the ai, many other things 
Its built on the source engine, heavly modified but that means models, and script will work
## Post #6
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-17T09:49:09+00:00
- Post Title: TitanFall (.vpk) archives

> Reply from Zench
>
> I did some digging and found that the compression it uses is lzham Alpha 8 (you need to get it from svn). Set the dictionary size to 20. Some files aren't compressed (e.g. audio tracks).

Hey I tried using

```

```


with the uncompressed size/compressed size/dictionary size and it returns 4 as the error. Could you explain how you tried it
## Post #7
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2014-02-18T04:16:58+00:00
- Post Title: TitanFall (.vpk) archives

I actually just modified lzhamtest as a quick hack to make sure it was working. The function you're using should work just fine. Error code 4 means it failed to initialize the decompressor state, and it looks like the only way this can happen is if the params struct (called options in your screenshot) is wrong. I would check that.
## Post #8
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-18T05:24:06+00:00
- Post Title: TitanFall (.vpk) archives

> Reply from Zench
>
> I actually just modified lzhamtest as a quick hack to make sure it was working. The function you're using should work just fine. Error code 4 means it failed to initialize the decompressor state, and it looks like the only way this can happen is if the params struct (called options in your screenshot) is wrong. I would check that.

Zench do you mean you are able to extract files from the packages with that hack ? :
## Post #9
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2014-02-18T05:35:28+00:00
- Post Title: TitanFall (.vpk) archives

> Reply from kalleoskar
>
> Zench do you mean you are able to extract files from the packages with that hack ? :Yes, I tested it out on a couple files. It's not really automated; instead of making it myself I figured cra0 could add it to his nice looking tool. Repacking is technically possible but probably wouldn't let you play online.
## Post #10
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-18T06:18:00+00:00
- Post Title: TitanFall (.vpk) archives

Unexpected good newsa  I was thinking about porting the mechs cockpits to kerbal space program haha, been modding that game for a while, i think they would fit, esp with an robot parts mod that exits.
Cheers for trying things out =)
## Post #11
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-18T10:20:14+00:00
- Post Title: TitanFall (.vpk) archives

-EDIT-

Ok all fixed actually   

will update tool in a day or so sit tight!
## Post #12
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-18T21:53:59+00:00
- Post Title: TitanFall (.vpk) archives

Cool man!!!
## Post #13
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2014-02-19T03:29:00+00:00
- Post Title: TitanFall (.vpk) archives

You awesome cra0. So, This program can extract all files in one click? Because I hate to select one-by-one for extract.
## Post #14
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2014-02-19T05:06:33+00:00
- Post Title: TitanFall (.vpk) archives

Woot! Great job cra0!
## Post #15
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-19T16:06:00+00:00
- Post Title: TitanFall (.vpk) archives

Look forward of trying the upcoming update, thank you
## Post #16
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2014-02-20T19:54:59+00:00
- Post Title: Re: TitanFall (.vpk) archives

Nice, great and speedy work there, looking forward to the updated tool
## Post #17
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-21T10:41:56+00:00
- Post Title: Re: TitanFall (.vpk) archives

Beta over now,hows the progress
## Post #18
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2014-02-21T18:19:12+00:00
- Post Title: Re: TitanFall (.vpk) archives

I made tool, that used game engine to extract files.

1. Copy to game directory.
2. Run UnVpk.exe and Alt+Tab to console window.
3. Look at "output" directory.
[UnVpk.zip](https://xentaxbackup.github.io/file/7033_UnVpk.zip)
## Post #19
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-22T04:21:40+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from kalleoskar
>
> Beta over now,hows the progress
Public beta release


Download
[http://cra0kalo.com/public/Titanfall_VPKTool2.zip](http://cra0kalo.com/public/Titanfall_VPKTool2.zip)
## Post #20
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2014-02-22T10:28:44+00:00
- Post Title: Re: TitanFall (.vpk) archives

Whoops thought it wasnt working but it was because I didn't click the *_dir.vpk file - clicked the main vpk files.

AWESOME work!  

Anyone have an idea whats up with the sound files?

Also, noob question, is there any software that will load up the models? I cant seem to get it to come up in Noesis and Source SDK seems like a no go?
## Post #21
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-22T17:43:10+00:00
- Post Title: Re: TitanFall (.vpk) archives

Thanks for both of the tools! Hm i havnt tried t´but the model files can bbe encrypted, will try some things later
## Post #22
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-23T00:17:18+00:00
- Post Title: Re: TitanFall (.vpk) archives

So after trying some things the model files wont decompile properly beacuse the texture files are missing, i suspect those files is in one of the vpk file we cant acces yet
## Post #23
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2014-02-23T02:01:38+00:00
- Post Title: Re: TitanFall (.vpk) archives

Pretty sure the textures are in the materials/models folders within the same VPKs as the models they belong to.  

For example:
models/titans/atlas has the mdl, while materials/models/titans/atlas has the textures
models/humans have the mdl files, while materials/models/humans have the textures
## Post #24
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-23T03:39:27+00:00
- Post Title: Re: TitanFall (.vpk) archives

Yupp, it was an error on the decompiler part  They are doing titanfall compatiable ton it asap
## Post #25
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2014-02-23T06:18:37+00:00
- Post Title: Re: TitanFall (.vpk) archives

Hmm if anyone finds the cockpit mesh give me a heads up  To bad we cant host titanfall beat ourselves, there are alot of settings for the ai bots in scripts and etc

Haha it works  
cra0kalo posted:
Hehe you can just rename .dx11 to .dx90 as a quick hack fix only works for some models 
 till the crowbar is updated:)
## Post #26
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-02T19:53:03+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from kalleoskar
>
> Hmm if anyone finds the cockpit mesh give me a heads up  To bad we cant host titanfall beat ourselves, there are alot of settings for the ai bots in scripts and etc

Haha it works  
cra0kalo posted:
Hehe you can just rename .dx11 to .dx90 as a quick hack fix only works for some models 
 till the crowbar is updated:)
Crowbar should now decompile the animations and model data fine. On a side note im working on repackaging support and vtf patching
## Post #27
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-08T15:02:12+00:00
- Post Title: Re: TitanFall (.vpk) archives

Titanfall .WAV audio files are just headerless I made my tool slap on a RIFF header but not all of them have 

samplerate: 44100
bitrate: 16
channel: 2


the headers are missing or obfuscated or something I have no idea.



some files here if someone wants to take a look

[https://dl.dropboxusercontent.com/u/107 ... udioSam.7z](https://dl.dropboxusercontent.com/u/10798900/DUMPBOX/audioSam.7z)
## Post #28
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-03-09T22:29:40+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from cra0
>
> Titanfall .WAV audio files are just headerless I made my tool slap on a RIFF header but not all of them have 

samplerate: 44100
bitrate: 16
channel: 2


the headers are missing or obfuscated or something I have no idea.



some files here if someone wants to take a look

https://dl.dropboxusercontent.com/u/107 ... udioSam.7z

Alot of the multichannel files indicate the channels in the file name, atleast for weapon sound effects. Also, there is an audible pop before the actual audio data, which my best guess is where it is, in some form.

Here's what I can see clearly:
CB starting header, BC ending footer, and those bytes in the header seem important, but I cant relate them to the files in a clear way.
## Post #29
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-09T22:47:41+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from Pepper
>
> cra0 wrote:Titanfall .WAV audio files are just headerless I made my tool slap on a RIFF header but not all of them have 

samplerate: 44100
bitrate: 16
channel: 2


the headers are missing or obfuscated or something I have no idea.



some files here if someone wants to take a look

https://dl.dropboxusercontent.com/u/107 ... udioSam.7z

Alot of the multichannel files indicate the channels in the file name, atleast for weapon sound effects. Also, there is an audible pop before the actual audio data, which my best guess is where it is, in some form.

Here's what I can see clearly:
CB starting header, BC ending footer, and those bytes in the header seem important, but I cant relate them to the files in a clear way.

maybe the headers are cached in a like audiocache.bin file ill keep looking.
## Post #30
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2014-03-10T03:07:00+00:00
- Post Title: Re: TitanFall (.vpk) archives

noob question, but why do some of my human faces look like they have pieces of their face shooting out in SFM?
## Post #31
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-03-10T20:07:09+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from cra0
>
> Pepper wrote:cra0 wrote:Titanfall .WAV audio files are just headerless I made my tool slap on a RIFF header but not all of them have 

samplerate: 44100
bitrate: 16
channel: 2


the headers are missing or obfuscated or something I have no idea.



some files here if someone wants to take a look

https://dl.dropboxusercontent.com/u/107 ... udioSam.7z

Alot of the multichannel files indicate the channels in the file name, atleast for weapon sound effects. Also, there is an audible pop before the actual audio data, which my best guess is where it is, in some form.

Here's what I can see clearly:
CB starting header, BC ending footer, and those bytes in the header seem important, but I cant relate them to the files in a clear way.

maybe the headers are cached in a like audiocache.bin file ill keep looking.

wav.acache might have some clues. seems to list each file name along with a good bit of data after that, it might just be their implementation of source's .2 second for each file sound cache system though. it's in the root of the sound directory.
## Post #32
- Username: ulukai
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 23, 2009 2:59 am
- Post datetime: 2014-03-18T02:01:19+00:00
- Post Title: Re: TitanFall (.vpk) archives

Well for my part i've been able to extract vtf file from vpk, many thx for the vpk extracting tool   

Then with VTF edit i've been able to extract the texture, modify the Militia character with Desert Tiger Strip Camo and put it back in VTF.

Now how do i put the vtf file back to the vpk file
## Post #33
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-19T06:25:14+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from Pepper
>
> wav.acache might have some clues. seems to list each file name along with a good bit of data after that, it might just be their implementation of source's .2 second for each file sound cache system though. it's in the root of the sound directory.

Yeah I attempted to reverse acache I found the channel number and theres some unknown data here is a dump of the mp_common wavs

[https://www.dropbox.com/s/0vpj6bs0k0f039u/Structure.zip](https://www.dropbox.com/s/0vpj6bs0k0f039u/Structure.zip)


```
{

uint32 headerVer? 3
uint32 unk1 17900
uint32 unk2 0
}
	
	
struct Entries_Acache
{
asciiz path2File
byte[189] BLOATdata
uint32 unk1
uint32 unk2
uint32 channels
uint32 unk3
uint32 unk4
uint32 unk5
uint32 unk6
uint32 unk7
uint32 unk8
}

```



unk5 i think is the sample rate but it's not here are some matches i found though
4140 = 44100
4176 = ?
2092 = 22050
2128 = ??
5120 = ??
12332 = ??
12368 = ??


> Reply from ulukai
>
> Well for my part i've been able to extract vtf file from vpk, many thx for the vpk extracting tool   

Then with VTF edit i've been able to extract the texture, modify the Militia character with Desert Tiger Strip Camo and put it back in VTF.

Now how do i put the vtf file back to the vpk file
Repack support next update very soon
## Post #34
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-03-19T13:53:42+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from cra0
>
> Pepper wrote:wav.acache might have some clues. seems to list each file name along with a good bit of data after that, it might just be their implementation of source's .2 second for each file sound cache system though. it's in the root of the sound directory.

Yeah I attempted to reverse acache I found the channel number and theres some unknown data here is a dump of the mp_common wavs

https://www.dropbox.com/s/0vpj6bs0k0f039u/Structure.zip

Code: Select allstruct Headt_Acache
{

uint32 headerVer? 3
uint32 unk1 17900
uint32 unk2 0
}
	
	
struct Entries_Acache
{
asciiz path2File
byte[189] BLOATdata
uint32 unk1
uint32 unk2
uint32 channels
uint32 unk3
uint32 unk4
uint32 unk5
uint32 unk6
uint32 unk7
uint32 unk8
}



unk5 i think is the sample rate but it's not here are some matches i found though
4140 = 44100
4176 = ?
2092 = 22050
2128 = ??
5120 = ??
12332 = ??
12368 = ??

ulukai wrote:Well for my part i've been able to extract vtf file from vpk, many thx for the vpk extracting tool   

Then with VTF edit i've been able to extract the texture, modify the Militia character with Desert Tiger Strip Camo and put it back in VTF.

Now how do i put the vtf file back to the vpk file  
Repack support next update very soon
seems like that 5th unknown might also be dependent on channel count.

4140=44khz stereo
4176=48khz stereo
2092=44khz mono
2128=48khz mono
5120=? seems to be stereo but sample rate falls within normal 48khz for me
12332=44khz six channel
12368=48khz six channel

This is just what I can gather from the listing and the files themselves.
## Post #35
- Username: ulukai
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 23, 2009 2:59 am
- Post datetime: 2014-03-19T21:59:25+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from ulukai
>
> Well for my part i've been able to extract vtf file from vpk, many thx for the vpk extracting tool   

Then with VTF edit i've been able to extract the texture, modify the Militia character with Desert Tiger Strip Camo and put it back in VTF.

Now how do i put the vtf file back to the vpk file
Repack support next update very soon



Ah nice thx
## Post #36
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-23T06:09:57+00:00
- Post Title: Re: TitanFall (.vpk) archives

Ok Sounds all checked and working
## Post #37
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2014-04-03T10:23:52+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from m0xf
>
> I made tool, that used game engine to extract files.

1. Copy to game directory.
2. Run UnVpk.exe and Alt+Tab to console window.
3. Look at "output" directory.

This tool got crashed after extracting 19.6 GB data.
My system is i7 3.5 GHz, 32 GB ram, 64 bit windows8 os, and the harddrive where I am extracting has more than 1TB free space.

Is anybody having the same problem?
## Post #38
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-04-06T00:57:10+00:00
- Post Title: Re: TitanFall (.vpk) archives

Latest update is great, just 6channel files play way too fast khz compared to ingame. the crb101 (standard carbine) sounds like a minigun at 88.2khz i think it sounds right at 48/44.
## Post #39
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2014-04-07T16:51:15+00:00
- Post Title: Re: TitanFall (.vpk) archives

Titanfall VPK Tool by cra0 is working great. 

Another question is, is there any way to import animation from the mdl files.
## Post #40
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-04-09T06:59:05+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from blackfoxeye
>
> Titanfall VPK Tool by cra0 is working great. 

Another question is, is there any way to import animation from the mdl files.
Yes decompile them using crowbar and import the smd files
## Post #41
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-04-09T07:02:44+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from Pepper
>
> Latest update is great, just 6channel files play way too fast khz compared to ingame. the crb101 (standard carbine) sounds like a minigun at 88.2khz i think it sounds right at 48/44.
Will take a look at those can you suggest some file names
## Post #42
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2014-04-09T18:25:01+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from cra0
>
> blackfoxeye wrote:Titanfall VPK Tool by cra0 is working great. 

Another question is, is there any way to import animation from the mdl files.
Yes decompile them using crowbar and import the smd files

I tried, but crowbar says "SKIPPING ANI FILE BECAUSE NOT SUPPORTED YET."
## Post #43
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-04-10T17:03:34+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from cra0
>
> Pepper wrote:Latest update is great, just 6channel files play way too fast khz compared to ingame. the crb101 (standard carbine) sounds like a minigun at 88.2khz i think it sounds right at 48/44.
Will take a look at those can you suggest some file names
"...\sound\weapons\cbr101\wpn_cbr101_1p_wpnfire_loop_core_6ch_v2_01.wav"

playback rate compared to ingame, or 2channel file is wrong, see:

"...\sound\weapons\cbr101\wpn_cbr101_3p_wpnfire_burst_close_2ch_v2_01.wav"

for appropriate speed. tons of the 6channel files i found are at wrong speed.

even
"...\sound\campaign\angelcity\angelcity_scr_imcintro_dropshipflyinamb_6ch_v2_01.wav"

is actually an almost 25 second sequence in game.
## Post #44
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-04-19T06:35:41+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from Pepper
>
> cra0 wrote:Pepper wrote:Latest update is great, just 6channel files play way too fast khz compared to ingame. the crb101 (standard carbine) sounds like a minigun at 88.2khz i think it sounds right at 48/44.
Will take a look at those can you suggest some file names
"...\sound\weapons\cbr101\wpn_cbr101_1p_wpnfire_loop_core_6ch_v2_01.wav"

playback rate compared to ingame, or 2channel file is wrong, see:

"...\sound\weapons\cbr101\wpn_cbr101_3p_wpnfire_burst_close_2ch_v2_01.wav"

for appropriate speed. tons of the 6channel files i found are at wrong speed.

even
"...\sound\campaign\angelcity\angelcity_scr_imcintro_dropshipflyinamb_6ch_v2_01.wav"

is actually an almost 25 second sequence in game.

Dam forgot to post 3.2 update here

```
-Fixed extraction of the root elements showing up in a folder called RootDir
-Reworked repacker once again (added compression option SLOW!)
-Optimized repacking code (faster CRC32 calculation) (Repacks a LOT faster)
-Removed check of filesizes in repacker
-Added Debug log generation for repacking
-Updated sound lookup table (should fix all 6ch sounds)

```

Download:
[http://cra0kalo.com/public/Titanfall_VP ... rtable.zip](http://cra0kalo.com/public/Titanfall_VPKTool3.2_Portable.zip)
Update:
Help>Check for updates

Repacking is way faster now
## Post #45
- Username: BioLife
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 24, 2012 2:54 am
- Post datetime: 2014-06-19T20:47:05+00:00
- Post Title: Re: TitanFall (.vpk) archives

Hello,

Thank you cra0 for this awesome tool!

Repacker seem to repack ALL the VPK into one VPK (~22gb). Is there any way to repack only the originaly unpacked VPK?

Thank you
## Post #46
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-22T06:43:03+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from BioLife
>
> Hello,

Thank you cra0 for this awesome tool!

Repacker seem to repack ALL the VPK into one VPK (~22gb). Is there any way to repack only the originaly unpacked VPK?

Thank you

tick compress checkbox should produce the same sized vpk
## Post #47
- Username: BioLife
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 24, 2012 2:54 am
- Post datetime: 2014-07-12T17:13:45+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from cra0
>
> 
tick compress checkbox should produce the same sized vpk

I've tried that, but its doesn't work as expected...

How the extraction and repack are working? If we select for extraction a _dir.vpk file, how can we repack that same _dir.vpk file with some mod? because actually the repack tool repack everything listed in _dir.vpk file, right?
## Post #48
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-07-12T18:56:09+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from BioLife
>
> cra0 wrote:
tick compress checkbox should produce the same sized vpk

I've tried that, but its doesn't work as expected...

How the extraction and repack are working? If we select for extraction a _dir.vpk file, how can we repack that same _dir.vpk file with some mod? because actually the repack tool repack everything listed in _dir.vpk file, right?
Yes that is correct. The next version of the vpk tool will support .bpk archives from the xbox360 version of the game along with a new tool called the ROM Repacker

Basically what the ROM repacker does is firstly ask for a vpk you wish to repack than you supply files which you would like packed into that existing vpk and it will override the vpk if the folder you supply contains files already present in the vpk. If the files are not present it will just append to the vpk. This makes modding a lot easier because you dont have to repack e entire archive to mod the game. Additionally there will be an option to revert changes from a vpk so no need to backup the vpk your modding especially the main one which is like 12gb. Look forward to the update!
## Post #49
- Username: BioLife
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 24, 2012 2:54 am
- Post datetime: 2014-07-12T21:13:14+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from cra0
>
> 
..... Look forward to the update!

Oh nice! I'll look forward!
## Post #50
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-08-02T16:52:02+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from BioLife
>
> cra0 wrote:
..... Look forward to the update!  

Oh nice! I'll look forward!

Quick update before that fixes all those audio problems people had   

```
-Fixed extract all dialog window saving incorrect folder path location.
-Fixed issue with application settings save
-Removed debug SelectedPath/InitialDirectory constants
-Implemented additional audio patcher (fixes extraction errors for good!)

```

[http://dev.cra0kalo.com/?p=137](http://dev.cra0kalo.com/?p=137)
## Post #51
- Username: ThaWhiteMexicant
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 07, 2014 5:32 pm
- Post datetime: 2014-12-07T09:37:05+00:00
- Post Title: Re: TitanFall (.vpk) archives

so im getting this error (got the same one for Intel gpa) and i cannot find the fix. Any suggestions?
[Capture2.PNG](https://xentaxbackup.github.io/file/8211_Capture2.PNG)
## Post #52
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-12-07T11:35:31+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from ThaWhiteMexicant
>
> so im getting this error (got the same one for Intel gpa) and i cannot find the fix. Any suggestions?
Make sure you have the latest NET frameworks installed (4.5)

Also let me update and ask if ANYONE wishes to help me decipher the BSP lumps present in Titanfall feel free to contact me

Here is what I've been working on
## Post #53
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2017-06-03T09:22:40+00:00
- Post Title: Re: TitanFall (.vpk) archives

So I've been trying to extract one of these .vpk files but am having some trouble.
This is what I have as the directory entry format.

```
	{
		unsigned __int32 iCRC32;
		unsigned __int16 iUnknown2;
		unsigned __int16 iArchiveIndex;
		unsigned __int16 iUnknown3;
		unsigned __int32 iUnknown4;
		unsigned __int32 iEntryOffset;
		unsigned __int32 iUnknown6;
		unsigned __int32 iEntryLength;
		unsigned __int32 iUnknown7;
		unsigned __int32 iFileSize; // uncompressed
		unsigned __int32 iUnknown8;
	};
```

iArchiveIndex is which _00x.vpk archive file the data is in, iEntryOffset is the offset into the archive, iEntryLength is the compressed data size and iFileSize is the uncompressed data size.
Some seem to have some extra data at the end which I haven't investigated yet.

My params for decompression are:

```
memset(&decomp_params, 0, sizeof(decomp_params));
decomp_params.m_struct_size = sizeof(decomp_params);
decomp_params.m_dict_size_log2 = 20;

```

I'm calling lzham::lzham_lib_decompress_memory (lzham_decompress_memory just passes through to it) - dest buf is iFileSize, src buf is iEntryLength.
I'm getting 3 as the return value (LZHAM_DECOMP_STATUS_SUCCESS) but the dest buf is just full of 0xCD (freshly malloced memory). Is there something wrong with what I'm doing? Is dest buf where the uncompressed data gets returned?
## Post #54
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2019-02-07T11:14:24+00:00
- Post Title: Re: TitanFall (.vpk) archives

Anyone tryed using lzham as a .dll or otherwise?
## Post #55
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2019-02-08T13:01:37+00:00
- Post Title: Re: TitanFall (.vpk) archives

Alright I got a bit further - the trick was to use an outdated version of lzham ([https://code.google.com/archive/p/lzham ... ult/source](https://code.google.com/archive/p/lzham/source/default/source)), not the latest version on GitHub.
So now I've mostly got stuff working but there are a few files that return errors 7, 9 and 14.
## Post #56
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2019-02-09T05:06:34+00:00
- Post Title: Re: TitanFall (.vpk) archives

And I think I've figured out the last problem - most but not all of the files are compressed - those with compressed size equal to uncompressed size are just raw data.
## Post #57
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2020-12-22T22:37:50+00:00
- Post Title: Re: TitanFall (.vpk) archives

And now I have a working extractor: [https://www.moddb.com/games/half-life/d ... gssmt-v004](https://www.moddb.com/games/half-life/downloads/gssmt-v004)
## Post #58
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-02T00:11:02+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from tschumann ↑Wed Dec 23, 2020 6:37 am at Wed Dec 23, 2020 6:37 am
>
> 
And now I have a working extractor: https://www.moddb.com/games/half-life/d ... gssmt-v004
Thanks for this nice tool, unfortunately, every time i want to extract any file at all from Titanfall1 it just crashes with out any output error, and i only see in the log file/folder structure with no output files extracted at all, you can see how it ends at the end in following example:

```

File: englishclient_mp_airbase.bsp.pak000_dir.vpk
Size: 330095 bytes

General information
===================
Magic Number: 1437209140
Version: 2.3
Directory tree size: 330079 bytes
Files
=====
---------------------------------------------------------------
materials/correction/airbase.raw
materials/correction/mp_fracture_main01.raw
models/robots/marvin/marvin_no_jiggle.phy
models/angel_city/box_small_01.phy
models/angel_city/box_small_02.phy
models/barriers/metal_parking_post_yell.phy
models/furniture/office_desk_accessories_papers.phy
models/furniture/chair_anim_prop.phy
models/furniture/chair_45angle_metal.phy
models/commercial/desk_lamp.phy
models/vehicle/mobile_turret/gun_mount_bottom.phy
models/holo_screens/holo_screen_wallshape.phy
models/signs/billboard_fracture/billboard_fracture_frame_3.phy
models/communication/radar_tower_imc_01.phy
models/domestic/working_floor_light_on.phy
models/domestic/working_floor_light.phy
models/domestic/wall_panel_fiberglass_corner.phy
models/metal_scraps/scrap_metal_vent02.phy
models/metal_scraps/scrap_metal_hinge02.phy
models/signs/billboard_supports01.phy
models/hardware/paint_container_plastic.phy
models/hardware/paint_spraycan_closed.phy
models/stairs/stairs_imc01_single.phy
models/stairs/stair_base_modular_imc_01.phy
models/stairs/stair_base_modular_imc_02.phy
models/stairs/stairs_imc01_support_slope10.phy
models/stairs/stair_base_modular_imc_03.phy
models/stairs/stair_base_modular_imc_04.phy
models/weapons/drums/triplethreat_drum.phy
models/weapons/drums/xo_16_drum.phy
models/weapons/drums/titan_rocket_launcher_drum.phy
models/containers/crate_blue_plastic.phy
models/containers/pelican_case_large.phy
models/containers/pelican_case_large_drabgreen.phy
models/containers/box_med_plastic.phy
models/containers/box_large_plastic.phy
models/containers/box_metal.phy
models/containers/styrofoam_box_dirty.phy
models/containers/styrofoam_box_short_dirty.phy
models/containers/box_small_cardboard.phy
models/containers/box_large_cardboard.phy
models/containers/box_shrinkwrapped.phy
models/containers/box_med_cardboard_01.phy
models/containers/box_med_cardboard_02.phy
models/containers/gas_tank.phy
models/containers/plastic_pallet_02.phy
models/containers/plastic_pallet_01.phy
models/containers/crate_orange_plastic.phy
models/containers/box_med_cardboard_03.phy
models/containers/pelican_case_ammobox.phy
models/containers/pelican_case_large_open_drabgreen.phy
models/containers/pelican_case_large_open.phy
models/containers/barrel.phy
models/containers/barrel_explosive.phy
models/containers/cargo_container_grey_orange_teal_combined.phy
models/containers/cargo_container_red_black_blue_combined.phy
models/containers/cargo_container_black_separate.phy
models/containers/cargo_container_orange_separate.phy
models/containers/cargo_container_teal_separate.phy
models/containers/cargo_container_white_separate.phy
models/containers/cargo_container_grey_separate.phy
models/containers/cargo_container_blue_separate.phy
models/containers/cargo_container_red_separate.phy
models/door/door_imc_interior_03_128.phy
models/door/bunker_door_frame_96x120.phy
models/door/pod_door_hangar_imc_01.phy
models/door/pod_door_hangar_imc_01_open.phy
models/door/door_imc_interior_03_128_frame.phy
models/door/door_imc_interior_64_frame.phy
models/weapons/ammoboxes/ammobox_missle.phy
models/weapons/ammoboxes/ammobox_01.phy
models/weapons/ammoboxes/ammobox_bigclip.phy
models/weapons/ammoboxes/ammobox_bigbullet.phy
models/weapons/ammoboxes/ammo_backpacks.phy
models/weapons/ammoboxes/backpack_single.phy
models/pipes/airduct_xl_vent.phy
models/pipes/pipe_ceiling_gray_set.phy
models/pipes/pipes_wall_02.phy
models/pipes/pipes_wall_01.phy
models/pipes/pipe_refinery_port.phy
models/pipes/pipe_refinery_section80.phy
models/pipes/pipe_refinery_section128.phy
models/pipes/pipe_refinery_cap.phy
models/pipes/pipe_refinery_frame.phy
models/pipes/duct_round_straight.phy
models/pipes/duct_round_elbow_90.phy
models/pipes/duct_round_straight_45.phy
models/signs/signage_plates_metal/sign_plate_a.phy
models/signs/signage_plates_metal/sign_plate_c.phy
models/signs/signage_plates_metal/sign_plate_b.phy
models/signs/signage_plates_metal/sign_plate_d.phy
models/signs/signage_plates_metal/sign_post_plate_h.phy
models/signs/signage_plates_metal/sign_post_plate_b.phy
models/signs/signage_plates_metal/sign_post_plate_d.phy
models/signs/signage_plates_metal/sign_post_plate_e.phy
models/signs/signage_plates_metal/sign_post_plate_a.phy
models/signs/signage_plates_metal/sign_post_plate_c.phy
models/handrails/railing_industrial_normal.phy
models/handrails/railing_imc_post.phy
models/handrails/handrail_yellow_end.phy
models/handrails/railing_imc_banister_top_slope10.phy
models/handrails/railing_imc_banister_bottom_slope10.phy
models/handrails/railing_imc_32in.phy
models/handrails/railing_imc_64in.phy
models/handrails/railing_imc_16in.phy
models/handrails/railing_imc_banister_long_slope10.phy
models/handrails/railing_imc_banister_short_slope10.phy
models/handrails/handrail_yellow_32.phy
models/handrails/handrail_yellow_48.phy
models/handrails/handrail_yellow_64.phy
models/handrails/handrail_yellow_corner90.phy
models/handrails/handrail_yellow_96.phy
models/handrails/railing_imc_corner.phy
models/handrails/handrail_yellow_128.phy
models/utilities/wire_ceiling_mounts_straight.phy
models/utilities/utility_hatchround_metal01_static.phy
models/utilities/wire_ceiling_mounts_corner.phy
models/utilities/wires_hanging_64.phy
models/utilities/power_gen1.phy
models/electricalboxes/fusebox.phy
models/electricalboxes/fuseboxnodoor.phy
models/electricalboxes/pipe_set_g.phy
models/electricalboxes/pipe_endcap.phy
models/electricalboxes/pipe_bracket_a.phy
models/electricalboxes/littlelectricbox_a.phy
models/electricalboxes/littlelectricbox_b.phy
models/electricalboxes/pipe_set_b.phy
models/vehicle/forklift_imc/forklift_imc.phy
models/lamps/light_fc_off.phy
models/lamps/light_fc.phy
models/lamps/light_parking_post.phy
models/lamps/light_imc_ceiling_command_center.phy
models/lamps/industrial_wall_light_on.phy
models/lamps/light_ontrack_fc.phy
models/lamps/interior_can_light_holder.phy
models/lamps/light_hanging_industrial.phy
models/lamps/light_hanging_industrial_on.phy
models/lamps/light_wall_industrial.phy
models/lamps/industrial_construction_lights_on.phy
models/colony/antenna_post_colony_broken_01.phy
models/colony/antenna_dish_colony_broken_01.phy
models/colony/antenna_02_colony.phy
models/colony/antenna_03_colony.phy
models/colony/antenna_06_colony.phy
models/turrets/turret_imc_lrg.phy
models/vehicle/vehicle_samson_truck/vehicle_samson_with_gear.phy
models/vehicle/straton/straton_imc_gunship_static.phy
models/vehicle/goblin_dropship/goblin_dropship_placed.phy
models/vehicle/goblin_dropship/goblin_dropship_static.phy
models/vehicle/ship_tow_tugger/vehicle_ship_trailer_gate.phy
models/vehicle/ship_tow_tugger/vehicle_ship_tow_tugger_large.phy
models/vehicle/ship_tow_tugger/vehicle_ship_tow_trailer.phy
models/industrial/gas_mask.phy
models/industrial/tool_chest.phy
models/industrial/workshop_goggles.phy
models/industrial/tool_chest_top.phy
models/industrial/tripod_cone_v1_low_on.phy
models/industrial/tool_chest_double.phy
models/industrial/modular_railing_trim_a.phy
models/industrial/modular_railing_trim_c.phy
models/industrial/tripod_cone_v1_high_on.phy
models/industrial/work_cart_plastic.phy
models/industrial/weapons_locker.phy
models/industrial/modular_railing_trim_mid.phy
models/industrial/hammer_mallet.phy
models/industrial/modular_railing_trim_long.phy
models/industrial/modular_railing_trim_short.phy
models/industrial/security_fence_post.phy
models/industrial/console_tower_rack_imc.phy
models/industrial/workshop_gloves.phy
models/industrial/hose_nozzle01.phy
models/industrial/gun_rack_arm_down.phy
models/industrial/reciprocating_saw.phy
models/industrial/imc_generator.phy
models/industrial/stand_alone_air_vent_02.phy
models/industrial/comm_relay.phy
models/industrial/traffic_barrel_03.phy
models/industrial/utg_spire.phy
models/industrial/metal_beam_support_vertical_short.phy
models/industrial/zipline_arm.phy
models/industrial/metal_awning.phy
models/industrial/satellite_antenna.phy
models/vehicle/imc_bomber/bomber.phy
models/vehicle/imc_bomber/bomber_parked.phy
models/imc_base/imc_tech_panel_64_01.phy
models/imc_base/imc_tech_panelsquare_48_05.phy
models/imc_base/imc_tech_tallpanel_48_02.phy
models/imc_base/monitor_arm_02.phy
models/imc_base/camera_imc_01.phy
models/imc_base/chair_imc_02.phy
models/imc_base/monitor_arm_01.phy
models/imc_base/monitor_imc_03.phy
models/imc_base/monitor_panel_01.phy
models/imc_base/monitor_panel_02.phy
models/imc_base/imc_vent_tall_128.phy
models/imc_base/monitor_hood_imc_02.phy
models/imc_base/beam_i_64_imc_01.phy
models/imc_base/monitor_hood_imc_04.phy
models/imc_base/monitor_hood_imc_03.phy
models/imc_base/chain_link_imc_01.phy
models/imc_base/beam_i_128_imc_01.phy
models/imc_base/monitor_arm_rack_01.phy
models/imc_base/monitor_hood_imc_01.phy
models/imc_base/camera_imc_base_01.phy
models/imc_base/beam_i_256_imc_01.phy
models/imc_base/beam_i_512_imc_01.phy
models/imc_base/dispenser_wall_imc_01.phy
models/imc_base/beam_wall_support_imc_01.phy
models/imc_base/monitor_command_imc_01.phy
models/imc_base/bracket_corner_imc_01.phy
models/imc_base/imc_fan_large_case_01.phy
models/imc_base/thumper_platform_steps.phy
models/imc_base/scaffold_tech_halfwalk.phy
models/imc_base/barrier_low_airport_imc.phy
models/imc_base/imc_tech_smallfan_32_06.phy
models/imc_base/command_trim_imc_01_128.phy
models/imc_base/chain_link_post_imc_01.phy
models/imc_base/imc_tech_pipepanel_92_04.phy
models/imc_base/bldg_wall_corner_imc_01.phy
models/imc_base/imc_tech_smallpanel_48_03.phy
models/imc_base/pillar_base_tile_imc_01.phy
models/imc_base/monitor_command_small_imc_02.phy
models/imc_base/monitor_command_small_imc_01.phy
models/imc_base/garage_support_wall_imc_01.phy
models/imc_base/beam_metal_hinge_imc_01.phy
models/imc_base/control_command_desk_imc_02_64.phy
models/imc_base/cargo_container_imc_01_green.phy
models/imc_base/cargo_container_imc_01_blue.phy
models/imc_base/cargo_container_imc_01_white.phy
models/imc_base/cargo_container_imc_01_orange.phy
models/imc_base/cargo_container_imc_01_red.phy
models/imc_base/control_command_desk_imc_01_32.phy
models/imc_base/control_command_top_desk_imc_01_64.phy
models/imc_base/control_command_top_desk_imc_01_32.phy
models/imc_base/experiment_tank_column_single.phy
models/imc_base/control_command_desk_post_imc_02_16.phy
models/imc_base/control_command_desk_post_imc_01_ext.phy
models/imc_base/landing_pad_foot.phy
models/imc_base/windowframe_armor_128_closed_imc_01.phy
models/imc_base/imc_keyboard_01.phy
models/imc_base/imc_pipe_base_01.phy
models/imc_base/control_desk_imc_02.phy
models/imc_base/bulk_head_footer_imc_01.phy
models/imc_base/garage_support_wall_imc_02.phy
models/imc_base/siren_wall_imc_01.phy
models/imc_base/beam_t_128_imc_01.phy
models/imc_base/beam_t_256_imc_01.phy
models/imc_base/ceiling_plugs_imc_01.phy
models/imc_base/ceiling_plugs_imc_02.phy
models/imc_base/control_desk_imc_01.phy
models/imc_base/imc_pipe_med_mount_01.phy
models/imc_base/table_wall_mounted_imc_01.phy
models/imc_base/beam_i_turn_90_01.phy
models/imc_base/pod_door_hangar_imc_01.phy
models/imc_base/scaffold_tech_alpharail_128.phy
models/imc_base/worker_base_whistle_tower_skybox.phy
models/imc_base/worker_base_whistle_tower_holo.phy
models/imc_base/control_command_desk_post_imc_01_16.phy
models/imc_base/worker_base_whistle_tower.phy
models/imc_base/thumper_platform_grid.phy
models/imc_base/imc_pipe_med_32.phy
models/imc_base/imc_pipe_med_cap.phy
models/imc_base/imc_pipe_med_64.phy
models/imc_base/imc_pipe_med_256.phy
models/imc_base/imc_pipe_med_128.phy
models/imc_base/imc_pipe_med_32_02.phy
models/imc_base/imc_pipe_med_512.phy
models/imc_base/imc_pipe_med_ring_02.phy
models/imc_base/imc_pipe_med_ring_01.phy
models/imc_base/imc_pipe_med_32_grey.phy
models/imc_base/imc_pipe_med_64_grey.phy
models/imc_base/imc_pipe_med_128_grey.phy
models/imc_base/imc_pipe_med_256_grey.phy
models/imc_base/imc_pipe_med_512_grey.phy
models/imc_base/bomb_imc_01.phy
models/imc_base/thumper_support_single_shock.phy
models/imc_base/imc_pipe_med_curve45_grey.phy
models/imc_base/hangar_gantry_support01.phy
models/imc_base/beam_t_32_imc_01.phy
models/imc_base/beam_t_64_imc_01.phy
models/imc_base/control_desk_corner_imc_01.phy
models/imc_base/thumper_generator_set_b_animated.phy
models/imc_base/scaffold_tech_adjustbeam_128.phy
models/imc_base/generator_imc_01.phy
models/imc_base/roof_corner_garage_imc_03.phy
models/imc_base/monitor_large_imc_01.phy
models/imc_base/roof_corner_garage_imc_01.phy
models/imc_base/beam_base_clamp_imc_01.phy
models/imc_base/outer_wall_imc_column_02.phy
models/imc_base/landing_pad_center_arm.phy
models/imc_base/chair_imc_01.phy
models/imc_base/windowframe_armor_128_opened_imc_02.phy
models/imc_base/imc_pipe_med_curve90.phy
models/imc_base/imc_pipe_med_curve90_grey.phy
models/imc_base/cargo_container_imc_01_white_open.phy
models/imc_base/cargo_container_imc_01_green_open.phy
models/imc_base/outer_wall_imc_01_closed.phy
models/imc_base/landing_pad_arm_top.phy
models/imc_base/roof_corner_garage_imc_02.phy
models/imc_base/column_base_imc_01.phy
models/imc_base/hangar_girder_45_imc_01.phy
models/imc_base/landing_pad_arm_topstrut.phy
models/imc_base/garage_blast_shield_imc_01.phy
models/imc_base/cargo_refrigerated_imc_01.phy
models/imc_base/bldg_frame_front_b_imc_02.phy
models/imc_base/bldg_frame_front_b_imc_03.phy
models/imc_base/hinge_arm_metal_imc_02.phy
models/imc_base/hinge_arm_metal_imc_01.phy
models/imc_base/thumper_shocks_rail.phy
models/imc_base/thumper_platform_grid_corner.phy
models/imc_base/bldg_frame_front_b_imc_01.phy
models/imc_base/bldg_frame_front_a_imc_03.phy
models/imc_base/bldg_frame_front_a_imc_02.phy
models/imc_base/landing_pad_top_strut.phy
models/imc_base/landing_pad_base_strut.phy
models/imc_base/barracks_bed_imc_01.phy
models/imc_base/landing_pad_arm_bottstrut.phy
models/imc_base/bldg_frame_front_a_imc_01.phy
models/imc_base/bldg_wall_support_imc_01.phy
models/imc_base/bldg_window_front_b_imc_01.phy
models/imc_base/thumper_generator_set_b_static.phy
models/imc_base/outer_wall_imc_01.phy
models/imc_base/bldg_window_front_a_imc_01.phy
models/imc_base/outer_gate_imc_closed.phy
models/imc_base/roof_swing_imc_01.phy
models/imc_base/swing_arm_imc_01.phy
models/imc_base/landing_pad_tarmac.phy
models/imc_base/hangar_gantry_imc_01.phy
models/imc_base/trolley_imc.phy
models/creatures/flyer/flyer_anims.phy
models/creatures/flyer/flyer_a_1000x.phy
models/robots/marvin/marvin_no_jiggle.mdl
models/metal_scraps/scrap_metal_vent02.mdl
models/metal_scraps/scrap_metal_hinge02.mdl
models/signs/billboard_fracture/billboard_fracture_frame_3.mdl
models/angel_city/manhole_cover_01.mdl
models/angel_city/box_small_01.mdl
models/angel_city/box_small_02.mdl
models/buildings/windows/window_frame_tech_01.mdl
models/signs/signage_plates_metal/sign_plate_a.mdl
models/signs/signage_plates_metal/sign_plate_d.mdl
models/signs/signage_plates_metal/sign_plate_c.mdl
models/signs/signage_plates_metal/sign_plate_b.mdl
models/signs/signage_plates_metal/sign_post_plate_a.mdl
models/signs/signage_plates_metal/sign_post_plate_d.mdl
models/signs/signage_plates_metal/sign_post_plate_e.mdl
models/signs/signage_plates_metal/sign_post_plate_h.mdl
models/signs/signage_plates_metal/sign_post_plate_c.mdl
models/signs/signage_plates_metal/sign_post_plate_b.mdl
models/hardware/paint_spraycan_closed.mdl
models/hardware/paint_container_plastic.mdl
models/barriers/metal_parking_post_yell.mdl
models/fx/carrier_jet_glow.mdl
models/fx/energy_hld_01.mdl
models/signs/billboard_airbase/airbase_sign_01.mdl
models/signs/billboard_airbase/airbase_sign_02.mdl
models/commercial/desk_lamp.mdl
models/electricalboxes/littlelectricbox_b.mdl
models/electricalboxes/littlelectricbox_a.mdl
models/electricalboxes/pipe_set_g.mdl
models/electricalboxes/pipe_endcap.mdl
models/electricalboxes/pipe_bracket_a.mdl
models/electricalboxes/fuseboxnodoor.mdl
models/electricalboxes/fusebox.mdl
models/electricalboxes/pipe_set_b.mdl
models/signs/billboard_supports01.mdl
models/stairs/stairs_imc01_support_slope10.mdl
models/stairs/stairs_imc01_single.mdl
models/stairs/stair_base_modular_imc_04.mdl
models/stairs/stair_base_modular_imc_03.mdl
models/stairs/stair_base_modular_imc_02.mdl
models/stairs/stair_base_modular_imc_05.mdl
models/stairs/stair_base_modular_imc_01.mdl
models/domestic/wall_panel_fiberglass_corner.mdl
models/domestic/working_floor_light.mdl
models/domestic/working_floor_light_on.mdl
models/relic/relic_ship_beams_64.mdl
models/relic/relic_ship_beams_128.mdl
models/handrails/handrail_yellow_corner90.mdl
models/handrails/handrail_yellow_end.mdl
models/handrails/handrail_yellow_32.mdl
models/handrails/handrail_yellow_48.mdl
models/handrails/railing_imc_post.mdl
models/handrails/railing_imc_banister_short_slope10.mdl
models/handrails/railing_imc_16in.mdl
models/handrails/railing_imc_banister_bottom_slope10.mdl
models/handrails/railing_imc_banister_long_slope10.mdl
models/handrails/railing_industrial_normal.mdl
models/handrails/handrail_yellow_64.mdl
models/handrails/railing_imc_banister_top_slope10.mdl
models/handrails/railing_imc_32in.mdl
models/handrails/railing_imc_64in.mdl
models/handrails/handrail_yellow_96.mdl
models/handrails/handrail_yellow_128.mdl
models/handrails/railing_imc_corner.mdl
models/vehicle/capital_ship_wallace/capital_ship_wallace_1000x.mdl
models/turrets/turret_imc_lrg.mdl
models/weapons/drums/triplethreat_drum.mdl
models/weapons/drums/xo_16_drum.mdl
models/weapons/drums/titan_rocket_launcher_drum.mdl
models/vehicle/imc_carrier/imc_carrier_airbase.mdl
models/pipes/airduct_xl_vent.mdl
models/pipes/duct_metal_large_cap.mdl
models/pipes/duct_metal_large_hatch_bottom.mdl
models/pipes/duct_metal_large_40.mdl
models/pipes/pipe_painted_red.mdl
models/pipes/duct_metal_large_128.mdl
models/pipes/duct_metal_large_corner_01.mdl
models/pipes/duct_metal_large_hatch_top.mdl
models/pipes/pipe_refinery_port.mdl
models/pipes/duct_round_elbow_90.mdl
models/pipes/duct_round_straight.mdl
models/pipes/pipe_refinery_frame.mdl
models/pipes/pipe_refinery_cap.mdl
models/pipes/duct_metal_large_vent_64.mdl
models/pipes/pipe_refinery_section128.mdl
models/pipes/duct_round_straight_45.mdl
models/pipes/pipe_refinery_section80.mdl
models/pipes/wall_pipes_control_set01.mdl
models/pipes/pipe_ceiling_gray_set.mdl
models/pipes/pipes_wall_02.mdl
models/pipes/wall_pipes_control_set02.mdl
models/pipes/pipes_wall_01.mdl
models/weapons/ammoboxes/ammobox_bigclip.mdl
models/weapons/ammoboxes/backpack_single.mdl
models/weapons/ammoboxes/ammobox_01.mdl
models/weapons/ammoboxes/ammobox_missle.mdl
models/weapons/ammoboxes/ammobox_bigbullet.mdl
models/weapons/ammoboxes/ammo_backpacks.mdl
models/weapons/p2011/p2011_handgun_ab_01.mdl
models/lamps/light_imc_ceiling_guard_32.mdl
models/lamps/light_podlight01.mdl
models/lamps/light_imc_ceiling_command_64_end_on.mdl
models/lamps/light_imc_ceiling_command_128_on.mdl
models/lamps/industrial_wall_light_on.mdl
models/lamps/interior_can_light_on.mdl
models/lamps/interior_can_light_holder.mdl
models/lamps/warning_light.mdl
models/lamps/warning_light_on_orange.mdl
models/lamps/runway_light_2ft_blue_on.mdl
models/lamps/light_imc_ceiling_command_center.mdl
models/lamps/light_wall_industrial.mdl
models/lamps/light_hanging_industrial.mdl
models/lamps/light_hanging_industrial_on.mdl
models/lamps/interrogation_light_rail.mdl
models/lamps/light_fc.mdl
models/lamps/light_fc_off.mdl
models/lamps/light_parking_post.mdl
models/lamps/industrial_construction_lights_on.mdl
models/lamps/light_ontrack_fc.mdl
models/furniture/office_desk_accessories_papers.mdl
models/furniture/chair_45angle_metal.mdl
models/furniture/chair_anim_prop.mdl
models/furniture/shelves_industrial_01.mdl
models/furniture/shelves_industrial_01_wires.mdl
models/industrial/electric_cable_pipes_thin_a_imc.mdl
models/industrial/crowbar_orange.mdl
models/industrial/hammer_metal_01.mdl
models/industrial/beam_imc_metal_gray.mdl
models/industrial/traffic_construction_light_01.mdl
models/industrial/hammer_mallet.mdl
models/industrial/tibilisi_support_cross_beams_round.mdl
models/industrial/screwdriver_01.mdl
models/industrial/screwdriver_02.mdl
models/industrial/hammer_metal_02.mdl
models/industrial/tool_chest_top.mdl
models/industrial/metal_girder_beams_128.mdl
models/industrial/modular_railing_trim_mid.mdl
models/industrial/modular_railing_trim_short.mdl
models/industrial/modular_railing_trim_a.mdl
models/industrial/modular_railing_trim_c.mdl
models/industrial/security_fence_post.mdl
models/industrial/workshop_gloves.mdl
models/industrial/modular_railing_trim_long.mdl
models/industrial/service_hatch_ground.mdl
models/industrial/reciprocating_saw.mdl
models/industrial/hose_nozzle01.mdl
models/industrial/gun_rack_arm_down.mdl
models/industrial/traffic_barrel_03.mdl
models/industrial/workshop_goggles.mdl
models/industrial/metal_beam_support_vertical_short.mdl
models/industrial/tripod_cone_v1_low_on.mdl
models/industrial/stand_alone_air_vent_02.mdl
models/industrial/metal_awning.mdl
models/industrial/tripod_cone_v1_high_on.mdl
models/industrial/tibilisi_leg_support_metal02.mdl
models/industrial/metal_brace_corner_footer.mdl
models/industrial/work_cart_plastic.mdl
models/industrial/console_tower_rack_imc.mdl
models/industrial/gas_mask.mdl
models/industrial/tool_chest_double.mdl
models/industrial/suspended_monitor_imc.mdl
models/industrial/tool_chest.mdl
models/industrial/comm_relay.mdl
models/industrial/weapons_locker.mdl
models/industrial/zipline_arm.mdl
models/industrial/utg_spire.mdl
models/industrial/imc_generator.mdl
models/industrial/satellite_antenna.mdl
models/holo_screens/screen_bar_frame.mdl
models/holo_screens/screen_writing_monitor.mdl
models/holo_screens/screen_writing_monitor_orange.mdl
models/holo_screens/monitor_command_small_imc_screen_01.mdl
models/holo_screens/monitor_command_small_imc_screen_map.mdl
models/holo_screens/monitor_hood_imc_01_screen_text.mdl
models/holo_screens/monitor_hood_imc_02_screen_text.mdl
models/holo_screens/monitor_hood_imc_01_screen_text_02.mdl
models/holo_screens/monitor_command_imc_screen_map.mdl
models/holo_screens/monitor_command_imc_screen_01.mdl
models/holo_screens/military_screen_map_scroll.mdl
models/holo_screens/medical_screen_scanner.mdl
models/holo_screens/military_screen_graphs_scroll.mdl
models/holo_screens/monitor_command_small_imc_screen_graph.mdl
models/holo_screens/monitor_command_imc_screen_graph.mdl
models/holo_screens/holo_screen_wallshape.mdl
models/holo_screens/hologram_dropship.mdl
models/holo_screens/hologram_map_workerbase.mdl
models/holo_screens/hologram_spider_turret_fracture.mdl
models/utilities/halogen_lightbulb_case.mdl
models/utilities/ceiling_vent_metal.mdl
models/utilities/wire_bundle_01.mdl
models/utilities/wire_bundle_02.mdl
models/utilities/wire_bundle_03.mdl
models/utilities/wires_hanging_64.mdl
models/utilities/wire_ceiling_mounts_straight.mdl
models/utilities/wire_ceiling_mounts_corner.mdl
models/utilities/wire_wall_section.mdl
models/utilities/utility_hatchround_metal01_static.mdl
models/utilities/utility_hatchround_metal01_open.mdl
models/utilities/power_gen1.mdl
models/containers/box_large_cardboard.mdl
models/containers/box_small_cardboard.mdl
models/containers/box_med_cardboard_01.mdl
models/containers/box_med_cardboard_02.mdl
models/containers/box_med_cardboard_03.mdl
models/containers/styrofoam_box_short_dirty.mdl
models/containers/styrofoam_box_dirty.mdl
models/containers/crate_blue_plastic.mdl
models/containers/box_med_plastic.mdl
models/containers/gas_tank.mdl
models/containers/box_large_plastic.mdl
models/containers/box_shrinkwrapped.mdl
models/containers/plastic_pallet_01.mdl
models/containers/plastic_pallet_02.mdl
models/containers/box_metal.mdl
models/containers/crate_orange_plastic.mdl
models/containers/barrel.mdl
models/containers/barrel_explosive.mdl
models/containers/pelican_case_large.mdl
models/containers/pelican_case_large_drabgreen.mdl
models/containers/cargo_container_blue_separate.mdl
models/containers/cargo_container_orange_separate.mdl
models/containers/cargo_container_black_separate.mdl
models/containers/cargo_container_white_separate.mdl
models/containers/cargo_container_red_separate.mdl
models/containers/cargo_container_teal_separate.mdl
models/containers/cargo_container_grey_separate.mdl
models/containers/pelican_case_large_open.mdl
models/containers/pelican_case_large_open_drabgreen.mdl
models/containers/pelican_case_ammobox.mdl
models/containers/cargo_container_grey_orange_teal_combined.mdl
models/containers/cargo_container_red_black_blue_combined.mdl
models/door/door_tech_02_frame.mdl
models/door/bunker_door_frame_96x120.mdl
models/door/door_imc_interior_03_128.mdl
models/door/door_imc_interior_64_frame.mdl
models/door/door_imc_interior_03_128_frame.mdl
models/door/pod_door_hangar_imc_01.mdl
models/door/pod_door_hangar_imc_01_open.mdl
models/vehicle/mobile_turret/mobile_turret_proxy.mdl
models/vehicle/mobile_turret/gun_mount_bottom.mdl
models/vehicle/mobile_turret/mobile_turret.mdl
models/levels_terrain/mp_airbase/airbase_dogwhistle_spotlight01.mdl
models/levels_terrain/mp_airbase/airbase_dogwhistle_tower_distant01.mdl
models/vehicle/forklift_imc/forklift_imc.mdl
models/colony/antenna_dish_colony_broken_01.mdl
models/colony/antenna_post_colony_broken_01.mdl
models/colony/antenna_02_colony.mdl
models/colony/antenna_03_colony.mdl
models/colony/antenna_06_colony.mdl
models/communication/terminal_usable_airbase.mdl
models/communication/radar_tower_imc_01.mdl
models/vehicle/vehicle_samson_truck/vehicle_samson_with_gear.mdl
models/vehicle/paladin/paladin_static.mdl
models/vehicle/goblin_dropship/goblin_dropship_static.mdl
models/vehicle/goblin_dropship/goblin_dropship_placed.mdl
models/vehicle/straton/straton_imc_gunship_01_1000x.mdl
models/vehicle/straton/straton_imc_gunship_static.mdl
models/vehicle/straton/straton_anims_1000x.mdl
models/vistas/bomber_single01.mdl
models/vistas/straton_single01.mdl
models/vistas/airebase_se_alpha.mdl
models/vistas/planet_blue_sun.mdl
models/vistas/airbase_se_buildings.mdl
models/imc_base/imc_tech_panel_64_01.mdl
models/imc_base/imc_tech_panelsquare_48_05.mdl
models/imc_base/imc_tech_tallpanel_48_02.mdl
models/imc_base/control_command_top_desk_imc_01_64.mdl
models/imc_base/control_command_top_desk_imc_01_32.mdl
models/imc_base/conduit_cap_imc_01.mdl
models/imc_base/conduit_str_16_imc_02.mdl
models/imc_base/cable_thin_terminator_cieling_01.mdl
models/imc_base/beam_t_32_imc_01.mdl
models/imc_base/beam_t_64_imc_01.mdl
models/imc_base/vent_air_imc_02.mdl
models/imc_base/conduit_cap_imc_02.mdl
models/imc_base/floor_clasp_imc_01.mdl
models/imc_base/floor_clasp_imc_02.mdl
models/imc_base/locker_divider_top_imc_01.mdl
models/imc_base/conduit_str_32_imc_02.mdl
models/imc_base/imc_vent_tall_128.mdl
models/imc_base/beam_i_128_imc_01.mdl
models/imc_base/conduit_str_16_imc_01.mdl
models/imc_base/beam_t_128_imc_01.mdl
models/imc_base/bulk_head_footer_imc_02.mdl
models/imc_base/imc_fan_large_01_animated.mdl
models/imc_base/conduit_start_imc_02.mdl
models/imc_base/window_frame_ceiling_imc_128.mdl
models/imc_base/pipe_ceiling_imc_str_01.mdl
models/imc_base/pipe_ceiling_imc_str_02.mdl
models/imc_base/conduit_bracket_imc_04.mdl
models/imc_base/pipe_ceiling_sml_imc_str_01.mdl
models/imc_base/conduit_str_64_imc_02.mdl
models/imc_base/conduit_bend_16_imc_02.mdl
models/imc_base/locker_divider_imc_01.mdl
models/imc_base/conduit_str_32_imc_01.mdl
models/imc_base/bldg_wall_corner_imc_01.mdl
models/imc_base/scaffold_tech_vert_a.mdl
models/imc_base/scaffold_tech_horz_rail_b.mdl
models/imc_base/beam_i_256_imc_01.mdl
models/imc_base/clasp_wall_imc_01.mdl
models/imc_base/beam_i_64_imc_01.mdl
models/imc_base/roof_corner_garage_imc_03.mdl
models/imc_base/beam_t_256_imc_01.mdl
models/imc_base/scaffold_tech_solidrail_128.mdl
models/imc_base/roof_corner_garage_imc_02.mdl
models/imc_base/monitor_panel_01.mdl
models/imc_base/monitor_panel_02.mdl
models/imc_base/scaffold_tech_vert_rail_c.mdl
models/imc_base/table_wall_mounted_imc_01.mdl
models/imc_base/conduit_bracket_imc_02.mdl
models/imc_base/pipe_ceiling_imc_str_03.mdl
models/imc_base/pipe_ceiling_sml_imc_str_03.mdl
models/imc_base/pipe_ceiling_imc_bend_02.mdl
models/imc_base/pipe_ceiling_sml_imc_bend_01.mdl
models/imc_base/ladder_modular_cap_imc.mdl
models/imc_base/conduit_start_imc_01.mdl
models/imc_base/pipe_ceiling_imc_end_01.mdl
models/imc_base/pipe_ceiling_imc_bend_01.mdl
models/imc_base/pipe_ceiling_sml_imc_end_01.mdl
models/imc_base/vent_air_imc_01.mdl
models/imc_base/bldg_wall_support_imc_02.mdl
models/imc_base/imc_pipe_med_curve45_grey.mdl
models/imc_base/roof_corner_garage_imc_01.mdl
models/imc_base/imc_fan_large_01.mdl
models/imc_base/conduit_str_64_imc_01.mdl
models/imc_base/roof_swing_imc_01.mdl
models/imc_base/pipe_ceiling_imc_junc_02.mdl
models/imc_base/pipe_ceiling_imc_junc_01.mdl
models/imc_base/beam_i_512_imc_01.mdl
models/imc_base/garage_support_wall_imc_02.mdl
models/imc_base/bulk_head_footer_imc_01.mdl
models/imc_base/control_command_desk_post_imc_01_ext.mdl
models/imc_base/camera_imc_base_01.mdl
models/imc_base/command_trim_imc_01_128.mdl
models/imc_base/control_command_desk_post_imc_02_16.mdl
models/imc_base/imc_tech_smallpanel_48_03.mdl
models/imc_base/thumper_platform_grid.mdl
models/imc_base/imc_pipe_med_32.mdl
models/imc_base/control_command_desk_imc_02_64.mdl
models/imc_base/imc_pipe_med_32_grey.mdl
models/imc_base/control_command_desk_imc_01_32.mdl
models/imc_base/bldg_frame_front_a_imc_03.mdl
models/imc_base/bldg_frame_front_a_imc_02.mdl
models/imc_base/pipe_ceiling_imc_end_02.mdl
models/imc_base/pipe_ceiling_sml_imc_end_02.mdl
models/imc_base/conduit_bend_16_imc_01.mdl
models/imc_base/light_wall_imc_01.mdl
models/imc_base/light_wall_imc_01_on.mdl
models/imc_base/light_wall_imc_02_on.mdl
models/imc_base/cable_thin_ceiling_64_02.mdl
models/imc_base/cable_thin_ceiling_64_01.mdl
models/imc_base/beam_i_turn_90_01.mdl
models/imc_base/thumper_generator_set_b_animated.mdl
models/imc_base/imc_pipe_med_curve90.mdl
models/imc_base/imc_pipe_med_curve90_grey.mdl
models/imc_base/locker_wall_imc_01.mdl
models/imc_base/locker_wall_imc_02.mdl
models/imc_base/bldg_glass_front_a_imc_01.mdl
models/imc_base/imc_fan_large_tube_01.mdl
models/imc_base/handle_modular_imc_lod0.mdl
models/imc_base/imc_pipe_med_cap.mdl
models/imc_base/imc_pipe_med_ring_02.mdl
models/imc_base/monitor_arm_02.mdl
models/imc_base/scaffold_tech_horz_rail_c.mdl
models/imc_base/imc_pipe_med_64.mdl
models/imc_base/scaffold_tech_brace_02.mdl
models/imc_base/imc_pipe_med_64_grey.mdl
models/imc_base/imc_antenna_01.mdl
models/imc_base/monitor_arm_01.mdl
models/imc_base/imc_keyboard_01.mdl
models/imc_base/control_command_desk_post_imc_01_16.mdl
models/imc_base/control_desk_imc_02.mdl
models/imc_base/monitor_arm_rack_01.mdl
models/imc_base/monitor_hood_imc_02.mdl
models/imc_base/monitor_hood_imc_04.mdl
models/imc_base/monitor_hood_imc_01.mdl
models/imc_base/beam_metal_hinge_imc_01.mdl
models/imc_base/monitor_hood_imc_03.mdl
models/imc_base/bldg_frame_front_a_imc_01.mdl
models/imc_base/scaffold_tech_beam_128.mdl
models/imc_base/bracket_corner_imc_01.mdl
models/imc_base/hangar_girder_45_imc_01.mdl
models/imc_base/scaffold_tech_adjustbeam_128.mdl
models/imc_base/imc_pipe_med_ring_01.mdl
models/imc_base/control_desk_imc_01.mdl
models/imc_base/clasp_ceiling_imc_02.mdl
models/imc_base/scaffold_tech_alpharail_128.mdl
models/imc_base/scaffold_tech_alpharaillong_128.mdl
models/imc_base/light_wall_imc_03_on.mdl
models/imc_base/light_wall_imc_03.mdl
models/imc_base/siren_wall_imc_01.mdl
models/imc_base/wire_hanging_imc_long_02.mdl
models/imc_base/wire_hanging_imc_short_01.mdl
models/imc_base/monitor_imc_03.mdl
models/imc_base/garage_support_wall_imc_01.mdl
models/imc_base/beam_wall_support_imc_01.mdl
models/imc_base/imc_pipe_med_32_02.mdl
models/imc_base/corner_piston_imc_01.mdl
models/imc_base/bldg_wall_support_imc_01_half.mdl
models/imc_base/connector_90_deg_01.mdl
models/imc_base/imc_tech_smallfan_32_06.mdl
models/imc_base/bomb_imc_01.mdl
models/imc_base/experiment_tank_column_single.mdl
models/imc_base/wall_handle_imc_01.mdl
models/imc_base/monitor_command_small_imc_02.mdl
models/imc_base/monitor_command_imc_01.mdl
models/imc_base/monitor_command_small_imc_01.mdl
models/imc_base/imc_tech_pipepanel_92_04.mdl
models/imc_base/bldg_frame_front_b_imc_03.mdl
models/imc_base/cargo_bomb_rack01.mdl
models/imc_base/scaffold_tech_frame_bottom_128.mdl
models/imc_base/imc_pipe_med_128.mdl
models/imc_base/bldg_frame_front_b_imc_02.mdl
models/imc_base/column_support_imc_01.mdl
models/imc_base/imc_pipe_med_128_grey.mdl
models/imc_base/outer_wall_imc_column_02.mdl
models/imc_base/imc_pipe_med_mount_01.mdl
models/imc_base/bldg_frame_front_b_imc_01.mdl
models/imc_base/scaffold_tech_frame_top_128.mdl
models/imc_base/console_door_small_imc_01.mdl
models/imc_base/cable_thin_ceiling_32_01.mdl
models/imc_base/chain_link_post_imc_01.mdl
models/imc_base/thumper_platform_steps.mdl
models/imc_base/thumper_platform_grid_corner.mdl
models/imc_base/buttress_imc_01.mdl
models/imc_base/landing_pad_foot.mdl
models/imc_base/cables_modular_med_imc_03.mdl
models/imc_base/cables_modular_med_imc_02.mdl
models/imc_base/dispenser_wall_imc_01.mdl
models/imc_base/cables_modular_med_imc_01.mdl
models/imc_base/cable_plugs_floor01.mdl
models/imc_base/ceiling_plugs_imc_01.mdl
models/imc_base/bldg_wall_support_imc_01.mdl
models/imc_base/ladder_modular_64_imc.mdl
models/imc_base/imc_fan_large_case_01.mdl
models/imc_base/monitor_imc_02.mdl
models/imc_base/pillar_base_tile_imc_01.mdl
models/imc_base/bldg_frame_interior_b_imc_01.mdl
models/imc_base/bldg_window_front_b_imc_01.mdl
models/imc_base/control_desk_corner_imc_01.mdl
models/imc_base/chair_imc_02.mdl
models/imc_base/holo_projector_large_imc_arm.mdl
models/imc_base/imc_pipe_base_01.mdl
models/imc_base/bldg_window_front_a_imc_01.mdl
models/imc_base/thumper_support_single_shock.mdl
models/imc_base/scaffold_tech_halfwalk.mdl
models/imc_base/scaffold_tech_solidrail_11u.mdl
models/imc_base/landing_pad_top_strut.mdl
models/imc_base/worker_base_whistle_tower_holo.mdl
models/imc_base/beam_base_clamp_imc_01.mdl
models/imc_base/landing_pad_cables.mdl
models/imc_base/chair_imc_01.mdl
models/imc_base/garage_wall_arm_imc_02.mdl
models/imc_base/garage_wall_arm_imc_01.mdl
models/imc_base/imc_pipe_med_256.mdl
models/imc_base/monitor_imc_01.mdl
models/imc_base/garage_blast_shield_imc_01.mdl
models/imc_base/barrier_low_airport_imc.mdl
models/imc_base/imc_pipe_med_256_grey.mdl
models/imc_base/ladder_aircraft_imc_01.mdl
models/imc_base/ceiling_plugs_imc_02.mdl
models/imc_base/camera_imc_01.mdl
models/imc_base/radar_g_skybox.mdl
models/imc_base/radar_c_skybox.mdl
models/imc_base/radar_d_skybox.mdl
models/imc_base/radar_i_skybox.mdl
models/imc_base/radar_g.mdl
models/imc_base/radar_c.mdl
models/imc_base/radar_d.mdl
models/imc_base/radar_i.mdl
models/imc_base/landing_pad_center_arm.mdl
models/imc_base/windowframe_armor_128_opened_imc_02.mdl
models/imc_base/hinge_arm_metal_imc_02.mdl
models/imc_base/windowframe_armor_128_closed_imc_01.mdl
models/imc_base/chain_link_imc_01.mdl
models/imc_base/radar_f_skybox.mdl
models/imc_base/radar_b_skybox.mdl
models/imc_base/radar_f.mdl
models/imc_base/radar_b.mdl
models/imc_base/hinge_arm_metal_imc_01.mdl
models/imc_base/landing_pad_arm_bottstrut.mdl
models/imc_base/landing_pad_arm_top.mdl
models/imc_base/hangar_gantry_support01.mdl
models/imc_base/landing_pad_base_strut.mdl
models/imc_base/thumper_shocks_rail.mdl
models/imc_base/landing_pad_arm_topstrut.mdl
models/imc_base/imc_pipe_med_512.mdl
models/imc_base/imc_pipe_med_512_grey.mdl
models/imc_base/generator_imc_01.mdl
models/imc_base/radar_e_skybox.mdl
models/imc_base/radar_h_skybox.mdl
models/imc_base/radar_a_skybox.mdl
models/imc_base/cargo_container_imc_01_green_open.mdl
models/imc_base/cargo_container_imc_01_white_open.mdl
models/imc_base/radar_a.mdl
models/imc_base/barracks_bed_imc_01.mdl
models/imc_base/radar_h.mdl
models/imc_base/radar_e.mdl
models/imc_base/outer_gate_imc_closed.mdl
models/imc_base/holo_projector_large_imc.mdl
models/imc_base/pod_door_hangar_imc_01.mdl
models/imc_base/cargo_container_imc_01_red.mdl
models/imc_base/cargo_container_imc_01_white.mdl
models/imc_base/cargo_container_imc_01_green.mdl
models/imc_base/cargo_container_imc_01_orange.mdl
models/imc_base/cargo_container_imc_01_blue.mdl
models/imc_base/trolley_imc.mdl
models/imc_base/outer_wall_imc_01.mdl
models/imc_base/column_base_imc_01.mdl
models/imc_base/outer_wall_imc_01_closed.mdl
models/imc_base/thumper_generator_set_b_static.mdl
models/imc_base/swing_arm_imc_01.mdl
models/imc_base/hangar_gantry_imc_01.mdl
models/imc_base/landing_pad_tarmac.mdl
models/imc_base/worker_base_whistle_tower_skybox.mdl
models/imc_base/worker_base_whistle_tower.mdl
models/imc_base/cargo_refrigerated_imc_01.mdl
models/vehicle/ship_tow_tugger/vehicle_ship_trailer_gate.mdl
models/vehicle/ship_tow_tugger/vehicle_ship_tow_tugger_large.mdl
models/vehicle/ship_tow_tugger/vehicle_ship_tow_trailer.mdl
models/creatures/leviathan/leviathan_holo_medium.mdl
models/creatures/leviathan/leviathan_brown_airbase_small.mdl
models/creatures/leviathan/leviathan_brown_airbase_medium.mdl
models/creatures/leviathan/leviathan_brown_airbase_large.mdl
models/vehicle/imc_bomber/bomber_rear_exhaust_1.mdl
models/vehicle/imc_bomber/bomber_r_exhaust_1.mdl
models/vehicle/imc_bomber/bomber_l_exhaust_1.mdl
models/vehicle/imc_bomber/bomber_l_exhaust_2.mdl
models/vehicle/imc_bomber/bomber_r_exhaust_2.mdl
models/vehicle/imc_bomber/bomber.mdl
models/vehicle/imc_bomber/bomber_parked.mdl
models/creatures/flyer/flyer_static_flying.mdl
models/creatures/flyer/flyer_a_1000x.mdl
models/creatures/flyer/flyer_a.mdl
models/creatures/flyer/flyer_a_500x.mdl
models/creatures/flyer/flyer_anims_500x.mdl
models/creatures/flyer/flyer_anims_1000x.mdl
models/creatures/flyer/flyer_anims.mdl
models/unique/redeye/redeye_flyer_path_1000x.mdl
models/unique/redeye/redeye_flyer_path_500x.mdl
models/unique/redeye/redeye_flyer_path.mdl
maps/mp_airbase_env.ent
maps/mp_airbase_snd.ent
maps/mp_airbase_spawn.ent
maps/mp_airbase_fx.ent
maps/mp_airbase_script.ent
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp
maps/mp_airbase.bsp
depot/r1dev/game/r1/maps/mp_airbase.bsp
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007f.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007d.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007c.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007b.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0079.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0078.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0077.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0076.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0075.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0074.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0073.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0072.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0071.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0070.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006f.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006d.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006c.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006b.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006a.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0069.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0068.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0067.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0066.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0065.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0064.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0063.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0062.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0061.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0060.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005f.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005d.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005c.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005b.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005a.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0059.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0058.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0057.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0056.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0055.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0053.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0052.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0051.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0050.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.004f.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.004a.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0049.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0047.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0046.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0045.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0044.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0042.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0036.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.002c.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.002b.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.002a.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0028.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0023.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.001e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.001d.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0018.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.000e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0003.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0002.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0001.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0000.bsp_lump
maps/mp_airbase.bsp.007f.bsp_lump
maps/mp_airbase.bsp.007e.bsp_lump
maps/mp_airbase.bsp.007d.bsp_lump
maps/mp_airbase.bsp.007c.bsp_lump
maps/mp_airbase.bsp.007b.bsp_lump
maps/mp_airbase.bsp.0079.bsp_lump
maps/mp_airbase.bsp.0078.bsp_lump
maps/mp_airbase.bsp.0077.bsp_lump
maps/mp_airbase.bsp.0076.bsp_lump
maps/mp_airbase.bsp.0075.bsp_lump
maps/mp_airbase.bsp.0074.bsp_lump
maps/mp_airbase.bsp.0073.bsp_lump
maps/mp_airbase.bsp.0072.bsp_lump
maps/mp_airbase.bsp.0071.bsp_lump
maps/mp_airbase.bsp.0070.bsp_lump
maps/mp_airbase.bsp.006f.bsp_lump
maps/mp_airbase.bsp.006e.bsp_lump
maps/mp_airbase.bsp.006d.bsp_lump
maps/mp_airbase.bsp.006c.bsp_lump
maps/mp_airbase.bsp.006b.bsp_lump
maps/mp_airbase.bsp.006a.bsp_lump
maps/mp_airbase.bsp.0069.bsp_lump
maps/mp_airbase.bsp.0068.bsp_lump
maps/mp_airbase.bsp.0067.bsp_lump
maps/mp_airbase.bsp.0066.bsp_lump
maps/mp_airbase.bsp.0065.bsp_lump
maps/mp_airbase.bsp.0064.bsp_lump
maps/mp_airbase.bsp.0063.bsp_lump
maps/mp_airbase.bsp.0062.bsp_lump
maps/mp_airbase.bsp.0061.bsp_lump
maps/mp_airbase.bsp.0060.bsp_lump
maps/mp_airbase.bsp.005f.bsp_lump
maps/mp_airbase.bsp.005e.bsp_lump
maps/mp_airbase.bsp.005d.bsp_lump
maps/mp_airbase.bsp.005c.bsp_lump
maps/mp_airbase.bsp.005b.bsp_lump
maps/mp_airbase.bsp.005a.bsp_lump
maps/mp_airbase.bsp.0059.bsp_lump
maps/mp_airbase.bsp.0058.bsp_lump
maps/mp_airbase.bsp.0057.bsp_lump
maps/mp_airbase.bsp.0056.bsp_lump
maps/mp_airbase.bsp.0055.bsp_lump
maps/mp_airbase.bsp.0053.bsp_lump
maps/mp_airbase.bsp.0052.bsp_lump
maps/mp_airbase.bsp.0051.bsp_lump
maps/mp_airbase.bsp.0050.bsp_lump
maps/mp_airbase.bsp.004f.bsp_lump
maps/mp_airbase.bsp.004a.bsp_lump
maps/mp_airbase.bsp.0049.bsp_lump
maps/mp_airbase.bsp.0047.bsp_lump
maps/mp_airbase.bsp.0046.bsp_lump
maps/mp_airbase.bsp.0045.bsp_lump
maps/mp_airbase.bsp.0044.bsp_lump
maps/mp_airbase.bsp.0042.bsp_lump
maps/mp_airbase.bsp.0036.bsp_lump
maps/mp_airbase.bsp.002c.bsp_lump
maps/mp_airbase.bsp.002b.bsp_lump
maps/mp_airbase.bsp.002a.bsp_lump
maps/mp_airbase.bsp.0028.bsp_lump
maps/mp_airbase.bsp.0023.bsp_lump
maps/mp_airbase.bsp.001e.bsp_lump
maps/mp_airbase.bsp.001d.bsp_lump
maps/mp_airbase.bsp.0018.bsp_lump
maps/mp_airbase.bsp.000e.bsp_lump
maps/mp_airbase.bsp.0003.bsp_lump
maps/mp_airbase.bsp.0002.bsp_lump
maps/mp_airbase.bsp.0001.bsp_lump
maps/mp_airbase.bsp.0000.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007f.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007e.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007d.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007c.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007b.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0079.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0078.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0077.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0076.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0075.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0074.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0073.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0072.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0071.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0070.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.006f.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.006e.bsp_lump
depot/r1dev/game/r1/m
```

Same results for Titanfall 2, crashes on all files, and no output, unless i'm missing something important here?
## Post #59
- Username: chieflukas
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 09, 2017 3:44 am
- Post datetime: 2021-01-02T04:31:47+00:00
- Post Title: Re: TitanFall (.vpk) archives

Hi! I know for Titanfall 2 you can use Legion ([https://wiki.modme.co/wiki/apps/Legion.html](https://wiki.modme.co/wiki/apps/Legion.html)) or you can use the Titanfall VPK tool (It says Titanfall 2 but if I remember correctly it works for both the original and the sequel: [https://noskill.gitbook.io/titanfall2/h ... ding-tools](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools))  and crowbar ([https://github.com/ZeqMacaw/Crowbar/releases](https://github.com/ZeqMacaw/Crowbar/releases)) for both TF 1 and 2. Hopefully this helps!

Cheers!

P.S. Crowbar extracts the .MDL files that the Titanfall VPK tool gives.
## Post #60
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2021-01-03T09:47:16+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from mono24 ↑Sat Jan 02, 2021 8:11 am at Sat Jan 02, 2021 8:11 am
>
> 
tschumann wrote: ↑Wed Dec 23, 2020 6:37 am
And now I have a working extractor: https://www.moddb.com/games/half-life/d ... gssmt-v004

Thanks for this nice tool, unfortunately, every time i want to extract any file at all from Titanfall1 it just crashes with out any output error, and i only see in the log file/folder structure with no output files extracted at all, you can see how it ends at the end in following example:
Code: Select allgssmt v0.0.4

File: englishclient_mp_airbase.bsp.pak000_dir.vpk
Size: 330095 bytes

General information
===================
Magic Number: 1437209140
Version: 2.3
Directory tree size: 330079 bytes
Files
=====
---------------------------------------------------------------
materials/correction/airbase.raw
materials/correction/mp_fracture_main01.raw
models/robots/marvin/marvin_no_jiggle.phy
models/angel_city/box_small_01.phy
models/angel_city/box_small_02.phy
models/barriers/metal_parking_post_yell.phy
models/furniture/office_desk_accessories_papers.phy
models/furniture/chair_anim_prop.phy
models/furniture/chair_45angle_metal.phy
models/commercial/desk_lamp.phy
models/vehicle/mobile_turret/gun_mount_bottom.phy
models/holo_screens/holo_screen_wallshape.phy
models/signs/billboard_fracture/billboard_fracture_frame_3.phy
models/communication/radar_tower_imc_01.phy
models/domestic/working_floor_light_on.phy
models/domestic/working_floor_light.phy
models/domestic/wall_panel_fiberglass_corner.phy
models/metal_scraps/scrap_metal_vent02.phy
models/metal_scraps/scrap_metal_hinge02.phy
models/signs/billboard_supports01.phy
models/hardware/paint_container_plastic.phy
models/hardware/paint_spraycan_closed.phy
models/stairs/stairs_imc01_single.phy
models/stairs/stair_base_modular_imc_01.phy
models/stairs/stair_base_modular_imc_02.phy
models/stairs/stairs_imc01_support_slope10.phy
models/stairs/stair_base_modular_imc_03.phy
models/stairs/stair_base_modular_imc_04.phy
models/weapons/drums/triplethreat_drum.phy
models/weapons/drums/xo_16_drum.phy
models/weapons/drums/titan_rocket_launcher_drum.phy
models/containers/crate_blue_plastic.phy
models/containers/pelican_case_large.phy
models/containers/pelican_case_large_drabgreen.phy
models/containers/box_med_plastic.phy
models/containers/box_large_plastic.phy
models/containers/box_metal.phy
models/containers/styrofoam_box_dirty.phy
models/containers/styrofoam_box_short_dirty.phy
models/containers/box_small_cardboard.phy
models/containers/box_large_cardboard.phy
models/containers/box_shrinkwrapped.phy
models/containers/box_med_cardboard_01.phy
models/containers/box_med_cardboard_02.phy
models/containers/gas_tank.phy
models/containers/plastic_pallet_02.phy
models/containers/plastic_pallet_01.phy
models/containers/crate_orange_plastic.phy
models/containers/box_med_cardboard_03.phy
models/containers/pelican_case_ammobox.phy
models/containers/pelican_case_large_open_drabgreen.phy
models/containers/pelican_case_large_open.phy
models/containers/barrel.phy
models/containers/barrel_explosive.phy
models/containers/cargo_container_grey_orange_teal_combined.phy
models/containers/cargo_container_red_black_blue_combined.phy
models/containers/cargo_container_black_separate.phy
models/containers/cargo_container_orange_separate.phy
models/containers/cargo_container_teal_separate.phy
models/containers/cargo_container_white_separate.phy
models/containers/cargo_container_grey_separate.phy
models/containers/cargo_container_blue_separate.phy
models/containers/cargo_container_red_separate.phy
models/door/door_imc_interior_03_128.phy
models/door/bunker_door_frame_96x120.phy
models/door/pod_door_hangar_imc_01.phy
models/door/pod_door_hangar_imc_01_open.phy
models/door/door_imc_interior_03_128_frame.phy
models/door/door_imc_interior_64_frame.phy
models/weapons/ammoboxes/ammobox_missle.phy
models/weapons/ammoboxes/ammobox_01.phy
models/weapons/ammoboxes/ammobox_bigclip.phy
models/weapons/ammoboxes/ammobox_bigbullet.phy
models/weapons/ammoboxes/ammo_backpacks.phy
models/weapons/ammoboxes/backpack_single.phy
models/pipes/airduct_xl_vent.phy
models/pipes/pipe_ceiling_gray_set.phy
models/pipes/pipes_wall_02.phy
models/pipes/pipes_wall_01.phy
models/pipes/pipe_refinery_port.phy
models/pipes/pipe_refinery_section80.phy
models/pipes/pipe_refinery_section128.phy
models/pipes/pipe_refinery_cap.phy
models/pipes/pipe_refinery_frame.phy
models/pipes/duct_round_straight.phy
models/pipes/duct_round_elbow_90.phy
models/pipes/duct_round_straight_45.phy
models/signs/signage_plates_metal/sign_plate_a.phy
models/signs/signage_plates_metal/sign_plate_c.phy
models/signs/signage_plates_metal/sign_plate_b.phy
models/signs/signage_plates_metal/sign_plate_d.phy
models/signs/signage_plates_metal/sign_post_plate_h.phy
models/signs/signage_plates_metal/sign_post_plate_b.phy
models/signs/signage_plates_metal/sign_post_plate_d.phy
models/signs/signage_plates_metal/sign_post_plate_e.phy
models/signs/signage_plates_metal/sign_post_plate_a.phy
models/signs/signage_plates_metal/sign_post_plate_c.phy
models/handrails/railing_industrial_normal.phy
models/handrails/railing_imc_post.phy
models/handrails/handrail_yellow_end.phy
models/handrails/railing_imc_banister_top_slope10.phy
models/handrails/railing_imc_banister_bottom_slope10.phy
models/handrails/railing_imc_32in.phy
models/handrails/railing_imc_64in.phy
models/handrails/railing_imc_16in.phy
models/handrails/railing_imc_banister_long_slope10.phy
models/handrails/railing_imc_banister_short_slope10.phy
models/handrails/handrail_yellow_32.phy
models/handrails/handrail_yellow_48.phy
models/handrails/handrail_yellow_64.phy
models/handrails/handrail_yellow_corner90.phy
models/handrails/handrail_yellow_96.phy
models/handrails/railing_imc_corner.phy
models/handrails/handrail_yellow_128.phy
models/utilities/wire_ceiling_mounts_straight.phy
models/utilities/utility_hatchround_metal01_static.phy
models/utilities/wire_ceiling_mounts_corner.phy
models/utilities/wires_hanging_64.phy
models/utilities/power_gen1.phy
models/electricalboxes/fusebox.phy
models/electricalboxes/fuseboxnodoor.phy
models/electricalboxes/pipe_set_g.phy
models/electricalboxes/pipe_endcap.phy
models/electricalboxes/pipe_bracket_a.phy
models/electricalboxes/littlelectricbox_a.phy
models/electricalboxes/littlelectricbox_b.phy
models/electricalboxes/pipe_set_b.phy
models/vehicle/forklift_imc/forklift_imc.phy
models/lamps/light_fc_off.phy
models/lamps/light_fc.phy
models/lamps/light_parking_post.phy
models/lamps/light_imc_ceiling_command_center.phy
models/lamps/industrial_wall_light_on.phy
models/lamps/light_ontrack_fc.phy
models/lamps/interior_can_light_holder.phy
models/lamps/light_hanging_industrial.phy
models/lamps/light_hanging_industrial_on.phy
models/lamps/light_wall_industrial.phy
models/lamps/industrial_construction_lights_on.phy
models/colony/antenna_post_colony_broken_01.phy
models/colony/antenna_dish_colony_broken_01.phy
models/colony/antenna_02_colony.phy
models/colony/antenna_03_colony.phy
models/colony/antenna_06_colony.phy
models/turrets/turret_imc_lrg.phy
models/vehicle/vehicle_samson_truck/vehicle_samson_with_gear.phy
models/vehicle/straton/straton_imc_gunship_static.phy
models/vehicle/goblin_dropship/goblin_dropship_placed.phy
models/vehicle/goblin_dropship/goblin_dropship_static.phy
models/vehicle/ship_tow_tugger/vehicle_ship_trailer_gate.phy
models/vehicle/ship_tow_tugger/vehicle_ship_tow_tugger_large.phy
models/vehicle/ship_tow_tugger/vehicle_ship_tow_trailer.phy
models/industrial/gas_mask.phy
models/industrial/tool_chest.phy
models/industrial/workshop_goggles.phy
models/industrial/tool_chest_top.phy
models/industrial/tripod_cone_v1_low_on.phy
models/industrial/tool_chest_double.phy
models/industrial/modular_railing_trim_a.phy
models/industrial/modular_railing_trim_c.phy
models/industrial/tripod_cone_v1_high_on.phy
models/industrial/work_cart_plastic.phy
models/industrial/weapons_locker.phy
models/industrial/modular_railing_trim_mid.phy
models/industrial/hammer_mallet.phy
models/industrial/modular_railing_trim_long.phy
models/industrial/modular_railing_trim_short.phy
models/industrial/security_fence_post.phy
models/industrial/console_tower_rack_imc.phy
models/industrial/workshop_gloves.phy
models/industrial/hose_nozzle01.phy
models/industrial/gun_rack_arm_down.phy
models/industrial/reciprocating_saw.phy
models/industrial/imc_generator.phy
models/industrial/stand_alone_air_vent_02.phy
models/industrial/comm_relay.phy
models/industrial/traffic_barrel_03.phy
models/industrial/utg_spire.phy
models/industrial/metal_beam_support_vertical_short.phy
models/industrial/zipline_arm.phy
models/industrial/metal_awning.phy
models/industrial/satellite_antenna.phy
models/vehicle/imc_bomber/bomber.phy
models/vehicle/imc_bomber/bomber_parked.phy
models/imc_base/imc_tech_panel_64_01.phy
models/imc_base/imc_tech_panelsquare_48_05.phy
models/imc_base/imc_tech_tallpanel_48_02.phy
models/imc_base/monitor_arm_02.phy
models/imc_base/camera_imc_01.phy
models/imc_base/chair_imc_02.phy
models/imc_base/monitor_arm_01.phy
models/imc_base/monitor_imc_03.phy
models/imc_base/monitor_panel_01.phy
models/imc_base/monitor_panel_02.phy
models/imc_base/imc_vent_tall_128.phy
models/imc_base/monitor_hood_imc_02.phy
models/imc_base/beam_i_64_imc_01.phy
models/imc_base/monitor_hood_imc_04.phy
models/imc_base/monitor_hood_imc_03.phy
models/imc_base/chain_link_imc_01.phy
models/imc_base/beam_i_128_imc_01.phy
models/imc_base/monitor_arm_rack_01.phy
models/imc_base/monitor_hood_imc_01.phy
models/imc_base/camera_imc_base_01.phy
models/imc_base/beam_i_256_imc_01.phy
models/imc_base/beam_i_512_imc_01.phy
models/imc_base/dispenser_wall_imc_01.phy
models/imc_base/beam_wall_support_imc_01.phy
models/imc_base/monitor_command_imc_01.phy
models/imc_base/bracket_corner_imc_01.phy
models/imc_base/imc_fan_large_case_01.phy
models/imc_base/thumper_platform_steps.phy
models/imc_base/scaffold_tech_halfwalk.phy
models/imc_base/barrier_low_airport_imc.phy
models/imc_base/imc_tech_smallfan_32_06.phy
models/imc_base/command_trim_imc_01_128.phy
models/imc_base/chain_link_post_imc_01.phy
models/imc_base/imc_tech_pipepanel_92_04.phy
models/imc_base/bldg_wall_corner_imc_01.phy
models/imc_base/imc_tech_smallpanel_48_03.phy
models/imc_base/pillar_base_tile_imc_01.phy
models/imc_base/monitor_command_small_imc_02.phy
models/imc_base/monitor_command_small_imc_01.phy
models/imc_base/garage_support_wall_imc_01.phy
models/imc_base/beam_metal_hinge_imc_01.phy
models/imc_base/control_command_desk_imc_02_64.phy
models/imc_base/cargo_container_imc_01_green.phy
models/imc_base/cargo_container_imc_01_blue.phy
models/imc_base/cargo_container_imc_01_white.phy
models/imc_base/cargo_container_imc_01_orange.phy
models/imc_base/cargo_container_imc_01_red.phy
models/imc_base/control_command_desk_imc_01_32.phy
models/imc_base/control_command_top_desk_imc_01_64.phy
models/imc_base/control_command_top_desk_imc_01_32.phy
models/imc_base/experiment_tank_column_single.phy
models/imc_base/control_command_desk_post_imc_02_16.phy
models/imc_base/control_command_desk_post_imc_01_ext.phy
models/imc_base/landing_pad_foot.phy
models/imc_base/windowframe_armor_128_closed_imc_01.phy
models/imc_base/imc_keyboard_01.phy
models/imc_base/imc_pipe_base_01.phy
models/imc_base/control_desk_imc_02.phy
models/imc_base/bulk_head_footer_imc_01.phy
models/imc_base/garage_support_wall_imc_02.phy
models/imc_base/siren_wall_imc_01.phy
models/imc_base/beam_t_128_imc_01.phy
models/imc_base/beam_t_256_imc_01.phy
models/imc_base/ceiling_plugs_imc_01.phy
models/imc_base/ceiling_plugs_imc_02.phy
models/imc_base/control_desk_imc_01.phy
models/imc_base/imc_pipe_med_mount_01.phy
models/imc_base/table_wall_mounted_imc_01.phy
models/imc_base/beam_i_turn_90_01.phy
models/imc_base/pod_door_hangar_imc_01.phy
models/imc_base/scaffold_tech_alpharail_128.phy
models/imc_base/worker_base_whistle_tower_skybox.phy
models/imc_base/worker_base_whistle_tower_holo.phy
models/imc_base/control_command_desk_post_imc_01_16.phy
models/imc_base/worker_base_whistle_tower.phy
models/imc_base/thumper_platform_grid.phy
models/imc_base/imc_pipe_med_32.phy
models/imc_base/imc_pipe_med_cap.phy
models/imc_base/imc_pipe_med_64.phy
models/imc_base/imc_pipe_med_256.phy
models/imc_base/imc_pipe_med_128.phy
models/imc_base/imc_pipe_med_32_02.phy
models/imc_base/imc_pipe_med_512.phy
models/imc_base/imc_pipe_med_ring_02.phy
models/imc_base/imc_pipe_med_ring_01.phy
models/imc_base/imc_pipe_med_32_grey.phy
models/imc_base/imc_pipe_med_64_grey.phy
models/imc_base/imc_pipe_med_128_grey.phy
models/imc_base/imc_pipe_med_256_grey.phy
models/imc_base/imc_pipe_med_512_grey.phy
models/imc_base/bomb_imc_01.phy
models/imc_base/thumper_support_single_shock.phy
models/imc_base/imc_pipe_med_curve45_grey.phy
models/imc_base/hangar_gantry_support01.phy
models/imc_base/beam_t_32_imc_01.phy
models/imc_base/beam_t_64_imc_01.phy
models/imc_base/control_desk_corner_imc_01.phy
models/imc_base/thumper_generator_set_b_animated.phy
models/imc_base/scaffold_tech_adjustbeam_128.phy
models/imc_base/generator_imc_01.phy
models/imc_base/roof_corner_garage_imc_03.phy
models/imc_base/monitor_large_imc_01.phy
models/imc_base/roof_corner_garage_imc_01.phy
models/imc_base/beam_base_clamp_imc_01.phy
models/imc_base/outer_wall_imc_column_02.phy
models/imc_base/landing_pad_center_arm.phy
models/imc_base/chair_imc_01.phy
models/imc_base/windowframe_armor_128_opened_imc_02.phy
models/imc_base/imc_pipe_med_curve90.phy
models/imc_base/imc_pipe_med_curve90_grey.phy
models/imc_base/cargo_container_imc_01_white_open.phy
models/imc_base/cargo_container_imc_01_green_open.phy
models/imc_base/outer_wall_imc_01_closed.phy
models/imc_base/landing_pad_arm_top.phy
models/imc_base/roof_corner_garage_imc_02.phy
models/imc_base/column_base_imc_01.phy
models/imc_base/hangar_girder_45_imc_01.phy
models/imc_base/landing_pad_arm_topstrut.phy
models/imc_base/garage_blast_shield_imc_01.phy
models/imc_base/cargo_refrigerated_imc_01.phy
models/imc_base/bldg_frame_front_b_imc_02.phy
models/imc_base/bldg_frame_front_b_imc_03.phy
models/imc_base/hinge_arm_metal_imc_02.phy
models/imc_base/hinge_arm_metal_imc_01.phy
models/imc_base/thumper_shocks_rail.phy
models/imc_base/thumper_platform_grid_corner.phy
models/imc_base/bldg_frame_front_b_imc_01.phy
models/imc_base/bldg_frame_front_a_imc_03.phy
models/imc_base/bldg_frame_front_a_imc_02.phy
models/imc_base/landing_pad_top_strut.phy
models/imc_base/landing_pad_base_strut.phy
models/imc_base/barracks_bed_imc_01.phy
models/imc_base/landing_pad_arm_bottstrut.phy
models/imc_base/bldg_frame_front_a_imc_01.phy
models/imc_base/bldg_wall_support_imc_01.phy
models/imc_base/bldg_window_front_b_imc_01.phy
models/imc_base/thumper_generator_set_b_static.phy
models/imc_base/outer_wall_imc_01.phy
models/imc_base/bldg_window_front_a_imc_01.phy
models/imc_base/outer_gate_imc_closed.phy
models/imc_base/roof_swing_imc_01.phy
models/imc_base/swing_arm_imc_01.phy
models/imc_base/landing_pad_tarmac.phy
models/imc_base/hangar_gantry_imc_01.phy
models/imc_base/trolley_imc.phy
models/creatures/flyer/flyer_anims.phy
models/creatures/flyer/flyer_a_1000x.phy
models/robots/marvin/marvin_no_jiggle.mdl
models/metal_scraps/scrap_metal_vent02.mdl
models/metal_scraps/scrap_metal_hinge02.mdl
models/signs/billboard_fracture/billboard_fracture_frame_3.mdl
models/angel_city/manhole_cover_01.mdl
models/angel_city/box_small_01.mdl
models/angel_city/box_small_02.mdl
models/buildings/windows/window_frame_tech_01.mdl
models/signs/signage_plates_metal/sign_plate_a.mdl
models/signs/signage_plates_metal/sign_plate_d.mdl
models/signs/signage_plates_metal/sign_plate_c.mdl
models/signs/signage_plates_metal/sign_plate_b.mdl
models/signs/signage_plates_metal/sign_post_plate_a.mdl
models/signs/signage_plates_metal/sign_post_plate_d.mdl
models/signs/signage_plates_metal/sign_post_plate_e.mdl
models/signs/signage_plates_metal/sign_post_plate_h.mdl
models/signs/signage_plates_metal/sign_post_plate_c.mdl
models/signs/signage_plates_metal/sign_post_plate_b.mdl
models/hardware/paint_spraycan_closed.mdl
models/hardware/paint_container_plastic.mdl
models/barriers/metal_parking_post_yell.mdl
models/fx/carrier_jet_glow.mdl
models/fx/energy_hld_01.mdl
models/signs/billboard_airbase/airbase_sign_01.mdl
models/signs/billboard_airbase/airbase_sign_02.mdl
models/commercial/desk_lamp.mdl
models/electricalboxes/littlelectricbox_b.mdl
models/electricalboxes/littlelectricbox_a.mdl
models/electricalboxes/pipe_set_g.mdl
models/electricalboxes/pipe_endcap.mdl
models/electricalboxes/pipe_bracket_a.mdl
models/electricalboxes/fuseboxnodoor.mdl
models/electricalboxes/fusebox.mdl
models/electricalboxes/pipe_set_b.mdl
models/signs/billboard_supports01.mdl
models/stairs/stairs_imc01_support_slope10.mdl
models/stairs/stairs_imc01_single.mdl
models/stairs/stair_base_modular_imc_04.mdl
models/stairs/stair_base_modular_imc_03.mdl
models/stairs/stair_base_modular_imc_02.mdl
models/stairs/stair_base_modular_imc_05.mdl
models/stairs/stair_base_modular_imc_01.mdl
models/domestic/wall_panel_fiberglass_corner.mdl
models/domestic/working_floor_light.mdl
models/domestic/working_floor_light_on.mdl
models/relic/relic_ship_beams_64.mdl
models/relic/relic_ship_beams_128.mdl
models/handrails/handrail_yellow_corner90.mdl
models/handrails/handrail_yellow_end.mdl
models/handrails/handrail_yellow_32.mdl
models/handrails/handrail_yellow_48.mdl
models/handrails/railing_imc_post.mdl
models/handrails/railing_imc_banister_short_slope10.mdl
models/handrails/railing_imc_16in.mdl
models/handrails/railing_imc_banister_bottom_slope10.mdl
models/handrails/railing_imc_banister_long_slope10.mdl
models/handrails/railing_industrial_normal.mdl
models/handrails/handrail_yellow_64.mdl
models/handrails/railing_imc_banister_top_slope10.mdl
models/handrails/railing_imc_32in.mdl
models/handrails/railing_imc_64in.mdl
models/handrails/handrail_yellow_96.mdl
models/handrails/handrail_yellow_128.mdl
models/handrails/railing_imc_corner.mdl
models/vehicle/capital_ship_wallace/capital_ship_wallace_1000x.mdl
models/turrets/turret_imc_lrg.mdl
models/weapons/drums/triplethreat_drum.mdl
models/weapons/drums/xo_16_drum.mdl
models/weapons/drums/titan_rocket_launcher_drum.mdl
models/vehicle/imc_carrier/imc_carrier_airbase.mdl
models/pipes/airduct_xl_vent.mdl
models/pipes/duct_metal_large_cap.mdl
models/pipes/duct_metal_large_hatch_bottom.mdl
models/pipes/duct_metal_large_40.mdl
models/pipes/pipe_painted_red.mdl
models/pipes/duct_metal_large_128.mdl
models/pipes/duct_metal_large_corner_01.mdl
models/pipes/duct_metal_large_hatch_top.mdl
models/pipes/pipe_refinery_port.mdl
models/pipes/duct_round_elbow_90.mdl
models/pipes/duct_round_straight.mdl
models/pipes/pipe_refinery_frame.mdl
models/pipes/pipe_refinery_cap.mdl
models/pipes/duct_metal_large_vent_64.mdl
models/pipes/pipe_refinery_section128.mdl
models/pipes/duct_round_straight_45.mdl
models/pipes/pipe_refinery_section80.mdl
models/pipes/wall_pipes_control_set01.mdl
models/pipes/pipe_ceiling_gray_set.mdl
models/pipes/pipes_wall_02.mdl
models/pipes/wall_pipes_control_set02.mdl
models/pipes/pipes_wall_01.mdl
models/weapons/ammoboxes/ammobox_bigclip.mdl
models/weapons/ammoboxes/backpack_single.mdl
models/weapons/ammoboxes/ammobox_01.mdl
models/weapons/ammoboxes/ammobox_missle.mdl
models/weapons/ammoboxes/ammobox_bigbullet.mdl
models/weapons/ammoboxes/ammo_backpacks.mdl
models/weapons/p2011/p2011_handgun_ab_01.mdl
models/lamps/light_imc_ceiling_guard_32.mdl
models/lamps/light_podlight01.mdl
models/lamps/light_imc_ceiling_command_64_end_on.mdl
models/lamps/light_imc_ceiling_command_128_on.mdl
models/lamps/industrial_wall_light_on.mdl
models/lamps/interior_can_light_on.mdl
models/lamps/interior_can_light_holder.mdl
models/lamps/warning_light.mdl
models/lamps/warning_light_on_orange.mdl
models/lamps/runway_light_2ft_blue_on.mdl
models/lamps/light_imc_ceiling_command_center.mdl
models/lamps/light_wall_industrial.mdl
models/lamps/light_hanging_industrial.mdl
models/lamps/light_hanging_industrial_on.mdl
models/lamps/interrogation_light_rail.mdl
models/lamps/light_fc.mdl
models/lamps/light_fc_off.mdl
models/lamps/light_parking_post.mdl
models/lamps/industrial_construction_lights_on.mdl
models/lamps/light_ontrack_fc.mdl
models/furniture/office_desk_accessories_papers.mdl
models/furniture/chair_45angle_metal.mdl
models/furniture/chair_anim_prop.mdl
models/furniture/shelves_industrial_01.mdl
models/furniture/shelves_industrial_01_wires.mdl
models/industrial/electric_cable_pipes_thin_a_imc.mdl
models/industrial/crowbar_orange.mdl
models/industrial/hammer_metal_01.mdl
models/industrial/beam_imc_metal_gray.mdl
models/industrial/traffic_construction_light_01.mdl
models/industrial/hammer_mallet.mdl
models/industrial/tibilisi_support_cross_beams_round.mdl
models/industrial/screwdriver_01.mdl
models/industrial/screwdriver_02.mdl
models/industrial/hammer_metal_02.mdl
models/industrial/tool_chest_top.mdl
models/industrial/metal_girder_beams_128.mdl
models/industrial/modular_railing_trim_mid.mdl
models/industrial/modular_railing_trim_short.mdl
models/industrial/modular_railing_trim_a.mdl
models/industrial/modular_railing_trim_c.mdl
models/industrial/security_fence_post.mdl
models/industrial/workshop_gloves.mdl
models/industrial/modular_railing_trim_long.mdl
models/industrial/service_hatch_ground.mdl
models/industrial/reciprocating_saw.mdl
models/industrial/hose_nozzle01.mdl
models/industrial/gun_rack_arm_down.mdl
models/industrial/traffic_barrel_03.mdl
models/industrial/workshop_goggles.mdl
models/industrial/metal_beam_support_vertical_short.mdl
models/industrial/tripod_cone_v1_low_on.mdl
models/industrial/stand_alone_air_vent_02.mdl
models/industrial/metal_awning.mdl
models/industrial/tripod_cone_v1_high_on.mdl
models/industrial/tibilisi_leg_support_metal02.mdl
models/industrial/metal_brace_corner_footer.mdl
models/industrial/work_cart_plastic.mdl
models/industrial/console_tower_rack_imc.mdl
models/industrial/gas_mask.mdl
models/industrial/tool_chest_double.mdl
models/industrial/suspended_monitor_imc.mdl
models/industrial/tool_chest.mdl
models/industrial/comm_relay.mdl
models/industrial/weapons_locker.mdl
models/industrial/zipline_arm.mdl
models/industrial/utg_spire.mdl
models/industrial/imc_generator.mdl
models/industrial/satellite_antenna.mdl
models/holo_screens/screen_bar_frame.mdl
models/holo_screens/screen_writing_monitor.mdl
models/holo_screens/screen_writing_monitor_orange.mdl
models/holo_screens/monitor_command_small_imc_screen_01.mdl
models/holo_screens/monitor_command_small_imc_screen_map.mdl
models/holo_screens/monitor_hood_imc_01_screen_text.mdl
models/holo_screens/monitor_hood_imc_02_screen_text.mdl
models/holo_screens/monitor_hood_imc_01_screen_text_02.mdl
models/holo_screens/monitor_command_imc_screen_map.mdl
models/holo_screens/monitor_command_imc_screen_01.mdl
models/holo_screens/military_screen_map_scroll.mdl
models/holo_screens/medical_screen_scanner.mdl
models/holo_screens/military_screen_graphs_scroll.mdl
models/holo_screens/monitor_command_small_imc_screen_graph.mdl
models/holo_screens/monitor_command_imc_screen_graph.mdl
models/holo_screens/holo_screen_wallshape.mdl
models/holo_screens/hologram_dropship.mdl
models/holo_screens/hologram_map_workerbase.mdl
models/holo_screens/hologram_spider_turret_fracture.mdl
models/utilities/halogen_lightbulb_case.mdl
models/utilities/ceiling_vent_metal.mdl
models/utilities/wire_bundle_01.mdl
models/utilities/wire_bundle_02.mdl
models/utilities/wire_bundle_03.mdl
models/utilities/wires_hanging_64.mdl
models/utilities/wire_ceiling_mounts_straight.mdl
models/utilities/wire_ceiling_mounts_corner.mdl
models/utilities/wire_wall_section.mdl
models/utilities/utility_hatchround_metal01_static.mdl
models/utilities/utility_hatchround_metal01_open.mdl
models/utilities/power_gen1.mdl
models/containers/box_large_cardboard.mdl
models/containers/box_small_cardboard.mdl
models/containers/box_med_cardboard_01.mdl
models/containers/box_med_cardboard_02.mdl
models/containers/box_med_cardboard_03.mdl
models/containers/styrofoam_box_short_dirty.mdl
models/containers/styrofoam_box_dirty.mdl
models/containers/crate_blue_plastic.mdl
models/containers/box_med_plastic.mdl
models/containers/gas_tank.mdl
models/containers/box_large_plastic.mdl
models/containers/box_shrinkwrapped.mdl
models/containers/plastic_pallet_01.mdl
models/containers/plastic_pallet_02.mdl
models/containers/box_metal.mdl
models/containers/crate_orange_plastic.mdl
models/containers/barrel.mdl
models/containers/barrel_explosive.mdl
models/containers/pelican_case_large.mdl
models/containers/pelican_case_large_drabgreen.mdl
models/containers/cargo_container_blue_separate.mdl
models/containers/cargo_container_orange_separate.mdl
models/containers/cargo_container_black_separate.mdl
models/containers/cargo_container_white_separate.mdl
models/containers/cargo_container_red_separate.mdl
models/containers/cargo_container_teal_separate.mdl
models/containers/cargo_container_grey_separate.mdl
models/containers/pelican_case_large_open.mdl
models/containers/pelican_case_large_open_drabgreen.mdl
models/containers/pelican_case_ammobox.mdl
models/containers/cargo_container_grey_orange_teal_combined.mdl
models/containers/cargo_container_red_black_blue_combined.mdl
models/door/door_tech_02_frame.mdl
models/door/bunker_door_frame_96x120.mdl
models/door/door_imc_interior_03_128.mdl
models/door/door_imc_interior_64_frame.mdl
models/door/door_imc_interior_03_128_frame.mdl
models/door/pod_door_hangar_imc_01.mdl
models/door/pod_door_hangar_imc_01_open.mdl
models/vehicle/mobile_turret/mobile_turret_proxy.mdl
models/vehicle/mobile_turret/gun_mount_bottom.mdl
models/vehicle/mobile_turret/mobile_turret.mdl
models/levels_terrain/mp_airbase/airbase_dogwhistle_spotlight01.mdl
models/levels_terrain/mp_airbase/airbase_dogwhistle_tower_distant01.mdl
models/vehicle/forklift_imc/forklift_imc.mdl
models/colony/antenna_dish_colony_broken_01.mdl
models/colony/antenna_post_colony_broken_01.mdl
models/colony/antenna_02_colony.mdl
models/colony/antenna_03_colony.mdl
models/colony/antenna_06_colony.mdl
models/communication/terminal_usable_airbase.mdl
models/communication/radar_tower_imc_01.mdl
models/vehicle/vehicle_samson_truck/vehicle_samson_with_gear.mdl
models/vehicle/paladin/paladin_static.mdl
models/vehicle/goblin_dropship/goblin_dropship_static.mdl
models/vehicle/goblin_dropship/goblin_dropship_placed.mdl
models/vehicle/straton/straton_imc_gunship_01_1000x.mdl
models/vehicle/straton/straton_imc_gunship_static.mdl
models/vehicle/straton/straton_anims_1000x.mdl
models/vistas/bomber_single01.mdl
models/vistas/straton_single01.mdl
models/vistas/airebase_se_alpha.mdl
models/vistas/planet_blue_sun.mdl
models/vistas/airbase_se_buildings.mdl
models/imc_base/imc_tech_panel_64_01.mdl
models/imc_base/imc_tech_panelsquare_48_05.mdl
models/imc_base/imc_tech_tallpanel_48_02.mdl
models/imc_base/control_command_top_desk_imc_01_64.mdl
models/imc_base/control_command_top_desk_imc_01_32.mdl
models/imc_base/conduit_cap_imc_01.mdl
models/imc_base/conduit_str_16_imc_02.mdl
models/imc_base/cable_thin_terminator_cieling_01.mdl
models/imc_base/beam_t_32_imc_01.mdl
models/imc_base/beam_t_64_imc_01.mdl
models/imc_base/vent_air_imc_02.mdl
models/imc_base/conduit_cap_imc_02.mdl
models/imc_base/floor_clasp_imc_01.mdl
models/imc_base/floor_clasp_imc_02.mdl
models/imc_base/locker_divider_top_imc_01.mdl
models/imc_base/conduit_str_32_imc_02.mdl
models/imc_base/imc_vent_tall_128.mdl
models/imc_base/beam_i_128_imc_01.mdl
models/imc_base/conduit_str_16_imc_01.mdl
models/imc_base/beam_t_128_imc_01.mdl
models/imc_base/bulk_head_footer_imc_02.mdl
models/imc_base/imc_fan_large_01_animated.mdl
models/imc_base/conduit_start_imc_02.mdl
models/imc_base/window_frame_ceiling_imc_128.mdl
models/imc_base/pipe_ceiling_imc_str_01.mdl
models/imc_base/pipe_ceiling_imc_str_02.mdl
models/imc_base/conduit_bracket_imc_04.mdl
models/imc_base/pipe_ceiling_sml_imc_str_01.mdl
models/imc_base/conduit_str_64_imc_02.mdl
models/imc_base/conduit_bend_16_imc_02.mdl
models/imc_base/locker_divider_imc_01.mdl
models/imc_base/conduit_str_32_imc_01.mdl
models/imc_base/bldg_wall_corner_imc_01.mdl
models/imc_base/scaffold_tech_vert_a.mdl
models/imc_base/scaffold_tech_horz_rail_b.mdl
models/imc_base/beam_i_256_imc_01.mdl
models/imc_base/clasp_wall_imc_01.mdl
models/imc_base/beam_i_64_imc_01.mdl
models/imc_base/roof_corner_garage_imc_03.mdl
models/imc_base/beam_t_256_imc_01.mdl
models/imc_base/scaffold_tech_solidrail_128.mdl
models/imc_base/roof_corner_garage_imc_02.mdl
models/imc_base/monitor_panel_01.mdl
models/imc_base/monitor_panel_02.mdl
models/imc_base/scaffold_tech_vert_rail_c.mdl
models/imc_base/table_wall_mounted_imc_01.mdl
models/imc_base/conduit_bracket_imc_02.mdl
models/imc_base/pipe_ceiling_imc_str_03.mdl
models/imc_base/pipe_ceiling_sml_imc_str_03.mdl
models/imc_base/pipe_ceiling_imc_bend_02.mdl
models/imc_base/pipe_ceiling_sml_imc_bend_01.mdl
models/imc_base/ladder_modular_cap_imc.mdl
models/imc_base/conduit_start_imc_01.mdl
models/imc_base/pipe_ceiling_imc_end_01.mdl
models/imc_base/pipe_ceiling_imc_bend_01.mdl
models/imc_base/pipe_ceiling_sml_imc_end_01.mdl
models/imc_base/vent_air_imc_01.mdl
models/imc_base/bldg_wall_support_imc_02.mdl
models/imc_base/imc_pipe_med_curve45_grey.mdl
models/imc_base/roof_corner_garage_imc_01.mdl
models/imc_base/imc_fan_large_01.mdl
models/imc_base/conduit_str_64_imc_01.mdl
models/imc_base/roof_swing_imc_01.mdl
models/imc_base/pipe_ceiling_imc_junc_02.mdl
models/imc_base/pipe_ceiling_imc_junc_01.mdl
models/imc_base/beam_i_512_imc_01.mdl
models/imc_base/garage_support_wall_imc_02.mdl
models/imc_base/bulk_head_footer_imc_01.mdl
models/imc_base/control_command_desk_post_imc_01_ext.mdl
models/imc_base/camera_imc_base_01.mdl
models/imc_base/command_trim_imc_01_128.mdl
models/imc_base/control_command_desk_post_imc_02_16.mdl
models/imc_base/imc_tech_smallpanel_48_03.mdl
models/imc_base/thumper_platform_grid.mdl
models/imc_base/imc_pipe_med_32.mdl
models/imc_base/control_command_desk_imc_02_64.mdl
models/imc_base/imc_pipe_med_32_grey.mdl
models/imc_base/control_command_desk_imc_01_32.mdl
models/imc_base/bldg_frame_front_a_imc_03.mdl
models/imc_base/bldg_frame_front_a_imc_02.mdl
models/imc_base/pipe_ceiling_imc_end_02.mdl
models/imc_base/pipe_ceiling_sml_imc_end_02.mdl
models/imc_base/conduit_bend_16_imc_01.mdl
models/imc_base/light_wall_imc_01.mdl
models/imc_base/light_wall_imc_01_on.mdl
models/imc_base/light_wall_imc_02_on.mdl
models/imc_base/cable_thin_ceiling_64_02.mdl
models/imc_base/cable_thin_ceiling_64_01.mdl
models/imc_base/beam_i_turn_90_01.mdl
models/imc_base/thumper_generator_set_b_animated.mdl
models/imc_base/imc_pipe_med_curve90.mdl
models/imc_base/imc_pipe_med_curve90_grey.mdl
models/imc_base/locker_wall_imc_01.mdl
models/imc_base/locker_wall_imc_02.mdl
models/imc_base/bldg_glass_front_a_imc_01.mdl
models/imc_base/imc_fan_large_tube_01.mdl
models/imc_base/handle_modular_imc_lod0.mdl
models/imc_base/imc_pipe_med_cap.mdl
models/imc_base/imc_pipe_med_ring_02.mdl
models/imc_base/monitor_arm_02.mdl
models/imc_base/scaffold_tech_horz_rail_c.mdl
models/imc_base/imc_pipe_med_64.mdl
models/imc_base/scaffold_tech_brace_02.mdl
models/imc_base/imc_pipe_med_64_grey.mdl
models/imc_base/imc_antenna_01.mdl
models/imc_base/monitor_arm_01.mdl
models/imc_base/imc_keyboard_01.mdl
models/imc_base/control_command_desk_post_imc_01_16.mdl
models/imc_base/control_desk_imc_02.mdl
models/imc_base/monitor_arm_rack_01.mdl
models/imc_base/monitor_hood_imc_02.mdl
models/imc_base/monitor_hood_imc_04.mdl
models/imc_base/monitor_hood_imc_01.mdl
models/imc_base/beam_metal_hinge_imc_01.mdl
models/imc_base/monitor_hood_imc_03.mdl
models/imc_base/bldg_frame_front_a_imc_01.mdl
models/imc_base/scaffold_tech_beam_128.mdl
models/imc_base/bracket_corner_imc_01.mdl
models/imc_base/hangar_girder_45_imc_01.mdl
models/imc_base/scaffold_tech_adjustbeam_128.mdl
models/imc_base/imc_pipe_med_ring_01.mdl
models/imc_base/control_desk_imc_01.mdl
models/imc_base/clasp_ceiling_imc_02.mdl
models/imc_base/scaffold_tech_alpharail_128.mdl
models/imc_base/scaffold_tech_alpharaillong_128.mdl
models/imc_base/light_wall_imc_03_on.mdl
models/imc_base/light_wall_imc_03.mdl
models/imc_base/siren_wall_imc_01.mdl
models/imc_base/wire_hanging_imc_long_02.mdl
models/imc_base/wire_hanging_imc_short_01.mdl
models/imc_base/monitor_imc_03.mdl
models/imc_base/garage_support_wall_imc_01.mdl
models/imc_base/beam_wall_support_imc_01.mdl
models/imc_base/imc_pipe_med_32_02.mdl
models/imc_base/corner_piston_imc_01.mdl
models/imc_base/bldg_wall_support_imc_01_half.mdl
models/imc_base/connector_90_deg_01.mdl
models/imc_base/imc_tech_smallfan_32_06.mdl
models/imc_base/bomb_imc_01.mdl
models/imc_base/experiment_tank_column_single.mdl
models/imc_base/wall_handle_imc_01.mdl
models/imc_base/monitor_command_small_imc_02.mdl
models/imc_base/monitor_command_imc_01.mdl
models/imc_base/monitor_command_small_imc_01.mdl
models/imc_base/imc_tech_pipepanel_92_04.mdl
models/imc_base/bldg_frame_front_b_imc_03.mdl
models/imc_base/cargo_bomb_rack01.mdl
models/imc_base/scaffold_tech_frame_bottom_128.mdl
models/imc_base/imc_pipe_med_128.mdl
models/imc_base/bldg_frame_front_b_imc_02.mdl
models/imc_base/column_support_imc_01.mdl
models/imc_base/imc_pipe_med_128_grey.mdl
models/imc_base/outer_wall_imc_column_02.mdl
models/imc_base/imc_pipe_med_mount_01.mdl
models/imc_base/bldg_frame_front_b_imc_01.mdl
models/imc_base/scaffold_tech_frame_top_128.mdl
models/imc_base/console_door_small_imc_01.mdl
models/imc_base/cable_thin_ceiling_32_01.mdl
models/imc_base/chain_link_post_imc_01.mdl
models/imc_base/thumper_platform_steps.mdl
models/imc_base/thumper_platform_grid_corner.mdl
models/imc_base/buttress_imc_01.mdl
models/imc_base/landing_pad_foot.mdl
models/imc_base/cables_modular_med_imc_03.mdl
models/imc_base/cables_modular_med_imc_02.mdl
models/imc_base/dispenser_wall_imc_01.mdl
models/imc_base/cables_modular_med_imc_01.mdl
models/imc_base/cable_plugs_floor01.mdl
models/imc_base/ceiling_plugs_imc_01.mdl
models/imc_base/bldg_wall_support_imc_01.mdl
models/imc_base/ladder_modular_64_imc.mdl
models/imc_base/imc_fan_large_case_01.mdl
models/imc_base/monitor_imc_02.mdl
models/imc_base/pillar_base_tile_imc_01.mdl
models/imc_base/bldg_frame_interior_b_imc_01.mdl
models/imc_base/bldg_window_front_b_imc_01.mdl
models/imc_base/control_desk_corner_imc_01.mdl
models/imc_base/chair_imc_02.mdl
models/imc_base/holo_projector_large_imc_arm.mdl
models/imc_base/imc_pipe_base_01.mdl
models/imc_base/bldg_window_front_a_imc_01.mdl
models/imc_base/thumper_support_single_shock.mdl
models/imc_base/scaffold_tech_halfwalk.mdl
models/imc_base/scaffold_tech_solidrail_11u.mdl
models/imc_base/landing_pad_top_strut.mdl
models/imc_base/worker_base_whistle_tower_holo.mdl
models/imc_base/beam_base_clamp_imc_01.mdl
models/imc_base/landing_pad_cables.mdl
models/imc_base/chair_imc_01.mdl
models/imc_base/garage_wall_arm_imc_02.mdl
models/imc_base/garage_wall_arm_imc_01.mdl
models/imc_base/imc_pipe_med_256.mdl
models/imc_base/monitor_imc_01.mdl
models/imc_base/garage_blast_shield_imc_01.mdl
models/imc_base/barrier_low_airport_imc.mdl
models/imc_base/imc_pipe_med_256_grey.mdl
models/imc_base/ladder_aircraft_imc_01.mdl
models/imc_base/ceiling_plugs_imc_02.mdl
models/imc_base/camera_imc_01.mdl
models/imc_base/radar_g_skybox.mdl
models/imc_base/radar_c_skybox.mdl
models/imc_base/radar_d_skybox.mdl
models/imc_base/radar_i_skybox.mdl
models/imc_base/radar_g.mdl
models/imc_base/radar_c.mdl
models/imc_base/radar_d.mdl
models/imc_base/radar_i.mdl
models/imc_base/landing_pad_center_arm.mdl
models/imc_base/windowframe_armor_128_opened_imc_02.mdl
models/imc_base/hinge_arm_metal_imc_02.mdl
models/imc_base/windowframe_armor_128_closed_imc_01.mdl
models/imc_base/chain_link_imc_01.mdl
models/imc_base/radar_f_skybox.mdl
models/imc_base/radar_b_skybox.mdl
models/imc_base/radar_f.mdl
models/imc_base/radar_b.mdl
models/imc_base/hinge_arm_metal_imc_01.mdl
models/imc_base/landing_pad_arm_bottstrut.mdl
models/imc_base/landing_pad_arm_top.mdl
models/imc_base/hangar_gantry_support01.mdl
models/imc_base/landing_pad_base_strut.mdl
models/imc_base/thumper_shocks_rail.mdl
models/imc_base/landing_pad_arm_topstrut.mdl
models/imc_base/imc_pipe_med_512.mdl
models/imc_base/imc_pipe_med_512_grey.mdl
models/imc_base/generator_imc_01.mdl
models/imc_base/radar_e_skybox.mdl
models/imc_base/radar_h_skybox.mdl
models/imc_base/radar_a_skybox.mdl
models/imc_base/cargo_container_imc_01_green_open.mdl
models/imc_base/cargo_container_imc_01_white_open.mdl
models/imc_base/radar_a.mdl
models/imc_base/barracks_bed_imc_01.mdl
models/imc_base/radar_h.mdl
models/imc_base/radar_e.mdl
models/imc_base/outer_gate_imc_closed.mdl
models/imc_base/holo_projector_large_imc.mdl
models/imc_base/pod_door_hangar_imc_01.mdl
models/imc_base/cargo_container_imc_01_red.mdl
models/imc_base/cargo_container_imc_01_white.mdl
models/imc_base/cargo_container_imc_01_green.mdl
models/imc_base/cargo_container_imc_01_orange.mdl
models/imc_base/cargo_container_imc_01_blue.mdl
models/imc_base/trolley_imc.mdl
models/imc_base/outer_wall_imc_01.mdl
models/imc_base/column_base_imc_01.mdl
models/imc_base/outer_wall_imc_01_closed.mdl
models/imc_base/thumper_generator_set_b_static.mdl
models/imc_base/swing_arm_imc_01.mdl
models/imc_base/hangar_gantry_imc_01.mdl
models/imc_base/landing_pad_tarmac.mdl
models/imc_base/worker_base_whistle_tower_skybox.mdl
models/imc_base/worker_base_whistle_tower.mdl
models/imc_base/cargo_refrigerated_imc_01.mdl
models/vehicle/ship_tow_tugger/vehicle_ship_trailer_gate.mdl
models/vehicle/ship_tow_tugger/vehicle_ship_tow_tugger_large.mdl
models/vehicle/ship_tow_tugger/vehicle_ship_tow_trailer.mdl
models/creatures/leviathan/leviathan_holo_medium.mdl
models/creatures/leviathan/leviathan_brown_airbase_small.mdl
models/creatures/leviathan/leviathan_brown_airbase_medium.mdl
models/creatures/leviathan/leviathan_brown_airbase_large.mdl
models/vehicle/imc_bomber/bomber_rear_exhaust_1.mdl
models/vehicle/imc_bomber/bomber_r_exhaust_1.mdl
models/vehicle/imc_bomber/bomber_l_exhaust_1.mdl
models/vehicle/imc_bomber/bomber_l_exhaust_2.mdl
models/vehicle/imc_bomber/bomber_r_exhaust_2.mdl
models/vehicle/imc_bomber/bomber.mdl
models/vehicle/imc_bomber/bomber_parked.mdl
models/creatures/flyer/flyer_static_flying.mdl
models/creatures/flyer/flyer_a_1000x.mdl
models/creatures/flyer/flyer_a.mdl
models/creatures/flyer/flyer_a_500x.mdl
models/creatures/flyer/flyer_anims_500x.mdl
models/creatures/flyer/flyer_anims_1000x.mdl
models/creatures/flyer/flyer_anims.mdl
models/unique/redeye/redeye_flyer_path_1000x.mdl
models/unique/redeye/redeye_flyer_path_500x.mdl
models/unique/redeye/redeye_flyer_path.mdl
maps/mp_airbase_env.ent
maps/mp_airbase_snd.ent
maps/mp_airbase_spawn.ent
maps/mp_airbase_fx.ent
maps/mp_airbase_script.ent
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp
maps/mp_airbase.bsp
depot/r1dev/game/r1/maps/mp_airbase.bsp
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007f.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007d.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007c.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.007b.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0079.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0078.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0077.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0076.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0075.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0074.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0073.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0072.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0071.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0070.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006f.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006d.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006c.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006b.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.006a.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0069.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0068.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0067.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0066.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0065.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0064.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0063.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0062.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0061.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0060.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005f.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005d.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005c.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005b.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.005a.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0059.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0058.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0057.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0056.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0055.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0053.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0052.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0051.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0050.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.004f.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.004a.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0049.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0047.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0046.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0045.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0044.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0042.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0036.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.002c.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.002b.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.002a.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0028.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0023.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.001e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.001d.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0018.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.000e.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0003.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0002.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0001.bsp_lump
depot/r1pcstaging/game/r1/maps/mp_airbase.bsp.0000.bsp_lump
maps/mp_airbase.bsp.007f.bsp_lump
maps/mp_airbase.bsp.007e.bsp_lump
maps/mp_airbase.bsp.007d.bsp_lump
maps/mp_airbase.bsp.007c.bsp_lump
maps/mp_airbase.bsp.007b.bsp_lump
maps/mp_airbase.bsp.0079.bsp_lump
maps/mp_airbase.bsp.0078.bsp_lump
maps/mp_airbase.bsp.0077.bsp_lump
maps/mp_airbase.bsp.0076.bsp_lump
maps/mp_airbase.bsp.0075.bsp_lump
maps/mp_airbase.bsp.0074.bsp_lump
maps/mp_airbase.bsp.0073.bsp_lump
maps/mp_airbase.bsp.0072.bsp_lump
maps/mp_airbase.bsp.0071.bsp_lump
maps/mp_airbase.bsp.0070.bsp_lump
maps/mp_airbase.bsp.006f.bsp_lump
maps/mp_airbase.bsp.006e.bsp_lump
maps/mp_airbase.bsp.006d.bsp_lump
maps/mp_airbase.bsp.006c.bsp_lump
maps/mp_airbase.bsp.006b.bsp_lump
maps/mp_airbase.bsp.006a.bsp_lump
maps/mp_airbase.bsp.0069.bsp_lump
maps/mp_airbase.bsp.0068.bsp_lump
maps/mp_airbase.bsp.0067.bsp_lump
maps/mp_airbase.bsp.0066.bsp_lump
maps/mp_airbase.bsp.0065.bsp_lump
maps/mp_airbase.bsp.0064.bsp_lump
maps/mp_airbase.bsp.0063.bsp_lump
maps/mp_airbase.bsp.0062.bsp_lump
maps/mp_airbase.bsp.0061.bsp_lump
maps/mp_airbase.bsp.0060.bsp_lump
maps/mp_airbase.bsp.005f.bsp_lump
maps/mp_airbase.bsp.005e.bsp_lump
maps/mp_airbase.bsp.005d.bsp_lump
maps/mp_airbase.bsp.005c.bsp_lump
maps/mp_airbase.bsp.005b.bsp_lump
maps/mp_airbase.bsp.005a.bsp_lump
maps/mp_airbase.bsp.0059.bsp_lump
maps/mp_airbase.bsp.0058.bsp_lump
maps/mp_airbase.bsp.0057.bsp_lump
maps/mp_airbase.bsp.0056.bsp_lump
maps/mp_airbase.bsp.0055.bsp_lump
maps/mp_airbase.bsp.0053.bsp_lump
maps/mp_airbase.bsp.0052.bsp_lump
maps/mp_airbase.bsp.0051.bsp_lump
maps/mp_airbase.bsp.0050.bsp_lump
maps/mp_airbase.bsp.004f.bsp_lump
maps/mp_airbase.bsp.004a.bsp_lump
maps/mp_airbase.bsp.0049.bsp_lump
maps/mp_airbase.bsp.0047.bsp_lump
maps/mp_airbase.bsp.0046.bsp_lump
maps/mp_airbase.bsp.0045.bsp_lump
maps/mp_airbase.bsp.0044.bsp_lump
maps/mp_airbase.bsp.0042.bsp_lump
maps/mp_airbase.bsp.0036.bsp_lump
maps/mp_airbase.bsp.002c.bsp_lump
maps/mp_airbase.bsp.002b.bsp_lump
maps/mp_airbase.bsp.002a.bsp_lump
maps/mp_airbase.bsp.0028.bsp_lump
maps/mp_airbase.bsp.0023.bsp_lump
maps/mp_airbase.bsp.001e.bsp_lump
maps/mp_airbase.bsp.001d.bsp_lump
maps/mp_airbase.bsp.0018.bsp_lump
maps/mp_airbase.bsp.000e.bsp_lump
maps/mp_airbase.bsp.0003.bsp_lump
maps/mp_airbase.bsp.0002.bsp_lump
maps/mp_airbase.bsp.0001.bsp_lump
maps/mp_airbase.bsp.0000.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007f.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007e.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007d.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007c.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.007b.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0079.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0078.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0077.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0076.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0075.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0074.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0073.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0072.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0071.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.0070.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.006f.bsp_lump
depot/r1dev/game/r1/maps/mp_airbase.bsp.006e.bsp_lump
depot/r1dev/game/r1/m
Same results for Titanfall 2, crashes on all files, and no output, unless i'm missing something important here?

Hm, I'll have to check that file - what command are you running?
## Post #61
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-03T17:34:24+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from tschumann ↑Sun Jan 03, 2021 5:47 pm at Sun Jan 03, 2021 5:47 pm
>
> 
Hm, I'll have to check that file - what command are you running?
Again, that was just an example, every single file has same result on both Titanfall games:

```
gssmt.exe englishclient_mp_airbase.bsp.pak000_dir.vpk -x
```
## Post #62
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2021-01-25T01:53:27+00:00
- Post Title: Re: TitanFall (.vpk) archives

Sorry, I haven't had a chance to check this yet - been busy.
englishclient_frontend.bsp.pak000_dir.vpk from Titanfall 2 and englishclient_mp_common.bsp.pak000_dir.vpk from Apex Legends are the test files I use - do they work for you? And are you copying across all the other .vpk files too? Extraction won't work unless all the pak00*_00*.vpk files are in the same directory.
## Post #63
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-25T20:05:00+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from tschumann ↑Mon Jan 25, 2021 9:53 am at Mon Jan 25, 2021 9:53 am
>
> ...do they work for you? And are you copying across all the other .vpk files too? Extraction won't work unless all the pak00*_00*.vpk files are in the same directory.
Every single file i try has same result on my end as i mentioned, and i used the tool in the VPK directory, there for every file was there nothing has been changed/removed.
## Post #64
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2021-01-26T04:41:06+00:00
- Post Title: Re: TitanFall (.vpk) archives

Can you try copying the .vpk files to your desktop say and run the extraction from there? It may not have permission to write to the Origin directory.
## Post #65
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-27T04:57:15+00:00
- Post Title: Re: TitanFall (.vpk) archives

> Reply from tschumann ↑Tue Jan 26, 2021 12:41 pm at Tue Jan 26, 2021 12:41 pm
>
> ...It may not have permission to write to the Origin directory.
Your joking, right?
Who keeps their games in C drive yet alone "Program Files"?
And, no its not a permission issue at all, the program simply does no extraction only outputs a log then it crashes, nothing else happens.
Does it need some sort of prerequisites?
## Post #66
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2021-01-27T19:27:09+00:00
- Post Title: Re: TitanFall (.vpk) archives

No, that's how Windows has its permissions set by default - Program Files and similar don't seem to be writable by a normal user.

Did you copy gssmt into Program Files?
## Post #67
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-28T03:38:05+00:00
- Post Title: Re: TitanFall (.vpk) archives

Hm, thought it was already self explanatory, my games are NOT in Program Files there for has nothing to do with permissions.
Everything resides in a different HDD, i did NOT have to copy it in Program Files as there are no games there to begin with, the tool does not work, or at least not on my end.
## Post #68
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2021-01-29T06:00:25+00:00
- Post Title: Re: TitanFall (.vpk) archives

Okay, I understand now.
I'm not sure what the problem is though - I tested on my computer and the files get extracted in the directory where gssmt is located. If it can't extract it segfaults. Do you get a crash dump? I can't remember where exactly they get created but somewhere in C:\Users\you
