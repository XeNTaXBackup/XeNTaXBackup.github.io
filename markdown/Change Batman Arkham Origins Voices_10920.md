## Post #1
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-01T03:15:00+00:00
- Post Title: Change Batman Arkham Origins Voices

This game works with Unreal Engine, so voices and subtitles are embedded together; can't choice a language for each one.

I have found this strings on DefaultGame.ini, but change it does not work; voices still embedded with the main language you choice:

```
BarksEnabled=1
TTSEnabled=1
;LanguageExtension codes are defined in Binaries\Audio\LocTool\languages.txt
+NonEnglishVoiceMappings=(LanguageExtension="int", bUseNonEnglishVoice=false)
+NonEnglishVoiceMappings=(LanguageExtension="fra", bUseNonEnglishVoice=true)
+NonEnglishVoiceMappings=(LanguageExtension="ita", bUseNonEnglishVoice=true)
+NonEnglishVoiceMappings=(LanguageExtension="esn", bUseNonEnglishVoice=[b]false[/b])
...
```


As far i have search on the game, the easiest solution lack of common subtitles because the Localization folder only have the menu, hud and other general strings, while the common subtitles seems to be embedded to general files of the game.

It seems that the better solution to get different languages on voice/subtitles is:
1. Extract the banks contained on the desired sound pack
2. Do the same with the one we want to replace
3. Repack the file with the desired ones and change file name to force the game load it.

However, we need an unpacker/repacker for Unreal Engine .wad files to do that. Also, i am not sure, but maybe names of the files are different between packages, so may be difficult to rename all the sound files.

So, i am asking help of someone who knows how to extract files from a file, maybe developing a script for Luigi's QBMS, don't know, any way that allow us to repack/unpack those files.

Here i have attached 2 .WAD files that i have modified with an HEX editor in order to get very small files. Hope it is enough to make an unpack/repack. If is someone interested in this and need something more, please fell free to ask me.
[BatmanAO_WAD_Examples.zip](https://xentaxbackup.github.io/file/6749_BatmanAO_WAD_Examples.zip)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-03T09:24:36+00:00
- Post Title: Change Batman Arkham Origins Voices

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "WWAD"
get UNKNOWN long
get FILES long
goto 0x1c

for i = 0 < FILES
	get HASH long
	get SIZE long
	get OFFSET long
	string NAME p= "%08X" HASH
	log NAME OFFSET SIZE
next i
```
## Post #3
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-04T05:24:56+00:00
- Post Title: Change Batman Arkham Origins Voices

Many Thanks for the script Ekey! It did worked and successfully extract the WAD's content! 

However, there's a problem when trying to repack with Luigi's QBMS: If desired files are bigger than target, then QBMS ask permission to repack and may damage the file, not sure. This far, it seems to be not a problem, however, there's almost 3000 files inside those .WAD and hit "force" for each file isn't practice

Could be there another way to repack the file, maybe creating a new file with same criteria so the game can work with it? Or can we modify QBMS to add an option so it auto force to repack the files? It is open source.

Also, it seems that what i am trying will not work. Apparently, Unreal engine gave the game a time to play the sounds, and that time change for every language. I was waiting that the .WAD file were the one with the instructions of that play time so all banks can be played fully. I am saying this because i sucessfully repack some files until i get tired of hit "force", then try the game:
Some strings doesn't play at all (Don't know if i broke the .WAD file for not repack it all), and others don't play complete.
## Post #4
- Username: Dehayat
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 29, 2013 6:54 pm
- Post datetime: 2013-12-26T19:28:35+00:00
- Post Title: Change Batman Arkham Origins Voices

hi i extracted the wad file with the bms code but it gives me a wav file i think it might be compressed.can someone please help me play them. BTW: im new
