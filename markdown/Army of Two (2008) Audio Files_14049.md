## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-03-04T20:54:26+00:00
- Post Title: Army of Two (2008) Audio Files

Since the game first came out I have been looking for ways to extract sounds and music that isn't in the official soundtrack by Trevor Morris. The game runs on a certain version of Unreal Engine 3, and I have tried time and time again to extract the sounds, but with no success whatsoever. All audio files are stored in ".xxx" format, I tried Umodel, ww2ogg, oggextract, countless decompressors and extractors, but no luck whatsoever. I will upload some files for view.
Thank you for reading and please help!
[Sounds.zip](https://xentaxbackup.github.io/file/10554_Sounds.zip)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-05T09:46:18+00:00
- Post Title: Army of Two (2008) Audio Files

> Reply from Pepsee
>
> All audio files are stored in ".xxx" format

No. These files you uploaded only contain zeroes. Sounds must be somewhere else.
## Post #3
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-03-05T11:23:53+00:00
- Post Title: Army of Two (2008) Audio Files

> Reply from daemon1
>
> Pepsee wrote:All audio files are stored in ".xxx" format

Sounds must be somewhere else.

No, I looked everywhere, that's the only possible place. It's the PS3 version of the game, and as I've seen in all Unreal Engine 3 games such as Unreal Tournament 3, Gears of War PC, all sounds are stored in the "Cooked" folders. Maybe the header has to be changed in a Hex Editor.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-05T12:19:06+00:00
- Post Title: Army of Two (2008) Audio Files

> Reply from Pepsee
>
> No, I looked everywhere, that's the only possible place. It's the PS3 version of the game, and as I've seen in all Unreal Engine 3 games such as Unreal Tournament 3, Gears of War PC, all sounds are stored in the "Cooked" folders. Maybe the header has to be changed in a Hex Editor.

At least NOT in these files you posted. There's nothing in these files at all!

Do you have a file called "01_map_ghetto_sound.xxx" for example?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-05T13:24:15+00:00
- Post Title: Army of Two (2008) Audio Files

So if you unpack some of the real XXX files containing sounds, like I mentioned before, using Umodel with -sounds switch, you will get a lot of  .ps3audio files in AT3 codec. Surely you can decode them with something, just find some tools that can handle that format. I used "msf_convert.bms" script by alpha23, and i was able to decode mono sounds from 01_map_ghetto_sound.xxx
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-03-05T19:32:44+00:00
- Post Title: Army of Two (2008) Audio Files

I didn't understand quite well. First I need Umodel with a "-sound" function, where do I add that. Secondly, can you post a link to alpha23's .bms script, please?
[Sounds (2).zip](https://xentaxbackup.github.io/file/10561_Sounds (2).zip)
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-05T19:59:06+00:00
- Post Title: Army of Two (2008) Audio Files

These files again have NO SOUNDS. Try this on a file I told you. It MUST be bigger than some kilobytes.

> Reply from Pepsee
>
> I didn't understand quite well. First I need Umodel with a "-sound" function, where do I add that. Secondly, can you post a link to alpha23's .bms script, please?

-sounds - is a command line switch. If you use GUI, check the "sound" checkbox.

[viewtopic.php?p=43570#p43570](http://forum.xentax.com/viewtopic.php?p=43570#p43570)
## Post #8
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-03-05T20:17:27+00:00
- Post Title: Army of Two (2008) Audio Files

How do I convert the ps3audio files, though? The same as with the msf files?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-05T20:23:55+00:00
- Post Title: Army of Two (2008) Audio Files

> Reply from Pepsee
>
> How do I convert the ps3audio files, though? The same as with the msf files?

Yes they are actually MSF files.
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-03-05T21:50:49+00:00
- Post Title: Army of Two (2008) Audio Files

Thank you very much
## Post #11
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-03-05T22:39:22+00:00
- Post Title: Army of Two (2008) Audio Files

Sorry for double post, but I really want to find the music in the Miami Airport level. I tried to extract all the levels i could find, I found a lot of cool tunes I've been searching for, but not any of the Miami soundtrack.. Any idea?
EDIT: Found it, but I have some strange .wav files. There are playable in Windows Media Player, but cannot be viewed in WavePad or Goldwave.
I uploaded some samples
[Sounds final.zip](https://xentaxbackup.github.io/file/10562_Sounds final.zip)
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-06T06:30:01+00:00
- Post Title: Army of Two (2008) Audio Files

Probably because the AT3 codec is not standard. Try another editor. Audition opens it.
## Post #13
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-03-06T12:08:02+00:00
- Post Title: Army of Two (2008) Audio Files

I seem to have an error while extracted certain sounds, and sadly, they're from the files of the levels I want the music from   
This is the error message: 
> Trying to allocate 1088045504 bytes
>
> appMalloc:size=1088045504 <- FArray::Empty:1088045504 x 1 <- TArray::SerializeSimple <- UAnimSequence::Serialize <- LoadObject:AnimSequence'08_map_hq_lobby_s.AnimSequence_5', pos=8C576, ver=445/79, game=800D <- UObject::EndLoad <- LoadWholePackage:08_map_hq_lobby_s <- CUmodelApp::ShowPackageUI <- Main:umodel_version=411

Here are a few samples: [https://www.dropbox.com/s/bfuf1i88o6jvk ... c.zip?dl=0](https://www.dropbox.com/s/bfuf1i88o6jvkym/Miami%20sounds%20and%20music.zip?dl=0)

Is there any way to extract them?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-06T12:21:53+00:00
- Post Title: Army of Two (2008) Audio Files

You can report that to gildor, but for now, just remove all checkboxes, and leave only "sounds" checked
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-16T20:18:51+00:00
- Post Title: Army of Two (2008) Audio Files

> Reply from Pepsee
>
> EDIT: Found it, but I have some strange .wav files. There are playable in Windows Media Player, but cannot be viewed in WavePad or Goldwave.

I found that is because of a problem with BMS script. It will be corrected soon.
