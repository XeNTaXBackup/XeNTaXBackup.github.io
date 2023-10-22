## Post #1
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-14T21:00:56+00:00
- Post Title: Mortal Kombat X sound format

It's something about FMOD, but i can't see any FSB header, only the FEV file. Can someone take a look and manage how to unpack mkx sounds?

[https://mega.co.nz/#!IsRDABjI!135retu2s ... 43NZvTPgZ4](https://mega.co.nz/#!IsRDABjI!135retu2spYU5WTUn8HZWM895qbDsQwV143NZvTPgZ4)

Update. Fsb files are encrypted. The key is 996164B5FC0F402983F61F220BB51DC6 , but steel need unpacker for .xxx files, cause gildor's extractor doesn't work.
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-15T12:22:55+00:00
- Post Title: Mortal Kombat X sound format

For example I took "scorpion". Package is not compressed. It exports 200 fmodevent files and the remaining part is audio data starting from 0x2CF23. Maybe it will help you.
## Post #3
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2015-04-15T13:34:35+00:00
- Post Title: Mortal Kombat X sound format

> Reply from daemon1
>
> For example I took "scorpion". Package is not compressed. It exports these 200 files and the remaining part is audio data starting from 0x2CF23. Maybe it will help you.

Hello! and you do not tell what kind of tool to extract you use?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-15T14:00:38+00:00
- Post Title: Mortal Kombat X sound format

> Reply from ponaromixxx
>
> Hello! and you do not tell what kind of tool to extract you use?

I have my own set of experimental tools to work with UE3. They are not ready to be published, because many things are done manually.

Gildor will soon update his tools for MK X support.
## Post #5
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2015-04-15T14:41:43+00:00
- Post Title: Mortal Kombat X sound format

> Reply from daemon1
>
> ponaromixxx wrote:Hello! and you do not tell what kind of tool to extract you use?

I have my own set of experimental tools to work with UE3. They are not ready to be published, because many things are done manually.

Gildor will soon update his tools for MK X support.

And you can try your achievements?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-16T10:16:22+00:00
- Post Title: Mortal Kombat X sound format

All issues resolved. It was relatively easy to unpack the sounds with fmod using their provided API. Working on the tool now.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-16T12:12:21+00:00
- Post Title: Mortal Kombat X sound format

Here you go, a universal FSB extractor for any formats. Needs fmodL.dll from the official fmod package. No error handling, no interface, because I'm lazy. Just give it the .fsb name and it will put all the sounds contained in .WAV format into the same folder.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-16T12:23:27+00:00
- Post Title: Mortal Kombat X sound format

Okay so its giving me a side by side config error when i try to run it even with the fmod DLL in the same directory.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-16T12:34:56+00:00
- Post Title: Mortal Kombat X sound format

> Reply from OrangeC
>
> Okay so its giving me a side by side config error when i try to run it even with the fmod DLL in the same directory.

It was compiled with MSVC2008, so maybe you need to update your vc++ 2008 runtimes. I don't have another version now, sorry.
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-16T13:01:17+00:00
- Post Title: Mortal Kombat X sound format

I see i installed the visual 2008 runtimes both x84 and x64 but stilll nothing.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-16T13:01:34+00:00
- Post Title: Mortal Kombat X sound format

Recompiled and updated the tool in release version, it must not give you errors now. Please also note that you need the latest fmodL.dll, because it will not work with old versions.
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-16T13:12:04+00:00
- Post Title: Mortal Kombat X sound format

Doesn't give me the error anymore but it just crashes instead. Have the latest DLL too.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-16T13:18:36+00:00
- Post Title: Mortal Kombat X sound format

> Reply from OrangeC
>
> Doesn't give me the error anymore but it just crashes instead. Have the latest DLL too.

You must give it one filename as parameter, it must be unencrypted .fsb file. If it doesn't work, send me that .fsb in PM and i will check it.
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-16T13:34:35+00:00
- Post Title: Mortal Kombat X sound format

Ahh okay.

And as you said there are no tools to support the MK archives?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-16T13:39:09+00:00
- Post Title: Mortal Kombat X sound format

> Reply from OrangeC
>
> Ahh okay.

And as you said there are no tools to support the MK archives?

So did it work?

I have a tool, but it is experimental. It just drops the whole bunch of files info one directory, and in case some files have same names, it overwrites them. I need time to correct this, if anyone needs this.
## Post #16
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-16T15:41:34+00:00
- Post Title: Re: Mortal Kombat X sound format

It works with a couple of fsb's lying about.
## Post #17
- Username: slaesche
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 10, 2012 8:53 pm
- Post datetime: 2015-04-17T02:18:46+00:00
- Post Title: Re: Mortal Kombat X sound format

I would like to use the experimental tool.
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-17T13:57:34+00:00
- Post Title: Re: Mortal Kombat X sound format

ok, testing it now. Animations, models, textures... it seems everything is there. But there will be just hundreds of files in one directory. And they are package-dependent, in UE3 format. I don't know what can you do with them.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-18T07:43:24+00:00
- Post Title: Re: Mortal Kombat X sound format

A little mistake found in wav header (data length calculated twice longer). Updated the old post:

[viewtopic.php?p=105280#p105280](http://forum.xentax.com/viewtopic.php?p=105280#p105280)
## Post #20
- Username: Micadi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 08, 2014 10:34 am
- Post datetime: 2015-04-18T12:45:03+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from OrangeC
>
> Doesn't give me the error anymore but it just crashes instead. Have the latest DLL too.

I'm having the same error, but knowing myself I'm doing something wrong.
So in case of my complete stupidity I would want to ask you to guide me a little here.

I put your extractor, fmodL.dll (from offical FMOD site - I got it from FMOD Studio UE4 Engine Integration for Windows) and the file I want to extract sounds from (for example  SND_SPEECH_JAX_ENG.xxx for example) into the same folder.
Then I run your extractor and after 2 seconds it crashes.

What am I missing? Probably something insanely easy >>
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-18T17:51:56+00:00
- Post Title: Re: Mortal Kombat X sound format

First you need to extract .fsb files from .xxx package and decrypt them.
## Post #22
- Username: Micadi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 08, 2014 10:34 am
- Post datetime: 2015-04-18T19:03:28+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from daemon1
>
> First you need to extract .fsb files from .xxx package and decrypt them.

Ok then, which tools should I use for it for the best result?
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-18T19:14:42+00:00
- Post Title: Re: Mortal Kombat X sound format

There's not many choices today: first you cut .fbs files from .xxx with Luigi's script, then decrypt them with his tool "fsbext". The script and encryption key are on top on this thread: [http://zenhax.com/viewtopic.php?f=6&t=833](http://zenhax.com/viewtopic.php?f=6&t=833)
## Post #24
- Username: crazymonkey25
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 23, 2013 5:09 am
- Post datetime: 2015-04-27T08:01:29+00:00
- Post Title: Re: Mortal Kombat X sound format

Has anyone managed to extract character audio for moves/SFX/battle voices yet?
## Post #25
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2015-04-27T10:31:12+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from crazymonkey25
>
> Has anyone managed to extract character audio for moves/SFX/battle voices yet?

No. I have been trying. daemon1 says you can manually cut the fsb's out (I did this with injustice by searching the FSB5 header) but MKX doesn't seem to have FSB headers. I did a dump with the tools posted in this script, tried this key several times (996164B5FC0F402983F61F220BB51DC6) no luck... tried naming this file to .fsb - SND_SPEECH_Scorpion_X64DataSource.FmodSourceData no luck. tried the fsbext on all extracted fmod files, nothing... so I need further help. I'm hoping someone can make an .fsb extraction tool then fsbext can do the rest.
## Post #26
- Username: crazymonkey25
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 23, 2013 5:09 am
- Post datetime: 2015-04-27T18:38:47+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from MusicNerd
>
> crazymonkey25 wrote:Has anyone managed to extract character audio for moves/SFX/battle voices yet?

No. I have been trying. daemon1 says you can manually cut the fsb's out (I did this with injustice by searching the FSB5 header) but MKX doesn't seem to have FSB headers. I did a dump with the tools posted in this script, tried this key several times (996164B5FC0F402983F61F220BB51DC6) no luck... tried naming this file to .fsb - SND_SPEECH_Scorpion_X64DataSource.FmodSourceData no luck. tried the fsbext on all extracted fmod files, nothing... so I need further help. I'm hoping someone can make an .fsb extraction tool then fsbext can do the rest.Ah gotcha. Yeah I tried the same thing, renaming a file like SND_SFX_Jax_X64DataSourceBank.FmodSourceData and it didn't work. I'm assuming the .FmodSourceData files contain the actual audio (seeing as the file size isn't just 1kb like everything else from the extract). So maybe they are referenced by the FMOD project/event files the NR devs worked with. 

But yeah for now this is kinda beyond me.
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-27T18:59:59+00:00
- Post Title: Re: Mortal Kombat X sound format

Each xxx may have many "fmodsourcedata" files, half of them encrypted, half not. You must somehow cut the first 32 bytes of them, then it will be one FSB file.
## Post #28
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2015-04-27T21:16:42+00:00
- Post Title: Re: Mortal Kombat X sound format

I was able to extract some characters sounds.
Here is an example.

1- use extract.exe (by Gildor) with CHAR_Jax_A.xxx now you have a folder with name CHAR_Jax_A
2- in audio folder there are audio, of course, but other sounds are located in Characters > Chars > Your character name > SND_your character and now you have SND_SFX_your char & SND_VO_your char, in both you need to enter in a sub folder with same name.
Now (i SND_VO_Jax) you have the SND_VO_Jax_X64DataSourceBank_0.FmodSourceData
3- open with an hexadecimal editor and delete all before FSB5, save as fsb
4- use fsbext or fsb_aud_extr

For some reason the fxs has the text FSB5 in another place and this method doesn't work.
I have no idea of this format, so maybe someone can take a look at it
## Post #29
- Username: crazymonkey25
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 23, 2013 5:09 am
- Post datetime: 2015-04-27T22:08:05+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from interloko
>
> I was able to extract some characters sounds.
Here is an example.

1- use extract.exe (by Gildor) with CHAR_Jax_A.xxx now you have a folder with name CHAR_Jax_A
2- in audio folder there are audio, of course, but other sounds are located in Characters > Chars > Your character name > SND_your character and now you have SND_SFX_your char & SND_VO_your char, in both you need to enter in a sub folder with same name.
Now (i SND_VO_Jax) you have the SND_VO_Jax_X64DataSourceBank_0.FmodSourceData
3- open with an hexadecimal editor and delete all before FSB5, save as fsb
4- use fsbext or fsb_aud_extr

For some reason the fxs has the text FSB5 in another place and this method doesn't work.
I have no idea of this format, so maybe someone can take a look at it
Interesting. I'll try this out when I get home!
## Post #30
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2015-04-27T22:55:54+00:00
- Post Title: Re: Mortal Kombat X sound format

I've checked all characters and a few of them are diferent   
Devora'h (ladybug) is the exception with sfx. seems she is the only one with FSB5 "text" at the begining, so I supose I can extract her SFXs
## Post #31
- Username: crazymonkey25
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 23, 2013 5:09 am
- Post datetime: 2015-04-28T01:17:44+00:00
- Post Title: Re: Mortal Kombat X sound format

Okay so I see what you're saying. I managed to do Jax's Foley sounds because it had the FSB5. But like you said, when you try the SFX, there' s no FSB5. Tricky.

Btw did you end up with OGG Vorbis files when you did the Jax extract? I can't see to open them with anything, wondering if I did something wrong.

edit: nvm got it, I wasn't using the suitable FSB extractor. "fsb_aud_extr" worked like a charm. I'm feeling like a genius right now even though I'm doing the most basic, noobish shit  . Props to all you dudes who know how to code and program, you make everything easy for guys like me haha.
## Post #32
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2015-04-29T07:27:47+00:00
- Post Title: Re: Mortal Kombat X sound format

I tried what was suggested above (I am working on Scorpions VO file SND_SPEECH_SCORPION_ENG.XXX) and no matter what no FSB header. This is Madness! 
I can see in the file the packed .wav file references, if I look at the .fev file I can see the 3 .fsb file containers but when I look at the source data file no headers. I am guessing this is an issue with the extract.exe or fsb dumper tool that was posted earlier. If It's not dumping at the correct offset the fsb headers are being cut off... Any further suggestions guys?
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-29T15:15:12+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from MusicNerd
>
> SND_SPEECH_SCORPION_ENG.XXX

Packages of this type have encrypted FSBs outside of package structure, just appended to the end of it. You can split them with Luigi's script. [http://zenhax.com/viewtopic.php?f=6&t=833](http://zenhax.com/viewtopic.php?f=6&t=833)
## Post #34
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2015-04-29T17:30:50+00:00
- Post Title: Re: Mortal Kombat X sound format

It's cool that you guys are making progress with this stuff. 

Was trying to extract the contents of SND_VO_Raiden_X64DataSourceBank_0.FmodSourceData, but ran into some problems.  So after I deleted all the lines above FSB5 and saved it as an fsb file I tried to extract the contents using both fsbext and fsb_aud_extr.  fsbext gave me an output of 110 ogg files that seemed unplayable, like crazymonkey25 said above.  Then I tried fsb_aud_extr and got 5 wav files as output (the command screen seemed like it was frozen or like it was still trying to output more files, but nothing came out).  I was able to play the wav files, but they came out distorted, almost like slo mo.

Any idea what the problem is?  I probably screwed something up along the way like a fool.  Thanks.
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-29T18:12:28+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from Seifer29
>
> I tried fsb_aud_extr and got 5 wav files as output (the command screen seemed like it was frozen or like it was still trying to output more files, but nothing came out).

This must be an error in official FMOD library. It hangs on "readData" function. It must either give me an error code or work, but it just hangs. We can wait until they find and fix this, or you can try "player ex".
## Post #36
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2015-04-29T21:29:16+00:00
- Post Title: Re: Mortal Kombat X sound format

Holy crap, it works, lol.  Just plugged the SND_VO_Raiden_X64DataSourceBank_0.fsb into musicplayer ex and it allowed me to convert the sounds and extract them as playable wavs.  It contains all of Raiden's combat sounds.  Assuming this works for the rest of the cast, as well.  

Thanks a bunch guys.

EDIT:  Ah, I see what you guys mean about certain files not having the FSB5 line.  Those won't open in music player ex.  Some files have it and some don't for some reason.
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-30T04:17:20+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from Seifer29
>
> Some files have it and some don't for some reason.

Those other files have them encrypted. Just check all DataSourceBank files.
## Post #38
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2015-04-30T15:19:10+00:00
- Post Title: Re: Mortal Kombat X sound format

Hey Daemon,

So is there any way to decrypt the files so that music player ex will recognize them as fsb files?  The method used for the other ones was to delete the first two lines before the FSB5 line and save it as an fsb file.  What would the method be for the encrypted file?

Sorry for the constant questions.
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-30T15:31:48+00:00
- Post Title: Re: Mortal Kombat X sound format

Delete first 32 bytes, then decrypt the file the way mentioned above.
## Post #40
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2015-04-30T16:57:57+00:00
- Post Title: Re: Mortal Kombat X sound format

Alright Daemon, it worked.  Thanks for the help.
## Post #41
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-30T17:27:59+00:00
- Post Title: Re: Mortal Kombat X sound format

OK, here's temporary workaround for these small sounds which freezes the extractor.

Somehow (i think by error in fmod official library) for MONO files, instead of sound length in bytes it returns twice smaller number, and then hangs when i try to read the sound. 2-,4-,6-channel files extracts without this problem. So I make it double the size only for mono files. That is wrong, but it works now. Suggestions welcome.

p.s. there was no error. See below.
## Post #42
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2015-04-30T18:02:12+00:00
- Post Title: Re: Mortal Kombat X sound format

Tested it out with CHAR_Mileena_A.xxx. It seems to have extracted most if not all of the encrypted SFX files, however most of the VO files weren't extracted correctly since they're at 1KB in size.
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-30T19:58:51+00:00
- Post Title: Re: Mortal Kombat X sound format

[file deleted, new version uploaded below]

Ok, problem was when the whole FSB file is marked as stereo, then fmod extracts all individual files as stereo, though they all can actually be mono. The same is probably true for other channel combinations.

So this new version ignores what's written in individual sound properties, and extracts all the files with the channel count given in FSB. At least it works for all files that i have now.
## Post #44
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2015-04-30T20:10:32+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from daemon1
>
> Ok, problem was when the whole FSB file is marked as stereo, then fmod extracts all individual files as stereo, though they all can actually be mono. The same is probably true for other channel combinations.

So this new version ignores what's written in individual sound properties, and extracts all the files with the channel count given in FSB. At least it works for all files that i have now.
Tested it. Extracted all the files successfully this time.  

Thanks a bunch, and great work!
## Post #45
- Username: crazymonkey25
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 23, 2013 5:09 am
- Post datetime: 2015-05-01T02:31:04+00:00
- Post Title: Re: Mortal Kombat X sound format

Holy crap, extracting the audio from all the characters works perfect now. You guys are amazing. Thank you!
## Post #46
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2015-05-05T04:23:38+00:00
- Post Title: Re: Mortal Kombat X sound format

You Guys Rule! 
Thanks for everyone that worked on this format
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-01T09:52:18+00:00
- Post Title: Re: Mortal Kombat X sound format

Latest version that will output numbered filenames if there are none inside of FSB. Also some basic error handling added, maybe something else, I can't remember now.
[fsb_aud_extr.rar](https://xentaxbackup.github.io/file/9474_fsb_aud_extr.rar)
## Post #48
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2015-09-02T13:10:34+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from daemon1
>
> Latest version that will output numbered filenames if there are none inside of FSB. Also some basic error handling added, maybe something else, I can't remember now.

thx tool,but not support PC game MAD MAX fsb5?
Samples：
[http://www17.zippyshare.com/v/1Ur2mWgE/file.html](http://www17.zippyshare.com/v/1Ur2mWgE/file.html)
## Post #49
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-02T15:40:29+00:00
- Post Title: Re: Mortal Kombat X sound format

This file is corrupted or it's not FSB file. FMOD doesn't support it.
## Post #50
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-09-02T17:32:45+00:00
- Post Title: Re: Mortal Kombat X sound format

Other FSB tools report the FSB using the celt codec.

Update: The file can be imported into FMOD Designer and exported as an FSB WAV.

Here's the [FSB WAV](http://www75.zippyshare.com/v/jJ6EGZPh/file.html)
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-02T17:37:48+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from brendan19
>
> Other FSB tools report the FSB using the celt codec.

This tool uses official FMOD library. If this library can't unpack this codec, I can't do anything about it. Or just wait till they'll support it in their API.
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-24T16:57:01+00:00
- Post Title: Re: Mortal Kombat X sound format

A new version of FMOD FSB extractor, that supports all of the formats. Strange enough, but using their old fmodex.dll library, we can now extract all of the latest FSB archives, including these .celt

I don't know what to do with the previous tool now. If testing will show that this tool work in all cases, I think I can remove it.
[fmod_extr.rar](https://xentaxbackup.github.io/file/9776_fmod_extr.rar)
## Post #53
- Username: wriggles
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 02, 2015 7:15 pm
- Post datetime: 2015-10-02T11:19:39+00:00
- Post Title: Re: Mortal Kombat X sound format

Has anyone uploaded the character files or know of any links?
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-02T15:10:44+00:00
- Post Title: Re: Mortal Kombat X sound format

What character files?
## Post #55
- Username: wriggles
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 02, 2015 7:15 pm
- Post datetime: 2015-10-02T15:23:22+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from daemon1
>
> What character files?
The voice files =)
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-02T16:56:22+00:00
- Post Title: Re: Mortal Kombat X sound format

All the tools for character voices are published, you can extract them all.
## Post #57
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2015-12-01T04:40:23+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from daemon1
>
> All the tools for character voices are published, you can extract them all.

thx tool,find not support PC game Just Cause 3 fsb5?
Samples：
[http://www64.zippyshare.com/v/9DGigmng/file.html](http://www64.zippyshare.com/v/9DGigmng/file.html)
## Post #58
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-01T15:39:21+00:00
- Post Title: Re: Mortal Kombat X sound format

Use my previous tool. It seems you need to try both. Some files are only extracted with only old or only new method. While some are working with both.
## Post #59
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-02T23:53:53+00:00
- Post Title: Re: Mortal Kombat X sound format

Thank you for your extractor - it's a bit choosy, though.
I had an elder fmodex.dll version and got this error message:
FMOD lib version279634 less than header version 279638

so I decided to patch your exe:



fmodex_dll_4-44-52.jpg (83.7 KiB) Viewed 57 times


Replaced two bytes (56) by 52 each - worked fine with an FSB5 file.

(I know that's very risky but I was too tired to search for the suiting dll version since there are way too many to be found in the web.)
## Post #60
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-03T04:23:03+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from shakotay2
>
> (I know that's very risky but I was too tired to search for the suiting dll version since there are way too many to be found in the web.)

Why wouldn't you just download the latest one from the official site of FMOD ?
## Post #61
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-12-03T11:23:00+00:00
- Post Title: Re: Mortal Kombat X sound format

You need to download the FMOD Ex Programmer’s API. But Firelight have now made it so you have to at least register in order to download any of their programs excluding the FMOD Studio Authoring Tool.
Registration is free to do.

Regardless, here are the latest DLLs.
[FMOD DLLs](http://www71.zippyshare.com/v/gfhmlOZL/file.html)
## Post #62
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-03T12:44:55+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from daemon1
>
> Why wouldn't you just download the latest one from the official site of FMOD ?Because of this sentence of yours:

> Reply from daemon1
>
> Strange enough, but using their old fmodex.dll library, we can now extract all of the latest FSB archives, including theseI was not sure whether the fsb I had would be handled.

It would just be just nice if your exe didn't have that version number hardcoded.
## Post #63
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-03T18:57:44+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from shakotay2
>
> Because of this sentence of yours:
daemon1 wrote:Strange enough, but using their old fmodex.dll library, we can now extract all of the latest FSB archives, including these

Sorry for misunderstanding, that was not about old VERSION of the same DLL, but about their old project. So I had to make 2 different tools. Moved them to a new thread now.

[viewtopic.php?f=17&t=13615](http://forum.xentax.com/viewtopic.php?f=17&t=13615)

Anyway, this check was in their example project, and I think it was done on purpose. With wrong DLL you can get sound decoded wrong. I still hate that Dying Light music "RIP" on the net, decoded with clicks and hiss.
## Post #64
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-03T18:59:12+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from brendan19
>
> Firelight have now made it so you have to at least register in order to download any of their programs excluding the FMOD Studio Authoring Tool.
Registration is free to do.

Bad sign. Good idea to save their DLLs now.
## Post #65
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2016-02-12T00:39:15+00:00
- Post Title: Re: Mortal Kombat X sound format

tool support ea game Unravel, but decoding is not complete?
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-12T04:23:20+00:00
- Post Title: Re: Mortal Kombat X sound format

what tool? Example files?
## Post #67
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2016-02-13T00:29:01+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from daemon1
>
> what tool? Example files?

Samples：
[https://mega.nz/#!oEYClRab!XeEdMMFJo4XB ... kjZN5ljXFI](https://mega.nz/#!oEYClRab!XeEdMMFJo4XBwwYqJhunge2U8CIfIeIv9kjZN5ljXFI)


use fsbext get 100 files,use fmod_extr get 78 files,why???
## Post #68
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-13T06:01:33+00:00
- Post Title: Re: Mortal Kombat X sound format

Many files inside this are called the same. So they are overwritten.

For example, there are about 5 files with the name "tema 1".
## Post #69
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2016-02-13T08:40:50+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from daemon1
>
> Many files inside this are called the same. So they are overwritten.

For example, there are about 5 files with the name "tema 1".

So, 78 files is complete extract?
## Post #70
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2016-02-13T08:50:52+00:00
- Post Title: Re: Mortal Kombat X sound format

Many files inside this are called the same, but different sizes。。
## Post #71
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-13T09:02:04+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from mappy2012
>
> Many files inside this are called the same, but different sizes。。

That's what i told you. Same names, so they are overwritten.
## Post #72
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-02-15T06:25:44+00:00
- Post Title: Re: Mortal Kombat X sound format

Is there anyway to implement a solution where they aren't overwritten by adding a "_1" or something to that description.
## Post #73
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-15T15:44:24+00:00
- Post Title: Re: Mortal Kombat X sound format

> Reply from brendan19
>
> Is there anyway to implement a solution where they aren't overwritten by adding a "_1" or something to that description.

This will require me changing the code. I don't have time for this now.
