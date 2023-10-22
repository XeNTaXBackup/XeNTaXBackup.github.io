## Post #1
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-02T02:41:35+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

I have managed to extract the files inside of swtor_main_bnk_audio_1.tor using the [EasyMYP](http://code.google.com/p/easymyp/downloads/list) Tool (rename .tor to .myp), which gives 12 .txt files. Renaming these to .bnk, I used the bnkextr Tool (attached) to get a large number of small .wav files named in a numerical order. 

I am having trouble decoding these files with wav2ogg (attached) and had a look in hex editor. I noticed the RIFF WAVE header, but I cannot decode it.

[](http://postimage.org/image/5m2dhl3gr/)
[bnkextr.zip](https://xentaxbackup.github.io/file/4883_bnkextr.zip)
## Post #2
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-02T14:19:04+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

The audio format of TOR is actually one of the easiest file formats. 

Most soundfiles are stored in BKHD/.bnk archives (eg. dialogues, sound effects) and can be extracted with "bnkextr" (see [this topic](http://forum.xentax.com/viewtopic.php?f=17&t=3477&start=30) for a link to Russian forum with the download, I recommend using Google Translate).

Once you extract the BKHD archives, you will get multiple .ogg files with the RIFF..6.WAVEfmt header. This is the proprietary audio format used by Wwise. The soundtrack (ie. music) of the game can be found directly in the TOR archives under the folder /bnk/streamed/ and does not need to be extracted, by the way. Once you have the .ogg files, you can convert them with the tool ww2ogg (download [here](http://hcs64.com/vgm_ripping.html)).

The converted files are often missing the duration and cannot be played in all .ogg players. I was able to play them in the Google Chrome audio player and the tool foobar2000, though I have not yet found a good tool to convert the files into WAV or MP3.

If you did not understand something or need more help, just tell me! We're already analysing the file formats in [this topic](http://forum.xentax.com/viewtopic.php?f=10&t=7186) so that's why I could answer so fast.
## Post #3
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-02T23:18:21+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

I did use the other topic to get into the .tor files, very helpful.

Well I unpacked a few of the .wav files from swtor_main_bnk_streamed_a_1.tor but they would not convert with ww2ogg. I got the error 'Error opening packed_codebooks.bin'. I'm not sure what is it on about as it's definitely there and I've tried copying it into the directory I am working in.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-03T01:25:11+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

packed_codebooks.bin needs to be in the current working directory, where you are running from, not necessarily where the .wav files or the .exe are.  Let me know how you are running ww2ogg.exe if you are still having problems.
## Post #5
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-03T01:44:22+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

Ok that worked, but now it does not play in VLC or FooBar2000. In Google Chrome, it comes out as some high pitched static.
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-03T06:08:02+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

If you could upload some of the source files that convert poorly I can take a look, as of 0.17 I am not entirely sure of how to detect a particular format change that has shown up a lot recently, so that may be an issue.

Also make sure you are using the latest version, and as [the vgm_ripping page](http://hcs64.com/vgm_ripping.html) suggests you might want to use revorb to clean up the output files (this at least fixes an issue I've heard for foobar).
## Post #7
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-03T06:13:24+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

They all converted poorly, and I have tried using revorb, which just crashes when I use it on any of the files. I tried attaching a .wav but I get a server error message, I'm going to host it somewhere and link to it.
## Post #8
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-03T06:16:16+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-03T14:29:37+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

You're right, ww2ogg no longer works with the newest version of the beta files. They very likely changed the audio format so we can no longer convert the files so easily.
I guess now it's back to the drawing board.
## Post #10
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-04T00:16:56+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

Yeah, this is an odd one.  It looks like every individual unit is being converted in a reasonable way, but some of the codebooks being chosen for residue are invalid (with 0 value mapping).  My best guess is that the packed codebooks have changed; usually they are accessed in a very different order than what is seen here (with the mapping 0 codebooks enumerated first, and in no particular order [414, 293, 247, 89, etc]; here the mapping 0 codebooks are scattered around and the enumeration is ordered [38, 39, 40, 41, 41, etc], and yet the residue still gives a contiguous list of codebooks as it used to), so the codebooks may have been shuffled around, or new ones may have been added, etc.

If there are any audiokinetic dlls sitting around could you be so kind as to zip 'em up and send them my way?

Edit:
Yeah, this seems quite likely to be the case.  In the changelist for 2011.2.1 (September 21, 2011), they mention:
WG-19004 Updated Vorbis encoder to aoTuV beta 6.03.

Since the old packed_codebooks.bin was generated from codebooks used by the Xiph encoder, it is likely laid out quite differently now.  With any luck everything will still work the same and we'll just need to locate the new codebooks.

Edit2:
It appears that this same item has been in the changelists since 2011.2 (July 25), so it's weird that it hasn't come up till now, but I guess it makes sense in terms of dev cycle.
## Post #11
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-04T00:27:53+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-04T01:05:35+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

No luck, must be linked into something else.  I'm grabbing the latest win SDK, it should show up there.

[edit]
ww2ogg 0.18 up now, includes a new file, packed_codebooks_aoTuV_603.bin, which contains the new packed codebooks.
0.18 supports specifying the name of the file to use with the --pcb switch, in order to avoid breaking things it defaults to packed_codebooks.bin, which is the old one.  The new packed codebooks works with the file you posted.

For clarity:
```
ww2ogg.exe 0AB0A18A_2BFF9306A49537DA.wav --pcb packed_codebooks_aoTuV_603.bin
```
## Post #13
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-04T04:07:29+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

It works.

For anyone looking to do a quick batch convert:

```
for %f in (*.ogg) do revorb.exe %f

```


The files will play in VLC after revorb
## Post #14
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-12-04T07:22:48+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

ww2ogg 0.19 fixes the previous and next window flags.  This is something that had been bothering me for a while, the reference decoder doesn't use these, but Tremor does, so files with shortened packets weren't playing right on some players (eg Rockbox) even after revorb.
## Post #15
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-04T10:23:20+00:00
- Post Title: Star Wars - The Old Republic Beta Audio Files

Great job, hcs! Thank you very much for fixing ww2ogg!  

In the newest version of Wwise, the audio files now have the extension .wem and not .wav, so I used the following lines for a batch file. And I had to use %%f instead of %f for it to work, but I am not an expert with DOS commands so I do not know why this is the case.

```
pause
for %%f in (*.ogg) do revorb.exe %%f
pause
```


Furthermore, I now wrote a quickBMS script for extracting the WEM archives that can be found in the localised assets. This is my first BMS script so I hope I did everything correct.

```
for i = 0 < numberOfFiles
get fileName string
get fileSize longlong
get fileOffset longlong
log fileName fileOffset fileSize
next i
```
## Post #16
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-04T11:25:08+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

What would be useful now is something that could convert all these hexadecimal file names into readable names. I've had a look around inside a few of the .tor files but there doesn't seem to be anything. Where and how do they store this information?
## Post #17
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-04T11:38:27+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

The TOR archives themselves do not store the file names but only their hashes. easyMYP has some of the file names stored and can therefore recognize many file names, but not all.
As an example, here are some file names of audio files:

```
/resources/bnk/streamed/sfx/music_background_unsettled_17_kotor2_mus_a_262_3959c1d5.ogg
/resources/bnk/streamed/sfx/music_event_mysterymoment_29_kotor1_mus_theme_czerka_3959c1d5.ogg
/resources/bnk/streamed/sfx/sfx_cine_custom_pipesystembreak_ba73f164.ogg
```

However, the newest version of the beta files is not yet completely supported by easyMYP; that's why you only see those hex values.
## Post #18
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-04T12:08:12+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

I don't know how to configure easyMYP to rename files like that. But there must be somewhere that contains a list of all the proper file names, the developers cannot reference resources by their hash.
## Post #19
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-04T12:26:08+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

You're right, the filenames are stored somewhere in some XML files from the TOR archives. The problem is that these files are spread all over the archives (eg. every dialogue file references its sound file) and therefore it is not that easy to automatically get all file names.

To import the file names, download the newest version from [here](http://holocron.so/files/tormyp.tar.bz2). The file hashes_filename.txt has to be placed in a subfolder called "Hash". But as I said, this file list (with about 50% of the file names recognized) is based on an earlier version of SW:TOR and does not recognize the files from the current versions.
## Post #20
- Username: Piviton
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 02, 2011 10:28 am
- Post datetime: 2011-12-04T12:44:07+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Which of the .tor files contain .xml files that reference the music? I have yet to find one reference. I have found some of the dialogue ones though.
## Post #21
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-04T12:59:12+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Some of the compiled XML files in the bucket files reference sounds to be played during a dialogue:

```
Play SFX: Play_cine_custom_stolenship_takeoff
```


And also some of the area files (_everywhere_.dat) contain the name of the background music:

```
.rgnCharacteristics=!ambience:char_sel_bounty_hunter,music:mus_char_sel_bounty_hunter!
```


However, I am not sure how these names relate to the file paths.

Some of the <DataTable> xml files also contain sound information:

```
   <Table>
      <Columns>
         <Column name="tree name" id="1631f07c-76f8-4207-bb93-02caa8691653" position="0" />
         <Column name="display name" id="20d4d3a4-efad-45c6-91e8-029408702277" position="1" />
         <Column name="event call" id="c3fd99c8-9356-45ee-b5ff-d8429d055271" position="2" refType="soundEvent" />
         <Column name="play time" id="f46ac95c-16ae-4ff2-b6e7-95a1afae52c9" position="3" />
         <Column name="priority" id="f6f27736-e671-42ec-8f89-7b27e00a9dcb" position="4" />
      </Columns>
      <Rows>
         <Row>
            <tree_name>background.calm</tree_name>
            <display_name>Background - Calm (1:30)</display_name>
            <event_call>playmusic_background_calm</event_call>
            <play_time>00:01:30</play_time>
            <priority>event</priority>
         </Row>
         <Row>
            <tree_name>background.dark</tree_name>
            <display_name>Background - Dark (1:30)</display_name>
            <event_call>playmusic_background_dark</event_call>
            <play_time>00:01:30</play_time>
            <priority>event</priority>
         </Row>
```


```
   <Table>
      <Columns>
         <Column name="spec" id="3dfdfe2b-c964-413c-b32e-c9c957a85c86" position="0" />
         <Column name="soundset" id="40f2d7f4-922a-427a-9ef5-7dc99618c650" position="1" refType="weak_relativePath[.bnk]"/>
         <Column name="soundset_fr-fr" id="e826ff1e-0b2e-4250-954d-ef4529ce9b3f" position="2" refType="weak_relativePath[.bnk]"/>
         <Column name="soundset_de-de" id="332ccf92-82c2-45c1-9bb3-0dc6dbcdd9d9" position="3" refType="weak_relativePath[.bnk]"/>
         <Column name="footstep_class" id="434afc19-f770-4fe7-a617-b454260869fe" position="4" />
         <Column name="impact_class" id="8217caf8-5375-4683-b0cc-2c096c348206" position="5" />
         <Column name="voice_processing" id="8f55ec98-2684-4e20-8937-7914e8eb0801" position="6" />
         <Column name="swing_type" id="a15c3abb-75b0-45fa-a5cb-fef1b840a000" position="7" />
         <Column name="continuous_movement" id="efb14528-0ba3-4813-9fac-d4ed67233e9d" position="8" />
         <Column name="armor_type" id="28336a9c-dfcf-4bf6-a0eb-5ed362640b3a" position="9" refType="datatableRef[tbl.utlwiseswitchgroups, 'armortype']"/>
      </Columns>
      <Rows>
         <Row>
            <spec>alien_abyssin_low</spec>
            <soundset>abyssin_m_alien_low_soundset</soundset>
            <soundset_fr-fr>abyssin_m_alien_low_soundset</soundset_fr-fr>
            <soundset_de-de>abyssin_m_alien_low_soundset</soundset_de-de>
            <footstep_class>humanoid</footstep_class>
            <impact_class>FLESH</impact_class>
            <voice_processing></voice_processing>
            <swing_type></swing_type>
            <continuous_movement></continuous_movement>
            <armor_type></armor_type>
         </Row>
```
## Post #22
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2011-12-30T14:52:22+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Anyone mind helping me with the command line function to extract from the .bnk's into separate sub folders, so that I don't overwrite any of the extracted wavs? since they do not like to extract under unique names... I get a slew of .001-.4000.wav files.
## Post #23
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2012-01-12T00:42:23+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Hey guys, I have been having a difficult time with these .bnk files from SWTOR.  So I am able to extract individual .bnk files from the .tor archives.  I then tried to use that bnkextr from that russian site that was posted earlier in the thread.  It ends up extracting various .wav files, numbered like .001.wav to .050.wav or whatever.  At this point I try to use this ww2ogg .19 and revorb to convert them into a playable format, but the .ogg files that are output still do not want to play.  

I am obviously messing something up here, so I am just wondering if someone can maybe post their methods on how they are able to get playable audio from some of the .tor bnk files.  Also, can quickbms be used to unpack/repack these bnk files at all?  Some of these questions might sound silly, but just trying to figure all this stuff out.  Thanks in advance.
## Post #24
- Username: marmelada
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 06, 2012 1:28 am
- Post datetime: 2012-02-06T18:20:09+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Bump.

I have similiar problem as Seifer. I'm able to extract bnk and wem files, but I can't do anything with them. And I want so badly sondtrack from tor
## Post #25
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-02-06T18:58:21+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Converting the WEM files is not so difficult, you can do this with ww2ogg.
However, I am not sure why you want to get those files. Most of the soundtrack is already on YouTube, and the remaining pieces are either background music or music from the Star Wars movies / KotOR games. The beautiful pieces that contain an actual melody are online.
And the file names in SW:TOR are terrible; you just have hundreds of files like /resources/bnk2/streamed/1004295821.wem and don't know what kind of music is in them. 

Anyway, here's a noobish step-by-step guide; I hope it's not too simple for you: 

Guide to identifying audio files in SW:TOR
Star Wars: The Old Republic uses three kinds of audio files: .bnk, .acb and .wem files. The first two file types are archives, a.k.a. they contain .wem files. The .wem files are just sound files in a special format developed by [Wwise](http://www.audiokinetic.com/en/products/wwise/introduction).
Depending on which files you have, pick the appropriate guide below.

If you have a different file extension, or are unsure which file you have, follow these steps:
1. If you do not have a hex editor, download [HxD](http://mh-nexus.de/en/hxd/), and open your file in this program.
2. Look at the first bytes at the beginning of the file. These will tell you which file you have:
--- a. If the file starts with BKHD, you have a *.bnk file. These files contain sound effects, like blaster fire, steps, wind effects, etc.
--- b. If the file starts with RIFF....WAVEfmt, you have a *.wem file. These are the files that contain the soundtrack, a.k.a. the music.
--- c. If bytes #5-9 are zeros (00 00 00 00), then you have a *.acb file. These files contain dialogue, i.e. spoken words.

Guide: Converting .bnk to .wem
1. Go to the folder where you have your .bnk files stored.
2. Download [bnkextr.zip](http://ctpax-cheater.narod.ru/personal/bnkextr.zip). You may need to click on the bold link on that Russian page if the download does not pop up immediately.
3. Extract the zip archive and copy bnkextr.exe to your .bnk folder.
4. Now drag a .bnk file and drop it onto bnkextr.exe. Beware: A .bnk archive may contain hundreds of .wem files, so do this one file at a time.
5. In the folder, you will now find a few .wav files. These are actually .wem files; the bnkextr program just uses an older file extension.
6. Create a new text document in this folder, rename it to extensionChanger.bat. Open this .bat file with notepad, then copy & paste the following line. Then save and close Notepad.

```
ren *.wav *.wem
```
7. In the folder, double-click on the .bat file. Your .wav files will now be renamed to .wem files. You can now follow the steps below to convert the .wem files to .ogg files.

Guide: Converting .acb to .wem
1. Go to the folder where you have your .acb files stored.
2. Create a new text document in this folder, rename it to convert.bms. Open this .bms file with notepad, then copy & paste the following lines. Then save and close Notepad.

```
for i = 0 < numberOfFiles
get fileName string
get fileSize longlong
get fileOffset longlong
log fileName fileOffset fileSize
next i
```
3. Download [quickbms.zip](http://aluigi.org/papers/quickbms.zip), copy quickbms.exe in your *.acb folder and run it.
4. In the open file dialogue, select your convert.bms file. In the second dialogue, select a .acb file or enter "" to convert all .acb files in the folder.
5. Select the output folder.
6. QuickBMS will now convert all .acb files to .wem files. See below on how to convert these files to .ogg files.

Guide: Converting .wem to .ogg
1. Go to the folder where you have your *.wem files.
2. Download [ww2ogg019.zip](http://hcs64.com/files/ww2ogg019.zip) and [revorb.exe](http://yirkha.fud.cz/progs/foobar2000/revorb.exe). Extract the ZIP archive. Then copy ww2ogg.exe, packed_codebooks_aoTuV_603.bin and revorb.exe into the folder with your *.wem files.
3. Now create a new text document in this folder, rename it to convert.bat. Open this .bat file with notepad, then copy & paste the following lines. Then save and close Notepad.

```
pause
for %%f in (*.ogg) do revorb.exe %%f
pause
```
4. In the folder, double-click on the .bat file. Now you will find—in addition to your .wem files—.ogg files in the folder. These files can be played in any .ogg player. I recommend [foobar2000](http://www.foobar2000.org/) as it is easy to create playlists there, but any other programs (except Windows Media Player) will work as well.
## Post #26
- Username: marmelada
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 06, 2012 1:28 am
- Post datetime: 2012-02-06T21:50:35+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Thank you! It turns out I had almost all tools downloaded, but I'd never figure out myself, how to write these batch files.


> However, I am not sure why you want to get those files. Most of the soundtrack is already on YouTube, and the remaining pieces are either background music or music from the Star Wars movies / KotOR games. The beautiful pieces that contain an actual melody are online.
>
> And the file names in SW:TOR are terrible; you just have hundreds of files like /resources/bnk2/streamed/1004295821.wem and don't know what kind of music is in them.

In game files you have much more music, than in OST. I learned that when I unpacked WoW and Portal files. Lightsaber sounds and dialogs also are very interesting.

Once again thank you
## Post #27
- Username: marmelada
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 06, 2012 1:28 am
- Post datetime: 2012-02-07T21:34:00+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

I managed to write a small batch script to handle bnk files. Since sometimes you get over 20 of these when unpacking a file and I'm lazy I wrote this:

```
md "%%~na" 2>nul
move "%%a" "%%~na"
copy bnkextr.exe %%~na
copy ww2ogg.exe %%~na
copy revorb.exe %%~na
copy packed_codebooks_aoTuV_603.bin %%~na
cd %%~na
bnkextr.exe %%a
del %%a
ren *.wav *.wem

for %%f in (*.wem) do (
ww2ogg.exe %%f --pcb packed_codebooks_aoTuV_603.bin
if exist "%%~nf.ogg" del %%f
)
for %%f in (*.ogg) do revorb.exe %%f

del packed_codebooks_aoTuV_603.bin
del *.exe
cd ..
)
for /f "delims=" %%d in ('dir /s /b /ad ^| sort /r') do rd "%%d"
```

WARNING: This will delete original bnk files after unpacking them!

How to use:
Copy bnkextr.exe; ww2ogg.exe; revorb.exe and packed_codebooks_aoTuV_603.bin along with this bat file to directory with bnk files and run .bat script.

What's going to happen:
Each bnk file will get its own directory and get unpacked. Then .wem files will be converted to ogg and revorbed. Wem files will be deleted (only those that got converted! I don't know why sometimes ww2ogg doesn't want to convert files). And then it goes to another bnk. At the end all empty folders will be deleted.

Ta-da!

I hope it'll be helpful to someone
## Post #28
- Username: Carsten2011b
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 31, 2011 3:44 am
- Post datetime: 2012-03-01T21:19:44+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

I tried the audio guide, but I'm stuck at the HxD part. :/ Can anyone tell me which .tor files contain .bnk, .wem, and .acb files (or better yet, upload and post all the converted files (the dialouge and SFX, and the music, but only if the music has path directories that show their file names (having the same for the SFX and dialogue would be nice too).
## Post #29
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-03-02T12:48:43+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

There are too many audio files to upload them all, but here's a list of the .tor archives containing audio files. (assuming you are using the current release version of the client files)
I'm recommending using the 90% hashes_filename.txt list for easyMYP I posted here as this has most of the file names and file extensions for the audio files. You only need to use HxD if you do not have a file extension.

The swtor_en-us_*_1.tor archives contain the English dialogue in .acb files, grouped by the planet and quest they are spoken in. (swtor_de-de_*_1.tor and swtor_fr-fr_*_1.tor contain the German and French dialogue, respectively). The subtitles can be found in the .stb files in swtor_en-us_global_1.tor but the .stb files themselves are encoded and AFAIK there is no public program to open them yet.
The three swtor_main_bnk_streamed_a/b/c_1.tor archives contain the music in .wem files.
All other swtor_main_bnk_*_1.tor archives contain sound effects in .bnk files:

swtor_main_bnk_voc_1.tor contains alien languages and grunts/laughter/coughs etc., so basically anything that does not need to be translated into German or French.
swtor_main_bnk_audio_1.tor contains weapon sounds (blaster fire, lightsabers) and steps on wood/metal/...
swtor_main_bnk_audiodata_1.tor and swtor_main_bnk_location_1.tor contain all other sound effects grouped by planet, e.g. wind noises, alarm sounds, background chatter, beeping computer consoles, ...
## Post #30
- Username: Carsten2011b
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 31, 2011 3:44 am
- Post datetime: 2012-03-02T14:08:43+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

> Reply from SWTOR fan
>
> There are too many audio files to upload them all, but here's a list of the .tor archives containing audio files. (assuming you are using the current release version of the client files)
I'm recommending using the 90% hashes_filename.txt list for easyMYP I posted here as this has most of the file names and file extensions for the audio files. You only need to use HxD if you do not have a file extension.

The swtor_en-us_*_1.tor archives contain the English dialogue in .acb files, grouped by the planet and quest they are spoken in. (swtor_de-de_*_1.tor and swtor_fr-fr_*_1.tor contain the German and French dialogue, respectively). The subtitles can be found in the .stb files in swtor_en-us_global_1.tor but the .stb files themselves are encoded and AFAIK there is no public program to open them yet.
The three swtor_main_bnk_streamed_a/b/c_1.tor archives contain the music in .wem files.
All other swtor_main_bnk_*_1.tor archives contain sound effects in .bnk files:

swtor_main_bnk_voc_1.tor contains alien languages and grunts/laughter/coughs etc., so basically anything that does not need to be translated into German or French.
swtor_main_bnk_audio_1.tor contains weapon sounds (blaster fire, lightsabers) and steps on wood/metal/...
swtor_main_bnk_audiodata_1.tor and swtor_main_bnk_location_1.tor contain all other sound effects grouped by planet, e.g. wind noises, alarm sounds, background chatter, beeping computer consoles, ...
Thank you, really. This helps me out a lot.  Just one other thing, how do you get the .bnk's organized like "/resources/bnk2/location_act_2_ships_media.bnk" and actual path names such as "/resources/bnk/streamed/sfx/music_event_mysterymoment_29_kotor1_mus_theme_czerka_3959c1d5.ogg"?
## Post #31
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-03-02T15:26:23+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Most of those file names were taken from the time when the archives still included the file names. The new file names that were added since then I mostly find out by guessing them or by checking other files that reference the file names. It really is a very arduous process to get the remaining file names. 

As a sidenote, the file name "/resources/bnk/streamed/sfx/music_event_mysterymoment_29_kotor1_mus_theme_czerka_3959c1d5.ogg" was used during the beta and unfortunately, the new music files no longer have such a descriptive file name but just something like "/resources/bnk2/streamed/1004295821.wem".
## Post #32
- Username: Carsten2011b
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 31, 2011 3:44 am
- Post datetime: 2012-03-02T17:07:19+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Darn it  Well, thank's for the info anyway.  And on a side note, I'm part of a group on Final Fantasy Shrine Forums where we're identifying the tracks from the files in accordance to the official tracks from the Free Soundtrack on the TOR website/Facebook/YouTube and the Collector's Edition soundtrack. I'll send you a PM to the link of the spreadsheet if you're interested
## Post #33
- Username: Odontoblaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 06, 2011 12:39 pm
- Post datetime: 2012-07-14T15:01:56+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

OK so I have done everything above as far as extracting the .bnk files and downloading the bnkext I put them in the same folder then dropped the bnk file onto the bnkext and all that happened is a window flashed open for a split second then nothing. Am I doing something wrong? Have the .bnk's changed to not work with the extractor any more? Any help would be great.
## Post #34
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-11-28T22:48:25+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Once more a long time has gone by, but I am still there, and as eager as ever to find out more about the files from SWTOR, in my mind the best MMO ever. 

So with encouragement from the people at Final Fantasy Shrine Forums, I decided to take another look at the Wwise SoundBank (.bnk) files, and boy, was I surprised. Finally, I have found the connection between the sound events given in the prototype nodes, and the audio files. It was in the SoundBanks all along, in the middle of the HIRC section, but I never bothered to take a closer look at it until I realised the missing information is in there.
Slowly, but steadily, I am getting there! As always, I am publishing a full file format specification (you can see my current progress on the wiki here: click - it will be even longer than the .gr2 specification I fear) so that other developers can write their own .bnk file extractor/converter, but I will not publish a .bnk program myself.

By the way, I am not sure why the bnkextr.exe no longer works, I have not used it in ages, since I wrote my own extractor a long time ago. However, I have not changed my own extractor for months so I doubt that the .bnk files have changed. Maybe the .bnk file you have is corrupted or was extracted the wrong way?
Anyway, you may want to try the [QuickBMS script](http://forum.xentax.com/viewtopic.php?f=10&t=4284) by AlphaTwentyThree.
## Post #35
- Username: Chiff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 19, 2016 10:29 pm
- Post datetime: 2016-01-19T14:38:26+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

> Reply from SWTOR fan
>
> 
Guide: Converting .wem to .ogg
1. Go to the folder where you have your *.wem files.
2. Download ww2ogg019.zip and revorb.exe. Extract the ZIP archive. Then copy ww2ogg.exe, packed_codebooks_aoTuV_603.bin and revorb.exe into the folder with your *.wem files.
3. Now create a new text document in this folder, rename it to convert.bat. Open this .bat file with notepad, then copy & paste the following lines. Then save and close Notepad.
Code: Select allfor %%f in (*.wem) do ww2ogg.exe %%f --pcb packed_codebooks_aoTuV_603.bin
pause
for %%f in (*.ogg) do revorb.exe %%f
pause4. In the folder, double-click on the .bat file. Now you will find—in addition to your .wem files—.ogg files in the folder. These files can be played in any .ogg player. I recommend foobar2000 as it is easy to create playlists there, but any other programs (except Windows Media Player) will work as well.

I've been using these instructions to convert .wem files from Star Citizen, and I can get quite a few .ogg files from using it, however it seems to fail on at least 2 out of 3 .wem files. Any idea why this might be?
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-19T16:46:34+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

They are PCM or ADPCM files. PCM are rare, can be opened after changing codec byte. 

ADPCM decoder: [viewtopic.php?p=110795#p110795](http://forum.xentax.com/viewtopic.php?p=110795#p110795)
## Post #37
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2016-01-30T15:18:49+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Hey daemon1,

I was just wondering if you knew of any program that can convert sound files (like .ogg or normal .wav) into the type of .wav that SWTOR recognizes.  You guys were mentioning .wem, so is that the type of file that swtor uses?  And if so, how would we convert sounds into that format?  

I was messing around with file swapping and the .wavs that I was able to extract from games like Assassins Creed Unity/Syndicate and Alien Isolation are easily recognizable by SWTOR and will play in game if you swap them out.  Vice versa is also true, AC games will recognize swtor sounds.  However, neither game recognizes normal .wav files.  So I assume both these companies use similar compression settings or something?  hah, I am pretty clueless when it comes to this stuff.

But yeah, any help in this matter would definitely be appreciated.
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-30T15:40:08+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

This "program" is called wwise.
## Post #39
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2016-01-30T19:51:46+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Hey, thanks for the reply.

I tried messing around with audiokinetic's wwise and was able to convert some random .wav to .wem.  However, they don't seem to play.  Not sure if I am using the proper conversion settings in Wwise's audio converter.  I looked up the details of the base SWTOR .wav I was able to extract from the .bnk files and it says:  24000 Hz, between 40-50 kb/s, 1 chnl.  For codec it says 0xffff (development use).

Not really sure if any of that info helps or not.  Just trying to provide as much info as I can.  

Anyways, thanks for the help.  If I can't get it to work, no big deal.

Take care.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-30T20:18:51+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

> Reply from Seifer29
>
> However, they don't seem to play.

That's most probably because of no forwards compatibility. You should use wwise version close to what they used to make the game. Maybe 2011 or 2010.
## Post #41
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2016-01-31T01:29:49+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

Hey, thanks for the help.

I figured out what I was screwing up.  There was an option for vorbis in the audio converter of wwise.  I stupidly thought that would output a .ogg file and figured that would be incorrect, lol.  Obviously, I was incorrect in my assumption.  So yeah, I used vorbis and 24000 Hz as my output options and it works fine.  This was done using wwise 2013, which was the earliest version that I could find, but it's possible this method works in the newest versions as well.

Anyway, thanks for the assistance.  Take care.
## Post #42
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2016-11-11T22:20:29+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

> Reply from Piviton
>
> I have managed to extract the files inside of swtor_main_bnk_audio_1.tor using the EasyMYP Tool (rename .tor to .myp), which gives 12 .txt files. Renaming these to .bnk, I used the bnkextr Tool (attached) to get a large number of small .wav files named in a numerical order. 

I am having trouble decoding these files with wav2ogg (attached) and had a look in hex editor. I noticed the RIFF WAVE header, but I cannot decode it.

Excuse me, but how do you get EasyMYP to read the hashnames and such? When I tried to extracted the .wem files, they came out as “BANK001” and other numbers. Can anybody walk me through this, please? I’ll try to send you the necessary information as best I can to help you too.
## Post #43
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-11-05T12:20:19+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files


## Post #44
- Username: pinglefingle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 14, 2018 8:50 am
- Post datetime: 2018-04-14T00:56:22+00:00
- Post Title: Re: Star Wars - The Old Republic Beta Audio Files

I realize this thread is very old, but I'm hoping somebody can help me out here. Forgive me for potential ignorance by the way. I'm trying to convert the WEM files from Star Fox Zero to OGG. I've followed the directions for this, but when I open the command prompt, it says this.

C:\Users\Me\Desktop\SFZ Voices>for %f in (*.wem) do ww2ogg.exe %f --pcb packed_codebooks_aoTuV_603.bin

C:\Users\Me\Desktop\SFZ Voices>pause
Press any key to continue . . .

C:\Users\Me\Desktop\SFZ Voices>for %f in (*.ogg) do revorb.exe %f

C:\Users\Me\Desktop\SFZ Voices>pause
Press any key to continue . . .

After pressing any key both times, the command prompt window just closes and the files aren't converted. Am I doing something wrong?
