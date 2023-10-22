## Post #1
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-23T23:39:48+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

Hi
First of all I have to say I am a total beginner at all that stuff. I have almost no programming experience and can only somewhat read some program languages but not write at all. The only languages I somewhat know are NQC and Java.
I came to this Forum when someone forwarded me to this Thread:
[viewtopic.php?f=10&t=7351](http://forum.xentax.com/viewtopic.php?f=10&t=7351)
Since I was modding DeadIsland, this thread really caught my attention. It opened the possibility to access the compressed game files and textures.
With this program it is possible to acces the textures/meshes and some other stuff. But it has still no function in modding the game since we either need to be able to completely rebuild new .rpack files or to inject the edited files into the already existing files.
After browsing through the forum I discovered this guide you made here and read it:
[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF)
(Great guide btw...it really helped me understand how to hexedit a lot more...I always avoided hexediting before)
Now I went into exploring the .rpack myself (started with smaller ones). After discovering some values and patterns i noticed that filesegments started with the tlib code.
So i unpacked one in offzip. I compared the extracted data with one of the mesh files that i extracted (out of the same .rpack using the rp5l.exe program from the first thread i mentioned). I than saw that this .mesh file was not only split into several of the .data files offzip extracted but the file was split into different segments located in different offsets in the original file.
After I was able to put together the pieces of the data files until i had my .mesh file (Comparing the file with the original one showed no difference) i wanted to test something out that i could use in game.

So I tried the same with the act1a_load_PC.rpack . But this file is compared to the other one I edited huge and I failed trying to do the same thing cause of two reasons:
1. You need to use -z -15 to extract this file in offzip. It fails if you use default (-z 15).
2. I could find no match at all to the extracted data from offzip when searching for code from one of the .tex files I extracted 

Going through the file in hex showed me that the file had less spaces between filechunks (less padding)..also I had a harder time to find beginnings of zlib files.
So this file is probably still too difficult for me even though it's a shame, since almost all data of a lvl is stored there.

Now I didn't want to give up in my plan to test if I am able to change an element in game the way I want.
So this time I did the same thing , but with the much smaller file menu2_common_PC.rpack .
As the name already says this file contains files that are used in the Game Menu.
So I used offzip and searched through the extracted files for data that had the beginnig of the code of the file ingame_bg.tex/ingame_bg.tex.dds (The .dds has the same content as the .tex but only a different header)
I found it in the 00132800.dat and I had luck...the whole content of the .dds /.tex file was the same as this files content. The file wasn't even split like it was in the file I used in the first test I did. So I edited the file .dds by changing it's color from green to red and augmenting the saturation and replace the content of the 00132800.dat with the one of my edited .dds (I payed attention so that it kept the same filesize). Than I used packzip to inject the edited 00132800.dat into the offset 132800 of the 
menu2_common_PC.rpack

packzip.exe -o 132800 filepath/00132800.dat  "filepath/menu2_common_PC.rpack" is what I used and it was a succes. I compared the original menu2_common_PC.rpack and the edited one and they were the same except the chunk i inserted.
Now I tested it in game by putting it into the /documents/DeadIsland folder that the game uses to load mods.

The game started fine but what I got wasn't the changed color of the menu background like I hoped.
instead all Menu elements were black (completely black screen, couldn't see a thing).Through the sound that it makes when hovering above an option I was able to go into my game. There were missing all Menu and Hud elements that were coded in this file, but the game itself was fine.

So either the game didn't want to load the file I put in at all and got errors...or the change is faulty and it breaks the file. (could also be that only the small files are corrupted pretty easily since I made tests before with the big file act1a_load_PC.rpack  by removing a big file chunk out of it and inserting a smaller file chunk from a sound file of the game .xwb to corrupt the file myself and to test if the game loads changes to the file even if it is corrupted...the game loaded fine into the edited level...there were only some textures missing and not all. )
So to test if the game doesn't like changing .rpack files I replaced 200 bytes in the middle of the original file with zeros.
This time the whole screen was red and not black...but in the upper left corner I was able to see my mouse again and partly the Hud.

I will attach the edited files and the original ones.
Would be nice if somebody would help me more with the understanding of these files, and why changing it the way I did didn't work in the end.

Also if someone that knows a lot about this stuff and would be so kind to create a tool to repack .rpack files or to or inject the edited files into the existing one, that would be awesome and the whole DeadIsland modding community would be in his debt.
I don't know if hhrhhr stopped working on his rp5l tool, but we didn't hear from him for days. Here is the link to it again:
[viewtopic.php?f=10&t=7351&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=7351&start=15)
It's awesome what he did but , but for us this tool is a real tease...we can see so much information and it can extract most of the content files of the game, but we can't use it to mod the game. And it only gives us access to the graphic data stuff like .tex .mesh .anim .fx but not to stuff that allows us to edit the game mechanics (which should be in the .rpack files too). Also out of the graphic data only the .tex files can be edited for now since they are the .dds .
For the other stuff we probably need a converter since they are for the chrome engine.

Thanks for taking the time to read this post and to help me,  and possibly the DeadIsland modding community.

EDIT: Nevermind the whole part about the act1a_load_PC.rpack ....made the silly mistake and used the small file act1a_load_PC.rpack ..the big file is act1a_PC.rpack..and this one unpacks just fine in offzip.

DL link of the files:
[http://ul.to/d6umuw0j](http://ul.to/d6umuw0j)

Password is xentax
## Post #2
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-24T11:02:17+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

try that:
packzip.exe -o 0x132800 filepath/00132800.dat "filepath/menu2_common_PC.rpack"
132800 is a hex number not decimal. Also, this method will work only if new compressed data is smaller than original one I think.

edit: it also work for bigger files, if you edited section packed size and file part packed size. I tried only tex files.
## Post #3
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2011-09-24T11:47:11+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

Cool  Any news about the other compression method used in some of the rpack files?
## Post #4
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-24T14:29:52+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-24T15:34:14+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

> Reply from rengareng
>
> try that:
packzip.exe -o 0x132800 filepath/00132800.dat "filepath/menu2_common_PC.rpack"
132800 is a hex number not decimal. Also, this method will work only if new compressed data is smaller than original one I think.

edit: it also work for bigger files, if you edited section packed size and file part packed size. I tried only tex files.
Awesome...thx that worked...i thought that packzip was able to use dec and hex adresses like offzip can.

I am now trying to do the same thing with the di_bloodsplatground.tex in the act1a_PC.rpack, since i already did a Texmod for this texture once and I am able to identify the difference pretty easily.
Now this file is actually split into different offsets in the act1a_PC.rpack and I am currently trying to identify the parts using Hex Editor Neo (since it can search for Hex parts in several files (the act1a_Pc.rpack is split into 16.000 different files by offzip.)
Is there a Hexeditor that can search for the content of an entire file in multiple other files? that would be great...hex editor neo does his job in this use pretty good too though and it is the only free Hex editor that I was able to find that can do stuff like that. (though you need the 14 days free trial to use this feature).


But I have a much bigger issue. The .tex file in the menu2_common_PC.rpack was exactly the same as the .dds that the rp5l program was able to extract out of it, but the only difference was the header.
But the di_bloodsplatground.tex does not only have a different header, but it also has a completely different file content as the di_bloodsplatground.tex.dds...so it seems the in the bigger files the .tex files are compressed...using offzip didn't work

How can I transform a .dds back into the corresponding .tex?
[bloodsplat.7z](https://xentaxbackup.github.io/file/4734_bloodsplat.7z)
## Post #6
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-24T17:09:13+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

you dont need to. they are indeed mipmap files of that font. you can seperate all of them. 
512*512 for mipmap0
256*256 for mipmap 1
.
.
.
1*1 for mipmap9
## Post #7
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-24T19:05:23+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

> Reply from rengareng
>
> you dont need to. they are indeed mipmap files of that font. you can seperate all of them. 
512*512 for mipmap0
256*256 for mipmap 1
.
.
.
1*1 for mipmap9
thx again for the help, i was confused about the change in the .tex files before, but it all makes sense now.
I'm glad that I used an easy .tex file before, that had no mipmaps, or i would have had a real hard time to figure this out and i would have possibly given up on my experiment back than.

the extracted .dds files only have the level 0 mipmap

since I don't really care about how the Texture looks if you are far away, it should be enough if I just edit the code of the level 0 mipmap (I already isolated the location now, thx to your tip)
This would also mean that I also need to search for much less code in the dat file that offzip extracted. This should make my work much easier.
## Post #8
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-25T08:02:21+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-25T08:54:11+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

I now hit another wall...I was able to change the Bloodtexture of the blood that splats on the ground when you hit someone. But changing it only works when changing the color of the original file.
If I add other pixels to the .dds and inject it into the act1a_PC.rpack the game starts but it doesn't load the level...the game gets stuck on the loading screen....I let it even load once for an hour but the level didn't load but the game was still running.
removing pixels should works since I did already did an experiment once to see if the game loads the .rpacks if they are in the same folder as where all other mods are located. I removed the whole content of the .rpack back than, and I was spawned in the void, but the level loaded.

I didn't change the size of the files...they still have the same amount of bytes. All that changed is the number of pixels that are colored in the file.

In the attachment I included the original offzip filepart that contains the data of this Texture (only the map0 level), the orignal .dds of the texture and the modded versions of both those files.
(and the original .tex file)

[http://www.file-upload.net/download-375 ... od.7z.html](http://www.file-upload.net/download-3756941/blood.7z.html)

I did inject the file into the right adress using packzip, since I was able to change the color of the texture in the game
## Post #10
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-25T10:18:28+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

compressed size matters in this case,and it will change. not uncompressed(it will not change). You should find coresponding packed file size hex in datas and section part of header in rpack file and increment packed size.
## Post #11
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-25T12:19:30+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

> Reply from rengareng
>
> compressed size matters in this case,and it will change. not uncompressed(it will not change). You should find coresponding packed file size hex in datas and section part of header in rpack file and increment packed size.
ahh yeah haven't thought about that.
k i found the file size header and edited it and fixed the overwritten file that comes after the one...but as I thought this doesn't work...the game loads the level but it loads messed up (into the void) since the pointers to the other files get broken through this....so either I have to make my file smaller till it has the compressed size of 79872 bytes...or I repair the pointers for all the files that come after this one...I'm just gonna do the first method since the game only loads the first upper left quarter of the whole texture for the change that I wanna test.
## Post #12
- Username: Sanchomld
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 15, 2012 4:18 pm
- Post datetime: 2012-06-15T09:15:23+00:00
- Post Title: [DeadIsland] Beginner's .rpack file experiments

where i can downlod rp5l.exe?
