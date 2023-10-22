## Post #1
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-02-11T00:19:29+00:00
- Post Title: War Thunder FSB

I have Tried to extract the FSB files to War Thunder and it would not extract using Music Player Ex. Anyone Else know how to open These files for this game?
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-02-11T01:53:49+00:00
- Post Title: War Thunder FSB

Try Aluigi's [FSBExt](http://aluigi.altervista.org/papers/fsbext.zip) tool.

If that doesn't work try using [FSBii](http://hcs64.com/files/fsbii07.zip) from HCS then use [VGMStream](http://hcs64.com/files/vgmstream/) to convert them to WAV.

If the FSBs are encrypted, you will need to decrypt them using HCS [GuessFSB](http://hcs64.com/files/guessfsb03.zip) to get the decryption key.
## Post #3
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-02-13T03:06:08+00:00
- Post Title: War Thunder FSB

Thank You. I have tried what you have recommended. 
When I use Aluigi's FSBExt tool, It give me .celt Files. I have Tried to extract them with an older tool, and Opus, But The .celt files are not recognized
When I use FSBii, It yields .fsb files. When I try to convert them with  VGMStream. It does not processes the Files

Does anyone know how to open these?
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-02-14T07:03:02+00:00
- Post Title: War Thunder FSB

The celt files are not recognised as they are extracted as raw data since no headers to include, there is not particularly good support if any
for extracting fsb celt or fsb vorbis, only good bet is probably get fmod designer i recall to open them and re-encode the banks to pcm and extract then.
## Post #5
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-02-15T22:25:09+00:00
- Post Title: War Thunder FSB

there is a fsb extractor for the witcher 2 celt audio that converts to standard waves, worked on some other games like strangers wrath for me.

forum.worldofplayers.de/forum/attachment.php?attachmentid=34639&d=1306096330

you need to also copy paste the fmodex.dll that comes with the game you're trying to extract into the same folder and tw2unfsb

If it's newer fsb5, this tool might not work.
## Post #6
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-02-26T23:42:32+00:00
- Post Title: War Thunder FSB

Thank you pepper for your response. There was no Fmodex.dll for War thunder 

I tried the 2nd program you recommended, and that did not work either. I actually Contacted the creator of the program, and told him about the problem.  
This is what he said:

"Thanks for the attached FSB file. Just like PlanetSide 2, the samples in your FSB file are actually
headerless Ogg/CELT data. Even when extracted they will not play because they have no header.

I just released a new version today to fix an issue with incorrect sample mode flags.
This issue caused the samples to not be detected as Ogg/CELT but incorrectly as PCM instead.
However, this new release will not make the extracted files playable. To fix that problem,
I would have to add some kind of Ogg header in the extraction process.
Even then, it may not work because they are apparently CELT and not of regular Ogg format.

This is all something I will have to look into."
## Post #7
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-03-30T14:30:32+00:00
- Post Title: War Thunder FSB

Bump - I'm still not able to extract the sound files, They have some really nice ones, especially the music.
## Post #8
- Username: nutbomb
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 03, 2007 3:34 pm
- Post datetime: 2013-04-27T12:08:36+00:00
- Post Title: War Thunder FSB

hi did you extract the war thunder dxp file success?
## Post #9
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-04-27T14:04:36+00:00
- Post Title: War Thunder FSB

No, I have not been able to extract any sounds from War Thunder yet
## Post #10
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-05-07T12:40:14+00:00
- Post Title: War Thunder FSB

Bump, I need help with extracting the sound as well. Any help is much appreciated !
## Post #11
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-06-05T00:50:34+00:00
- Post Title: War Thunder FSB

It's been a month with no response, So I will bump this again
## Post #12
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-06-07T01:46:43+00:00
- Post Title: War Thunder FSB

Ok, there has been an update, using the current version of Aezay FSB Extractor (13.03.09) [http://aezay.site11.com/aezay/fsbextractor/](http://aezay.site11.com/aezay/fsbextractor/), you are able to extract most of the FSB files, ex. guns, engines.  
The 2 files that I have not been listen to so far, are the dialogs_wopl_english.fsb , and the music.fsb
I do not know if it is the codecs that are preventing me from listening, or the extraction method, so I am supplying a sample for anyone to view.
The FSB file:          music.fsb                     [http://www.mediafire.com/download/m2spz ... /music.fsb](http://www.mediafire.com/download/m2spz5pvzlo9599/music.fsb)
An Individual file :   midway_4_us(.ogg?)       [http://www.mediafire.com/download/l13mi ... y_4_us.ogg](http://www.mediafire.com/download/l13mis6il5zflaa/midway_4_us.ogg)
## Post #13
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-06-13T01:42:15+00:00
- Post Title: War Thunder FSB

Could someone tell me if it's my audio codecs, or the extracted file that is the problem 
/ bump
## Post #14
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-06-25T16:54:52+00:00
- Post Title: War Thunder FSB

ogg vorbis is extracted without proper headers by that tool. vorbis decodes in a way that a generic header is near impossible and so is remaking the header very unlikely. I'd have to guess there is some trick fmod uses on it's files, be it creating files that it knows the header for already somehow or whatnot.
## Post #15
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2013-09-15T14:55:16+00:00
- Post Title: War Thunder FSB

I am going to bump this, it has been several months, I have looked around and there still seems to be little to no progress in anyone creating anything for it.
## Post #16
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2014-01-26T04:39:53+00:00
- Post Title: Re: War Thunder FSB

Hi all i try all programs so far no luck as get sound to work as well i use fsbext.exe, FsbExtractor, RavioliGameTools_v2.5, when use fsbext i get this at the bottom u my know more me, 
some of the extracted files use IMA ADPCM and this tool has assigned them
  the codec 0x69 (Xbox ADPCM) but if you want to play them immediately with
  VLC or mplayer you must add the -A option to fsbext so that they will be
  created with the codec 0x01 (IMA ADPCM).
How i add the -A to fsbext txt or change the 0x69 (Xbox ADPCM) to 0x01 (IMA ADPCM) i don't how edit it thanks.
when open file in hex edit they are FSB5 were codemasters grid 1 use FSB4.
here website tell about celt format i looking into it now get back.
[http://fileformats.archiveteam.org/wiki/CELT](http://fileformats.archiveteam.org/wiki/CELT)
## Post #17
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-01-27T11:18:28+00:00
- Post Title: Re: War Thunder FSB

Save the following into a text editor.

```
for %%i in (*.fsb) DO fsbext.exe -A %%i
```


Make sure the extension is .bat and run it inside the folder with FSBExt and the .FSB file
## Post #18
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-01-28T20:08:45+00:00
- Post Title: Re: War Thunder FSB

will this create a folder with the name of the FSB file for each file?
## Post #19
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2014-02-10T08:39:00+00:00
- Post Title: Re: War Thunder FSB

> Reply from Devilot
>
> will this create a folder with the name of the FSB file for each file?

no just unpacks ever file to game folder u have to make new folders with names copy ever file in each game folder it plays all
the sound spot on thank all great work you have done. cheers.
## Post #20
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2014-02-10T08:52:34+00:00
- Post Title: Re: War Thunder FSB

now work out fsb files can do sumthing with dxp.bin files please as want do sum skins. thanks.
## Post #21
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2014-02-10T09:28:00+00:00
- Post Title: Re: War Thunder FSB

this info off one files after u unpack them, the trouble is cannot edit them as they Bit depth : 4 bits files can not fine program that do 4 bit most low as 8 bit
i play them in media players but edit still not i try convert them and see but no luck.

General
Complete name                            : F:\War Thunder\sound\tur\tur_aircraft_damaged_v1_r3_t1_mood_med.wav
Format                                   : Wave
File size                                : 9.61 KiB
Duration                                 : 394ms
Overall bit rate mode                    : Constant
Overall bit rate                         : 200 Kbps
Audio
Format                                   : ADPCM
Codec ID                                 : 11
Codec ID/Hint                            : Intel
Duration                                 : 394ms
Bit rate mode                            : Constant
Bit rate                                 : 198 Kbps
Channel count                            : 1 channel
Sampling rate                            : 44.1 KHz
Bit depth                                : 4 bits
Stream size                              : 9.56 KiB (100%)
## Post #22
- Username: hairypaulsack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 30, 2015 9:28 pm
- Post datetime: 2016-04-03T14:21:52+00:00
- Post Title: Re: War Thunder FSB

> Reply from Rafael09ed
>
> I have Tried to extract the FSB files to War Thunder and it would not extract using Music Player Ex. Anyone Else know how to open These files for this game?

Okay so I don't know if this is new or you [the guy who said there is no fmodex.dll "from/provided in" the War Thunder folder] just missed it, but I am looking at fmodex.dll right this moment. It's located in the fmod.zip archive stored in the main War Thunder directory.

EDIT: so the fmodex.dll file that came in the WT directory is not the right header. Downloading the FMOD Ex API from the website gives you the new version of the .dll and all you need is the fmod_extr.exe utility.

Completely bypassed the .celt altogether. 


Also the WT directory has .FSV files, but you just need to download FMOD Designer 2010 for that. I tested and verified and have a .wav of all the files =)


[randleman.p@gmail.com](mailto:randleman.p@gmail.com) if you have questions.. I won't come back to this thread ever again and I'm not on XENTAX very much
## Post #23
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2019-01-03T13:06:57+00:00
- Post Title: Re: War Thunder FSB

Hey guys, 

I tried all those solutions but no one worked. 
I want to extract audio from fsb files.
Is there a new solution since 2016 ?
