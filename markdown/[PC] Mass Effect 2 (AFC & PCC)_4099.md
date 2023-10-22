## Post #1
- Username: hdnine
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 07, 2005 1:02 am
- Post datetime: 2010-01-31T21:41:43+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

Hey everyone,

I just played through this amazing game and was equally amazed of the superb sound effects and voice acting. I really would like to find a way to extract the audio but haven't found a way yet to do it. Any help would be appreciated!

[http://www.sendspace.com/file/4vphdb](http://www.sendspace.com/file/4vphdb) (PCC file)
[http://www.sendspace.com/file/lravmd](http://www.sendspace.com/file/lravmd) (AFC file)

The AFC files seems to be WAV (RIFF) but i still can't play them? PCC seems to be a container or archive om sorts? Thanks!
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-01T00:08:01+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

The RIFFs are Wwise's custom Vorbis container, try ww2ogg ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)) to convert to Ogg.  I saw an extractor for .afc the other day on [extractor.ru](http://ipb.extractor.ru/index.php?showtopic=2053&view=findpost&p=13135), you could always use some other method for extracting RIFFs.
As noted in that thread you'll need to use the --full-setup command line switch with ww2ogg.
## Post #3
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-02-01T00:24:16+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

Awesome!  Man so many tools to keep track of,  I'm wondering how to use this, treating it like umodel, sick it's directory in the paths for the OS to use in commandline.  Only getting 1kb OGG files output cuz it's having an error, so i'm trying to find some sort of documentation, the hist.txt file that comes with it is all screwed up!
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-01T06:24:20+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

I suggest running it from the command prompt.  You need to give it the argument "--full-setup" along with the .wav file name on the command line.  You may be able to do this from start->run or if you make a batch or shortcut, but I think it'd be easier to just use the command line.  It also prints reasonably informative errors on the command line in case you have something wrong.
## Post #5
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-02-01T10:40:22+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

yea, found that and tried it, it complains it cant find some bin file which is actually located in the same directory the executable comes with  tried just running via command line and putting an afc file in the directory of the program itself! still getting the error and a 1kb ogg output.
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-01T15:59:10+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

If you are using --full-setup it won't need packed_codebooks.bin.  You should be running it like:

```
ww2ogg whatever.wav --full-setup
```

For files where you do need packed_codebooks.bin (though I don't think you'll find any in this game), you just need to have it in the directory that you are running the program from.  I suppose it would be easiest to build it in, but I had anticipated that it might change at some point.
## Post #7
- Username: hdnine
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 07, 2005 1:02 am
- Post datetime: 2010-02-01T19:43:33+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

Thanks people... i got the AFC files converted to OGG as per instructions on the Russian website. Not sure if any sound effects are in these though, i will have to look? What are the PCC files you think -- are they the ones containing the SFX?
## Post #8
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-02-02T00:03:29+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

PCC = Upk for most everything else, textures, static meshes, material ids, etc... [umodel](http://www.gildor.org/news) can extract these.  I noticed it had trouble with certain games and they list the games they have limited support for.  IE: a couple I tried extracting only ended up with staticmesh exports at 1k because they just hold uv information and not the "brush" itself, which means no exporting it.  However, the formats it can export to default as PSK / PSA (animations), and can be imported into Milkshape 3d, or with the use of Gildor's reverse engineered exporter from Unreal Developers' ActorX Import tool he created, right into 3dsmax!
## Post #9
- Username: hdnine
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 07, 2005 1:02 am
- Post datetime: 2010-02-02T17:26:25+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

Superb, very much appreciated information ^^
## Post #10
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-02-20T16:50:51+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

Does anyone have idea on the sound effect RIFF wavs in *.PCC files (upk), they appear to use adpcm compression but the header is a bit custom too... 

I have manually cutted so fits under size limit and apparently this is wwise adpcm bank format...
[wwiseadpcm.rar](https://xentaxbackup.github.io/file/2789_wwiseadpcm.rar)
## Post #11
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-20T20:23:40+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

Looks very much like Microsoft IMA (codec id 0x11) but with blocks interleaved rather than using MS's method of having all the channel headers at the start of one block.  However, I'm not able to decode it quite correctly with this assumption.
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-20T21:33:24+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

Seems like quite a few of these music files use the same thing for the pc version, 360 might use xma but i dont have the speeds now to get both iso's for the 360 version.
## Post #13
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-25T06:15:37+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

I'm thinking that I may have been right, but this file just sounds weird because it's an explosion.  Here's something you can try out: [http://hcs64.com/files/ima_rejigger00.zip](http://hcs64.com/files/ima_rejigger00.zip)
If you give it the RIFF, it'll interleave the IMA frames so they can be decoded normally.  Note that it modifies the file in place!  Recent vgmstreams will accept codec id 0x69 so you can try it out there, or just change the id manually (to 0x11).
## Post #14
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-02-25T08:38:05+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

It works, found out trying use dragon unpacker/game extractor to get the wavs ends up in chunk size out range with the tool except when i use gildor's tool and manually cut the start of file to riff so likely said tools cut the file too soon making it not match the header specified lenght.

Curiously the original kbps values as per 32khz are different in xbox adpcm (144kbps) vs ima adpcm (128kbps)
Of course no converter likes the output due to lacking fact chunk entry as well other mess in header so just vlc transcoding to other format for now.
## Post #15
- Username: Kyp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 01, 2010 1:10 am
- Post datetime: 2010-02-28T20:10:33+00:00
- Post Title: [PC] Mass Effect 2 (AFC & PCC)

I wrote myself a little program, which uses afcextr and ww2ogg to extract and convert any number of .afc files to .ogg, and i thought some people might like it, as it really saves the time you would spend messing with the console. 
You can choose any number of .afc files and it will extract them to specified location (each to separate folder or all to one place).
It works with Mass Effect 2 audio files, but should also work with other games that use this kind of audio storage.
It uses .NET, so if you don't have it, you might have to download it.

Enjoy  
[Afc2ogg.zip](https://xentaxbackup.github.io/file/2818_Afc2ogg.zip)
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-01T14:33:35+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

This is great, why not add it to the tools blog yourself, you should have author rights there
## Post #17
- Username: arcuido
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 10, 2010 6:59 pm
- Post datetime: 2010-04-10T19:13:50+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

> Reply from Kyp
>
> I wrote myself a little program, which uses afcextr and ww2ogg to extract and convert any number of .afc files to .ogg, and i thought some people might like it, as it really saves the time you would spend messing with the console. 
You can choose any number of .afc files and it will extract them to specified location (each to separate folder or all to one place).
It works with Mass Effect 2 audio files, but should also work with other games that use this kind of audio storage.
It uses .NET, so if you don't have it, you might have to download it.

Enjoy

Im really searching for something like this but im not sure if i should use this, my AVGuard tells me theres a Trojan / Spy inside. 
Does a similiar programm exist ? I used  gibbets audio extractor before, but the problem is that i cant change the directory. I need the Audio from the Mass Effect 2 DLC (Kasumi) and the Gibbet Audio Extractor dont have the option to change directory to the DLC. Does anyone have an idea for my problem ?

Sry for my bad english
## Post #18
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-10T21:34:36+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

My tool doesn't do any searching for resources, it has a premade list of files. So it won't currently work on DLC.
## Post #19
- Username: arcuido
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 10, 2010 6:59 pm
- Post datetime: 2010-04-11T07:25:25+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

And thats exactly my Problem
## Post #20
- Username: Kyp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 01, 2010 1:10 am
- Post datetime: 2010-12-27T14:54:45+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

in case someone still needs it:
i released a new version of afc2ogg, you can download it at [http://kypapps.co.cc/index.php/afc2ogg](http://kypapps.co.cc/index.php/afc2ogg)

more stable, more options, and no longer puts virus alerts

enjoy
## Post #21
- Username: Thesaltyrock
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 14, 2011 10:31 pm
- Post datetime: 2011-08-14T14:40:50+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

Hello,

I just want to say: Thank you a'lot Kyp! I'm sound designer for games and it means a lot for me!

Cheers,
Salty

Edit:
There are no sound effects, only dialogue audio :/
Any idea how I can get the sound effects?

Thanks,
Salty

Edit No2.: 
Managed to find the rest of the sfx. Now I only need to extract it from .upk file!
## Post #22
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T12:18:43+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

Thesaltyrock: Mass Effect 2 doesn't use Unreal packages with UPK extension. It uses PCC extension.

It is possible to use [UnHood](http://code.google.com/p/unhood/) with slight modifications to "extract" contents of Mass Effect 2 Unreal packages (*.PCC).
## Post #23
- Username: Thesaltyrock
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 14, 2011 10:31 pm
- Post datetime: 2011-08-22T12:29:16+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

I'm not blind. 

There are plenty of .pcc, yes, but there is also one .upk file (144MB).

Thank you about .pcc extractor anyway...

Salty
## Post #24
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T12:59:21+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

Sorry, I haven't looked into CookedPC folder of ME2 for a while - forgot about the shader cache package.
## Post #25
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2012-03-08T03:42:39+00:00
- Post Title: Re: [PC] Mass Effect 2 (AFC & PCC)

How do I repack an extracted PCC file?
Thank you.
