## Post #1
- Username: Kushami
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 06, 2010 10:03 am
- Post datetime: 2013-07-15T06:08:03+00:00
- Post Title: Silhouette Mirage .BIN Reverse Engineering / Restoration

Hi all,

I apologize if this is in the wrong place, but I'm unsure, honestly, what format these files are in. I know some stuff, but not all. I figure one post is better than many though.

So I've been working on undubbing/restoring the English version of this game. Essentially make it play like the Japanese version, but with english text. For those that don't know, when this game came out in the US, Working Designs changed a bunch of things. 

-They dubbed the game (which was a decent dub, actually!)
-They changed how the saving system works. (Which is fine.)
-They changed how the game mechanics worked (for the worse.): Shyna's gun now drains your power, shooting an enemy from the wrong side drains theirs, but it's very disproportionate and heavily unbalances the game.
-They changed the price of items in the stores.
-They censored some of the textures to be less religious.
-They changed the names of a lot of the characters to seem less religious. 

My goal for this project is to-

-Replace the English voices with the Japanese voices.
-Revert the game mechanics and item prices to their original state.
-Fix some of the translation mistakes. Like changing the gun names to the original sins, such as Priday going back to Pride.
-POSSIBLY replace the dialogue font with something less 1980s digital.
-POSSIBLY fix that changed texture.

I've made some progress! See here: [http://youtu.be/EjHKUqLxyEU](http://youtu.be/EjHKUqLxyEU)

And these:


[http://twistygadget.com/projects/silhou ... ixes02.png](http://twistygadget.com/projects/silhouettemirage/sm_namefixes02.png)
[http://twistygadget.com/projects/silhou ... ixes03.png](http://twistygadget.com/projects/silhouettemirage/sm_namefixes03.png)

Just, well, not enough. I need help. I've hit some stumbling blocks I know I won't be able to figure out. However, I have figured out a lot of stuff about the filesystem, how the game works, and so on. Some things I've learned about the game so far:

-Most graphics are not .TIM format. The only things that are in .TIM format for the most part are the menus, loading screens, and some incidental graphics. No idea how most graphics are stored.
-Repacking the US version of the game with larger files with new LBAs/TOC does not seem to break the game.
-A lot of the files in the US version are identical to the Japanese version. See here: [http://twistygadget.com/projects/silhou ... nces01.png](http://twistygadget.com/projects/silhouettemirage/differences01.png)
-For most of the level structures, they only changed the SND and STG data between US and JP. The other files are identical.
-For some reason, Working Designs accidentally left some of the Japanese stage 1 files in the directory for stage 2. Haha.
-Almost every file is a .bin, which I know is a pretty common container extension on games in general which a lot of the time have no actual relation to most other .bins in other games. I couldn't find anything that would open a Treasure style .bin since I doubt many people are into hacking Treasure games, though I'm pretty newb when it comes to understanding container formats.

The way the game is laid out is as follows:

SLPS/US file
System.cnf
Directory 00 -> Contains Level 00 which is the tutorial, the main menu, and all the options screens. Clear level stuff I think too.
Directory 10-80 -> Contains the actual game levels.
 The most important files in these directories are:
  -SND##.BIN - Sound data.
  -STG##.BIN - Stage data.
  -V##A-E.BIN - Dunno. These seem to all be identical between the US and JP version though. I'm guessing they may be graphics?
  -S##.BIN - Dunno. Again. Identical between US and JP versions.
Directory 99 -> This contains the credits, game over screen, some other misc stuff.
C1/C2 -> I'm not sure what these are. However, everything in them according to KDIFF3 are byte identical between US and JP.
DA -> These seem to be bin files of the music in the game. Some are byte identical, some aren't. This is weird because the game seems to use redbook audio?
LOAD -> These are the special loading screens which only exist in the US version. They're all TIM files.
MV -> Contains the .STR movies.

How the stage files work, as far as I know:
 -For stage 1-3, the files for that would be STG13.BIN and SND13.bin, S13.BIN, and V13A-E.bin. All the files are split between their various stage #s.
 -The SND files are the sound for all of the stages, including all of Shyna's grunts, etc. They repeat, and all of the basic system ones seem to be in every SND.
 -So if you replace the US SND12.BIN with the Japanese SND12.BIN but not SND13.BIN, stage 1-2 will have Japanese voices, but not stage 1-3.
 -All the STG files seem to begin as a PSX EXE, so I'm pretty sure each STG file is a mini version of the game that contains almost everything it needs to run.
 -The STG files seem to contain all of the text for a scene.
 -The text seems to be packed in in plain ASCII with #00 placed between each letter. #20 seems to call up the weapon level in text. There's also color codes, but I'm not astute enough to understand it all yet.



 -The STG files contain all of the gameplay changes that Working Designs integrated into the levels. 
 -When you swap a US STG file with a Japanese one, the US game will play like the Japanese one, reverting the gameplay changes and store prices as well as the old save system.
 -This would be great... except when you run into any dialogue, it still tries to load the Japanese text but with the US text system. Which pretty much breaks that.




 -The US STG files also contain the code which calls the new saving system that WD created, because when you swap in a JP file all the extra saving prompts are replaced with the original Japanese ones which just say 'Now Loading.'




Ideally, I just want to do the following:
 -Unpack and edit the US STG files with the portions of the JP STG files which will revert the gameplay mechanics changes. I'm GUESSING this would mean hard editing the EXE once it's unpacked, but I'm hoping that there'll be simple hex sections I can hopefully copy and paste maybe. Maybe. ;__; For this, I don't even know where to begin, and I'm hoping some kind soul might. 
 -Figure out how the pricing works in the store and revert the prices to how they are in the original game.
 -Find an easy way to search and replace the names in the text in the STG files. Right now it's ascii but with 00's between every letter, and I'm unsure if there's a way to make this more readable and easier to edit. I've figured out what some of the codes mean between words (there's one to change the color to yellow, etc.) but not much else.
 -If there's a way to unpack and repack these files, that would be awesome, though from the looks of things it's all hard packed into the exe? I really don't know anything about zlib and whatnot, so I'm at a loss here.

[Here](http://twistygadget.com/projects/silhouettemirage/SM_STAGE01_DEMO.zip) are some samples of the US and JP stage one files if people want to check them out. These were includes in the demos way back when.  I'm willing to compensate anyone if they end up building a tool or tools to help with this, though I'm not not a rich man by any means so keep that in mind.

Thanks for your time!
