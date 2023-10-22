## Post #1
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-12-08T14:39:43+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Hi mates,

I was wondering if someone was curious enough to look into the .pck audio containers from this game because it's pissing me off. 
Indeed, it appears that different audio format are used in a same .pck container: like Wwise OGG Vorbis and Wwise IMA ADPCM (not sure for this one).

I already tried multiple tools and techniques on those files:

_Nova Extractor (works, but doesn't recognize different formats).
_Riveal (works too, can make the difference between Wwise OGG and Wwise IMA ADPCM, makes correct folder, but doesn't extract all the files).
_Ravioli scanner and extractor (doesn't work at all).

So, if one of you guys got a better way to correctly convert those files, I'll take it.

Many thanks in advance.
## Post #2
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-12-08T17:10:36+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Try [this](http://forum.xentax.com/viewtopic.php?p=80192#p80192) for extracting PCK. For decoding Wwise Vorbis use [ww2ogg](https://www.hcs64.com/vgm_ripping.html), for Wwise APDCM use [this](http://forum.xentax.com/viewtopic.php?p=110795#p110795), and [this](http://forum.xentax.com/viewtopic.php?p=108929#p108929) for Wwise PCM.
## Post #3
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-12-09T06:46:40+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Alright, thanks spider91.

Now, I've got some questions:

I've got, at least, 4 containers extracted from .pck (with this [func_getTYPE.bms](http://forum.xentax.com/download/file.php?id=8265) from the .pck archive extractor you gave me):

-at3 (don't know anything about this format at all)
-lwav (don't know much about this format too)
-wwise (can't make the difference between Vorbis and/or ADPCM)
-bnk (ok, no big deal for this one)

My first question: is it possible to create correct subfolders via bnkextr.exe during exraction (like "BNK_S_W_Assault_RemingtonR4" subfolder, "BNK_S_W_pistol_FN57USG" subfolder, "BNK_VO_Hostage" subfolder, etc...) Like "Riveal" do?

Second question: is it possible to distinguish Wwise Vorbis and Wwise ADPCM during extraction with the pck extractor script?

If I ask those questions it's because it'll take me ages to know which tool I'll have to use on each format...

PS: one of those screwed up format that I couldn't convert with the tools you gave me: attached!
[BNK_S_W_Pistol_Desert_Eagle_NW.001.zip](https://xentaxbackup.github.io/file/10130_BNK_S_W_Pistol_Desert_Eagle_NW.001.zip)
## Post #4
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-12-09T15:39:44+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

-at3 - i guess it's wwise pcm.
-lwav - upload some samples.

Don't know about subfolders.

Yes, it's possible, but script need to be modified to do that. Maybe i'll do that in future, don't have much time now.

Sometimes files inside .bnk are only small parts from original .wwise files inside .pck. That's your case, so you can't convert that files and don't need to, cause you have full versions of that files in .pck. Also you can use [this](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=89662#p89662) script to extract .bnk too.

As about discovering each fomat. Why should it take ages? Just run ww2ogg batch file for *.wwise than same with wwise_adpcm tool and you will get all files converted.
## Post #5
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-12-10T05:10:48+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Ok thanks mate I'll try it.

I've attached some lwav samples and one at3 file.
[AT3&LWAV-samples.zip](https://xentaxbackup.github.io/file/10133_AT3&LWAV-samples.zip)
## Post #6
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-12-10T05:40:49+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

.at3 - wwise pcm
.lwav - wwise adpcm
## Post #7
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-12-10T05:58:26+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Nice,

I noticed that some (not all of them) at3 files are correctly converted but can't be played by any audio software.
[AT3files.zip](https://xentaxbackup.github.io/file/10134_AT3files.zip)
## Post #8
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-12-10T07:55:33+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

I see where is the problem, it's about additional chunks. Will update script a bit later, now i need some sleep.
## Post #9
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-12-10T18:24:28+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Here you go

```
get DUMMY long
idstring "WAVEfmt "
get CHUNK_SIZE long
for CHUNK_NAME = "" != "data" 
	goto CHUNK_SIZE 0 SEEK_CUR
	savepos CHUNK_POS 0
	getdstring CHUNK_NAME 4 0
	get CHUNK_SIZE long 0
next
math DATA_OFFSET = CHUNK_POS
math DATA_SIZE = CHUNK_SIZE
math DATA_SIZE += 0x8
math RIFF_SIZE = DATA_SIZE
math RIFF_SIZE += 0x1C
log MEMORY_FILE 0 0
append
log MEMORY_FILE 0 0x24
log MEMORY_FILE DATA_OFFSET DATA_SIZE
append
putVarChr MEMORY_FILE 0x04 RIFF_SIZE long
putVarChr MEMORY_FILE 0x10 0x10 long
putVarChr MEMORY_FILE 0x14 0x01 short
get SIZE asize MEMORY_FILE
get NAME basename
string NAME += ".wav"
log NAME 0x00 SIZE MEMORY_FILE

```
## Post #10
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-12-10T19:51:23+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Okay thanks mate. I'll give it a shot tomorrow.
## Post #11
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-01-11T18:02:43+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Hey there,

I tried to extract all the R6 Siege sound files and after several hours of trial and error I managed to convert all the .lwav and .at3 files into .wav files, however, this does not include any of the voice files (which are all in .Wwise). I also tried to make use of Riveal, but with barely any success (regarding the voice files) either: exactly 3 files were correctly extracted and they were all the same...

I also didn't have any success using ww2ogg to convert the .Wwise (and .wem) files, no matter wether I extracted them of the .bnk files or .pck files, as the converted files don't playback any sound (using VLC). They've however different file sizes (reaching from 4KB to 310KB) but when trying to use Revorb it just crashes.

My question is: did anyone manage to extract and convert these files and if so, what did I do wrong?

tl;dr: .pck files get (apparently) extracted correctly, .Wwise files can (apparently) not get converted correctly, .bnk files are (apparently) useless and .lwav and .at3 files get converted correctly.


Edit:
Took a break, came back and figuered it out within a few minutes: Using ww2ogg with the other codebook converts the .Wwise files correctly and thus revorb doesn't crash either. The .bnk files also contain .Wwise, .lwav and .at3 files which can get converted correctly, too, however, "only" 121'870 of the nearly 400'000 files are convertable.
## Post #12
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-01-22T20:36:06+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

> Reply from FatalBulletHit
>
> As it took me quite a time to extract and convert all audio files properly I wrote a batch script which does every step completley automated.

All scripts are included in the archive down below (of course with sources in the ReadMe.txt), QuickBMS and ww2ogg are downloaded automatically, paths can be changed if necessary and you may choose which file formats to extract/convert and/or delete, too.

EDIT

The batch only solution is no longer available as it is outdated, but you can click [here](http://forum.xentax.com/viewtopic.php?p=140570#p140570) for the latest version of the PowerShell based Tom Clancy's Rainbow Six Siege Audio Extractor.
## Post #13
- Username: agm114d
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 11, 2017 9:18 pm
- Post datetime: 2018-03-01T10:50:11+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

Hello guys, as I have found, all the weapons sounds(the most exciting part) are contained in bnk files. 

How ever, I used quick bms code, and different versions of bnkextr.exe, the output are some strange files with different suffix (wem ,wav). 

The extracted files can not be played, or converted using ww2oggg or ww_apdcm. 

I upload one of the files extracted from a bnk file (which is BenelliM3 Shotgun sound by the name of extracted files). Can anyone find a tool to convert them?
[BNK_S_W_Shotgun_BenelliM3_NW.001.zip](https://xentaxbackup.github.io/file/13975_BNK_S_W_Shotgun_BenelliM3_NW.001.zip)
## Post #14
- Username: agm114d
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 11, 2017 9:18 pm
- Post datetime: 2018-03-01T10:53:44+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

> Reply from FatalBulletHit
>
> As it took me quite a time to extract and convert all audio files properly I wrote a batch script which does every step completley automated.

All scripts are included in the archive down below (of course with sources in the ReadMe.txt), QuickBMS and ww2ogg are downloaded automatically, paths can be changed if necessary and you may choose which file formats to extract/convert and/or delete, too.

Thx for the work. However I have to point out that you missed the bnk file, which contains all the weapons sounds.
## Post #15
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-03-02T10:27:45+00:00
- Post Title: Rainbow Six: Siege AudioKinetic PCK container

> Reply from agm114d
>
> Thx for the work. However I have to point out that you missed the bnk file, which contains all the weapons sounds.

Very true indeed, am busy with another project as of now, but if there is demand I may as well just finish this beforehand over the weekend. Will post another reply when the update version is finished and uploaded.
## Post #16
- Username: borntosowdeath
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 04, 2018 8:15 am
- Post datetime: 2018-05-04T00:17:32+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Reply from FatalBulletHit
>
> agm114d wrote:Thx for the work. However I have to point out that you missed the bnk file, which contains all the weapons sounds.

Very true indeed, am busy with another project as of now, but if there is demand I may as well just finish this beforehand over the weekend. Will post another reply when the update version is finished and uploaded.

It would be very nice of you :> 
PS. You can safely rename/remove map sounds and it doesn't break the game... I wonder if you'd be able to re-pack those sounds to remove just annoying things s.a. sprinklers in vault/lockers on Bank map. Then it would be nice to remove sound imparements s.a. stun grenade, flash grenade, explosion etc. Last (but not least) it would be nice to do something with video part (no flash/dizzy, remove objects, change textures) - but that's not for this section :>
## Post #17
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-05-05T13:26:14+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Reply from borntosowdeath
>
> I wonder if you'd be able to re-pack those sounds to remove just annoying things s.a. sprinklers in vault/lockers on Bank map. Then it would be nice to remove sound imparements s.a. stun grenade, flash grenade, explosion etc. Last (but not least) it would be nice to do something with video part (no flash/dizzy, remove objects, change textures) - but that's not for this section :>

I'd hope and assume that Ubisoft/BattlEye verifies the FileHashes of the user's installation directory on each and every game launch.
While I'd love to see more control over the audio playback, it is most likely impossible to repack altered files and play the game.
## Post #18
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-05-15T16:11:19+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Tom Clancy's Rainbow Six Siege - Audio Extractor (0.9.3)

!!! This project is on hold indefinitely !!!
For further info see my latest post.

This does not work with the latest version of Tom Clancy's Rainbow Six Siege as there are no .pck files anymore.

```
[code]####################################################################################################
# <><><><><><><><><> [READ ME] Tom Clancy's Rainbow Six Siege - Audio Extractor <><><><><><><><><> #
#                                                                                                  #
#                                                                                                  #
# The Tom Clancy's Rainbow Six Siege - Audio Extractor will download multiple resources in order   #
# to extract, convert and sort most of the audio files from the Ubisoft game Tom Clancy's Rainbow  #
# Six Siege.                                                                                       #
#                                                                                                  #
# Be aware that the entire process may take several hours. For information on how to increase      #
# performance, check the documentation (see below).                                                #
#                                                                                                  #
#                                                                                                  #
# Note that from now on sorting is no longer directly possible as the proper names have been       #
# removed from the end of the '.bnk' files when the audio source files were changed and is now     #
# done based on file names and OasisIDs from old source files.                                     #
#                                                                                                  #
# Additionally all the '.lwav' files have been altered in a way that they are now extracted as     #
# '.wav_unknown' files and cannot be converted at the moment.                                      #
#                                                                                                  #
#                                                                                                  #
# Disclaimer:                                                                                      #
#                                                                                                  #
# I did not write any of the programs or scripts that are needed for extraction and conversion.    #
# All credits belong to their authors, you may check out the links to the forum entries and        #
# websites below.                                                                                  #
#                                                                                                  #
#     QuickBMS                                                                                     #
#         http://aluigi.altervista.org/quickbms.htm                                                #
#                                                                                                  #
#     pck_AKPK_extractor.bms                                                                       #
#         http://forum.xentax.com/viewtopic.php?p=80192#p80192                                     #
#                                                                                                  #
#     func_getTYPE.bms                                                                             #
#         http://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577                                #
#                                                                                                  #
#     bnk_extractor.bms                                                                            #
#         http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=89662#p89662                         #
#                                                                                                  #
#     ww2ogg (includes packed_codebooks_aoTuV_603.bin)                                             #
#         https://www.hcs64.com/vgm_ripping.html                                                   #
#         https://github.com/hcs64/ww2ogg                                                          #
#                                                                                                  #
#     revorb                                                                                       #
#         https://hydrogenaud.io/index.php/topic,64328.msg574110.html#msg574110                    #
#                                                                                                  #
#     wwise_ima_adpcm (sound_conveter_v1.15.zip)                                                   #
#         https://bitbucket.org/zabb65/payday-2-modding-information/downloads                      #
#                                                                                                  #
#     wwise_pcm_decoder.bms                                                                        #
#         http://forum.xentax.com/viewtopic.php?p=110795#p110795                                   #
#                                                                                                  #
#                                                                                                  #
# Documentation:                                                                                   #
#                                                                                                  #
#     XeNTaX post                                                                                  #
#         http://forum.xentax.com/viewtopic.php?p=140570#p140570                                   #
#                                                                                                  #
#     Name overview                                                                                #
#         https://goo.gl/PxQuCTv                                                                   #
#                                                                                                  #
#                                                                                                  #
# Feel free to contact me if you have any suggestions or feedback, as well as bugs or similar.     #
# You can do that by replying in the XeNTaX thread (see above) or emailing me (see below).         #
#                                                                                                  #
#                                                                                                  #
# <><><><><><><><><><><><><><><> Contact:  FatalBulletHit@gmail.com <><><><><><><><><><><><><><><> #
####################################################################################################[/ code]
[color=#0040FF][b]Feel free to post suggestions, feedback and bug reports down below, it is greatly appreciated![/b][/color] :roll:


[size=125][b]INSTALLATION AND USAGE[/b][/size]

All you need is Tom Clancy's Rainbow Six Siege[color=#FF0000][b]¹[/b][/color], Windows PowerShell 5[color=#FF0000][b]²[/b][/color] (included in Windows 10) and the launcher for the Tom Clancy's Rainbow Six Siege - Audio Extractor.

[b][list=1][*] Download either the Launcher.zip attachment (see below) or use the [url=https://drive.google.com/uc?export=download&id=1K8qAaSNEo-VGB5KKY5hlTTHdDyMx4yls][color=#4885ed]G[/color][color=#db3236]o[/color][color=#f4c20d]o[/color][color=#4885ed]g[/color][color=#3cba54]l[/color][color=#db3236]e[/color] Drive direct download link[/b][/url].

There is also a [url=https://pastebin.com/iC6YuYPj][b]Pastebin[/b][/url] mirror and a [url=https://drive.google.com/drive/folders/1RCNF1xBNTBi31BLiVVj3Omy6DVdt7Hl4?usp=sharing][b][color=#4885ed]G[/color][color=#db3236]o[/color][color=#f4c20d]o[/color][color=#4885ed]g[/color][color=#3cba54]l[/color][color=#db3236]e[/color] Drive folder[/b][/url] with all the resources (all will be kept up-to-date).


[attachment=0]Launcher.zip[/attachment]



[b][*] Open the archive and start 'Launcher.bat'.[/b]

The launcher functions as a wrapper[color=#FF0000][b]³[/b][/color] and will download and start the main PowerShell script ('tc_r6s_audio_extractor.ps1'), which will guide you through the rest.
If you need/want to adjust some preferences, exit after installation and edit the main PowerShell script with notepad or a source code editor of your choice.
[/list]


[color=#FF0000][b]¹[/b][/color] Only the audio containers ('.pck' files) are needed.
[color=#FF0000][b]²[/b][/color] Also tested with PowerShell 7 (Windows PowerShell 4 and potentially PowerShell 6 should work, too). If you don't have Windows 10 or any of the listed PowerShell versions, I recommend you download the latest version of PowerShell from [url=https://github.com/PowerShell/powershell/releases][b]GitHub[/b][/url]).
[color=#FF0000][b]³[/b][/color] The batch wrapper is used in order to improve accessibility (primarily for those who are unfamiliar with PowerShell) and bypass the normally restricted script execution policy.


[b][size=125]DOCUMENTATION[/size][/b]

[list=1][*][u][b]PERFORMANCE[/b][/u]

[b][color=#FF0000]Note that this is under no circumstances required and should be treated with care![/color][/b]

Performance can be increased quite significantly by disabling Real-time protection, as explained in [url=https://youtu.be/6ZGqKUQkWA4][b]this short video[/b][/url]. This may vary a lot from system to system, for reference: the overall duration on my system is reduced by a third from 1h30 to 1h.


[b][/b]
[*][u][b]ERRORS AND WARNINGS[/b][/u]

[b][color=#FF0000]ERROR: Script crashed on startup![/color][/b]
[list][b]The script crashed on startup and no preferences were adjusted.[/b]
This is probably down to me. Please share the displayed error log by either replying in this thread or sending me an email.[/list]

[list][b]The script crashed on startup and at least one preference was adjusted.[/b]
Check if the syntax is correct (see [b]PREFERENCES[/b] below).[/list]

[b][color=#FF0000]ERROR: Script already running![/color][/b]
[list][b]An instance of the script is already running.[/b]
Wait for the current instance to finish or close it.[/list]

[b][color=#FF0000]ERROR: Missing the following resources: [...] Download manually or try again.[/color][/b]
[list][b]The script could not not establish an internet connection.[/b]
Check your internet connection and try again.[/list]

[list][b]The script cannot download all of the resources.[/b]
Download the resources manually from the [url=https://drive.google.com/drive/folders/1RCNF1xBNTBi31BLiVVj3Omy6DVdt7Hl4?usp=sharing][b][color=#4885ed]G[/color][color=#db3236]o[/color][color=#f4c20d]o[/color][color=#4885ed]g[/color][color=#3cba54]l[/color][color=#db3236]e[/color] Drive folder[/b][/url] (you can right click the folder 'resources', select download and extract the archive at the location of the main script).[/list]

[b][color=#FF0000]ERROR: Cannot find Tom Clancy's Rainbow Six Siege installation directory, define manually in script![/color][/b]
[list][b]The script cannot retrieve the installation directory from the registry (most likely non-UPlay version).[/b]
Uncomment line 76 by deleting the hash symbol (#) at the beginning of the line and adjust the path if needed (see [b][url=https://support.ubisoft.com/en-US/Faqs/000038997/Finding-the-installation-location-of-your-games]Finding the installation of your games - Ubisoft Support[/url][/b] for more information).

[b]Example 1 (line 76):[/b] [code]$dirSource = "C:\Program Files (x86)\Steam\steamapps\common\Tom Clancy's Rainbow Six Siege"[/ code][/list]

[list][b]The adjusted path does not exist.[/b]
Check if the adjusted path is correct and enclosed by double quotation marks (see [b]Example 1[/b] above).[/list]

[list][b]You only have the audio containers ('.pck' files).[/b]
Uncomment line 76 by deleting the hash symbol (#) at the beginning of the line and adjust the path.

[b]Example 2 (line 76):[/b] [code]$dirSource = "D:\Audio\Tom Clancy's Rainbow Six Siege\pck"[/ code][/list]

[b][color=#FF0000]ERROR: Cannot find any source files, define manually in script![/color][/b]
[list][b]The script cannot find any '.pck' files at the installation directory.[/b]
Verify the game files and try again.[/list]

[list][b]The script cannot find any '.pck' files at the adjusted path.[/b]
Check if the adjusted path is correct and enclosed by double quotation marks (see [b]Example 1[/b] above).[/list]

[b][color=#FFBF00]WARNING: Cannot establish internet connection![/color][/b]
[list][b]The script could not establish an internet connection.[/b]
Check your internet connection and try again.[/list]

[b][color=#FFBF00]WARNING: An error occurred during script execution![/color][/b]
[list][b]There was an error during script execution.[/b]
This is probably down to me. Please share the error log (should be in the error_logs folder) by either replying in this thread or sending me an email.[/list]


[b][/b]
[*][u][b]PREFERENCES[/b][/u]

[b]Output directory[/b]
[list][b]By default, an output directory is created at the location of the main script.[/b]
This can be changed by adjusting the path at line 79.

[b]Example 3 (line 79):[/b] [code]$dirOutput = "D:\Rainbow Six Siege\Audio"[/ code][/list]

[b]Remove '.wav_unknown' files[/b]
[list][b]By default, '.wav_unknown' files (previously extracted as '.lwav' files) are removed before conversion together with the remaining redundant files ('.00040000', '.01020000' and '.wav' (before conversion)) as they currently cannot be converted.[/b]
This can be changed by adjusting the option at line 82. Note that this option will have no affect if removing redundant files is disabled.

[b]Example 4 (line 82):[/b] [code]$wav_unknownRedundant = 0[/ code][/list]

[b]Remove redundant files[/b]
[list][b]By default, redundant files ('.00040000', '.01020000', '.wav' (before conversion) and '.wav_unknown') are removed before conversion.[/b]
This can be changed by adjusting the option at line 85. Note that these files seem to be useless.

[b]Example 4 (line 85):[/b] [code]$removeRedundant = 0[/ code][/list]

[b]Remove duplicate files[/b]
[list][b]By default, duplicate files are removed before conversion.[/b]
This can be changed by adjusting the option at line 88.

[b]Example 4 (line 88):[/b] [code]$removeDuplicates = 0[/ code][/list]

[b]Remove source files[/b]
[list][b]By default, '.bnk' files are removed before conversion and the remaining source files removed after conversion.[/b]
This can be changed by adjusting the option at line 91.

[b]Example 4 (line 91):[/b] [code]$removeSource = 0[/ code][/list]

[b]Remove empty directories[/b]
[list][b]By default, empty directories are removed after all source files were removed.[/b]
This can be changed by adjusting the option at line 94.

[b]Example 4 (line 94):[/b] [code]$removeEmptyDir = 0[/ code][/list]

[b]Use greedy oasis alias table[/b]
[list][b]By default, the greedy oasis alias table is used (see below).[/b]
This can be changed by adjusting the option at line 97. Note that this will most likely make no to barely any difference.

[b]Example 4 (line 97):[/b] [code]$greedyOasisTable = 0[/ code][/list]

[b]Create log file[/b]
[list][b]By default, a log file is created and moved into the 'logs' folder at the location of the main script.[/b]
This can be changed by adjusting the option at line 100.

[b]Example 4 (line 100):[/b] [code]$createLog = 0[/ code][/list]


[b][/b]
[*][u][b]SOURCE FILES[/b][/u]

[b][url=https://drive.google.com/file/d/1spA2h_5Gzr4YizXwsaCSrNM1h6hkK3bF/view?usp=sharing]File Overview[/url][/b]
[img]https://i.imgur.com/Y0I4bmr.png[/img]


[list][b]'.pck' containers[/b]
The '.pck' containers hold '.bnk' containers and '.at3', '.wav_unknown' and '.Wwise' files.
[/list][list][b]'.bnk' containers[/b]
The '.bnk' containers hold  '.01020000', '.00040000', '.at3', '.wav', '.wav_unknown' and '.Wwise' files.
The '.01020000' and '.00040000' files seem to be useless, the same goes for the '.wav' files as they are all duplicates and only have a size of 44 bytes.
The '.wav_unknown' and '.Wwise' files are mainly stub files.
[/list][list][b]'.at3' files (Wwise PCM)[/b]
The '.at3' files are mainly weapon and gadget related.
[/list][list][b]'.wav_unknown' / '.lwav' files (Wwise (IMA) ADPCM)[/b]
The '.wav_unknown' files are differently encoded '.lwav' files and are currently extracted incorrectly by the 'pck_AKPK_extractor.bms' script. They are mainly ambient related.
[/list][list][b]'.Wwise' files (Wwise RIFF/RIFX Vorbis)[/b]
The '.Wwise' files are voice, cutscene, effect, music and ambiance related.
Mostly, they hold an unique identifier, which will be referred to as OasisID, as it consists of the string 'OasisID' and an integer. 

[b]RegEx Pattern:[/b][code]OasisID[0-9]+[/ code][/list]
[b]
Note that all files with a space in their name were extracted from a '.bnk' container![/b]


[b]Changelog since 28/06/18[/b]
Note that the version numbers may not always be correct and from 18/12/18 on, changes are only logged from time to time.

[code]
3.2.1 (29/06/18):
Added 'sounds_eng_012009248.pck'

3.2.2 (23/07/18):
Added 'sounds_eng_012063704.pck'
Added 'sounds_sfx_012063704.pck'
Added 'sounds_sfx_bootstrap_012063704.pck'

3.3.0 (04/09/18):
Added 'sounds_eng_000000009.pck'
Added 'sounds_eng_012213254.pck'
Added 'sounds_sfx_000000009.pck'
Added 'sounds_sfx_012213254.pck'
Added 'sounds_sfx_bootstrap_000000009.pck'
Added 'sounds_sfx_maps_000000009.pck'
Added 'sounds_sfx_playgo_000000009.pck'

3.3.1 (18/09/18):
Added 'sounds_eng_012254817.pck'
Added 'sounds_sfx_012254817.pck'

3.3.1.1 (?) (19/09/18):
Added 'sounds_eng_012261114.pck'

3.3.1.2 (18/10/18):
Added 'sounds_eng_012362767.pck'

3.3.2 (29/10/18):
Added 'sounds_eng_012395233.pck'

3.3.2.1 (?) (29/11/18):
Added 'sounds_eng_012482487.pck'

3.4.0 (04/12/18):
Added 'sounds_eng_000000010.pck'
Added 'sounds_eng_playgo_000000010.pck'
Added 'sounds_sfx_000000010.pck'
Added 'sounds_sfx_bootstrap_000000010.pck'
Added 'sounds_sfx_maps_000000010.pck'
Added 'sounds_sfx_playgo_000000010.pck'

3.4.1 (17/12/18):
Added 'sounds_eng_012540733.pck'
Added 'sounds_sfx_playgo_012540733.pck'

Audio source files have been reworked!
4.2.0 (11/06/19):
Updated 'sounds_eng.pck'
Added 'sounds_eng_013085959.pck'
Added 'sounds_eng_events.pck'
Added 'sounds_eng_events_013147883.pck'
Updated 'sounds_eng_playgo.pck'
Added 'sounds_eng_playgo_013085959.pck'
Updated 'sounds_sfx.pck'
Added 'sounds_sfx_013085959.pck'
Added 'sounds_sfx_013147883.pck'
Updated 'sounds_sfx_bootstrap.pck'
Added 'sounds_sfx_bootstrap_013085959.pck'
Added 'sounds_sfx_bootstrap_013147883.pck'
Added 'sounds_sfx_events.pck'
Added 'sounds_sfx_events_013147883.pck'
Updated 'sounds_sfx_maps.pck'
Added 'sounds_sfx_maps_013085959.pck'
Added 'sounds_sfx_maps_013147883.pck'
Updated 'sounds_sfx_playgo.pck'
Added 'sounds_sfx_playgo_013085959.pck'
Added 'sounds_sfx_playgo_013147883.pck'

4.3.1 (19/09/19):
Added 'sounds_eng_013396867.pck'
Updated 'sounds_eng_events.pck'
Added 'sounds_eng_events_013522963.pck'
Added 'sounds_eng_playgo_013396867.pck'
Added 'sounds_sfx_013396867.pck'
Added 'sounds_sfx_013479271.pck'
Added 'sounds_sfx_013522963.pck'
Added 'sounds_sfx_bootstrap_013396867.pck'
Added 'sounds_sfx_bootstrap_013479271.pck'
Added 'sounds_sfx_bootstrap_013522963.pck'
Updated 'sounds_sfx_events.pck'
Added 'sounds_sfx_events_013522963.pck'
Added 'sounds_sfx_maps_013396867.pck'
Added 'sounds_sfx_maps_013479271.pck'
Added 'sounds_sfx_maps_013522963.pck'
Added 'sounds_sfx_playgo_013396867.pck'

4.3.1 Halloween (23/10/19):
Added 'sounds_sfx_013625283.pck'
Added 'sounds_sfx_bootstrap_013579711.pck'
Added 'sounds_sfx_bootstrap_013625283.pck'

4.4.0 (??/12/19):
Added 'sounds_eng_013777760.pck'
Updated 'sounds_eng_events.pck'
Added 'sounds_eng_events_013820966.pck'
Added 'sounds_sfx_013777760.pck'
Added 'sounds_sfx_013820966.pck'
Added 'sounds_sfx_bootstrap_013777760.pck'
Added 'sounds_sfx_bootstrap_013820966.pck'
Updated 'sounds_sfx_events.pck'
Added 'sounds_sfx_events_013820966.pck'
Added 'sounds_sfx_maps_013777760.pck'
Added 'sounds_sfx_maps_013820966.pck'
Added 'sounds_sfx_playgo_013777760.pck'
Added 'sounds_sfx_playgo_013820966.pck'
[/ code]


[b][/b]
[*][u][b]MEANINGFUL NAMES (ALIASES) AND SORTING[/b][/u]

[url=https://docs.google.com/spreadsheets/d/1luePEG5MG_Z1w6KJTwuCT2olIHVUGOkuvxCDmAr9SaI][b]Name Overview[/b][/url]

Since the audio source files were changed in the first half of 2019, the meaningful names at the last line of each of the '.bnk' container have been removed and it is no longer possible to extract '.bnk' containers to meaningful named folders.

However, based on my backups of the audio source files, I created alias tables which allow for known files to be extracted and moved into meaningful named folders again.
These alias tables consist of an (ideally) unique identifiers for a file and a meaningful name (the alias).

There are currently 5 alias tables:

[list][b]bnkTable[/b]
If the table contains the name of a '.bnk' container, it is extracted to the according alias.
[/list][list][b]nameTable_bnk[/b]
If the table contains the name of a file extracted from a '.bnk' container (identified by a space), it is moved to the according alias.
[/list][list][b]nameTable_pck[/b]
If the table contains the name of a file extracted from a '.pck' container (identified by no space), it is moved to the according alias.
[/list][list][b]oasisTable_exact[/b]
If the table contains the OasisID of a '.Wwise' file, it is moved to the according alias.
Note that the table only got populated with OasisIDs which occurred previously.
[/list][list][b]oasisTable_greedy[/b]
If the table contains the OasisID of a '.Wwise' file, it is moved to the according alias.
Note that the table is based on the 'oasisTable_exact', but gaps between two integers with the same alias are filled.
[/list]

Sorting is still primarily done by comparing the stub files extracted from the '.bnk' containers with the remaining files, but the name and oasis tables will try and sort the leftover files afterwards, allowing for 87% of the currently 72'814 convertible audio files to be sorted.

[/list]


[b][size=125]EDIT HISTORY[/size][/b]

[b]Edit (22/05/18)[/b]:
Updated to version 0.6.0 ([url=http://forum.xentax.com/viewtopic.php?p=140759#p140759]read more[/url])!

[b]Edit (24/05/18)[/b]:
Added link to the Google Drive folder.

[b]Edit (19/06/18)[/b]:
Updated to version 0.7.0 ([url=http://forum.xentax.com/viewtopic.php?p=141430#p141430]read more[/url])!

[b]Edit (12/05/20)[/b]:
Updated to version 0.9.2 ([url=https://forum.xentax.com/viewtopic.php?p=163091#p163091]read more[/url])!

[b]Edit (15/07/20)[/b]:
Updated to version 0.9.3 ([url=https://forum.xentax.com/viewtopic.php?p=165005#p165005]read more[/url])!

```

Edit (12/09/23):
Project on hold indefinitely  ([read more](https://forum.xentax.com/viewtopic.php?p=194476#p194476))!
[Launcher.zip](https://xentaxbackup.github.io/file/18473_Launcher.zip)
## Post #19
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-05-16T04:45:04+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Not done!

Thats Good!
But AKPK script cant import files... Can you fix that?
I creating package for edit all of wwise files

Right now, i can edit all wem files and .bnk files and other Wwise files
I can edit any .PCK file, But Ubisoft using a different PCK files...
If anyone help me to repack this PCK, i can make a package to edit any (.bnk , .wem , .pck .stm and other) files and share to all
## Post #20
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-05-16T14:25:24+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Reply from GHOST DEAD
>
> But AKPK script cant import files... Can you fix that?

I definitley cannot fix it, maybe @AlphaTwentyThree can.

However, in case you want to launch the game with modified '.pck' files, bare in mind that this will most likely get you banned.
That is, if you own an original copy of the game and Ubisoft or BattlEye checks the intergrity of the game files on each launch (which I'd hope and assume as mentioned earlier).

Might be intresting for the cracked version, tho!
## Post #21
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-05-16T16:07:02+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

i have Uplay version, dont worry, not gonna happen in offline mode

i really want to make a package to edit Wwise files for all of guys
and @AlphaTwentyThree not was online for months  

and aluigi (quick bms programmer) cant read my massage, you know any other guy?
## Post #22
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-05-16T23:16:48+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Reply from GHOST DEAD
>
> i have Uplay version, dont worry, not gonna happen in offline mode
Didn't think about that, however, the online use is restricted then - unless one would install the cracked version and mess around with friends over VPN! 

> Reply from GHOST DEAD
>
> and aluigi (quick bms programmer) cant read my massage, you know any other guy?
When I posted a question on Aluigi's ZenHAX forum the other day he responded within 24h, maybe try your luck there.
## Post #23
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-05-21T22:46:25+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Changelog 0.6.0
>
> 
>
> Added proper renmaing *
>
> Added automatic installation directory recognition
>
> 
>
> Fixed update function (you need to download this update manually)
>
> Fixed batch wrapper

* Each '.bnk' file will be extracted into a folder with the proper name which is based on the last bytes of said '.bnk' file. '.Wwise' files directly extracted from the '.pck' files will also be moved into folders with proper names which is possible because the '.Wwise' files have OasisIDs (strings in the file header, e.g. 'OasisID193307'). The '.Wwise' files extracted from the '.bnk' files are in proper named folders and, although barely any are convertable, the '.Wwise' files extracted from the '.pck' files have matching OasisIDs. Bare in mind that these are not the exact names for each and every file rather than a collection of files and that there are still a lot of files which remain unnamed. Any help regarding this is greatly appreciated!

Edit (23/05/18):
I created a Name Overview. Again, help (in form of comments) is greatly appreciated!  

Edit (24/05/18):
It seems like '.Wwise' files are mostly voice overs and cutscene sounds, '.lwav' files are mostly ambient sounds and '.at3' files are mostly gun fire and similar sounds.
There are also still a lot of '.Wwise' files extracted from '.pck' files which do not have a proper named folder and a lot of proper named folders for the '.Wwise' files extracted from the '.bnk' files with no or barely any convertable files. However, I will have a look into comparing the '.Wwise' files extracted from the '.bnk' files with the ones extracted fromt the '.pck' files, as it seems like the '.bnk' ones are simply duplicates which are cut off at some point.
## Post #24
- Username: borntosowdeath
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 04, 2018 8:15 am
- Post datetime: 2018-06-15T06:31:50+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Reply from FatalBulletHit
>
> Update 0.6.0
This file redundancy is nonsence. I've successfully set this file list to size 0 (BattlEye actually doesn't check any files, the game just won't load without some files, will load to lobby but not into game without some files etc - game engine has to be the checker). If you'd be able to code whole repacker it would be great (being able to extract sounds/textures, convert to usable format, change them/set to 0 size or remove, convert back to original format and put back inside).

<those remove lobby ops animation>
\
'datapc64_r6_menuworld_playgo*'

<lector and ops dialog lines>
\sounddata\pc\
'sounds_eng*'

<sfx; probably redundant  - just seen file names in main folder ending with  000000006 sooo...>
\sounddata\pc\
'sounds_sfx_000000000*' to 'sounds_sfx_000000005*''sounds_sfx_playgo_000000000*' to 'sounds_sfx_playgo_000000005*'EDIT: Seems like they use it after all ;p

<menu sounds>
\sounddata\pc\
'sounds_sfx_bootstrap*'

<map zone sounds (s.a. water in Bank Lockers area)>
\sounddata\pc\
'sounds_sfx_maps*'[/list]

PS. They've changed the way they're putting sound zones in-game - they used to put those inside 'sounds_sfx_maps*' packs - in Villa sounds are inside 
'1_pck\4_lwav_converted\sfx\sounds_sfx_000000008' (radio), 
'1_pck\2_wwise_converted\sfx\sounds_sfx_000000008' (ambient), 
'1_pck\2_wwise_converted\sfx\sounds_sfx_playgo_000000008' (clock) 
and might be somewhere else too due to this redundancy...
## Post #25
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-06-15T20:32:48+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Reply from borntosowdeath
>
> This file redundancy is nonsence.
Brought to you by Ubisoft. 

> Reply from borntosowdeath
>
> I've successfully set this file list to size 0 (BattlEye actually doesn't check any files, the game just won't load without some files, will load to lobby but not into game without some files etc - game engine has to be the checker).
Good to know!

> Reply from borntosowdeath
>
> If you'd be able to code whole repacker it would be great (being able to extract sounds/textures, convert to usable format, change them/set to 0 size or remove, convert back to original format and put back inside).
I'd love to tell you I'm able to, but I'm not, sry... :/
## Post #26
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-06-19T10:16:14+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Changelog 0.7.0
>
> 
>
>  Added more launch parameters:
>
> Code: Select allPowerShell.exe -ExecutionPolicy Unrestricted -NoProfile -File ".\bin\r6s_extractor_0.7.0.ps1"
>
>     [-DownloadLatestVersion]
>
>     [-Profile <string>]
>
>     [-Output <string>]
>
>     [-Exit]
>
>     [-Batch]
>
>     [-Debug]
>
> 
>
> 
>
> -DownloadLatestVersion
>
> Will download the latest version.
>
> 
>
> -Profile Default
>
> Will start the script with the default profile.
>
> 
>
> -Profile 'Profile Name'
>
> Will start the script with a custom profile named 'Profile Name'.
>
> 
>
> -Output
>
> Overwrites the output directory.
>
> 
>
> -Exit
>
> Script will exit when finished.
>
> 
>
> -Batch
>
> Will use the paths from the r6s_extractor_0.7.0.bat, rather than from the r6s_extractor_0.7.0.ps1.
>
> 
>
> -Debug
>
> Will save error logs if any.
>
> 
>
> 
>
> Example:
>
> PowerShell.exe -ExecutionPolicy Unrestricted -NoProfile -File ".\bin\r6s_extractor_0.7.0.ps1" -DownloadLatestVersion -Profile 'Some Profile' -Output 'C:\some\path' -Exit -Batch -Debug
>
> 
>
>  Improved proper renaming (quite a bit) *
>
>  Improved update function (hopefully)
>
>  A bunch of minor improvements, fixes and additions which are not worth being mentioned (but lead to the version jump from 0.6.0 to 0.7.0)

* '.pck' output is now moved into properly named folders based on the '.bnk' output as mentioned in the [0.6.0 changelog](http://forum.xentax.com/viewtopic.php?p=140759&sid=cddf20d6c94f727ce6981f6637fe6e02#p140759) (under 'Edit (24/05/18)'). Out of the currently 87'428 convertable files only 6'644 are unsorted (that's just under 7.6%)!
## Post #27
- Username: benishandler
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jun 25, 2018 5:41 am
- Post datetime: 2018-08-06T20:40:14+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Didn't think about that, however, the online use is restricted then - unless one would install the cracked version and mess around with friends over VPN!

Ha, I remember the old VPN trick for Tom Clancy, did it with Far cry 5 too, had some VPN promotion code over at [https://www.vpncompare.co.uk/unlock-far-cry-5-early/](https://www.vpncompare.co.uk/unlock-far-cry-5-early/) so only cost a couple of dollars but well work it to unrestrict online use.
## Post #28
- Username: Voron111999
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 11, 2018 11:34 pm
- Post datetime: 2018-09-14T14:18:35+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Hey guys, thanks for the help. I might sound stupid but anyways. I don't know if you already found the way to open .at3 files which are the gun sounds, but I found a way to open them. Use Audacity and import them as raw data and change Rate to something more than 48,000Hz and you will hear the proper audio.
## Post #29
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-09-14T17:03:33+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

The current version (0.7.0) of the extractor is capable of converting the '.at3' files to '.wav' files, but this seems like an easy workaround if one only needs a couple of gun sounds or so. Thank you for the information!
## Post #30
- Username: Voron111999
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 11, 2018 11:34 pm
- Post datetime: 2018-09-14T21:03:45+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Wow that reply was fast man! its good cuz I have a problem with the script and I need to ask you about it. I do everything as u say but in the end, the script completely deletes whatever is in the output folder. Before doing that (while in the middle of conversion) I regularly check the output folder and I never see any converted file. All of them are either left as .bnk , wwise , at3 or lwav and not a single converted .wav file. So that's why the scripts deletes everything in the output folder when its done because nothing converted and all that's left are junk unconverted files. I also check the script while its running and not a single error is shown. Every step is done completely that's what script says at least. Maybe you would know why... 
(just so you know, my r6 siege is not up to date and still has day 1 sound files but they are not damaged or corrupted as singleplayer runs without problems.) Please help me with this.
## Post #31
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-09-15T09:48:57+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

If you are using Windows 7 or Windows 8, chances are that you need to update your PowerShell:

 Search 'PowerShell' in Windows and open it
 Type (or paste):
Code: Select all$PSVersionTable
 Hit 'Enter'

Your PowerShell version should be no lower than '4.0.0.0'.
You can update PowerShell here and some more information can be found here.


If you are using Windows 8.1 or higher, please enable the '-Debug' parameter and run the script once more (you may use additional parameters):

If you are launching the script with the batch wrapper ('r6s_extractor_0.7.0.bat'):

Right click on 'r6s_extractor_0.7.0.bat' and click 'Edit' (or: 'Edit with Notepad++' - I strongly suggest you use Notepad++ or a similar text editor rather than Microsofts default notepad.)
Line 78 (the 3rd last line) should look like this:
Code: Select allPowerShell.exe -ExecutionPolicy Unrestricted -NoProfile -File ".\bin\r6s_extractor_0.7.0.ps1" -Batch
Just add ' -Debug', should look like this:
Code: Select allPowerShell.exe -ExecutionPolicy Unrestricted -NoProfile -File ".\bin\r6s_extractor_0.7.0.ps1" -Batch -Debug
If you are launching the script directly ('r6s_extractor_0.7.0.ps1'):

Open PowerShell (adjust the path if necessary) and add ' -Debug'
Code: Select all$Home\Desktop\r6s_extractor_0.7.0.ps1 -Debug

You will find a folder called 'debug' next to the 'r6s_extractor_0.7.0.bat', all error logs are saved there.

PS: I'd be really intrested in those day 1 audio files...
## Post #32
- Username: Voron111999
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 11, 2018 11:34 pm
- Post datetime: 2018-09-15T14:13:14+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

alright I did it and lets see how It goes. im running the script again. Day 1 files aren't that much different but ive found some unused musics/soundtracks and 1 song which is really sad and gives me story mode music vibes I dunno how to explain ill upload it to youtube. [https://www.youtube.com/channel/UCQ8eI6 ... subscriber](https://www.youtube.com/channel/UCQ8eI6DkYbTLGIwsuJSC-TQ?view_as=subscriber) this is my channel I upload cool stuff sometimes.

EDIT: Debug shows all sorts of errors you would understand so here they are.  

[https://www.dropbox.com/sh/7bzm7mjge9vj ... Mg9Ba?dl=0](https://www.dropbox.com/sh/7bzm7mjge9vj04h/AACeDO5mPkoRT81udoSUMg9Ba?dl=0)

just so you know, all error txt files here are untouched except r6s_extractor_12_wwise_error.txt because this one alone was 20mb lol thats a lot for txt file so it required lots of time to be uploaded so i opened it and saw all the errors are the same and i deleted most of them to reduce file size. I left around 10 or 15 lines there im sure you will know whats the error from those. All the errors in that txt say the same thing though.
## Post #33
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-09-16T08:45:05+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

It seems like the enviromental variables are not set and if I had to take a guess on why the merging does not work, I'd say the path contains special characters.
However, I need some more information to help you out:

 What operating system are you running? (e.g.: 'Microsoft Windows 10 Pro')

Search for 'System Information' and open it
Check the first line ('OS Name')
What version of PowerShell are you running? (e.g.: '5.1.17134.228')

Search for 'PowerShell' and open it
Type (or paste)
Code: Select all$PSVersionTable
Hit 'Enter' and check the first line ('PSVersion')
Are you using the 'r6s_extractor_0.7.0.bat' or the 'r6s_extractor_0.7.0.ps1' to launch the script? (Either 'Windows Batch File (.bat)' or 'Windows PowerShell Script (.ps1)')

Right click on the file and choose 'Properties'
Check 'Type of file:'
What is the location of the file? (e.g.: 'C:\Users\Username\Desktop\extractor')

Right click on the file and choose 'Properties'
Check 'Location:'
## Post #34
- Username: Voron111999
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 11, 2018 11:34 pm
- Post datetime: 2018-09-19T16:33:27+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

OS Name	Microsoft Windows 10 Enterprise

PowerShell:  5.1.17134.228

I'm using the r6s_extractor_0.7.0.bat on desktop.

First i downloaded the r6s_extractor_0.7.0.bat from the link u posted here , i extract it to desktop and open it. Then it downloads Bin folder to the desktop and there it downloads all the required stuff as you know.

I can show you what folder and files i have in my siege directory. Its not an original copy though its a torrent. The thing is, r6_extractor.bat wouldnt work on my game because extractor looked for siege in directory where uplay games are installed and it wouldnt find siege because thats not where my game is installed. So what i did is, i entered system registry and added new keys for siege and placed my game files where uplay games are originally installed. Then .bat worked and now im stuck with this current problem.

So here are the pics: 

       This is the game's folder. 

         This is what i see when i enter sounddata folder.

          And this is what the game has in pc folder of sounddata folder.
## Post #35
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-09-20T16:35:13+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Reply from Voron111999
>
> The thing is, r6_extractor.bat wouldnt work on my game because extractor looked for siege in directory where uplay games are installed and it wouldnt find siege because thats not where my game is installed. So what i did is, i entered system registry and added new keys for siege and placed my game files where uplay games are originally installed. Then .bat worked and now im stuck with this current problem.
You could have just simply pasted the path to your Rainbow Six Siege directory there instead (just don't forget the double quotation marks), e.g.:

```
:: dir_rainbow = "C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Tom Clancy's Rainbow Six Siege"
```
Will make sure to put this in the comment above to prevent confusion with the next update. 


Back to your problem: I assume you either moved the folder 'bin' or some of the files. If that should be the case, recreate the default structure (see below) or adjust the paths to the programs in 'r6s_extractor_0.7.0.bat' (don't forget the quotation marks).
If you do the latter, make sure that the '.bms' scripts are in the same folder as the 'r6s_extractor_0.7.0.ps1' script (this is due to hardcoded script locations - again, will look into this and fix it with the next update).

The default structure should look like this (files and folders marked with '[optional]' are not important for the script to run properly):

```
├───bin
│   ├───archives [optional]
│   ├───bnk_extractor.bms
│   ├───func_getTYPE.bms
│   ├───packed_codebooks_aoTuV_603.bin
│   ├───pck_AKPK_extractor.bms
│   ├───quickbms.exe
│   ├───r6s_extractor_0.7.0.ps1
│   ├───revorb.exe
│   ├───ww2ogg.exe
│   ├───wwise_ima_adpcm.exe
│   └───wwise_pcm_decoder.bms
├───debug [optional]
├───logs [optional]
├───output [optional]
├───profiles [optional]
├───ReadMe.txt [optional]
└───r6s_extractor_0.7.0.bat

```
## Post #36
- Username: Voron111999
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 11, 2018 11:34 pm
- Post datetime: 2018-09-20T17:27:05+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Hey thanks man youve been really helpful! i just deleted the torrent r6 siege i had after extracting required audio files such as musics and stuff manually and bought the game on uplay so its much better that way. I will get to play it and test ur script on it too ill let u know how it goes.
## Post #37
- Username: borntosowdeath
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 04, 2018 8:15 am
- Post datetime: 2018-12-10T02:12:28+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Hmm... waiting for the updates I guess 

Meanwhile I'll try to figure out myself how to delete some sounds that are not 'needed' in the game.
## Post #38
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2018-12-10T22:09:06+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

For clarification and as mentioned earlier: I can't do that, I was just the pleb who put a couple of scripts together in a more userfriendly way.
Try to get in contact with spider91 for example, from what I believe to know he should be able to do such a task and he also seems to be still somewhat active.
## Post #39
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2019-06-25T14:26:52+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Unfortunately even after all these months I still have the same problem as Voron111999. Extracting and moving and deleting works fine. But it just won't convert them. So it ends up deleting all the unconverted files when it finishes (.wwise, .bnk, etc.)

I set the paths just like you instructed me to. Both in the .bat and in the powershell file. Still deletes everything when it finishes





Windows 10 Pro, PowerShell Version 5.1.17763.316, I added -debug to that line you mentioned, and I tried running it from the desktop, as well as different folders. Oh and the HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Ubisoft\Launcher\Installs\635 is not found because I bought the game through Steam and not uPlay

Thank you very much in advance for any hints or help with this matter

I'll update this post if I ever figure it out so that others don't have to struggle x_x

Edit1:

Actually just tried re-doing the whole thing from the scratch and I'm getting this error when I run the bat and then it just closes itself:



If I try adjusting the paths to my game folder and a random output folder, the window appears for a split-second and then instantly closes. It won't even download the rest of the files in the bin folder. If I manually download and paste all the other files in the bin folder it just closes instantly same as before

Tried running the bat and the PS by itself and I'm getting the same result, they both instantly close

Edit2:

OK so .bat problems aside, even if it somehow extracts and doesn't delete the files - it still won't convert them :< I have these folders full of the following file formats: .bnk, .wwise, .lwav, and .at3.




What could be causing the .bat to skip the converting. I have all the tools required in my bin folder I think
## Post #40
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2019-07-05T14:48:21+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Hate to keep you waiting, but I'm really busy right now.
I'll try to update the script rather sooner than later, but can't make any promises right now, nor can I give you a time frame.


For now, try this:

```

Get-ChildItem -LiteralPath $Path -File -Recurse -Include *.Wwise | Where-Object { !(Test-Path -LiteralPath ($_.DirectoryName + '\' + $_.Name + '.ogg')) } | ForEach-Object {

	& .\ww2ogg.exe $_.FullName --pcb .\packed_codebooks_aoTuV_603.bin

}

Get-ChildItem -LiteralPath $Path -File -Recurse -Include *.lwav | Where-Object { !(Test-Path -LiteralPath ($_.DirectoryName + '\' + $_.Name + '.wav')) } | ForEach-Object {

	& .\wwise_ima_adpcm.exe -d $_.FullName ($_.FullName).Replace('.lwav', '.wav')

}

Start-Process -FilePath '.\quickbms.exe' -ArgumentList "-K -D -Y -. -R -F "*.at3" .\wwise_pcm_decoder.bms $Path $Path"


```


Go to your bin folder, press shift+right click and click on 'Open PowerShell here'.
Then paste this and it should convert the files.
For the renaming you'll have to wait a bit more, sorry... :/
## Post #41
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2019-07-09T15:02:12+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Thanks for the reply. I did what you said and it kinda worked, but it's all messed up   No file names, most of them aren't revorbed correctly or at all, empty folders, everything is stacked in one place, etc.

I'm grateful for your help, but if it's ok with you I'll just wait for the script update. Whenever you have time, no rush, and thanks again!
## Post #42
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2019-11-13T18:57:15+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Small status update. 
Between 3.4.1 and 4.2 the audio files have been reworked and the somewhat proper names are no longer at the end of the '.bnk' files and I cannot find them anywhere else. However, luckily I started doing backups of the old files a year earlier or so and I'll be able to still sort the majority of the files.
I'll also have a look into the files I don't have references for, but no promises on that end.

Last but not least, I'm aware that the script isn't working properly right now and an update will come rather sooner than later (hopefully near the end of this month, no promises once again, tho (sorry)).
## Post #43
- Username: ZRH3H
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 26, 2019 6:28 pm
- Post datetime: 2019-11-26T10:42:21+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

please help
[cpt.PNG](https://xentaxbackup.github.io/file/17110_cpt.PNG)
## Post #44
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2020-05-13T22:13:43+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

> Changelog 0.9.2
>
> 
>
>  Added alias tables
>
> 
>
> bnkTable
>
> nameTable_bnk
>
> nameTable_pck
>
> oasisTable_exact
>
> oasisTable_greedy
>
> 
>
> Added documenatation
>
> Added installation
>
> 
>
> Fixed compatibility (partially)
>
> Fixed various bugs
>
> 
>
> Improved performance
>
> Improved update function
>
> 
>
> Replaced UI
>
> 
>
> Removed enhanced folder structure
>
> Removed profiles
>
> Removed launch parameters
>
> Removed file overview
>
> Removed various preferences

First of all, sorry for taking ages to come back to this.

Secondly, if you have any problems updating, remove the main script ('r6s_extractor_0.7.0.ps1') or the folder 'bin' and start the batch wrapper. If it still doesn't work, then you'll have to manually download the 'Launcher.zip' from the [main post](https://forum.xentax.com/viewtopic.php?p=140570#p140570). I improved the update function once again to ensure reliability, but the issue is down to version 0.7.0 of the main script.


Version 0.7.0 was a mess, so I completely rewrote the script and focused primarily on restoring compatibility with the new audio source files as they were changed in the first half of 2019 (see [Small status update](https://forum.xentax.com/viewtopic.php?f=17&t=13641&start=30#p157697)), saying that, converting the files previously known as '.lwav' is currently impossible as they are now extracted as '.wav_unknown'.
Additionally, I got rid of the enhanced folder structure, profiles, launch parameters and file overview and the new UI also lead to some preferences being dropped and the remaining ones now needing to be adjusted in the main script before starting (see Documentation - 3. Preferences - if you think some of the dropped preferences were important, let me know and I'll have a look into it).

On the bright side, I fixed (hopefully) all bugs and implemented a lot of error caching (please let me know if you encounter any issues) and performance has been increased drastically (also partially down to the missing '.lwav' files). For reference, I'm running an i7-4960X @3.50Ghz and the overall duration dropped from previously more than 3 hours to now just over 1 and a half hours and, when disabling real-time protection (see Documentation - 1. Performance), to as low as 1 hour.

I also added a complete documentation with all the details I could think of regarding not just the extractor but also the source files.

But the important thing is that, although the meaningful names have been removed from the end of the '.bnk' files, I was able to create alias tables based on my backups which allow for 87% of the currently 72'814 convertible audio files to still be sorted properly (see Documentation - 5. Meaningful Names (Aliases) And Sorting). Note, however, that all files added from 2019 on are probably not sortable anymore (feel free to figure out which folder in 'english(us)\sounds_eng' is for which operator and please let me know).

Last but not least, the batch wrapper has been rewritten and its version (currently 1.1) is now independent from the version of the main script.

All of the above paired with my very limited motivation to complete version 0.8 at the time, lead to version 0.9.2.
I hope everything is working fine again!
## Post #45
- Username: Custard
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Oct 25, 2019 7:33 am
- Post datetime: 2020-05-14T03:32:48+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Nice, I'm glad you've decided to update this. There's been some work towards deciphering metadata for searchable identifiers in the .FORGE files, for making a tool for the 3d assets in this game. No breakthrough as such yet, but if the headers of those become understood I wonder if it might also show the way to proper names in these too. Anyway, I'll be sure to give this a try soon.
## Post #46
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2020-07-15T15:24:49+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

> Changelog 0.9.3
>
> 
>
> Added default location detection based on launcher location for installation
>
> 
>
> Fixed alias tables being corrupted when downloaded from Google drive
>
> Fixed dot animation preventing extractor from closing when an error occurred
>
> Fixed errors not being logged (includes launcher update to v1.2)
>
> 
>
> Improved performance after confirming installation location

Tested and working and should automatically update. If you encounter any issues, let me know, please.
## Post #47
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2020-08-17T19:39:06+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

they seem to be packing soundbanks in 2 forge (scimitar) files (soundbank and soundmedia) and compressing them(not sure about this one) (latest TS, Shadow Legacy)
## Post #48
- Username: garysplay
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 31, 2019 3:49 am
- Post datetime: 2020-09-13T21:37:23+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

How can i repack old PCK files? (for testing purposes)
## Post #49
- Username: borntosowdeath
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 04, 2018 8:15 am
- Post datetime: 2020-09-14T08:53:38+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor


## Post #50
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2020-09-17T20:28:09+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

> Reply from Custard ↑Thu May 14, 2020 11:32 am at Thu May 14, 2020 11:32 am
>
> 
There's been some work towards deciphering metadata for searchable identifiers in the .FORGE files, for making a tool for the 3d assets in this game. No breakthrough as such yet, but if the headers of those become understood I wonder if it might also show the way to proper names in these too.
Seems like we got bigger problems now... :/

> Reply from floxay ↑Tue Aug 18, 2020 3:39 am at Tue Aug 18, 2020 3:39 am
>
> 
they seem to be packing soundbanks in 2 forge (scimitar) files (soundbank and soundmedia) and compressing them(not sure about this one) (latest TS, Shadow Legacy)
I can extract the .forge files w/ scimitar, but no idea what to do from there on.

> Reply from garysplay ↑Mon Sep 14, 2020 5:37 am at Mon Sep 14, 2020 5:37 am
>
> 
How can i repack old PCK files? (for testing purposes)
No idea and iirc nobody has managed to do so yet (don't quote me on that).

I'll have a look into uploading my backup of the .pck files (or the extracted files) to make at least some sounds available, but no promises.
## Post #51
- Username: floxay
- Rank: veteran
- Number of posts: 84
- Joined date: Thu Mar 05, 2020 5:35 pm
- Post datetime: 2020-09-18T01:07:16+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

> Reply from FatalBulletHit ↑Fri Sep 18, 2020 4:28 am at Fri Sep 18, 2020 4:28 am
>
> 
I can extract the .forge files w/ scimitar, but no idea what to do from there on.

not sure what script you used, I found one which is a bit broken, maybe(?) i can make it to work properly with these files
## Post #52
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2020-09-18T12:27:54+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

> Reply from floxay ↑Fri Sep 18, 2020 9:07 am at Fri Sep 18, 2020 9:07 am
>
> 
not sure what script you used
[https://zenhax.com/viewtopic.php?p=21465#p21465](https://zenhax.com/viewtopic.php?p=21465#p21465)

Admittedly, extracting the .forge files will give me a whole bunch of files w/o extension and only hexadecimal names.
## Post #53
- Username: TourniquetTerror
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 20, 2020 4:10 am
- Post datetime: 2020-10-19T20:57:36+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

So trying to access the .pck files like I usually do when I want to make some R6-content, I notice the SoundData-folder doesn't exist anymore. Apparently doesn't for anyone else either. So to recap, is there (as of now, 19th of october 2020) any ways to export the sounds from the game files?

Just in case, I put together a small zip file that contains some of the sound files i've exported/named over time. Includes stuff like operator trailers with/without music, foley effects, music etc. There's not too much but hopefully enough to get some use out in case all goes to sh*t.

(note that the names of the files are not in any super-categorized order, i just named them quickly while going through the thousands of oggs.)

[https://drive.google.com/file/d/1HNfxBP ... sp=sharing](https://drive.google.com/file/d/1HNfxBPJCozjFmMxJuV0PnRWtFQsNuxHF/view?usp=sharing)
## Post #54
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2020-10-20T10:24:31+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

Working on it, hang in there.

Edit:
A few more details:

There will be a backup with either all the old '.pck' files or all the already extracted and converted files, hopefully multi language as well.
The '.forge' files can be (partially) extracted with Ravioli Game Tools, but it's completely unsorted (I was able to find duplicates between the '.pck' output and the '.forge' output, so hopefully some sorting will be possible).

Using '.pck' files, extraction, sorting and conversion performance has been increased quite significantly once again, not sure about '.forge' files, but I've the feeling it'll take some more time to extract them (only did 1 run so far, tho).
## Post #55
- Username: borntosowdeath
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 04, 2018 8:15 am
- Post datetime: 2020-12-16T23:05:33+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

> Reply from FatalBulletHit ↑Tue Oct 20, 2020 6:24 pm at Tue Oct 20, 2020 6:24 pm
>
> 

Any news? Anything we can help you with?
## Post #56
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2020-12-17T10:44:21+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

> Reply from borntosowdeath ↑Thu Dec 17, 2020 7:05 am at Thu Dec 17, 2020 7:05 am
>
> 
Any news? Anything we can help you with?
Yeah, sorry it's taking so long, but I've had very little team the past weeks, so if you could just make the days last longer, that'd be perfect... 
I've a bit of time on my hand in the next 2 weeks, tho, will keep you posted.
## Post #57
- Username: borntosowdeath
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 04, 2018 8:15 am
- Post datetime: 2021-04-28T18:46:55+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

> Reply from FatalBulletHit ↑Thu Dec 17, 2020 6:44 pm at Thu Dec 17, 2020 6:44 pm
>
> 
borntosowdeath wrote: ↑Thu Dec 17, 2020 7:05 am
Any news? Anything we can help you with?

Yeah, sorry it's taking so long, but I've had very little team the past weeks, so if you could just make the days last longer, that'd be perfect... 
I've a bit of time on my hand in the next 2 weeks, tho, will keep you posted.
## Post #58
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2021-05-10T12:38:29+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

> Reply from borntosowdeath ↑Thu Apr 29, 2021 2:46 am at Thu Apr 29, 2021 2:46 am
>
> 

Still working on it, no ETA, I'm sorry.
## Post #59
- Username: darthme
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 18, 2021 11:12 am
- Post datetime: 2021-07-08T02:06:08+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

I know people have extracted 3d assests from the forge files, but afaik not audio
## Post #60
- Username: AgentMaine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 11, 2023 11:35 pm
- Post datetime: 2023-09-11T15:40:58+00:00
- Post Title: [Update 0.9.3] Tom Clancy's Rainbow Six Siege - Audio Extractor

Hi guys. I'm new on this platform. I want to extract audio files from siege.
I downloaded operation steel wave so the files should still work.
But the tool that someone made on this platform doesn't launch.
I mean it doesn't work at all. I just launch the batch file and than it quits.

Any idea whats wrong?
## Post #61
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2023-09-12T07:37:17+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Hey, I haven't worked on this for years as I couldn't and ultimately didn't want to invest the time needed for this to work in a way I'd be content with - not least because reliable sorting became impossible due to the removable of file names from the files itself (last I checked anyway).

What I ended up using to extract the .forge files was [Ravioli Game Tools](https://www.scampers.org/steve/sms/other.htm#ravioli_download), this should give you .wem files which can be converted with [vgmstream](https://vgmstream.org/).

As I said, I haven't tested this in years, but this should hopefully get you somewhere.

For clarification: This project is (at least from my end) on hold indefinitely.
## Post #62
- Username: AgentMaine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 11, 2023 11:35 pm
- Post datetime: 2023-09-15T13:29:42+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Ravioli doesn't seem to support .forge files at all.

So far what I have been able to do is use a combination of Ravioli and Foobar2000 with vgmstream plugin to extract the.pck files in a build of Y5S2 (Steel Wave) and Y3S2 (Para Bellum)

These 2 build have very different file structures but everything is still in simple .pck containers.

There are MANY problems with this approach.
Ravioli can extract .wem, .wav, and .bnk files from the .pck containers.
It can also extract .wem and .wav files from .bnk containers. (and some files with no extension)
It can also convert some of the .wem files it extracts into usable .wav files.
The .wav files that it extracts (not converts) are unusable.
Some of the .wem files get converted into broken 1kb .wav files and some just completely fail.

Foobar2k with vgmstream can convert a lot of the .wem files that Ravioli can't but it seems to fail with some that Ravioli can.
It also seems like it's unable to open some of the .bnk files, while Ravioli can extract all of them.

About Y7S1... In this build the audio data is packed into 95 .forge files (total of 7.13GB).
I used this: [https://github.com/parzivail/RainbowForge](https://github.com/parzivail/RainbowForge) tool to extract some of the .forge files.
It looks like there is just a bunch of .wem files in there but they are all unusable. I tried multiple ways to convert them but no luck. I don't know if they are encoded differently or this tool can't extract the audio files without corrupting them. (Although it is compatible with Y7S1, it was made for meshes and textures)

So at the moment I can extract and use a lot of the audio files but unfortunately a lot is still missing.
For example some weapon sounds are missing completely, some only have the supressed shot sound, some are missing the reload sounds etc...

All of the audio files are just a string of characters but I don't really mind it because I know the game well enough to be able to label the ones I want just by listening to them.

I don't know where to go from here. I can download any build of the game between Vanilla and Y7S1 (If someone wants to be able to do that join the Operation Throwback Discord server. People play old Siege there. Mostly White Noise and Para Bellum. There is a downloader that can download almost any version but you need to own a copy of Siege on steam to use it)

I still want to extract the audio files but I seem to be stuck at this point. Any help would be much appreciated.
## Post #63
- Username: FatalBulletHit
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Nov 07, 2016 2:29 am
- Post datetime: 2023-09-16T06:49:28+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

Like I said, I haven't touched this in 2 years, there's a good chance I'm misremembering some things.

If you are interested in audio files prior to 5.2.2 (Operation Steel Wave) and have R6S on steam, you can use [Steam DepotDownloader](https://github.com/SteamRE/DepotDownloader) to download all the .bnk and .pck files, these are easy to extract, convert and sort with QuickBMS, ww2ogg and revorb (s. [https://pastebin.com/eGSUFbcs](https://pastebin.com/eGSUFbcs) - this will probably not work as is, but you should be able to piece together the steps needed for extraction and conversion).

That's also what I used when trying to sort the .forge output by comparing it to the .bnk and .pck output. If I recall correctly, sorting the .forge files didn't work very well.

I've a [table of all the depot ids (languages) and the needed manifest ids](https://pastebin.com/XkZ0jsqT).

Alternatively you can go through e.g. [Depot Sku WW](https://steamdb.info/depot/377237/manifests/) yourself.
## Post #64
- Username: Ayla658
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 06, 2023 6:04 am
- Post datetime: 2023-09-19T06:29:45+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

To convert Rainbow Six: Siege AudioKinetic PCK containers to OGG Vorbis, you can use the following steps:

Download and install the ww2ogg tool.
Open a command prompt and navigate to the directory where the ww2ogg tool is located.
Enter the following command, replacing <input_file> with the path to the PCK container you want to convert:
ww2ogg <input_file>
For example, to convert the PCK container audio.pck to OGG Vorbis, you would enter the following command:

ww2ogg audio.pck
The ww2ogg tool will create a new directory named ogg containing the converted OGG Vorbis files.
Note: If the PCK container contains Wwise IMA ADPCM files, the ww2ogg tool will not be able to convert them. You can use the following steps to convert Wwise IMA ADPCM files to OGG Vorbis:

Download and install the SoX audio converter.
Open a command prompt and navigate to the directory where the SoX converter is located.
Enter the following command, replacing <input_file> with the path to the Wwise IMA ADPCM file you want to convert:
sox <input_file> -t vorbis <output_file>
For example, to convert the Wwise IMA ADPCM file voice.adpcm to OGG Vorbis, you would enter the following command:

sox voice.adpcm -t vorbis voice.ogg
Once you have converted the PCK container to OGG Vorbis, you can play the audio files in any media player that supports the OGG Vorbis format.
## Post #65
- Username: borntosowdeath
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri May 04, 2018 8:15 am
- Post datetime: 2023-09-24T14:18:24+00:00
- Post Title: Re: Rainbow Six: Siege AudioKinetic PCK container

As far as I understand - the game doesn't check for the file integrity.
It just checks if the file is available (even empty file will work).

How would you repack this container with modified sounds?
