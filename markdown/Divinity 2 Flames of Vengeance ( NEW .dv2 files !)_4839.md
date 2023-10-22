## Post #1
- Username: Xep76
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 14, 2010 5:57 pm
- Post datetime: 2010-08-04T04:38:10+00:00
- Post Title: Divinity 2: Flames of Vengeance ( NEW .dv2 files !)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-05T17:04:48+00:00
- Post Title: Divinity 2: Flames of Vengeance ( NEW .dv2 files !)

It seems that it has two bonus fields at the beginning of the file header:
Something5 : DWORD // (5)
Something1 : DWORD // (1)
the rest are the same, as the original DV2 files.
Here is aluigi's QuickBMS script for the original Divinity2 dv2 files: [http://aluigi.org/papers/bms/divinity2.bms](http://aluigi.org/papers/bms/divinity2.bms)
So just put this two line to the beginning of the script and it will work:

```
GET DUMMY long
```
## Post #3
- Username: Farflame
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Nov 11, 2009 12:11 am
- Post datetime: 2010-08-05T18:10:44+00:00
- Post Title: Divinity 2: Flames of Vengeance ( NEW .dv2 files !)

Nice tool. Thanks bacter and aluigi.

But all dialogs from DialogData are stored in uncommon xml files (Gamebryo format). Do you know how to unpack or edit them? You can edit them directly in hexa editor but its not probably the best way.
## Post #4
- Username: Xep76
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 14, 2010 5:57 pm
- Post datetime: 2010-08-05T19:02:05+00:00
- Post Title: Divinity 2: Flames of Vengeance ( NEW .dv2 files !)

Thanks bacter !
## Post #5
- Username: lord13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 09, 2010 10:31 pm
- Post datetime: 2010-08-09T17:58:10+00:00
- Post Title: Divinity 2: Flames of Vengeance ( NEW .dv2 files !)

Anyone succeeded changing the Flames of Vengeance language to english? 
I unpaked and modified the dialog dv2 located in Divinity II - Ego Draconis\data\Win32\Packed\Episode_2 but it didn't work. 
Do i Modifying the right file?
## Post #6
- Username: Farflame
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Nov 11, 2009 12:11 am
- Post datetime: 2010-08-10T09:04:05+00:00
- Post Title: Divinity 2: Flames of Vengeance ( NEW .dv2 files !)

Yes, there are dialogues in that file.

Well, how did you modify it exactly?
And how it works in game? Do you see any dialogues in game or not (game doesnt load the file)?
## Post #7
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2010-08-10T11:33:30+00:00
- Post Title: Divinity 2: Flames of Vengeance ( NEW .dv2 files !)

From testing various stuff and what seems to be due to changes in the game engine and the file format as well between version 1.3 (English/normal game.) and 1.4 (German release of FoV) the translation files won't work properly at all and only part of the game can be re-localized to a different language.

Part of them are located in the Episode_2 folder but the rest is inside patch.dv2, this file also overrides maindatastreaming.dv2 in load order so the localization is overriden, unpacking patch.dv2 and copying that data info into the same folder where the episode_2 dialog .dv2 text localization files were unpacked will give a complete set, adding the English format files to the Episode1 folder (NPC dialogue and such.) won't work but the menu info for Books, Credits and Localization (GUI/HUD elements and similar.) will work partially, any new strings from the German version will however be blank and there is no localized data aside from German in the new Patch.dv2 file and dialogue files, editing the format is also problematic as it's part XML and easy to modify but also part NIF or some other gamebryo file and can't be edited at all outside of minor alterations via hex editing or similar to handle the different data and characters in the file.
(As mentioned above with the translation file repackaging the patch.dv2 file will allow somewhat English texted menu data for the main game campaign but FoV will be showing blank lines, merging both so that the English text works for the German localization will show any new German dialogue strings as ... where it's overriden and the game dialogue files won't work at all.)

(patch_2 and Patch_3 being new models and textures for the game so not that useful, patch.dv2 can't exceed 2GB either as a reminder as the packer utility won't function above that file size and it's 1.6 GB already at default.)


EDIT: I'm really bad at explaining things in a good and clear way but.

MainDataStreaming.dv2 - Localized data for the game and some other stuff, important thing here is the localized data for books, credits menu, the "Episode1" folder for the game localization and the localization folder for HUD/GUI elements like the various menus.

Patch.dv2 - Now contains the full German localization with voice over and all for both the main game and expansion and patch archives override the other ones as they load last, thus the game is stuck in German unless this file is repackaged as per above.

DialogData.dv2 - Also has some localization data and there's some data for the expansion in the Data\Episode_2 folder as well but it's all overriden by patch.dv2 as far as I know so modifying this file isn't going to change anything but you might need the localized data to complete the "set" so to speak.
(Overriding the data in patch.dv2 with these files isn't recommended as they're older.)

The voice files are also set to German and won't work with speech set to any other language unless renamed, this takes a bit of space by copying over them and mass renaming them via some utility so it would be easiest to leave them at German and there is no other language data but German for the expansion or even the main game included this time.
(As expected somewhat.)

Repackaging Patch.dv2 with the above stuff taken from the English localization will leave the main Episode1/normal campaign books, credits menu and UI elements in somewhat working English but the Episode1 folder data won't work at all due to changes to the game engine and related file format, how the UI and other elements still work I don't know but it's nice that they do.

This will break any new localization in the game that is controlled by the overwritten files such as the campaign button for starting with Divinity 2 Flames of Vengeance and item descriptions and so on as those "strings" aren't in the English localization files. 

The expansion along with the rebalanced and retouched original game are both planned for release in October (Dragon Knight Saga edition.) and the main game will also be patched then to that version for those who already have it.
(Without the expansion that is as it's a separate product.)
## Post #8
- Username: lord13
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 09, 2010 10:31 pm
- Post datetime: 2010-08-10T11:50:21+00:00
- Post Title: Divinity 2: Flames of Vengeance ( NEW .dv2 files !)

Yes, i tryed that and i get German audio in FOV and no text. To bad. Thanks for the answers.
