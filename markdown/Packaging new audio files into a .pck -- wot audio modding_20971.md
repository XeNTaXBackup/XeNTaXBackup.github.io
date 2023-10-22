## Post #1
- Username: Anymn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 16, 2019 7:09 pm
- Post datetime: 2019-08-16T11:40:26+00:00
- Post Title: Packaging new audio files into a .pck -- wot audio modding

I am trying to mod the music sounds in World of Tanks.
As you might or might not know, World of Tanks uses from 1.0+ a different audio system which uses interactive music during battles. I like the old music more, so decided to try to mod them in.

My progress so far
I researched the file structure, and found out that the World of Tanks sounds are located in:
Games/World_of_tanks_EU/res/packages/audioww-part1.pkg

Now this .pkg happens to be an ordinary renamed .zip file. So I renamed it to.zip and unpackaged that. Inside, I found the file I'm looking for:
music_interactive.pck

Using quickbms / wavescan.bms / revorb.exe  (following the steps I saw on youtube [https://www.youtube.com/watch?v=WHrX0DHD99o](https://www.youtube.com/watch?v=WHrX0DHD99o)), I managed to unpack all the sounds. This resulted in 2884 different .ogg sound files which I can listen succesfully.
This process was basically .pck --> .wem --> .wav --> .ogg

How does wot interactive music work?
To my understanding, wot starts when the game loads, a specific music file for each map and equally long tracks for halfway a battle. On top of that, a pool of extra shorter music sounds are played to give varying results in what the user hears. 

What I want to try, is to replace all 'short' sounds samples with silent sound samples, and replace the longer, main music samples with the replacement I have in mind (the old music, which files I have). I can easily identify which tracks are what by sorting them on size, there are only 44 long tracks, the remaining 2840 are shorter sounds.

Now, in theory this should work if I replace the .ogg files with my own files, revert them back into .wem files, and then repackage them into a .pck file and replace the whole audioww-part1.pkg with the newly packaged files.

Replacing the .wem files I would use this tutorial: [http://forum.worldoftanks.com/index.php ... d/#topmost](http://forum.worldoftanks.com/index.php?/topic/488138-how-to-create-voice-mods-914-version-and-onward/#topmost)

My question:
Has anyone has experience compiling a .pck files? Is it possible? What bugs are to expected?
And is it possible using a script.bat so that I do not have to do that manually for 2884 files? 

Many thanks for answering,
Anymn
