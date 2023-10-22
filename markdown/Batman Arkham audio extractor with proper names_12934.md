## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-12T13:27:38+00:00
- Post Title: Batman Arkham audio extractor with proper names

This little tool will unpack the WAD file into chunks named according to bank names. Then you can split them into individual sounds and convert them with WAV splitting scripts.

batman_bnk [wad file]

Hash list included for "knight", "origins" & "city" games. It must be in the same folder. "Arkham Origins" game WAD contains a lot of redundant audio, not used in game. Some of them even spoken by female synth voice. These will have no proper names after unpacking, just hash.

update: Batman Arkham Knight support added.

update2: Batch files for unpacking music with proper names. Warning! Run the corresponding batch file, many music chunks have the same name: just "music".

update3: updated to support Arkham Knight DLC's about Redhood & Batgirl.

This is a scheme of how audio/subtitles relation works in Batman games. Every dialogue line has a corresponding audio event, and through the chain of IDs it points to sound segment in WAD file and the sound inside of it (or to the actual sound if it's embedded in a bank).


[batman_bnk.rar](https://xentaxbackup.github.io/file/10006_batman_bnk.rar)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-06-15T01:23:07+00:00
- Post Title: Batman Arkham audio extractor with proper names

Thx deamon.

btw this does for music too?
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-15T15:32:14+00:00
- Post Title: Batman Arkham audio extractor with proper names

No, its only for voice WADs now. Music/sfx will be later.
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-06-15T17:19:07+00:00
- Post Title: Batman Arkham audio extractor with proper names

okay nice.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-24T18:14:48+00:00
- Post Title: Batman Arkham audio extractor with proper names

Tool updated. Batman Arkham Knight support added.
## Post #6
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-07-03T08:32:26+00:00
- Post Title: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Tool updated. Batman Arkham Knight support added.

DLC's are supported?
## Post #7
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-07-03T09:42:49+00:00
- Post Title: Batman Arkham audio extractor with proper names

Thanks, very useful.

Wait for music\sfx unpacking. (if not already)
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-07-03T17:46:07+00:00
- Post Title: Batman Arkham audio extractor with proper names

Arkham Knight tool update should have already the .txt file to unpack the music bank.
## Post #9
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-07-03T19:59:21+00:00
- Post Title: Batman Arkham audio extractor with proper names

In attach is version from 24.06.2015.

Try to unpack Music bank, but "Unsupported WAD version".

Or I miss something?
## Post #10
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-07-03T20:36:57+00:00
- Post Title: Batman Arkham audio extractor with proper names

You can unpack music without names with .wad BMS script or even with ravioli tools and then decode it with ww2ogg & revorb.
## Post #11
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-07-03T20:44:36+00:00
- Post Title: Batman Arkham audio extractor with proper names

Know about it.

Off-topic: anyone knows how to do "for %%f in (*.wem) do ww2ogg.exe %%f --pcb packed_codebooks_aoTuV_603.bin" with batch mass folders with such a scheme?:

> D:\2\qbms1\
>
> D:\2\qbms1\SFX_1\
>
> D:\2\qbms1\SFX_1\AMB_ACE_A2\
>
> D:\2\qbms1\SFX_1\Music\
>
> etc
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-03T21:01:09+00:00
- Post Title: Batman Arkham audio extractor with proper names

> Reply from Researchman
>
> Off-topic: anyone knows how to do "for %%f in (*.wem) do ww2ogg.exe %%f --pcb

try "for /r %%f..."

> Reply from Researchman
>
> Try to unpack Music bank, but "Unsupported WAD version".

What file that is?
## Post #13
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-07-03T21:06:03+00:00
- Post Title: Batman Arkham audio extractor with proper names

Extracted Music file without extention from SFX_1.wad

> try "for /r %%f..."
Thanks.
## Post #14
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-07-03T21:50:42+00:00
- Post Title: Batman Arkham audio extractor with proper names

> Reply from spider91
>
> daemon1 wrote:Tool updated. Batman Arkham Knight support added.

DLC's are supported?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-04T18:59:05+00:00
- Post Title: Batman Arkham audio extractor with proper names

> Reply from Researchman
>
> Extracted Music file without extention from SFX_1.wad
This is not music bank, nor WAD file.

Let's say, we have dialogue DLG_MAIN_CH02_S14_ACE_A1_ORAC_BM_ASSET

It has 2 sound files: 
Main_Ch02_S14_Ace_A1_Orac_Bm_Asset_01
Main_Ch02_S14_Ace_A1_Orac_Bm_Asset_02

There's no need to extract these names from the real bank, they are too simple.

But it's different for music. All music segments are in one big bank, and it's not easy to find the relation between music events and these segments. Maybe I will try and find it, but it will take time.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-05T13:59:33+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

Tool updated. Now all 3 games with sfx and DLCs are supported.
## Post #17
- Username: GencayKulac
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 05, 2015 9:55 pm
- Post datetime: 2015-07-05T14:26:14+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

I don't know how to use it. Can anybody explain me ?
I want to edit Batman Arkham Origins' subtitles and i guess they're in 28CCF006_LOC_INT.wad
Can I edit them with this tool? If answer is yes, how?
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-05T16:18:47+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

No, subtitles are in dialogue files inside .upk packages.
## Post #19
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-07-05T17:26:32+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

daemon1 any theories of music segment event name searches? I'd help but i dunno where to start?
## Post #20
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2015-07-06T02:08:14+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

-
## Post #21
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2015-07-06T03:21:29+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

> Reply from 41hc1
>
> You can already extract most music and sfx with Ravioli Tools.
I think everyone knows about it. Many people want to extract the audio with the original names.
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-07T16:34:16+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

We are close to unpacking music with names. Here's the current list for origins main game:

[http://pastebin.com/nDZUY3ux](http://pastebin.com/nDZUY3ux)

as you can see, some audio files are used in more than one situation, which is logical
only need to choose one for each file, and i can make an extractor with names
those without names are probably not used in game, or missing by some error
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-08T11:01:13+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

Ok first test version of Origins music extraction with names.
Just run the corresponding bat file and it will cut the music chunk made by my extractor into individual files.

Every music event may have multiple playlists, including multiple sound segments.
So filenames are made like this:

MUS_Explore_Openworld_Ch9_1_2

is from music event MUS_Explore_Openworld_Ch9 playlist 1, segment 2

Now all duplicates will be extracted. So for example

MUS_Shiva_BossFight_End
MUS_SET_A_GCPD_ENDING
MUS_SET_A_Blackgate_EP1_Ending

will be the same file. So if anyone have an idea which files to remove and which to leave, let me know. For now, you can remove them with some duplicate removal tool.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-09T16:24:01+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

The same thing for City. Again, you get 759 files duplicated from 314 originals, but you will see where each of them used. Later I plan to make a batch that will extract only unique files.
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-11T10:01:18+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

Arkham Knight music names are almost ready. This includes more work, because new wwise version has completely new 4-level tree switch structure.
## Post #26
- Username: Whover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 05, 2015 11:22 pm
- Post datetime: 2015-07-13T16:50:03+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

How do you use these files to extract Arkham Origins music from the wad file with track names? Sorry bit of a newbie :/
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-13T17:49:02+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

Batch for Arkham Knight.

note: a few locations remain unidentified, having some unique music. So if someone know what side-quests these are, let me know and I will rename the files:

MUS_SideStory.88CF93E0..MUSIC_Chase_1.wem 
MUS_SideStory.88CF93E3..MUSIC_Chase_2.wem 
MUS_SideStory.88CF93E5..MUSIC_Chase_0.wem 
MUS_SideStory.88CF93E5..MUSIC_Chase_2.wem 
MUS_SideStory.88CF93E5..MUSIC_Chase_3.wem 
MUS_SideStory.88CF93E5..MUSIC_Chase_4.wem 
MUS_SideStory.88CF93E5..MUSIC_Chase_Fail.wem 
MUS_SideStory.88CF93E5..MUSIC_Chase_Success.wem 

MUS_SideStory.BA4D0D6C..MUSIC_Combat_0.wem 
MUS_SideStory.BA4D0D6C..MUSIC_Combat_1.wem 
MUS_SideStory.BA4D0D6C..MUSIC_CombatFail.wem 
MUS_SideStory.BA4D0D6C..MUSIC_CombatSuccess.wem 
MUS_SideStory.BA4D0D6E..MUSIC_Combat_0.wem 
MUS_SideStory.BA4D0D6E..MUSIC_Combat_1.wem
MUS_SideStory.BA4D0D6E..MUSIC_Combat_2.wem 
MUS_SideStory.BA4D0D6F..MUSIC_Combat_0_0.wem
MUS_SideStory.BA4D0D6F..MUSIC_Combat_1.wem 
MUS_SideStory.BA4D0D6F..MUSIC_Combat_1_0.wem 
MUS_SideStory.BA4D0D6F..MUSIC_Combat_2_0.wem 
MUS_SideStory.BA4D0D6F..MUSIC_CombatFail.wem
MUS_SideStory.BA4D0D6F..MUSIC_CombatSuccess.wem
## Post #28
- Username: Grand Admiral Thrawn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 10, 2015 3:34 pm
- Post datetime: 2015-07-14T13:01:21+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

Hi there.

So, I've downloaded both batman_bnk.rar and batman_city_music.rar. I unpacked them and tried many times to open/extract many files I believed are responsible for music in Arkham City. I give up. I don't know what am I doing wrong. If anyone could write down step by step what to do I would be very grateful, cause right now I'm in a dead end.
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-14T17:47:06+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

batman_bnk is a command line tool. It takes 2 parameters. You must put it to the same folder as WAD sfx file. For city its called 17705D3E.wad and you can find it in "BmGame\CookedPCConsole\SFX\" folder.

Then you must somehow run this command:

batman_bnk 17705D3E.wad banklist_city.txt

After that among others you will get a file "music", that is music chunk.

Then run "city.bat" and it will cut individual music files from it.
## Post #30
- Username: Grand Admiral Thrawn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 10, 2015 3:34 pm
- Post datetime: 2015-07-14T20:03:53+00:00
- Post Title: Re: Batman: "Knight", "Origins" & "City" audio extractor

I've put the 17705D3E.wad file into batman_bnk folder (F:\batman_bnk). When inputting batman_bnk 17705D3E.wad banklist_city.txt, nothing happens. I've tried writing F:\>start batman_bnk Batman_bnk.exe 17705D3E.wad banklist_city.txt and the only thing that happens is that the folder opens and thats that. I'm just to stupid to do it.
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-14T20:18:28+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

if you're currently in "F:\" folder, try typing "cd batman_bnk" to go to program folder, then that

batman_bnk 17705D3E.wad banklist_city.txt
## Post #32
- Username: Grand Admiral Thrawn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 10, 2015 3:34 pm
- Post datetime: 2015-07-14T21:29:01+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

OK, I did it. I've copied the 'Music' file into batman_city_music folder and run city.bat. Now I have something like 750 'wem' files.
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-15T07:03:56+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

These are wwise audio files that you get when extracting any game using wwise.

You can convert them with ww2ogg by hcs
## Post #34
- Username: Grand Admiral Thrawn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 10, 2015 3:34 pm
- Post datetime: 2015-07-15T14:57:19+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I used this tutorail by SWTOR fan

> Guide: Converting .wem to .ogg
>
> 1. Go to the folder where you have your *.wem files.
>
> 2. Download ww2ogg019.zip and revorb.exe. Extract the ZIP archive. Then copy ww2ogg.exe, packed_codebooks_aoTuV_603.bin and revorb.exe into the folder with your *.wem files.
>
> 3. Now create a new text document in this folder, rename it to convert.bat. Open this .bat file with notepad, then copy & paste the following lines. Then save and close Notepad.
>
> Code:
>
> for %%f in (*.wem) do ww2ogg.exe %%f --pcb packed_codebooks_aoTuV_603.bin
>
> pause
>
> for %%f in (*.ogg) do revorb.exe %%f
>
> pause
>
> 4. In the folder, double-click on the .bat file. Now you will find—in addition to your .wem files—.ogg files in the folder.

And everything goes according to it until I want to play the files. Nothing, just statics.
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-15T16:11:14+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

This guide will work for origins game. For city instead of 

for %%f in (*.wem) do ww2ogg.exe %%f --pcb packed_codebooks_aoTuV_603.bin

use this line

for %%f in (*.wem) do ww2ogg.exe %%f
## Post #36
- Username: Grand Admiral Thrawn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 10, 2015 3:34 pm
- Post datetime: 2015-07-15T17:49:59+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Ufff....finally

I've managed to make those pesky ogg files that actually work. When I used only this line 

for %%f in (*.wem) do ww2ogg.exe %%f

the ogg files were all 1KB size. So I've changed it to

for %%f in (*.wem) do ww2ogg.exe %%f --pcb packed_codebooks.bin

and it worked. The only 'problem' now is that in Winamp (yes, I use it still) all of these ogg files are 0:00 (they do play though - and they don't want to convert into mp3). To be honest, extracting music from the Witcher 2 was far easier that this.

Still, thank you sooo much for helping me and not shouting because of my ignorance
## Post #37
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-15T18:25:46+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Use Revorb on those OGGs to fix the timecode.
## Post #38
- Username: Grand Admiral Thrawn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 10, 2015 3:34 pm
- Post datetime: 2015-07-15T18:28:38+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I did

> for %%f in (*.wem) do ww2ogg.exe %%f --pcb packed_codebooks.bin
>
> pause
>
> for %%f in (*.ogg) do revorb.exe %%f
>
> pause

EDIT

OK, everything is fine. I only used revorb.exe this time.

Thanks again for you help and patience.
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-16T07:10:24+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

extract Origins music with this batch:
[viewtopic.php?p=107477#p107477](http://forum.xentax.com/viewtopic.php?p=107477#p107477)

There are 3 files for main music and 2 DLCs. I don't have multiplayer WAD though, so I can't make a batch for it.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-16T10:26:30+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Can you explain in details howd you get them? Maybe it's that multiplayer music? Then its normal, because i have no lists for it.
## Post #41
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-18T10:07:44+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

That's bad idea to copy all WAD files into one folder. You can lose some audio this way.

I'm making a list for origins online music now. Again there's some difficulties.
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-18T16:55:33+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Update!

- All hash lists merged into one, no need for second parameter for batman_bnk anymore.
- All 7 batch files moved to the first post.
- Origins Online support (note it was made with old wwise version, like City)

Notify me of any problems in this new version.

notmebug2 you can now unpack the last music file.
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-20T11:36:40+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Which WAD file are you trying to unpack?
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-20T15:47:18+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

The music chunk in "harleypolice" DLC folder contains music for 4 different DLCs, including Redhood and something else. Without a list of files I can't make proper music list.

If anyone has Batman Arkham Knight with all DLC's on any platform and can provide a list of files, let me know.
## Post #45
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-07-20T21:43:22+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> 
If anyone has Batman Arkham Knight with all DLC's on any platform and can provide a list of files, let me know.
[http://sendfile.su/1138989](http://sendfile.su/1138989)
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-21T13:45:41+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

This is because, as I said, it was made with old wwise version, like City.

You must use old codebooks for ww2ogg to convert this file.
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-26T17:19:52+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

New version with support for Knight DLCs: Harley Quinn, RedHood, Scarecrow, Batgirl.
Last three are not available on PC, so I don't have exact location names.

Example:

```
1D1A5D6E Music.MDLC00_Music_Chapter_Scarecrow.75682E28.47B8B04E.
06C1E770 Music.MDLC00_Music_Chapter_Scarecrow.75682E29.B32327AE.
2BD5B58E Music.MDLC00_Music_Chapter_Scarecrow.75682E29.D6817F0B.
0511DCF1 Music.MDLC00_Music_Chapter_Scarecrow.75682E2A.2AA69BAB.
1D1A5D6E Music.MDLC00_Music_Chapter_Scarecrow.75682E2A.47B8B04E.
2738FDB6 Music.MDLC00_Music_Chapter_Scarecrow.75682E2A.49B6BE4F.
31160573 Music.MDLC00_Music_Chapter_Scarecrow.75682E2A.7083F32F.

```


75682E28 is location name, 2AA69BAB is track name. If anyone have DLCs on PS4 on XBOX, let me know the filenames, so I can make proper lists.
## Post #48
- Username: devilbat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 29, 2015 9:25 am
- Post datetime: 2015-07-29T02:07:21+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Hi
May I ask how can I extract dialogue voice from bataman arkham city/Origin?
which file i need to use?
Thanks for many help~
## Post #49
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-03T03:32:22+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I really would like to know if i can use this tool to edit arkham knight subtitles, since the game doesn't give the option to choose subtitles different from audio language.
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-03T18:36:07+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from devilbat
>
> Hi
May I ask how can I extract dialogue voice from bataman arkham city/Origin?
which file i need to use?
Thanks for many help~

You only need batman_bnk. All other files are for music banks.

You also need scripts for splitting. Maybe other users can find a link for you.
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-03T18:38:06+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> I really would like to know if i can use this tool to edit arkham knight subtitles, since the game doesn't give the option to choose subtitles different from audio language.

No, this tool can't help you. But as we know all the structures, this is possible, but requires some work. What exactly do you want to do?
## Post #52
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-03T19:27:05+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> BallisticSmith wrote:I really would like to know if i can use this tool to edit arkham knight subtitles, since the game doesn't give the option to choose subtitles different from audio language.

No, this tool can't help you. But as we know all the structures, this is possible, but requires some work. What exactly do you want to do?

I want to edit the game subtitles to my language (brazilian portuguese), 'cause i prefer the original english audio, so i would like to know if the game's subtitles are stored in the wad files, or somewhere else, and if there's a way to edit just the text, i have no intention to edit audio files.
## Post #53
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-03T19:36:04+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> I want to edit the game subtitles to my language (brazilian portuguese), 'cause i prefer the original english audio, so i would like to know if the game's subtitles are stored in the wad files, or somewhere else, and if there's a way to edit just the text, i have no intention to edit audio files.

Subtitles are inside AkDialogueEvent files inside all sublevel packages.

Have you tried to delete (move) the folder with portuguese WAD file? It's possible in this case the game will play english audio.
## Post #54
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-03T20:26:03+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Subtitles are inside AkDialogueEvent files inside all sublevel packages.

Have you tried to delete (move) the folder with portuguese WAD file? It's possible in this case the game will play english audio.

I tried deleting the portuguese folder, the game gets the portuguese subtitles, hud and menus, but no audio plays during the game (no voice nor music, only sfx), so i'm kinda confused how it works.
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-06T17:44:36+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Ok. This will not be easy, and I don't have the game.

First try unpacking some main location packages with Gildor's decompress with "-game=batman3" switch and run the game in that location. If it will work, we can try modifying them to change languages.
## Post #56
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-06T23:46:40+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Ok. This will not be easy, and I don't have the game.

First try unpacking some main location packages with Gildor's decompress with "-game=batman3" switch and run the game in that location. If it will work, we can try modifying them to change languages.

Sorry for me being noob, but are you talking about the .upk files? Cause there's a folder called localization with files with .int extension (english) and another with .ptb (portuguese), but those are only for hud and menus, and can be viewed by notepad.

Then there's the CookedPCConsole folder, which has the SFX folder with .wad files, English(US) and Portuguese(Brazil) folders with .wad files too, and all the main .upk files from the game.

If you want, maybe i can upload some files for you, since you have a lot of knowledge about this.
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-07T19:46:23+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> are you talking about the .upk files?

Yes, we have to change those. I have an idea. I'll try it on other batman games, and if it will work, then we proceed with the knight.
## Post #58
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-08T09:27:37+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

It worked! I just played with French subtitles + english audio, then with english subs + french audio 

It means we can now make an independent audio/subtitle switcher for ALL Batman games. Stay tuned.
## Post #59
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-08T10:40:35+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> It worked! I just played with French subtitles + english audio, then with english subs + french audio 

It means we can now make an independent audio/subtitle switcher for ALL Batman games. Stay tuned.

You're my hero hahaha, i'll stay tuned for more updates.
## Post #60
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-09T06:29:14+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

ok, let's make a test with one location. I've watched it on youtube, and I think if you start a new story, then after all the intros you meet Gordon on the roof. So I've swapped ENG - PTB audio ONLY this one location dialogue.

Download this and replace the file (make a backup too):

[http://www58.zippyshare.com/v/qkamQDuo/file.html](http://www58.zippyshare.com/v/qkamQDuo/file.html)

Then rename English(US) and Portuguese(Brazil) folders, so the game will look for audio in Portuguese folder and it will find English audio there. Also rename all the files inside from INT_1.WAD to whatever in was in Portuguese.

Then run the game and let me know if it works
## Post #61
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-09T12:33:35+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Then run the game and let me know if it works

I tried doing what you said, but when i do this, the scene with gordon rendezvouz gets no dialogue, and sometimes during the game, the english audio starts and even gets perfectly synced with the subtitles, but the dialogue never finishes, it always gets muted before the end of the dialogue.

Too bad, maybe the devs didn't want people to mod it, so they made hard to do it.
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-09T13:09:11+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> the scene with gordon rendezvouz gets no dialogue

This means we did something wrong. You shouldn't check other dialogues, they must be broken in this setup. But Gordon scene must work.

Let's check it again. Do you see any subtitles there? How does your Portuguese(Brazil) folder look now?
## Post #63
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-09T13:09:57+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> Too bad, maybe the devs didn't want people to mod it, so they made hard to do it.

No, they were just too lazy to do this.
## Post #64
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-09T14:05:37+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

ah, it seems it was one of those rare 6-channel dialogues. So this needs an update:

[http://www74.zippyshare.com/v/96DHe7ii/file.html](http://www74.zippyshare.com/v/96DHe7ii/file.html)

get this file and check it once again
## Post #65
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-09T21:28:39+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> ah, it seems it was one of those rare 6-channel dialogues. So this needs an update:

http://www74.zippyshare.com/v/96DHe7ii/file.html

get this file and check it once again

Thanks man, it worked now, the gordon scene audio and subtitles are perfectly synced, with english audio and portuguese subs, now you gotta tell me how to do it myself, so i stop bothering you lol

Is there anyway to script this process, so there's no need to mod each file?
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-10T18:11:35+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Here you go:

[viewtopic.php?f=17&t=13174](http://forum.xentax.com/viewtopic.php?f=17&t=13174)

I can't guarantee it will work for ALL files, so maybe first you can choose one big chapter, say, all CITY_X files. Good luck. Let me know if something is wrong.

p.s. This is only for ingame dialogues, not movies.
## Post #67
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-10T20:04:18+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Thank you so much, i really appreciate it, i'll patch some files and give you the feedback as i play the game.
## Post #68
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-08-10T20:32:48+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Well, I've managed to split the music, but when I convert them, all I get is this. Be sure to turn down the volume before you listen. If someone could please either PM me or post in this thread to tell me how to fix it, I would be very grateful.
[08D43800.mp3](https://xentaxbackup.github.io/file/9511_08D43800.mp3)
## Post #69
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-11T02:19:18+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> p.s. This is only for ingame dialogues, not movies.

Which tool should i use to do the same process for the .usm movie files?
## Post #70
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-11T04:22:35+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Cameron007
>
> Well, I've managed to split the music, but when I convert them, all I get is this. Be sure to turn down the volume before you listen. If someone could please either PM me or post in this thread to tell me how to fix it, I would be very grateful.

Use other codebooks
## Post #71
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-11T11:15:22+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> Which tool should i use to do the same process for the .usm movie files?

VGMToolbox can demux the audio streams from the .USM video files for you.
## Post #72
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-11T11:25:41+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from brendan19
>
> BallisticSmith wrote:Which tool should i use to do the same process for the .usm movie files?

VGMToolbox can demux the audio streams from the .USM video files for you.

Ok, and from there i can edit the subtitles?
## Post #73
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-11T17:02:19+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> Which tool should i use to do the same process for the .usm movie files?

Are there many movies with voice?
## Post #74
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-11T20:31:40+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Are there many movies with voice?

With voice I can't say for sure, but there's about 1.010 .usm files on the "Movies" game folder.

(by the way, i patched all the upk's and no problem so far during the game, everything is working fine)
## Post #75
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-08-12T21:12:43+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Cameron007 wrote:Well, I've managed to split the music, but when I convert them, all I get is this. Be sure to turn down the volume before you listen. If someone could please either PM me or post in this thread to tell me how to fix it, I would be very grateful.

Use other codebooks
Ah, okay, that worked. I'm enjoying the soundtrack now.
## Post #76
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-13T01:12:07+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Are there many movies with voice?

I managed to extract the .usm file using VGMToolbox, and it gave me 1 .m2v file, 10 .adx files and 1 .cut file. (It's the game Ending cutscene)

Now i need to know which file to edit to use the Portuguese subtitle w/ English audio.
## Post #77
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-08-13T03:19:37+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I have one last question (hopefully). For Asylum, there are RFMODSOUND files that come out as 0 bytes after being converted through fsbii and fsb_mpeg. To be specific, the music from Max B1 Ch267.
## Post #78
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-13T17:24:29+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> 10 .adx files

These are 10 audio files. You need to somehow force it to play english. I'm not sure if its possible, because all languages are stereo, and english is encoded in 6 channel.

Anyway, there are only 3 videos with voice: intro, ending & ch10 press.

Maybe you can live without it?
## Post #79
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-13T17:24:56+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Cameron007
>
> I have one last question (hopefully). For Asylum, there are RFMODSOUND files that come out as 0 bytes after being converted through fsbii and fsb_mpeg. To be specific, the music from Max B1 Ch267.

Maybe if you can send me these files, I can check.
## Post #80
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-08-14T02:48:35+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Cameron007 wrote:I have one last question (hopefully). For Asylum, there are RFMODSOUND files that come out as 0 bytes after being converted through fsbii and fsb_mpeg. To be specific, the music from Max B1 Ch267.

Maybe if you can send me these files, I can check.
[https://www.sendspace.com/file/ehq2p7](https://www.sendspace.com/file/ehq2p7)

Also, I tried other extractors. They worked, but the files were really noisy.
## Post #81
- Username: Gone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 16, 2015 11:07 am
- Post datetime: 2015-08-16T04:46:15+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I'm having a problem exporting most voice files to audio files for Arkham Knight.

Using this tool, I'm able to extract something like INT_1.wad in the English(US) into many smaller files. Using Ravioli Game Tools, I can open these small files and get a list of audio clips. For files like Militia_Walla, these audio clips play fine and I can export them to ogg files. However, for most of the audio clips this is not the case. I assume this has something to do with the subtitles being merged with the audio file. Does anyone have a solution to this? I want to be able to export normal dialog sound clips as oggs.
## Post #82
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-16T06:37:39+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

This may be caused by old version of ww2ogg in ravioli tools. If not, describe how you do extraction and name some files that don't work
## Post #83
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-16T15:21:49+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Ravioli Game Tools v2.8 uses ww2ogg v0.20
## Post #84
- Username: Gone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 16, 2015 11:07 am
- Post datetime: 2015-08-16T15:36:28+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Thanks for the help so far. Is there an older version of the converter that's supposed to work? The newest one on [http://www.hcs64.com/vgm_ripping.html](http://www.hcs64.com/vgm_ripping.html) is version 0.22.

One example of a file that doesn't work is DLG_AR, extracted from INT_1.wad using this tool. I've attached the file I'm talking about. Anything that's suffixed with "DLG_" doesn't seem to work.


[DLG_AR.zip](https://xentaxbackup.github.io/file/9542_DLG_AR.zip)
## Post #85
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-16T15:41:11+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

This exact file you uploaded works fine for me with ww2ogg v.0.22
## Post #86
- Username: Gone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 16, 2015 11:07 am
- Post datetime: 2015-08-16T21:34:56+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Okay, managed to get this to work. Just had the wrong arguments in my bat file. If anyone else had this problem and is curious, here's what it should be for Knight:

```
pause
for %%f in (*.ogg) do revorb.exe %%f
pause
```


Thanks Daemon1 for the help and of course for making the tool. Much love!
## Post #87
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2015-08-25T16:17:35+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Apparently I cannot use it for Arkham City GOTY music, any suggestion?
## Post #88
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-25T16:36:38+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Devilot
>
> Apparently I cannot use it for Arkham City GOTY music, any suggestion?

Why can't ?
## Post #89
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2015-08-25T16:41:31+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Devilot wrote:Apparently I cannot use it for Arkham City GOTY music, any suggestion?

Why can't ?

because I'm too dumb to use it properly I suspect. I keep trying to adapt it to a BIN file, where there is none.
## Post #90
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-25T16:49:09+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Go to "SFX" folder, and drag the WAD file onto Batman_bnk.exe. You must get many files, one of them called "music".

Then run city.bat in that folder.
## Post #91
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2015-08-25T16:52:13+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Go to "SFX" folder, and drag the WAD file onto Batman_bnk.exe. You must get many files, one of them called "music".

Then run city.bat in that folder.

I always dragged it onto Cut.exe... must have been that the problem.
## Post #92
- Username: joeyjoey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 20, 2012 5:28 am
- Post datetime: 2015-08-28T22:51:44+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

This is for Arkham Knight, right?   

When I drag and drop the .wad (INT_5.wad) file on "Batman_bnk.exe" I get the follow error:
"Batman_bnk does not work anymore"

I dunno what im doing wrong
## Post #93
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-29T05:49:29+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

No, this is for ALL batman games using wwise, including Arkham Knight.

Never seen such message. Can you make a screenshot?
What's your system? .net version?
## Post #94
- Username: joeyjoey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 20, 2012 5:28 am
- Post datetime: 2015-08-29T11:34:20+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Well the message is in Dutch but I translated it to English.


Error1:
(Batman_bnk has stopped working is maybe a better translation)


If you wait a few seconds you will see this:

Error 2



Specs:

Windows 7 Pro,  64 bits
Service pack 1 and .net v4
## Post #95
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-29T15:47:04+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I think the problem is in .net
Try updating it to 4.5 or additionally installing 3.5
## Post #96
- Username: joeyjoey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 20, 2012 5:28 am
- Post datetime: 2015-08-30T20:27:00+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

That's not it. When installing both I get a message that I already have .net 4.5 and 3.5.
Also tried it on my laptop (same windows version) but I got the same error. I think Im just doing something wrong   

1. I unzip both folders
2. Drag and drop the INT_1.wad file into the bnk folder (it contains Batman_bnk.exe and hashlist.txt)
3. I drag and drop the INT_1.wad onto the Batman_bnk.exe file

(Also tried to run it as administrator and older windows version but does not work either)
## Post #97
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-30T20:52:00+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Yes, this must work. Maybe the problem is in some special characters in your language version of windows.
## Post #98
- Username: joeyjoey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 20, 2012 5:28 am
- Post datetime: 2015-09-01T14:22:33+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I dont know how, but it works now
## Post #99
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2015-09-17T09:49:59+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

anyone can create a tool for subtitles?
i know subtitles stored in AkDialogueEvent files and easy for modify.
but i am amateur and not good at programing so i can't create a tool.
if anyone create a tool i will be grateful.

and sorry for my bad English
## Post #100
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-17T14:56:48+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I can help you with that.

But maybe it is better to create a new topic for this, if you want.
## Post #101
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-17T15:31:29+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from dante h3
>
> i know subtitles stored in AkDialogueEvent files and easy for modify.

You mean they're working from these small files outside of a package? Lucky.
## Post #102
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2015-09-17T15:56:15+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from ekanspt
>
> I can help you with that.

But maybe it is better to create a new topic for this, if you want.
it is up to you.
unfortunately i don't know much about programing.
so I can't help you.
but if you need ingame tests, send me a pm.

> Reply from daemon1
>
> You mean they're working from these small files outside of a package? Lucky.
no. only when work who I replace them in upk files.
## Post #103
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-17T16:46:27+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from dante h3
>
> no. only when work who I replace them in upk files.

Then how do you plan packing UPK files back? People say with UPKs upkacked game works much slower, and requires more memory.
## Post #104
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2015-09-17T17:54:17+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

i know two method, if someone can create a tool for one of this two, than we can import modified files easily.

and if you mean deompressed upk requires more memory and make game slower, than who cares!
as long as game can be localized and does not cause serious problem, players can live with that.
## Post #105
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-17T18:16:35+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from dante h3
>
> and if you mean deompressed upk requires more memory and make game slower, than who cares!

This is a message from another thread, where i made a subtitle switcher:

> Reply from BallisticSmith
>
> Just an issue that i found in Arkham Knight, given that the files are decompressed, and the .upk's get a lot bigger (extra 8gb to the total size) , the game suffers from a lot of loadings during gameplay.

Every 10 seconds, the game stutters and the loading symbol appears

This may be a problem, check how the game will run.
## Post #106
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-17T19:54:43+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

So there's a problem with the UPK files also?
## Post #107
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2015-09-18T15:56:17+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> dante h3 wrote:and if you mean deompressed upk requires more memory and make game slower, than who cares!

This is a message from another thread, where i made a subtitle switcher:
BallisticSmith wrote:Just an issue that i found in Arkham Knight, given that the files are decompressed, and the .upk's get a lot bigger (extra 8gb to the total size) , the game suffers from a lot of loadings during gameplay.

Every 10 seconds, the game stutters and the loading symbol appears

This may be a problem, check how the game will run.

> Reply from ekanspt
>
> So there's a problem with the UPK files also?
okay, that is true.
i decompressed all upk files and tested in my system. (i have 8gb ram and GeForce GTX 570)
and every time a upk file was loaded (player enter in mission area), the loading symbol appears.
if upk file was small (almost 20mb) loading takes one or two second.
but if upk was big, it takes minutes. (or forever!)
i checked all upk files and create a list of upks who have AkDialogueEvent in them.
here is the list:
[http://www.mediafire.com/view/o1qon4bpu ... eEvent.txt](http://www.mediafire.com/view/o1qon4bpulq45db/upk_files_with_AkDialogueEvent.txt)

next time i decompressed only this upks and tested again.
after that total upk files size changed only 5.5gb.
this time i didn't see any loading at all.
my game is not updated so i can't recognize other problems.
but at least after second test no loading appears.

i don't think we have problem anymore but if decompressed files still cause problem 
we should do something about big files who most of times cook (use).
most of upks always not use ingame or not big enough to cause problem.
## Post #108
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-18T20:56:26+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Good news. Then you can proceed with subtitling tool.
## Post #109
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-19T18:20:16+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

You mentioned that the modified and original files must have the same size right?
## Post #110
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2015-09-19T18:26:46+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from ekanspt
>
> You mentioned that the modified and original files must have the same size right?
as I said we have two way for import files to upks.
first one is make sure size does not change and just replace them with original.

so yes. modified and original files must have the same size.
## Post #111
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-19T18:42:43+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Have you checked this post: [viewtopic.php?f=35&t=12525](http://forum.xentax.com/viewtopic.php?f=35&t=12525)?
## Post #112
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2015-09-19T18:47:27+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from ekanspt
>
> Have you checked this post: viewtopic.php?f=35&t=12525?
yes, and I tested this tool.
but not worked. you can test it too with example file who I uploaded.

I think this is source of that tool.
[https://github.com/ahmet-celik/UPKTool_PC_XBOX_BAC](https://github.com/ahmet-celik/UPKTool_PC_XBOX_BAC)
## Post #113
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-20T08:38:27+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Of course it doesn't work, because UPK format has changed a lot, and wwise dialogue just a bit. Maybe with some corrections you can make it work with the Knight.
## Post #114
- Username: spike32
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 26, 2010 10:46 am
- Post datetime: 2015-10-07T01:15:46+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Thanks for this! I'm having a bit of trouble with Arkham Knight (only one I'm trying right now). I have extracted the INT wad files into several files like FFFA1277 etc. I am confused as to what to do from there?

Thanks.
## Post #115
- Username: souperzombie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 25, 2015 12:47 am
- Post datetime: 2015-10-08T21:39:01+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I'd also like to know how to use this correctly. I copy the batch file and the hashlist into folder and drag a wad onto it and get a bunch of files with no extension, and I've no idea what to do with them. It would also probably help if I knew what a "WAV splitting script" was.
## Post #116
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-10T12:40:41+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from spike32
>
> I have extracted the INT wad files into several files like FFFA1277 etc.

If you did everything right, files must have proper names, not these hashes. Are you sure hashlist was in the same folder?
## Post #117
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-10T12:43:31+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

There are lots of WAV splitting scripts. Check scripts by Luigi, Alpha23, maybe others. Also there are many programs that do this. For example, Ravioli tools.
## Post #118
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-10-10T22:36:37+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Good news. Then you can proceed with subtitling tool.

One thing that i tested, there are some languages in the game (russian for example) that don't have localized audio, only subtitles, hud and menu, so if you choose to use the russian language, the game will automatically play english audio. So why can't we do the same process for every other language that the game already does, which it is to force original audio since there's no russian audio. Maybe if we edit some .ini files. Just some food for thought.
## Post #119
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-11T05:38:19+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from BallisticSmith
>
> if you choose to use the russian language, the game will automatically play english audio. So why can't we do the same process for every other language

People tried that. It seems this is built into the EXE, so if we remove, say, spanish audio, the game doesn't play any audio at all.
## Post #120
- Username: souperzombie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 25, 2015 12:47 am
- Post datetime: 2015-10-11T14:39:29+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> There are lots of WAV splitting scripts. Check scripts by Luigi, Alpha23, maybe others. Also there are many programs that do this. For example, Ravioli tools.
Thanks for that, I've used quickbms in the past but apparently I forgot it existed 
I've converted them into some kind of wav files that don't play properly, but I don't know where to go from there. I've with anything that involves ww2ogg or revorb (I'm assuming that's what I need.)
## Post #121
- Username: spike32
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 26, 2010 10:46 am
- Post datetime: 2015-10-13T12:48:08+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> spike32 wrote:I have extracted the INT wad files into several files like FFFA1277 etc.

If you did everything right, files must have proper names, not these hashes. Are you sure hashlist was in the same folder?

Thanks, made sure hashlist was in the same folder, now I got names like DLG_MAIN_CH07_S22_CITYZ_RED_HOOD_TAUNT (except a few of them still have hashes for some reason). No extensions still. I run ravioli tools and get wwise files. Run them through ww2ogg022 and the OGG files don't play? What should I do from here? Thanks.

EDIT: So the only one where the previews seem to work in ravioli tools is sfx folder stuff. Everything else can't play the preview. I'm trying to get the voices.
## Post #122
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-13T15:24:00+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

That usually means you're using wrong codebooks
## Post #123
- Username: spike32
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 26, 2010 10:46 am
- Post datetime: 2015-10-13T17:40:54+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> That usually means you're using wrong codebooks

Hate to ask, but could you upload or link me to the right one? Thanks again.
## Post #124
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-13T17:53:05+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I'm using RavioliGameTools_v2.8 and its RExplorer can succesfully preview those files

As for manually converting them, use packed_codebooks_aoTuV_603.bin
These are always present with ww2ogg since 2011
## Post #125
- Username: spike32
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 26, 2010 10:46 am
- Post datetime: 2015-10-13T17:59:01+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> I'm using RavioliGameTools_v2.8 and its RExplorer can succesfully preview those files

As for manually converting them, use packed_codebooks_aoTuV_603.bin
These are always present with ww2ogg since 2011

This is what I get when I open a file in RGT_v2.8. I just opened a random one but they're all the same.
[AK.jpg](https://xentaxbackup.github.io/file/9852_AK.jpg)
## Post #126
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-13T18:55:06+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Is this from PC or XBOX?
## Post #127
- Username: spike32
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 26, 2010 10:46 am
- Post datetime: 2015-10-13T18:56:04+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Is this from PC or XBOX?

PC. Steam Version.

S:\Steam\steamapps\common\Batman Arkham Knight\BMGame\CookedPCConsole\English(US)

Came from the .wad files in this folder.
## Post #128
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-13T19:26:30+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

You are doing something wrong. Check manuals on Ravioli and ww2ogg. I even double-checked, and both programs work for me.
## Post #129
- Username: souperzombie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 25, 2015 12:47 am
- Post datetime: 2015-10-13T22:36:40+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from spike32
>
> daemon1 wrote:I'm using RavioliGameTools_v2.8 and its RExplorer can succesfully preview those files

As for manually converting them, use packed_codebooks_aoTuV_603.bin
These are always present with ww2ogg since 2011

This is what I get when I open a file in RGT_v2.8. I just opened a random one but they're all the same.
I'm having the same problems. No idea where to go from here, and I really need them ASAP for an upcoming project I'm working on.
## Post #130
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-14T04:33:02+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Did you try to convert files using ww2ogg? Do you know how to use command line or bat files? Did you change the codebooks for the one I said?

Use Google to find some tutorials.
## Post #131
- Username: souperzombie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 25, 2015 12:47 am
- Post datetime: 2015-10-14T09:07:14+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Did you try to convert files using ww2ogg? Do you know how to use command line or bat files? Did you change the codebooks for the one I said?

Use Google to find some tutorials.
Thanks for the help, apparently googling for batch files was all I needed. Using these two batch files in order seems to work so far at converting them to working .ogg files.

```
for %%i In (*.wwise) do "%CD%/ww2ogg.exe" %%i --pcb packed_codebooks_aoTuV_603.bin
```


```
for %%c in (*.OGG) do revorb.exe "%%c"
del *.bnk
del *.wav
pause
exit
```


Edit: Apparently you only need the first .bat sometimes? Eh, it works now either way.

Edit 2:Also for some reason the Joker voice lines from AK seem to only play in one ear. I think it's meant to be that way but I'm not too sure.
Revorb also seems to have a lot of trouble with voice lines from Arkham City, because it brings up an error whenever it tries to convert them. I think it's something to do with the .bat file, but it works fine with Arkham Knight. Specifically it crashes when it tries to convert a file with revorb.

Edit 3: I dragged some of the converted Joker voice line .ogg files from Arkham Knight into Vegas pro and discovered that they're actually made up of 5 different 'layers'. 4 of them are made up of ambient laughter with the other one being the voice line itself. When played in Vegas the files play normally, rather than only playing in one ear, and the layers can be unlinked from each other. If possible I'd greatly appreciate it if someone could find a way to separate the main voice lines from the ambience. Attached a sample, can't upload more because of filesize limits but to my knowledge they're all the same.


 DLG_MAIN_CH10_S03_JOKER_C1_CRIME_ALLEY_COMBAT_LINES_10.rar
(248.53 KiB) Downloaded 39 times
## Post #132
- Username: souperzombie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 25, 2015 12:47 am
- Post datetime: 2015-10-16T15:08:43+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Also the INT_8.wad file from AK and the 28CCF006_LOC_INT.wad file from AO still produce unsorted filenames (e.g. DFD38A66) even with the hashlist. Is there any fix for this?
## Post #133
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-17T07:24:39+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from souperzombie
>
>  28CCF006_LOC_INT.wad file from AO

"Arkham Origins" game WAD contains a lot of redundant audio, not used in game. Most of them spoken by female synth voice. These will have no proper names after unpacking, just hash

> Reply from souperzombie
>
> INT_8.wad file from AK

I'll check this. Probably that's from DLC that's not out yet.
## Post #134
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-17T12:00:04+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Ok I checked phrases in INT_8.wad and they are from DLCs like Scarecrow, BatGirl.... maybe others. When they will be out on PC, or when somebody will give me files from console version, I will update hash list.
## Post #135
- Username: souperzombie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 25, 2015 12:47 am
- Post datetime: 2015-10-17T13:11:00+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Ok I checked phrases in INT_8.wad and they are from DLCs like Scarecrow, BatGirl.... maybe others. When they will be out on PC, or when somebody will give me files from console version, I will update hash list.
Ok, cool. Also could I get some help or info about the stuff I put in edits in an earlier post? I'm not desperate about bulk converting/splitting/whatever the Joker audio anymore (assuming it was even possible) since they still play in a regular media player I can easily edit the ones I need in audacity, but I would like someone to fix my .bat so it works with city.
Thanks for all your help btw.
## Post #136
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-17T13:22:50+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from souperzombie
>
> I would like someone to fix my .bat so it works with city.

City is an old game, remove "--pcb packed_codebooks_aoTuV_603.bin" and it will use old codebooks.
## Post #137
- Username: souperzombie
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 25, 2015 12:47 am
- Post datetime: 2015-10-17T14:01:19+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> souperzombie wrote:I would like someone to fix my .bat so it works with city.

City is an old game, remove "--pcb packed_codebooks_aoTuV_603.bin" and it will use old codebooks.
Looks like that did it. Thanks
## Post #138
- Username: spike32
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 26, 2010 10:46 am
- Post datetime: 2015-10-19T20:31:12+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Does anyone know where the file is for the Red Hood DLC? I can find bits here and there, I can even find Black Mask's clip, but I can't find the two I'm looking for. Looking for when Red Hood says "Do I look like Batman to you" and "How about you go to hell? Say hi to the Joker for me". I searched through all the random name files and couldn't find it. But maybe I just missed it.
## Post #139
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-20T15:10:24+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Did you look in this file INT_DLC_RedHood.wad ?

Bank names EDDB613E , 153E8A78

To quickly find the phrase you need, unpack all akgialogueevent files and search them for text you need. This will give you audio event name and package (.upk) name. Then unpack the whole package and look for files with that name. Next to it you will find .akbank file.

FNV hash of this name (in lowercase) will be the number you need. You can also find this number inside of a file just after the "BKPK" magic word. Or wait while I update hashlist.
## Post #140
- Username: spike32
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 26, 2010 10:46 am
- Post datetime: 2015-10-20T16:41:31+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Did you look in this file INT_DLC_RedHood.wad ?

Bank names EDDB613E , 153E8A78

To quickly find the phrase you need, unpack all akgialogueevent files and search them for text you need. This will give you audio event name and package (.upk) name. Then unpack the whole package and look for files with that name. Next to it you will find .akbank file.

FNV hash of this name (in lowercase) will be the number you need. You can also find this number inside of a file just after the "BKPK" magic word. Or wait while I update hashlist.

I just extracted the INT_DLC_RedHood.wad and all the files there I already have from the main files. Unfortunately the files you provided don't have his responses. It just has the parts right before it where the thug and BM talks. Can't find the audio files anywhere, but I'll keep searching. Thanks.
## Post #141
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-20T17:47:20+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from spike32
>
> Unfortunately the files you provided don't have his responses.

I have these files and they have the words you mentioned. I listened to them myself. What's the file size on your side?
## Post #142
- Username: spike32
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Oct 26, 2010 10:46 am
- Post datetime: 2015-10-20T18:02:03+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> spike32 wrote:Unfortunately the files you provided don't have his responses. 

I have these files and they have the words you mentioned. I listened to them myself. What's the file size on your side?

153E8A78 is 60.7 kb
EDDB613E is 99.6 kb

EDIT: Whoops, my bad, for some reason I forgot to extract the file before running the scripts.
## Post #143
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-20T18:11:08+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

i have both files about 150kb. Very strange. So they somehow made different WAD packages for different game versions?
## Post #144
- Username: SFC3
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 04, 2015 8:42 am
- Post datetime: 2015-11-04T05:26:00+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I'm doing something wrong. Cannot seem to get .wem files to "cut" into DLC music for Arkham Knight. I'm extracting the music from SFX_DLC_Batgirl.wad, but they're coming out as blank files that I can only open in Ravioli and extract without any "metadata", so I can't cut it.

Are the DLC .wad's configured for PC yet or am I doing something horribly wrong?
## Post #145
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-04T06:22:34+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I don't have that DLC, so they can't have proper names.
## Post #146
- Username: SFC3
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 04, 2015 8:42 am
- Post datetime: 2015-11-04T07:04:45+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> I don't have that DLC, so they can't have proper names.
That's unfortunate. Is there anyway I can "add" these proper names myself? Where would they be located?
## Post #147
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-04T10:23:22+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

pm sent
## Post #148
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2015-11-10T20:06:54+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I tryed to localizating Red Hood DLC but this tool only gave me this files.

[http://pho.to/9rrol](http://pho.to/9rrol)

Is there need a another tool for localizate?
## Post #149
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-10T20:27:15+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

i forgot to update the files
## Post #150
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2015-11-11T01:11:15+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Skrillex
>
> I tryed to localizating Red Hood DLC but this tool only gave me this files.

http://pho.to/9rrol

Is there need a another tool for localizate?

UP! I tryed INT_DLC_RedHood.wad.
## Post #151
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-11T15:16:59+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Skrillex
>
> UP! I tryed INT_DLC_RedHood.wad.

You did something wrong. It works with this file.
## Post #152
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2015-11-14T03:54:33+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> Skrillex wrote:UP! I tryed INT_DLC_RedHood.wad.

You did something wrong. It works with this file.

Localization is work? I only pull the .wad file and left on the batman_bnk.exe, i'd make wrong now?
## Post #153
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-14T08:33:15+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Skrillex
>
> Localization is work? I only pull the .wad file and left on the batman_bnk.exe, i'd make wrong now?

Localization is what? Do you have the "hashlist.txt" there?
## Post #154
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-14T08:34:44+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Tools updated. Support for Arkham Knight DLC's about Redhood & Batgirl (names for banks, also proper names for music)
## Post #155
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2015-11-15T18:35:49+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> 
Localization is what? Do you have the "hashlist.txt" there?

That's mean i want the localization to turkish language. It that possible on this tool?
## Post #156
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-15T19:48:52+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Skrillex
>
> daemon1 wrote:
Localization is what? Do you have the "hashlist.txt" there?

That's mean i want the localization to turkish language. It that possible on this tool?

No. It's a tool for audio extraction.
## Post #157
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2015-11-18T18:38:55+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> 

No. It's a tool for audio extraction.

Is there any tool for extract and repack subtitles this game?
## Post #158
- Username: leop2p
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 20, 2013 12:49 am
- Post datetime: 2016-09-18T22:35:14+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Hi there!!!

Everything is almost great, thanks for the great tool for extracting the music from Batman AC. But I faced one little problem.
I've got 759 WEMs and ww2ogg extracts only 749 of them. So there's an error while extracting that 10 files. I will quote only one of them:
> Input: MUS_Chapter1_MUS_Explore_0.wem
>
> Parse error: RIFF truncated
>
> Audiokinetic Wwise RIFF/RIFX Vorbis to Ogg Vorbis converter 0.19 by hcs

So, could you please help me. Or should I not to worry about? I just need only music, not SFX.


Thank you!!!
## Post #159
- Username: Whover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 05, 2015 11:22 pm
- Post datetime: 2017-01-15T12:03:44+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I've extracted the 'Music' file from the Arkham Knight SFX_1.wad file but then for extracting the wwise files I don't have the banklist.txt file for Knight, only a hashlist.txt file. I can extract the files from the 'Music' file but they just output as 'File0001', 'File0002' etc with no proper names. Where do I find the banklist.txt file for Knight for proper name extraction?
## Post #160
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-15T12:23:56+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

You don't need any text files to extract music.
Just run .bat files.
## Post #161
- Username: Whover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 05, 2015 11:22 pm
- Post datetime: 2017-01-15T12:49:02+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

If I run the knight.bat file (in the same folder as the 'Music' file) then the command prompt says "'cut' is not recognized as an internal or external command, operable program or batch file". Do I need to do something else?

EDIT: I hadn't moved the cut.exe into the same folder - it works now, thanks for the help
## Post #162
- Username: killbane77
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 18, 2017 9:29 am
- Post datetime: 2017-01-19T14:57:22+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Where can I find a WAV splitting script for these files
## Post #163
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T15:09:53+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from killbane77
>
> Where can I find a WAV splitting script for these files

it can be any WAV splitting  script. google it
## Post #164
- Username: LitosbC
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 11, 2017 8:15 pm
- Post datetime: 2017-02-11T14:26:37+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

This is my first post in the forum, so I want to apologize in advance if it's too vague or nooby...

I just wanted to ask if it's possible to change the .akEvent in some .upk files (wich means decompressing and recompressing them) to change the dialogue associated with some specific events? The aim is to make the normal thugs react to the Red Hood player as the Black Mask thugs react in the story DLC. This is evident in the AR challenges in which the thugs react to Nightwing, Robin and Catwoman (the Rocksteady characters) and not to the DLC characters (the WB Montréal ones). Now this can be done in different ways, but the easiest seems to be to add the relevant lines from the SFX_DLC_RedHood.wad to the SFX_1.wad (through  and change the BARKSET_DLC_RS_AR_BANKS-CLONED_CombatThug-AlwaysLoaded-nightwing-ALL_SF and the BARKSET_COMBAT-CLONED_CombatThug-AlwaysLoaded-nightwing-ALL_SF to point to said lines of dialog. That might be too complicated to do, but I wanted to ask if it's possible. Shame that the rocksteady characters got their own specific Barksets but the WBM didn't. 

So tell me what you think, and if this is offtopic sorry.

You guys might be able to pull this off.

And daemon thx for the great tool.

PS: I tried to extract the lines from SFX_DLC_RedHood.wad and it only gave me these:
MDLC00_AMB_Gen_Room_01
MDLC00_AMB_Gen_Room_03
MDLC00_Music_All
MDLC00_SE_MUS_Stingers_GEN
MDLC00_SE_MUS_Stingers_GEN
MDLC00_SE_Redhood_B1_Mall_Intro
MDLC00_SE_Redhood_B1_Officel_Intro
MDLC00_WEA_Exterior_Rain_2D
MDLC00_WEA_Rain_From_Inside_PS
## Post #165
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-11T20:13:20+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Replacing anything in UPK files will take a lot of efforts. This is possible, so if you like, you can try it.
## Post #166
- Username: LitosbC
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 11, 2017 8:15 pm
- Post datetime: 2017-02-11T20:34:07+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Well I can't do it... I was hoping to get some guidance here...

BTW were are the DLC dialogue sounds stored? Cause I extracted the respective .wad files and I didn't find the dialogue lines... Any help getting those?
## Post #167
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-12T09:52:28+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I don't remember. It was almost 2 years ago. And I don't have DLCs myself.
## Post #168
- Username: LitosbC
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 11, 2017 8:15 pm
- Post datetime: 2017-02-12T10:24:47+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from daemon1
>
> I don't remember. It was almost 2 years ago. And I don't have DLCs myself.

Are they not supposed to be stored inside the .wad file? Or are there any other files containing sound?
## Post #169
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-12T11:29:06+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

As I said, I don't remember. But if you say they use some different sounds, they can be in another WAD file.
## Post #170
- Username: bob64
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 18, 2017 8:10 am
- Post datetime: 2017-04-23T04:38:50+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Hello everyone,

First of all, I want to thank daemon1 for giving us this great tool!

But I do have a burning question: how does someone go about repacking a .WAD file, after extracting it?

I hate having to ask which might seem like an obvious question-- but I've read this thread up and down. As well other Batman related threads on this forum and even tried googling stuff on .WAD files (mostly found a bunch of stuff about the old doom .WAD files, haha), to no avail. 

My goal is to eventually edit audio files said by the militia thugs in Arkham Knight.

I should also state that I've had no problems with extracting .WAD files so far, using Daemon1's tool. I'm just stuck on the basics of how to repack them, so I can use the modified .WAD's in-game. 

Thanks in advance to anyone who can answer.

Many thanks,
bob64
## Post #171
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-23T05:30:56+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from bob64
>
> I'm just stuck on the basics of how to repack them

Repacking audio is not a basic thing. Its much more complex than extracting. I made no tools for that, because there was no need.
## Post #172
- Username: bob64
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 18, 2017 8:10 am
- Post datetime: 2017-04-23T05:55:54+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Oh wow! 

Now lets say I wanted to try and figure out how to repack audio, do you have any suggestions? (even vague tips, since I know this is uncharted territory, haha)

And thanks for your response! I appreciate it nonetheless.
## Post #173
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-23T06:09:18+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from bob64
>
> Oh wow! 

Now lets say I wanted to try and figure out how to repack audio, do you have any suggestions?

Look at the picture at the thread start, it will tell you that proper packing would require writing a program that can change 100s or even 1000s of game files, because thugs audio is embedded in almost every single game package.

You can also try replacing them only in WAD file, that could be done manually with hex editing, but it will require making audio equal or less in size than original. You can encode audio with official wwise tools.
## Post #174
- Username: bob64
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 18, 2017 8:10 am
- Post datetime: 2017-04-23T06:10:50+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Ok, many thanks again!
## Post #175
- Username: Khronos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 05, 2017 5:23 pm
- Post datetime: 2017-06-05T09:30:03+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

I know it's been a while, but is there any chance of getting the new Arkham DLC added to the music unpacker?

There's the GCPD, Flip a Coin and Catwoman DLC available.
## Post #176
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-05T15:14:08+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

i doubt i will have time for this. But in any case, I will need game files to do it.
## Post #177
- Username: Drozz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 29, 2017 1:38 am
- Post datetime: 2017-07-28T17:49:57+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Hi there, not sure if this is the correct way to ask this or proper for this forum, but here goes:

Arkham Origins - Steam

So I love this free roam song, The Night Before Christmas, and it used to play nonstop/constant on my old save file, which I loved, it really immersed me more than the other 4 free roam songs. Now I'm on my second save file and I've yet to here this song.

Is there a requirement to activate the song? Maybe my previous file was messed up by only playing The Night Before Christmas and nothing else whilst free roam? Eitherway, is there a way to mod the game or something to allow me to listen to only this free roam song and not the others?

Now my save file seems to be stuck with "Winter Comes to Gotham" free roam song, as I can't get it to change for the life of me. I've entered/exit multiple areas in the game multiple times and I keep getting the same free roam song. I've exit the game and relaunched it and it's stuck on this song and wont play any other song whilst free roaming.

After searching for a solution, I decided to look into the .ini files for some sort of syntax to give me a clue to be able to remove "Winter Comes to Gotham" and replace it with "The Night Before Christmas" track. I've looked for what seems dozens of .ini files to no avail. Is this possible? I'd figure this would be the best forum to get help on editing the music.

Any help would be great. Thanks!
## Post #178
- Username: arkham45128
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 26, 2017 5:22 am
- Post datetime: 2017-12-06T23:09:37+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Hi everyone!

I want to have the spanish audio of Batman AA, AC and AO 

What do I have to do? Thanks!
## Post #179
- Username: MToprakTRE1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 29, 2018 6:03 am
- Post datetime: 2018-08-04T16:51:53+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Hello, guys i want to find Batman Arkham Knight audio files and replace it with my own record. I dont know what to do. May someone explain and show everythink step by step ? I am very grateful if you show it. You seem very knowledgeable in such matters. I think you can help me
## Post #180
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-05-30T19:00:06+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Thank you so much for this.
## Post #181
- Username: Gamer101
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2016 11:01 pm
- Post datetime: 2020-09-16T00:10:23+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Hello,

I liked to thank you, daemon1, for the wonderful program and all the other inputs posted on this thread.

I used the program over the last couple days on all the Batman games with .wad files with resounding results, however it's not perfect.

1) I get hash names for all the later Arkham Knight DLC's starting with Nightwing's GCPD Lockdown to the Season of Infamy.

2) Even with the success of getting Arkham city dialogue files, some of files are seem to be incomplete. One example is that at the start of the Mr. Freeze boss fight, Freeze would say "You are in my world now, Batman." If you will not help me, you will die here." but when I played the audio file, he only says the second sentence. Another better example would be stories of Calendar Man's murders on certain holidays are not complete.

3) The .wad files doesn't look like it has the audio from the Game Over scenes. They could be in the .upk files, but so far I haven't much luck.

If you're interested/willing to update the hashlist, I can provide you the Arkham Knight later DLC files via a MEGA link (I have all the Batman files with me). I just need a confirmation by PM.
If you move on to greener pastures, I understand. Thank you again for your wonderful program.
## Post #182
- Username: spennser
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 30, 2016 1:12 pm
- Post datetime: 2020-09-16T23:54:43+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Gamer101 ↑Wed Sep 16, 2020 8:10 am at Wed Sep 16, 2020 8:10 am
>
> 
Hello,

I liked to thank you, daemon1, for the wonderful program and all the other inputs posted on this thread.

I used the program over the last couple days on all the Batman games with .wad files with resounding results, however it's not perfect.

1) I get hash names for all the later Arkham Knight DLC's starting with Nightwing's GCPD Lockdown to the Season of Infamy.

2) Even with the success of getting Arkham city dialogue files, some of files are seem to be incomplete. One example is that at the start of the Mr. Freeze boss fight, Freeze would say "You are in my world now, Batman." If you will not help me, you will die here." but when I played the audio file, he only says the second sentence. Another better example would be stories of Calendar Man's murders on certain holidays are not complete.

3) The .wad files doesn't look like it has the audio from the Game Over scenes. They could be in the .upk files, but so far I haven't much luck.

If you're interested/willing to update the hashlist, I can provide you the Arkham Knight later DLC files via a MEGA link (I have all the Batman files with me). I just need a confirmation by PM.
If you move on to greener pastures, I understand. Thank you again for your wonderful program.

would you be able to send over the random fight SFX from the games? thank you so much!
## Post #183
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-17T04:31:44+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

> Reply from Gamer101 ↑Wed Sep 16, 2020 8:10 am at Wed Sep 16, 2020 8:10 am
>
> 
If you move on to greener pastures, I understand. Thank you again for your wonderful program.
Yes, i'm far away now
## Post #184
- Username: DarkKJin13
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 29, 2022 11:45 am
- Post datetime: 2022-04-29T05:20:01+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Can't find the Origins Online Haslist.
## Post #185
- Username: MidwayMoster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 05, 2023 2:51 pm
- Post datetime: 2023-01-05T06:54:55+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

anyone have any idea where the punch and knockout sounds are?
## Post #186
- Username: Beaminator
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 04, 2023 5:50 am
- Post datetime: 2023-01-05T20:21:18+00:00
- Post Title: Re: Batman Arkham audio extractor with proper names

Hey guys, I'm looking for the Arkham Knight Batmobile sound files, but it seems that the extractor didn't extract all of the Batmobile sounds judging by the hashlist (unless there's Batmobile sounds in some other Arkham game that I'm missing).

It isn't just the Batmobile stuff either, a lot of the sounds aren't being extracted. Can anyone help me?
