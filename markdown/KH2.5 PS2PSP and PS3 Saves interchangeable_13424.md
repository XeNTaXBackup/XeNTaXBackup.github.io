## Post #1
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-10-14T21:47:25+00:00
- Post Title: KH2.5 PS2/PSP and PS3 Saves interchangeable

I just loaded a Birth By Sleep Final Mix PSP save on my PS3 and it works fine! Just follow these steps:

1. Use SaveGame Deemer or SED or JPCSP or any other PSP savegame decrypter to decrypt a PlayStation Portable BBSFM save. For SGD, the decrypted files will be in the SAVEPLAIN folder.
2. Copy a Birth By Sleep HD savefile to a USB
3. Use Bruteforce Save Data 4.7.4 to load your save and Decrypt PFD(All Files) [You will have to open your PARAM.SFO to get your UserID and ConsoleID]
4. (Optional) Edit the PARAM.SFO to match your new stats
5. (Optional) Use Kingdom Hearts BBS - Save Editor v0.4 to edit D-Links you couldn't normally obtain into your character
6. Update PFD(Partial)(All Files)
7. Encrypt PFD(All Files)
8. Verify PFD
9. Override your old save with the new one

This was possible due to the fact that no actual new game content was added between the Re/Final Mix and HD versions of the games; in fact, the SD Jap versions' serial numbers can even be found in the save folders names! Because of this, I believe that with a variation of this method using a PS2 save decrypter, you could very well import old saves from every PlayStation Kingdom Hearts game to the HD versions. I'm fairly confident of this, because this is not the first time I've region-transferred a Square Enix game; Deus Ex The Fall iOS saves and PC saves are also interchangeable.

This process causes a few minor glitches, though, as I will denote below. 
If you use save editor to enable Vanitas D-Link, you can't disable it in the menu, possibly because it has no name in the regular files. However, I enabled it on a Ventus save where I also had a Multiplayer D-Link, and while the multiplayer D-Link was not available, its custom name could be selected in the D-Link menu to activate the Vanitas D-Link.
Changes made to Birth by Sleep HD from Final Mix:
Several one button-pressing Shotlocks became random sequences of the four different buttons.
The buttons are shown in their respective PS3 colors if displayed
Mirage Arena has no multiplayer, and thus also has neither custom D-Links nor any use for friendship commands like Group Curaga over normal Curaga besides story party members.
KH2.5 altered the way Mirage Arena handles player coloration. In addition to Red, Green and Blue, there is a hidden Alpha value for coloring Mirage Arena player models. Additionally, if you import a Birth by Sleep Final Mix PSP save into the PS3 or vice-versa, it will ramp up at least one of the starting RGB values to a previously unknown 199%, which you can change back, and the A value to 50%, which you can't. Barring a creative hex edit of your save file, you will spend the rest of the game's Mirage battles as transparent as a ghost.
The original Japanese menu font characters are present within the English version of the game and have not been upscaled, so importing non-English Patch gamesaves results in a lot of PSP-quality Japanese text. For the same reason, you will have to manually edit the gamesaves to make Finish Commands previously unlocked in Japanese into English again, and those characters use two bits for information instead of 1, as BBSFM uses a version of Shift-JIS to encode all those characters. For accented Latin characters, I've compiled a partial list at [viewtopic.php?f=13&t=6059](http://forum.xentax.com/viewtopic.php?f=13&t=6059) .
With all this in mind, it would appear that identifying the significance of several of the save files' Hex values and adding them to Yosh's program would make the conversion process a lot simpler. The source code for version 0.4 is available freely on the net, so with that in mind, I may just code up and compile some updates to the BBSFM Save Editor.

EDIT: I've recently discovered that the same is true of KH2FM; that you can import PS3 saves to the PS2. You need Bruteforce Savedata, Mymc 2.6, either a Hex Editor or PS2 Save Editor, and optionally the KH2.5HD checksum tool.
1. Use Bruteforce to decrypt/encrypt the PS3 saves in the folder BLUS31460-BISLPM66675FM. They'll be named USR-##; with ## being the save's numbered slot.
2. Use Mymc to open a memory card file containing a previous KH2FM save and extract it to a .psu savefile. Backup this file because it will be overridden!
2.5. (Optional) Edit the savefile with a Hex Editor and use the KH2.5HD checksum tool to re-verify the save.
3. Use the Save or Hex editor to isolate the part of the save containing BISLPM-66675FM-## and replace it with the USR-## file. If using Save Editor, rename it to that file before import.
4. Using Mymc, DELETE the save you just exported and reimport the newly modified version you just made. If you try to import it without deleting the original, the import WILL be corrupt.
5. Load the memory card on a PS2 or PCSX2, and you will see your PS3 save in your KH2FM+ saves list in the overridden save's slot.

Warning: If you import a save from a PS2/PSP KH game to the PS3 and use it to gain Trophies that usually require you to first obtain prerequisite trophies before obtaining those Trophies, your game will be flagged by PSN Trophy-tracking sites.
## Post #2
- Username: Sora1995
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 23, 2016 4:43 pm
- Post datetime: 2016-06-24T08:56:21+00:00
- Post Title: KH2.5 PS2/PSP and PS3 Saves interchangeable

Hello! I have found your instructions to be rather confusing. Can you upload a video of the BBSFM instructions somewhere? Thanks!
## Post #3
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2016-06-25T20:11:07+00:00
- Post Title: KH2.5 PS2/PSP and PS3 Saves interchangeable

> Reply from Sora1995
>
> Hello! I have found your instructions to be rather confusing. Can you upload a video of the BBSFM instructions somewhere? Thanks!
I don't have any means to capture video on my computer at this time. Hopefully the personal message I replied to you will be enough, and if it does help, any feedback on how I can edit my original post to make the instructions clearer would be appreciated.
## Post #4
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2017-01-19T18:22:01+00:00
- Post Title: KH2.5 PS2/PSP and PS3 Saves interchangeable

This is a pretty old thread but I just wanna confirm that I ran into this myself and did it myself before discovering this thread. Converted an emulated PS2 Kingdom Hearts 2 save into the PS3 2.5 Remix flawlessly simply by importing the save file into the PS3's save and resigning it. Looked for the "KH2J" header(4B 48 32 4A) within the PS2 save and did a straight paste-in of the 0x10FB0 bytes after into a decrypted USR-00 file. Re-encrypted, resigned, and it worked all fine.
## Post #5
- Username: Skarekrow73
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 07, 2017 11:44 am
- Post datetime: 2017-02-07T04:01:27+00:00
- Post Title: KH2.5 PS2/PSP and PS3 Saves interchangeable

Hey there, also aware this thread is old, but looks like it was bumped quite recently. I'm trying to figure out exactly how to do this for both a KHBBSFM PSP save and a KH2FM PS2 save.

With the former (KHBBSFM), the instructions don't seem to explain properly the part where the decrypted PSP save is injected/used as a replacement in the decrypted PS3 save. I'm not having any luck so I'm also unsure if I'm decrypting them correctly. Does this process happen purely via hexedit? Or do you just swap the savedata.dat and re-encrypt? I'm a bit of a newbie to this stuff, though I did manage to get a Dragons Dogma Dark Arisen save from the PS3 to the PC version recently.

Additionally in regards to this PSP game, I'm having a hard time determining whether the files are decrypted because the only GUI PC decrypter I've been able to find requires a Game Key which I thought I had but none of the files seem to work, and the only other options appear to be PSP plugins which I don't know how to use (I found a plugin for dumping the Game Key also but again don't know how to actually use it). I found one (I think) GUI PSP app called SEN but it gave me an error in Chinese (fairly sure it was Chinese) and then booted me back to XMB. As far as the plugins go, I just don't get how to use them at all. I can install them, add their file path to game.txt or VSH.txt, and enable them/confirm they are enabled in the recovery menu, but after that how do you actually USE them? I think I have one that did something when I booted KHBBSFM, loaded the save and saved it in another slot. It wrote some .bin files to the SAVEPLAIN folder which I assume are decrypted saves, but the file names are different so I don't get how to use them to replace what's in the PS3 save. (SDDATA.BIN, SDINFO.BIN, ULJM05775.bin as opposed to SAVEDATA.DAT, PARAM.SFO and the ICON and PIC images).

With the latter (KH2FM PS2), I have extracted the USR-00 file from the PS2 version memcard (PCSX2), and I THINK I've decrypted the PS3 one with bruteforce, but having trouble understanding what "did a straight paste-in of the 0x10FB0 bytes after" means, and again I'm not sure if my files are actually decrypted. I tried copying everything after that KH2J address straight into the PS3 save I decrypted (not sure, it looked unreadable to humans like the top right screenshot in your post DEElekgolo) but the total copy was bigger than the whole file and I had a strong feeling it wasn't the correct thing to be doing.

Any help would be amazing.
## Post #6
- Username: Skarekrow73
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 07, 2017 11:44 am
- Post datetime: 2017-02-12T13:31:48+00:00
- Post Title: KH2.5 PS2/PSP and PS3 Saves interchangeable

Okay so I've done a bunch more work on this this weekend and have pretty much verified that these posts are misleading or at the very least omitting vital information about what makes this work (as I do believe you both got it to work).

Just talking about KH2FM PS2 > PS3 and vice versa now, I've given up on BBSFM until I can get this working at least.

I've managed to solve a bunch of glaring issues, like the Disc Hash Key Hash and File Key Hash both failing when trying to verify a re-encrypted save. They now both give me an "OK" - the solution was to manually add this to the games.conf in BSD:

; "KINGDOM HEARTS ? FINAL MIX"
[BLES02070/BLUS31460]
;disc_hash_key=
secure_file_id:*=4B304EBA47364431E6334D3548D24530

as the key here is correct, where the one that is usually contained in the games.conf file is somehow wrong and causes these errors.

I've made sure I'm using the checksum fixer before reencrypting, which as far as I can tell is very important, but it has been cited as optional in the first post (for going from PS3 > PS2) and was completely glossed over in DEElekgolo's post. That hasn't made a difference anyway, so maybe it actually is unimportant after all.

As for results, saves are still showing as corrupted every single time. Both ways.

Straight copy from KH2J header onwards of the 0x10FB0 bytes (or the 0x10FC0 bytes which is the ACTUAL length of the USR-00 file) from a PS2 .psu save file exported using Mymc to a decrypted USR-00 does not work. It doesn't even look like it should work. The original save has tons of random characters in it, and the .psu file has heaps of empty 00 addresses. I've confirmed it isn't the encryption method or process as decrypting, not modifying the save and then re-encrypting does not "corrupt" it.

I've even tried it the other way, using tools and not doing the hex editing, following the steps provided in the first post. I exported the PS2 save, opened it with PS2 Save Builder (the closest thing I could find to a "PS2 Save Editor") and imported the decrypted USR-00 file after renaming it to match the BISLPM-66675FM-00 part of the PS2 save. The program acknowledges that the file is the same as another one in the save and I confirmed to replace it, then deleted the original save from the memcard and re-imported the modified save. Booted up PCSX2, corrupted. The other thing that tipped me off to the fact that it wasn't going to work was that the file name within the memory card still shows my original progress, LVL99/205:51 etc. when the save I was importing is from the very beginning of KH2FM on PS3 with less than 15 mins playtime or something.

Anyway, there is a bunch more I could write about what I've tested and tried but I'm not sure anyone is reading this so maybe if I give it another shot later and learn some more I'll post again.

Short version of all this, is that these few posts above make this out to be the easiest thing in the world, and it surely is not. There is pertinent information missing in regards to how to get this to work.

My other small thought is surely region needs to be considered here? The PS3 version I assume could be Japanese, North American or European, and then Final Mix+ PS2 is Japanese only, so does anything need changing for that? The hex doesn't even slightly look the same, I honestly don't see how DEElekgolo got it to work the way it appears in those screenshots.
## Post #7
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2017-03-04T19:28:27+00:00
- Post Title: KH2.5 PS2/PSP and PS3 Saves interchangeable

I don't actually have access to my PS3 at the moment, so I can't go through the process again and clarify what steps might have been unclear or incorrect at this time. But if the savedata was properly exported, decrypted, edited, checksumed, and re-encrypted with the player's User and Playstation IDs, then when I imported to the PS3, it would usually run just fine for me. I could try again next month with the PS4 version of the games, assuming there is an equivalent program to Bruteforce SaveData for the PS4.
