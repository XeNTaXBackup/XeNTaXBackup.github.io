## Post #1
- Username: Nick41516
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 13, 2021 2:29 am
- Post datetime: 2021-12-13T17:45:35+00:00
- Post Title: Cat Daddy Tycoons - .bin archives

Cat Daddy Games developed a bunch of games in tycoon genre at the beginning of 2000s. I'd like to mod them to enable widescreen resolution.

While I can force 1920x1080 resolution by hex editing settings file in game root, UI breaks in widescreen and to fix it I need to change some UI files that are stored in game archives.

All their games of the time seem to be using the same type of archive with .bin extension. I've been reading much on file extensions on this forum and wiki lately, but I can't quite figure it out.

So far, I can pinpoint the following:

 Begins with a string "d";
 Offset C - archive name;
 Offset 50 - number of files;
 Offset 54 - number of folders?;
 Then there are pointers to folders;
 And pointers to files;
 Each file begins with its name, and after exactly 0x40 bytes there are "CD" characters;
 Each folder? begins with its name, followed (after 0x40 bytes) by some number (files in folder?) and some pointers.


But I'm not sure how to do extraction and whether it's even possible. If anyone can take a look at this format, I'd greatly appreciate it.

I'm attaching two samples from Cruise Ship Tycoon (2003), I think they both contain graphic files:

 mousecursor.bin, 3 636 bytes, 2 files and 1 folder?
 NavigationUI.bin, 161 135 bytes, 11 files and 7 folders?


UPD. Turns out, these bin files are useless for my purpose anyway. I've fixed UI issues in Cruise Ship Tycoon only by hex editing executable with a help of Ghidra.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-23T23:44:05+00:00
- Post Title: Cat Daddy Tycoons - .bin archives

> But I'm not sure how to do extraction and whether it's even possible. If anyone can take a look at this format, I'd greatly appreciate it.

Hi, here is a quickbms script for extracting data from BIN archives
[https://github.com/bartlomiejduda/Tools ... %20Tycoons](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Cat%20Daddy%20Tycoons)

I have also updated the wiki with this new file format
[http://wiki.xentax.com/index.php/Cat_Daddy_Tycoons_BIN](http://wiki.xentax.com/index.php/Cat_Daddy_Tycoons_BIN)


After extraction I had some success in getting raw image data from output files.
[https://i.imgur.com/tFIUOi7.png](https://i.imgur.com/tFIUOi7.png)
[https://i.imgur.com/5MAJeB3.png](https://i.imgur.com/5MAJeB3.png)
I can't figure out the palette, but data seems to be uncompressed.
More reseach needs to be done on this to edit those BIN files.
