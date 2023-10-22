## Post #1
- Username: Izerantas
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-09-03T19:52:48+00:00
- Post Title: [IKS] MediEvil Resurrection PSP - Tools & Tips

Hello. I would like to share my knowledge about modding and translating MediEvil Resurrection on PSP platform. It wouldn't be possible without help from @ViToTiV who created working unpacker/repacker for this  game.


* gamedata.bin unpack and repack *

If you want to get any important data from this game, you have to unpack main archive which is called gamedata.bin. It can be found in MEDIEVIL\PSP_GAME\USRDIR\gamedata.bin and you can unpack/repack using ViToTiV's tool.

Download gamedata.bin repacker + sources --> [https://www.dropbox.com/s/e3k2r70nnan9k ... 9.rar?dl=0](https://www.dropbox.com/s/e3k2r70nnan9kmj/Medievil_psp_extractor_%28plus_source%29.rar?dl=0)

There is also quick bms script for that [https://www.dropbox.com/s/2w31lh16im1ld ... p.bms?dl=0](https://www.dropbox.com/s/2w31lh16im1ldd3/medievil_resurrection_psp.bms?dl=0), but I recommend to use repacker tool.

* Text replace *

There are currently two tools for changing in-game texts. One is text editor from ViToTiV
and the second one is my LTR Tool. Both tools you can download below.

Download MediEvil Text Editor + sources --> [https://www.dropbox.com/s/layfqs27odgng ... 9.rar?dl=0](https://www.dropbox.com/s/layfqs27odgngob/MediEvil_psp_TextEditor_%28plus_source%29.rar?dl=0)

Download MediEvil LTR Tool:


 MediEvil_Ressurection_LTR_Tool_6.zip
(2.66 KiB) Downloaded 39 times



I'm not sure how to work with text editor, because I have never used it.  Instead, I used my LTR Tool, because it fullfilled all my needs for translation (like built-in char replacer or export to INI function).

So to use my LTR tool just adjust paths on the end of the script, comment/uncomment functions and run it in Python 2.7.


* Font replace *

After unpacking content from gamedata.bin, all fonts can be found in folder "01-global.group.toc_ex".

Here is the list with descriptions:

```
00493.PSM - Sound and controls settings font, also font for subtitles in loading screens, for menu after pressing start button while playing and for subtitles when you pick up a  new weapon
00495.PSM - Inventory, big yellow font on the middle of the screen. Also some subtitles in mini games.
00497.PSM - Main menu font (where skeleton is pointing on subtitles)
00499.PSM - Small font on game HUD (gold amount,life amount, percent of chalice fill). Also font in mini games description.
00501.PSM - The most important font. It is used in all gamme dialogues, books and during cutscenes.
```


To edit fonts, open them in TileMolester with these settings:
codec - 4bit
offset - 0x60
Block size - 4x1
Canvas size - 32x30

* Movies replace *

Movies are not stored in gamedata.bin archive. They can be found in MEDIEVIL\PSP_GAME\USRDIR\movies folder.
There are 4 movies which don't have in-game subtitles and can be translated separately:

```
p_fm_cs_001.pmf - intro
p_fm_cs_002.pmf - outro + credits
p_fm_cs_005.pmf - game over scene
```


There are some tools to extract and replace movies. See the list below.

PMF to AVI Tools:
- mplayer
- mencoder
- vgm toolbox
- virtualdub

AVI to PMF Tools:
- Umd Stream Composer
- MPStoPMF
- PmfCreator

After you collect all tools, you can start conversion.

PMF to AVI conversion:
1. Run Windows command-line (cmd.exe).
2. Execute cd <mplayer_folder>
3. Execute mplayer -dumpvideo <pmf_file_path>
4. Execute mencoder.exe stream.dump -ovc raw -noskip -ofps 29.97 -o done.avi
5. Extract OMA Audio from PMF file using vgm toolbox
6. Convert OMA to WAV. You can do it here [https://audio.online-convert.com/convert-to-wav](https://audio.online-convert.com/convert-to-wav) or here [https://www.filezigzag.com/](https://www.filezigzag.com/)
7. Use virtualdub to merge audio and video to AVI file.
8. [optionally] Use AVI ReComp to add subtitles to AVI and decrease file size.

AVI to PMF conversion:
1. Run Umd Stream Composer
2. Create new project in Umd Stream Composer. Remember to check option "PSP Movie".
3. Drag your AVI and WAV files to Umd Stream Composer window.
4. Compile MPS file in Umd Stream Composer using option "Encode+Multiplex".
5. Create PMF using MPStoPMF or PmfCreator tools.

In case of any troubles, this tutorial will be useful [http://forums.dashhacks.com/psp-xmb-sou ... orial.html](http://forums.dashhacks.com/psp-xmb-sounds-pmfs/140043-alternative-custom-gameboot-tutorial.html)
After you convert all movies to PMF, you can simply replace them in movie folder MEDIEVIL\PSP_GAME\USRDIR\movies.


* More translation info *

Translation is possible on USA version of the game, but there are some technical issues while trying to fully translate EUR version. There is no way to replace english subtitles in some dialogues, they may be compiled in game executable. So it's better for you to get USA version.

If you want to see some examples, please check my polish translation here [https://ikskoks.pl/medievil-resurrection-spolszczenie/](https://ikskoks.pl/medievil-resurrection-spolszczenie/)
And youtube video here [https://www.youtube.com/watch?v=xFRYKU_KxZE](https://www.youtube.com/watch?v=xFRYKU_KxZE)
## Post #2
- Username: Izerantas
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 08, 2021 9:38 pm
- Post datetime: 2021-01-08T15:12:58+00:00
- Post Title: [IKS] MediEvil Resurrection PSP - Tools & Tips

Thank you for sharing all this! Do you still have Vitotiv's unpacker by any chance? I'm trying to get Dan's voice files from the game but the quickbms script didn't export everything for me.
## Post #3
- Username: Izerantas
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-08T15:42:14+00:00
- Post Title: [IKS] MediEvil Resurrection PSP - Tools & Tips

Yeah, I have these tools. They are still on my dropbox, but something has changed in sharing policy. That's why above links don't work.

Here is an mirror on googe drive instead:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1-3JkSSW1-TEiUo2D_t2AtCK9g9s2xSHc?usp=sharing)
## Post #4
- Username: Izerantas
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 08, 2021 9:38 pm
- Post datetime: 2021-01-09T00:19:51+00:00
- Post Title: [IKS] MediEvil Resurrection PSP - Tools & Tips

It works! Much appreciated thank you 
 At this point I just have to figure out which are the audio files other than the at3 ones
