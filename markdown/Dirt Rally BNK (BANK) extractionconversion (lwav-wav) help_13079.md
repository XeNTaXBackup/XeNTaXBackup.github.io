## Post #1
- Username: drdoomslab
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 22, 2014 9:40 pm
- Post datetime: 2015-07-19T21:33:53+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

Hi guys,

I'm trying to extract and convert some audio from Dirt Rally and am running into difficulty's. I think its a Wwise BNK Fmod files as i found some xml files saying Wwise in it so i used the Wwise_bnk_fmod.bms script and got a bunch of .lwav files (seemed to work). They do not appear to play correctly in FooBar2000 (with VGMStream plugin) so i converted them to .wav with Video Game Sound Converter but its still playing static back. I also tryed towav (didn't seem to do anything) and ww2ogg (gave a Parse error: expected 0x42 fmt if vorb missing) but no luck.

This is the first time i've tryed to convert an BNK file from fmod. Am i doing something wrong? Am i using the wrong commands? Is it because its FMOD?

I have a file with some of the .lwav, .wav and the original .bnk. Could you audio wizards point me in the right direction?

Please can you help me?
Many thanks in advance.
Cheers,

DrDoomsLab.
## Post #2
- Username: drdoomslab
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 22, 2014 9:40 pm
- Post datetime: 2015-07-21T04:28:43+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

Hi guys,

I've been trying again with this and have managed to extract some .WEM files. But i'm getting an error when trying to convert using ww2ogg 

```
Audiokinetic Wwise RIFF/RIFX Vorbis to Ogg Vorbis converter 0.22 by hcs
Input: BANKDATA.001.wem
Parse error: expected 0x42 fmt if vorb missing
```


This is the same error that Kein had with Trine 3 WEMs so i tryed importing the .WEM in Audacity using RAW import but i've had no luck with it so far, just static. I'm quite new to this so am feeling a little lost. I have not much clue what settings to use when importing. I've tryed quite a few combos but have had no luck yet. What am i doing wrong? 

I would really appreciate some input.
Cheers.

DrDoomsLab.
## Post #3
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-07-21T08:03:02+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

These are WWise ADPCM files, so you need to use [this converter](http://forums.lastbullet.net/showthread.php?tid=101).
## Post #4
- Username: drdoomslab
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 22, 2014 9:40 pm
- Post datetime: 2015-07-21T13:42:56+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

> Reply from barti
>
> These are WWise ADPCM files, so you need to use this converter.

Hi barti,

Thank you for this info. This seems to have worked. Very useful. Have a grate one.
Cheers,

DrDoomsLab.

Edit: does anyone know what *.bdl files are? and/or how to extract them?
Edit Edit: from what i've found .bdl files have not yet been figured out. They are linked to the codemasters sound engine somehow but no one so far has found any audio in them.
## Post #5
- Username: RadeonX1950
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 21, 2010 3:28 pm
- Post datetime: 2015-07-31T12:12:00+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

Thanks for the reply barti, it works  But I have a problem with output .wav files. Some tracks are distorted (it seems like a incorrect frequency setup)
## Post #6
- Username: olliraa
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 15, 2015 1:42 am
- Post datetime: 2015-12-14T19:30:35+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

Still having problems with the Dirt Rally bnk-files. I can extract the files to wem witHout problems, but then basically nothing works (converting to wav etc.). I've tried the wwisetool, but it crashes all the time?

Has someone done this? I'd like to do my own pacenotes 

Thnks!
## Post #7
- Username: olliraa
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 15, 2015 1:42 am
- Post datetime: 2015-12-16T09:34:16+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

> Reply from olliraa
>
> Still having problems with the Dirt Rally bnk-files. I can extract the files to wem witHout problems, but then basically nothing works (converting to wav etc.). I've tried the wwisetool, but it crashes all the time?

Has someone done this? I'd like to do my own pacenotes 

Thnks!

I got it working  bnk -> wem -> wav -> back to wem

Haven't tried building the bnk-files back. One problem:  The encoded wem-files are huge compared to the original ones. Is this by design, or am I just stupid? For example the original wem was 11KB and the encoded (from wav) wem was over 5MB. The wav was 2 seconds long and 32Khz 16-bit mono. I used the  Wwise Sound Tool.

Any clues?
## Post #8
- Username: Palo Samo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 23, 2015 3:04 am
- Post datetime: 2015-12-22T19:08:47+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

Your custom .wav has to be 48Hz and exactly the same length as the original one. Then it is possible to encode it to .wem. Nevertheless, it is not possible to pack it to the soundbank, even though wwisetool.exe says it was done.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-25T19:47:12+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

> Reply from drdoomslab
>
> from what i've found .bdl files have not yet been figured out. They are linked to the codemasters sound engine somehow but no one so far has found any audio in them.

BDL files decoded here:

[viewtopic.php?f=10&t=13681](http://forum.xentax.com/viewtopic.php?f=10&t=13681)
## Post #10
- Username: Palo Samo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 23, 2015 3:04 am
- Post datetime: 2015-12-26T08:22:36+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

I have finally done it!
## Post #11
- Username: giacomo90
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 09, 2016 10:49 am
- Post datetime: 2016-01-11T00:50:19+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

Hi guys, someone finds files of sound engine?
thx
## Post #12
- Username: Palo Samo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 23, 2015 3:04 am
- Post datetime: 2016-01-11T08:44:36+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

If I understand you correctly then yes, I have
## Post #13
- Username: giacomo90
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 09, 2016 10:49 am
- Post datetime: 2016-01-11T13:52:53+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

> Reply from Palo Samo
>
> If I understand you correctly then yes, I have
can you tell me the names of the banks where they are?
thx!
## Post #14
- Username: Palo Samo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 23, 2015 3:04 am
- Post datetime: 2016-01-11T17:08:26+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

General sounds soundbanks are located in ../DiRT Rally/audio/soundbanks
Co-Driver calls soundbanks are located in ..DiRT Rally/tracks/locations/ and then respective countries, eg.g finland/ouninpohja_rally_01/banks
## Post #15
- Username: InYoFace
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 24, 2016 9:06 pm
- Post datetime: 2016-01-24T13:09:00+00:00
- Post Title: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) help

> Reply from Palo Samo
>
> General sounds soundbanks are located in ../DiRT Rally/audio/soundbanks
Co-Driver calls soundbanks are located in ..DiRT Rally/tracks/locations/ and then respective countries, eg.g finland/ouninpohja_rally_01/banks

Hey!

I read the topic but i'm stuck. I would like to convert engine sounds to a usable mp3 or wav format to use it in another game. How do I do that exactly? 

I found the engine sound location.
## Post #16
- Username: Palo Samo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 23, 2015 3:04 am
- Post datetime: 2016-02-02T22:48:17+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

I'm sorry, I posted locations for Co-Driver sounds. Try end export the sounds using Ravioli Scanner.
## Post #17
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-22T21:37:28+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from daemon1
>
> drdoomslab wrote:from what i've found .bdl files have not yet been figured out. They are linked to the codemasters sound engine somehow but no one so far has found any audio in them.

BDL files decoded here:

viewtopic.php?f=10&t=13681

BDL files from DIRT RALLY its not decoded with your tool but ai BDL yes.  However, this is the great work thanks.

I'd like to try to improve some engine sounds but I need a tool to inject my own files in these BDL files.

If it were possible that would be great...
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-23T06:41:25+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from Tiger33
>
> BDL files from DIRT RALLY its not decoded with your tool

Send me examples. They are all a little different.
## Post #19
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-23T07:09:52+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from daemon1
>
> Tiger33 wrote:BDL files from DIRT RALLY its not decoded with your tool

Send me examples. They are all a little different.

Ok Dirt Rally BDL file :

[http://dl.free.fr/r18aEVHsc](http://dl.free.fr/r18aEVHsc)
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-23T07:20:54+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

I remember now. Codec 2 is actually no codec. You can open them with any audio editor as plain 16-bit PCM
## Post #21
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-23T07:33:38+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from daemon1
>
> I remember now. Codec 2 is actually no codec. You can open them with any audio editor as plain 16-bit PCM

Sorry but with your tool the samples from BDL file is not extracted Only from " AI BDL"
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-23T08:03:43+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from Tiger33
>
> daemon1 wrote:I remember now. Codec 2 is actually no codec. You can open them with any audio editor as plain 16-bit PCM

Sorry but with your tool the samples from BDL file is not extracted Only from " AI BDL"

You don't need to extract them! They can be opened already.
## Post #23
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-23T12:07:12+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

Sorry but I don't understand.

Paste/open the BDL file on your tool and extract 4 samples but only folder "ai bdl" work .

So it's not a problem because "ai bdl" with same name ".bdl" is heard  in place of original one in game (apparently only the sampling rate change)

Is there a way to import our modified samples in place original in this bdl file ?

Thank you for your interest.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-23T13:30:53+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from Tiger33
>
> Sorry but I don't understand.

Ok, let's try it once again.

Do you have an audio editor? Audition? Sound forge? Whatever you use do EDIT sounds?

Open it. Then open .bdl file from it.

If asked, say it is PCM 16-bit, 48000 khz.

After it's done, I'll try and explain how to edit that.
## Post #25
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-23T19:38:57+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from daemon1
>
> Tiger33 wrote:Sorry but I don't understand.

Ok, let's try it once again.

Do you have an audio editor? Audition? Sound forge? Whatever you use do EDIT sounds?

Open it. Then open .bdl file from it.

If asked, say it is PCM 16-bit, 48000 khz.

After it's done, I'll try and explain how to edit that.

Ok I usually work with Audition and audacity.
If I open the bdl file  with these audio editors I can only import in "RAW" format 16 bit 48000 khz mono.. so it's inaudible.
The samples are one after the other on the same audio track.

But maybe it is more easily editable now?
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-24T17:14:08+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from Tiger33
>
> But maybe it is more easily editable now?

No. This tool was made to extract files that couldn't be extracted before.
The use unique codemasters codec, never seen anywhere else.
## Post #27
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-24T20:30:03+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from daemon1
>
> Tiger33 wrote:But maybe it is more easily editable now?

No. This tool was made to extract files that couldn't be extracted before.
The use unique codemasters codec, never seen anywhere else.

So there is no no way to export, edit, and reimport new samples in bdl file ?
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-26T20:24:41+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from Tiger33
>
> So there is no no way to export, edit, and reimport new samples in bdl file ?

You can edit them directly in Audition. If you don't mess it, and don't change length, it will work.
## Post #29
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-27T09:22:12+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from daemon1
>
> Tiger33 wrote:So there is no no way to export, edit, and reimport new samples in bdl file ?

You can edit them directly in Audition. If you don't mess it, and don't change length, it will work.

I understand but I can not add or replace the samples because I can not hear them. 
Audition open bdl file only in raw format.
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-27T14:25:35+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from Tiger33
>
> I understand but I can not add or replace the samples because I can not hear them. 
Audition open bdl file only in raw format.

Really? When I open it in audition as RAW, I can play them without problems. You're doing something wrong.

How are you doing it?
## Post #31
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-27T16:24:21+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

I realized my mistake .  

With Audition if I open the bdl file that can be found in  "ai" folder I can not hear the samples, but if I open bdl file in "bundle" folder  it's ok.

To test I tried to change the power of the samples but when I save I have a message telling me that I saved in a format that could degrade the sound (raw).

So when I test in game I get an  CTD withe the affected car.. However the file is exactly the same in size and characteristics are the same (48000 hz, 16 bit mono, pcm )...

Any idea ?

I continue to search.
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-27T16:43:31+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

You must be careful, and do not touch the parts of the file where tables are located.

You can easily see 4 them in the beginning of each sample inside the file.
## Post #33
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-27T22:05:33+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from daemon1
>
> You must be careful, and do not touch the parts of the file where tables are located.

You can easily see 4 them in the beginning of each sample inside the file.

Thanks for the tips but  if I replace a portion of sample with another even if the length and size of the new bdl are identical ..ctd ..what a shame! 

bdl modified at the end of 4th sample:

[http://dl.free.fr/getfile.pl?file=/ulLmpLCX](http://dl.free.fr/getfile.pl?file=/ulLmpLCX)

and original bdl :

[http://dl.free.fr/getfile.pl?file=/YhGHj7Hn](http://dl.free.fr/getfile.pl?file=/YhGHj7Hn)
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-28T06:21:13+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from Tiger33
>
> Thanks for the tips but  if I replace a portion of sample with another even if the length and size of the new bdl are identical

You modified the WHOLE sample (changed power) and this ruined the tables.
Then you modified the end of 4th sample.

Revert back to the original file. Modify only the end of 4th sample and it will work.
## Post #35
- Username: romaw
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 05, 2016 11:51 pm
- Post datetime: 2018-07-07T15:16:11+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

hi, is replace the music in game possible?
## Post #36
- Username: kimmysawi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 27, 2018 5:06 pm
- Post datetime: 2018-08-06T09:42:51+00:00
- Post Title: Re: Dirt Rally BNK (BANK) extraction/conversion (lwav->wav) 

> Reply from drdoomslab
>
> barti wrote:These are WWise ADPCM files, so you need to use this converter.

Hi barti,

Thank you for this info. This seems to have worked. Very useful. Have a grate one.
Cheers, PhenQ

DrDoomsLab.

Edit: does anyone know what *.bdl files are? and/or how to extract them?
Edit Edit: from what i've found .bdl files have not yet been figured out. They are linked to the codemasters sound engine somehow but no one so far has found any audio in them.

Those asian creeds are make these things over to market these bridal things lol
