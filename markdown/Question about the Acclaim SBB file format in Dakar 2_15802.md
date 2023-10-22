## Post #1
- Username: eisnerguy1
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 18, 2016 1:24 am
- Post datetime: 2017-01-29T15:04:26+00:00
- Post Title: Question about the Acclaim SBB file format in Dakar 2

So, I was going through one of my old gamecube discs (Dakar 2: The World's Ultimate Rally) and I was trying to find where the multi boot GBA roms were stored. It looks like they're all included in a file called "GBA.SBB".  Here’s the directories for the SBB file & RBB file:
res/GBA.DAT/RBB/GameCube/GBA.RBB
res/GBA.DAT/RBB/GameCube/GBA.SBB

I opened up the file in a text editor & found 13 .bin files that match up with the GBA downloadable files listed in-game:
DAKAR2CREDITS.BIN
PARIS1.BIN 
PARIS2.BIN 
PARIS3.BIN 
ROCK1.BIN 
ROCK2.BIN 
ROCK3.BIN 
DIRT1.BIN 
DIRT2.BIN 
DIRT3.BIN 
SAND1.BIN 
SAND2.BIN 
SAND3.BIN

And here's how they're listed in-game:
Mini Game Setup
Artois
Le Parc
La Petit Ville
Sun Baked
The Canyon Run
Driving On The Edge
Savannah
Muddy River
Mudbath
Sahara
The Dry Heat
Oskar Beach

Some of the multiboot files were released on the internet & here are how they match up with the in-game list:
Dakar 2 - Racing Game 02 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 02 (MultiBoot).mb - Artois
Dakar 2 - Racing Game 03 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 03 (MultiBoot).mb - Le Parc
Dakar 2 - Racing Game 04 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 04 (MultiBoot).mb - Le Petit Ville

Dakar 2 - Racing Game 05 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 05 (MultiBoot).mb - Sun Baked
Dakar 2 - Racing Game 06 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 06 (MultiBoot).mb - The Canyon Run
Dakar 2 - Racing Game 07 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 07 (MultiBoot).mb - Driving On The Edge

Savannah
Dakar 2 - Racing Game 01 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 01 (MultiBoot).mb - Muddy River
Mudbath

Dakar 2 - Racing Game 09 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 09 (MultiBoot).mb - Sahara
Dakar 2 - Racing Game 10 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 10 (MultiBoot).mb - The Dry Heat
Dakar 2 - Racing Game 11 (MB2GBA).gba.Dakar 2 - The World's Ultimate Rally - Racing Game 11 (MultiBoot).mb - Oakar Beach

Missing:
Mini Game Setup
Dakar 2 - Racing Game 08 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 08 (MultiBoot).mb
Dakar 2 - Racing Game 12 (MB2GBA).gba/Dakar 2 - The World's Ultimate Rally - Racing Game 12 (MultiBoot).mb


I was wondering if anyone knows how to open up an Acclaim SBB file/archive?   Any help would be greatly appreciated.
## Post #2
- Username: eisnerguy1
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 18, 2016 1:24 am
- Post datetime: 2018-07-03T02:11:32+00:00
- Post Title: Question about the Acclaim SBB file format in Dakar 2

So, I've got a small update:
Based on the multiboot files I mentioned (from the old ‘[No-Intro] Nintendo Game Boy Advance (MultiBoots) (20070704)’ set), I was able to view the “GBA.SBB” file in a hex editor and approximately extract the sections for “Mini Game Setup: DAKAR2CREDITS.BIN”, “Savannah: DIRT1.BIN” & “Mudbath: DIRT3.BIN”.

While the beginning of the files look fine (when compared to the already extracted multiboot files that I mentioned before), I can’t tell if the end of the file is missing something or has too much.  The extracted multiboot file is off just enough to not work when converted with mb2gba.

Might anyone have a GBA & an EZIV SD & could try running the [gba-multiboot-dump tool](https://github.com/shinyquagsire23/gba-multiboot-dump)?  I could send you the .GCI file containing all of the GBA multiboot games unlocked in the GCN version of Dakar 2 (once I unlock everything).  With that setup, dumping clean versions of the multiboot files should be possible.

I would do it myself but, I no longer have a functional GBA (my SP screen is cracked) and I don’t have an EZIV SD.
