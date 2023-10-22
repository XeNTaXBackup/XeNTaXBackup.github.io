## Post #1
- Username: Micadi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 08, 2014 10:34 am
- Post datetime: 2014-12-12T01:09:18+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

Hello
I'm sorry to take your time but I need some help with SoundNodeWaveEx files. I've decided recently to try to extract audio files from game Deadpool. Unexpectedly most voice files are hidden within game packages - the obvious ones (ending with LOC_int) either have only a few of them or Umodel is simply unable to extract them properly (extracting all packages resulted in only about 700 files with different file names, 90% of which is pain grunts). After looking a little bit I've noticed that Umodel in fact is unable to open at all some of game packages. Because of this I've decided to use different program, UnrealPackageExtractor and I ended with bunch of SoundNodeWaveEx files. The file names strongly suggest that they are in fact what I'm looking for but I'm unable to find anything that would work to convert them to readable format. the ...LOC_int.xxx packages (when unpacked with Umodel) consist of fsb files, but FMOD/FSB converter didn't work for SoundNodeWaveEx files. Renaming them to .fsb format didn't work either. I tried to use also Oggextract (since SoundNodeWave files (without Ex on the end) were in fact ogg files in some of other Unreal Engine games but unfortunately it was a miss again.

I know I'm asking for a lot, but can someone help me with this problem? Either finding a program that is able to convert those files or finding an easier working way to extract sound files from Deadpool the game would work. I've attached 3 samples of SoundNodeWaveEx files to the post for reference.
[SoundNodeWaveEx.rar](https://xentaxbackup.github.io/file/8252_SoundNodeWaveEx.rar)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-12-12T15:37:05+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

They are MPEG FSB files, not OGG Vorbis.

Get VGM Toolbox and use its Advanced Cutter/Offset Finder to remove the data before the FSB header.

VGMToolbox > Misc. Tools > Extraction Tools > Generic > Advanced Cutter/Offset Finder

I've attached an XML file that you can put in the "plugins\AdvancedCutter" folder that will do this for you.

If you don't see the XML, click the Refresh Presets button (green icon), also you need to click the Load button after selecting it.

Drag and drop the SoundNodeWaveEx files onto the Advanced Cutter and it will remove it.

Then just use FSBExt from Aluigi to extract the MP3 audio.

Done 
[FSB_Cutter.zip](https://xentaxbackup.github.io/file/8262_FSB_Cutter.zip)
## Post #3
- Username: Micadi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 08, 2014 10:34 am
- Post datetime: 2014-12-12T20:24:09+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

VGM Toolbox got me confused a little, I've followed your instructions, the program apparently searches files I've drag into "files to search" window and then nothing happens besides the log in the lower window. I don't know whats wrong here, aren't the resulting fsb files supposed to go somewhere (output folder I've set up remains empty)? Or is there somewhere a hidden button to actually start the process?
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-12-13T22:28:30+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

Make sure that the box "Cut to EOF when Terminator Not Found" is checked
## Post #5
- Username: Micadi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 08, 2014 10:34 am
- Post datetime: 2014-12-14T11:51:20+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

Thank you very much, everything works now.
## Post #6
- Username: antagonysthc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 14, 2015 9:21 pm
- Post datetime: 2015-06-14T13:52:31+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

Guys I'm trying this but I have NO idea what to do, from start to finish. 

Can somebody write a short guide/tutorial? Would appreciate that very much! Thank you!
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-06-16T09:48:35+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

[Download VGMToolbox](http://sourceforge.net/projects/vgmtoolbox/)

Extract it to a folder.

Download my XML preset in the post above and put it inside the advanced cutter folder.

e.g. "C:\VGM Toolbox\plugins\AdvancedCutter"

Run VGM Toolbox and navigate through the menu tree as follows:

VGMToolbox > Misc. Tools > Extraction Tools > Generic > Advanced Cutter/Offset Finder

In the top right hand corner is a drop down menu box with all the presets, select the FSB Cutter and click the 'Load' button.

Down the bottom there is a check box that says "Cut to EOF (End of File) when Terminator Not Found". Make sure that box is ticked.

In the top left hand corner, next to the presets drop down menu is another box, you need to drag and drop the SoundNodeWaveEx files you wish to extract the FSB files from here. It has to be dragged and dropped onto this box or VGM Toolbox won't extract the files.

After you have extracted the FSBs from the SoundNodeWaveEx files, download [Aluigi's FSB Extractor tool from his website](http://aluigi.altervista.org/papers.htm#fsbext) and extract it.

Run the fsbext.exe and select all of the FSB files you want to convert from into MP3

Done
## Post #8
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2015-08-29T11:07:27+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

not working for kingkest any idea please
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-29T14:50:12+00:00
- Post Title: SoundNodeWaveEx files (Deadpool the game)

Kingkest?

EDIT: Ahh you meant King's Quest. Since it's unreal engine 3, I'd imagine they're just vorbis inside an OGG container and not MP3 like these one's are.
