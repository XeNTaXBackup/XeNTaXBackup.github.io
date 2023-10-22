## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-13T20:14:26+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

Better late than never  Here is a tool for loading/extracting models from VP2. I focused mainly on the characters, but monsters and npcs seem fine too. Map geometry will be loaded, but no proper positioning makes it kind of useless.

It supports geometry, skeleton, skinning and materials (badly). Skeleton is mostly loaded properly (few exceptions), but some dummy bones might be positioned wrongly which don't effect the skinning. Material support is there to give an idea of what textures are used, since there are lots of copies of the same model. It doesn't work well on more complex models.

Overview of the tool and example exported model



How to use

Load (File Menu)

Load PK1 : Loads the files inside the PK1 archives and adds them to the list. Not all files contain model data. Read below for getting PK1 files from the game disc.
Load SLZ/DAT : Loads single files that are extracted from the PK1 archives.
Load DAT Folder: Loads the folder extracted with "VP2 Model Searcher". Also read below for that.
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
IQE : Exports the model in IQE format. Read here to see how to load IQE : viewtopic.php?p=138153#p138153
PNG : Exports the textures in PNG format. Only 8bpp textures are supported.
Note  : Models and textures will be exported into the folder Export.
Download : [https://www.mediafire.com/file/63371kae ... r.rar/file](https://www.mediafire.com/file/63371kae82p9vzo/VP2Viewer.rar/file)

Getting the game files

Download the "VP2ArchiveTools.rar" attached to this post below. First you need to extract the files from the game iso. Use triAce-PS2.exe for this. Example usage : triAce-PS2.exe vp2.iso outfolder . It will export bunch of files to the output folder. We are mainly interested in PK1 because they have the models, along with other stuff.

At this point you can load the extracted PK1 directly into the viewer, or extract them with the bms script and load them. Still it might take some time to find what you are looking for. So I made another tool to search all the PK1 files and extract model related files based on their type.




Program is called "VP2ModelSearch.exe" and you can find it inside the downloaded files. Basically you select the input folder(output folder of triAce-PS2.exe), select the model type (Character/NPC/Monster), and click Extract. Wait for it it to complete. After that you can load the whole folder (extracted model files) in the viewer using File -> Load DAT Folder.

Feel free to report the errors, but I might not fix them  The model format wasn't that easy, and I think I have spent enough time on it. There are problems, still I am more or less happy with the current state of the program.

Credits
CUE - SLZ Decompressor and archive tools
[VP2ArchiveTools.rar](https://xentaxbackup.github.io/file/15719_VP2ArchiveTools.rar)
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-02-14T12:49:58+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

This will work perfectly for me and many Valkyrie Profile Fans!
Thank you for completing the difficult work!

----

I finished the conversion work of all the main characters.
All models work properly. No problem. Next I will try NPC's.
[brahms.png](https://xentaxbackup.github.io/file/15721_brahms.png)
## Post #3
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2019-02-17T14:30:15+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

the extract the files game iso to the outfolder not working.
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-17T15:59:14+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

> Reply from blacknight411 ↑Sun Feb 17, 2019 10:30 pm at Sun Feb 17, 2019 10:30 pm
>
> 
the extract the files game iso to the outfolder not working.
You must be doing something wrong. Maybe you are running the program with wrong parameters. I can't say much without seeing an error message, or what you are trying to do.
## Post #5
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2019-02-19T08:45:34+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

I  find some models’ texture are wrong。


[Snap_2019.02.jpg](https://xentaxbackup.github.io/file/15753_Snap_2019.02.jpg)
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-19T08:51:47+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

> Reply from phay008 ↑Tue Feb 19, 2019 4:45 pm at Tue Feb 19, 2019 4:45 pm
>
> 
I  find some models’ texture are wrong。
Yes, they won't work properly for every model. Assign/fix them manually.
## Post #7
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2019-02-19T10:34:24+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

Ok let go step by step  Load PK1 : Loads the files inside the PK1 archives and adds them to the list.   what  is archives   what list file
Load SLZ/DAT : Loads single files that are extracted from the PK1 archives. where do you get dat.  Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format.  custom binary  to Noesis script  First you need to extract the files from the game iso. Use triAce-PS2.exe for this. Example usage : triAce-PS2.exe vp2.iso outfolder.  ok this  one I do not understand  I  extracted  iso I took the game part. I dump  the ios  part and  the triAce-PS2.exe  and put a folder  it did not work and that   is  my problems.









































i
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-20T22:12:44+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

Maybe post the cmd output as screenshot? What happens when you run "triAce-PS2.exe"? Nothing happens or do you get some an error message?
## Post #9
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2019-03-13T12:40:12+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

Run triAce-PS2.exe  with pk1 Nothing happens  no error message nothing.
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-13T13:47:59+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

> Reply from blacknight411 ↑Wed Mar 13, 2019 8:40 pm at Wed Mar 13, 2019 8:40 pm
>
> 
Run triAce-PS2.exe  with pk1 Nothing happens  no error message nothing.
"triAce-PS2.exe" is for the iso file only. Once you have the pk1 files, either use  "VP2ModelSearch.exe", or load them directly with the model viewer. Read the first post carefully, I have explained everything there.
## Post #11
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-15T09:25:01+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

Finally!!!!!! I've being waiting for this for years!!

And more because they never remake it for PS3/4, Xbox360/One or PC
## Post #12
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2019-03-16T02:43:45+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

I drag the ios  and the triAce-PS2.exe but none happened.
## Post #13
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2019-03-20T16:06:31+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

Ok I see the file lists  but  keep getting error.
## Post #14
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-03-20T16:58:33+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

triAce-PS2.exe is a command line tool. 
You should be able to use it by specifying the properly ripped iso. "triAce-PS2.exe VALKYRIEPROFILE2.ISO Newfolder"
## Post #15
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-26T21:27:31+00:00
- Post Title: Valkyrie Profile 2: Silmeria Tool

Tested and I've to admit its a marvelous tool. It did extract pretty much all the models of the game with correct in all (except the textures, but, that can manual be fix).

The only problem was the viewer, for constantly reset the view every time after open a new model. But besides that, I cannot complain many for something I've being waiting more than 10 years to happen
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-27T03:53:47+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

> Reply from Darkhowlings ↑Wed Mar 27, 2019 5:27 am at Wed Mar 27, 2019 5:27 am
>
> 
The only problem was the viewer, for constantly reset the view every time after open a new model.
It is the same camera script that I use for all of my tools. So I had to make something that auto adjusts based on mesh bounds, to make it work with everything.
## Post #17
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-03-27T04:21:26+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

The view is just optimized, not reset. If optimization is not performed, 
it will not be displayed properly on the screen and you will not be able to check the model.

I know the process. akderebur gave the best fix.
## Post #18
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-27T12:29:16+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

Ok, ok! I got it. No need to be on the defensive for that .

I mentioned early and I stick with it: Marvelous tool.

And what are the next planes? Extract voice samples? I wouldn't mind for the legendary quote of Lezard at the begging of Meteor Swarm
## Post #19
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-03-28T02:01:47+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

> Reply from Darkhowlings ↑Wed Mar 27, 2019 8:29 pm at Wed Mar 27, 2019 8:29 pm
>
> 
Ok, ok! I got it. No need to be on the defensive for that .

I mentioned early and I stick with it: Marvelous tool.

And what are the next planes? Extract voice samples? I wouldn't mind for the legendary quote of Lezard at the begging of Meteor Swarm

Audio files are encrypted. And I know that they are included in the bin file.
used unique XOR for encryption, decryption is difficult
## Post #20
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-28T18:53:46+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

> Reply from einherjar007 ↑Thu Mar 28, 2019 10:01 am at Thu Mar 28, 2019 10:01 am
>
> 
Darkhowlings wrote: ↑Wed Mar 27, 2019 8:29 pm
Ok, ok! I got it. No need to be on the defensive for that .

I mentioned early and I stick with it: Marvelous tool.

And what are the next planes? Extract voice samples? I wouldn't mind for the legendary quote of Lezard at the begging of Meteor Swarm 


Audio files are encrypted. And I know that they are included in the bin file.
used unique XOR for encryption, decryption is difficult

I can get that, after all, its a miracle they make the viewer & extractor. So, its reasonable.

Still, no wonder PSound didn't work with the game
## Post #21
- Username: aobaseragaki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 27, 2019 7:05 am
- Post datetime: 2019-05-29T02:50:35+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

i cant get triace to work , i tried run as administrator, i restarted my computer and everything, can someone please help me??
## Post #22
- Username: AceK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 05, 2014 4:14 pm
- Post datetime: 2019-08-28T04:33:29+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

> Reply from einherjar007 ↑Thu Mar 28, 2019 10:01 am at Thu Mar 28, 2019 10:01 am
>
> 
Darkhowlings wrote: ↑Wed Mar 27, 2019 8:29 pm
Ok, ok! I got it. No need to be on the defensive for that .

I mentioned early and I stick with it: Marvelous tool.

And what are the next planes? Extract voice samples? I wouldn't mind for the legendary quote of Lezard at the begging of Meteor Swarm 


Audio files are encrypted. And I know that they are included in the bin file.
used unique XOR for encryption, decryption is difficult

That's kind of odd if it is XOR'd... because the generic header information and the file structure referencing the file length and chunk count throughout the whole sample data isn't encrypted. I do notice that the section before the sample data/sample chunk header ("not" the beginning of file header) undergoes different bitwise operations that forms into 3 separate tables.
## Post #23
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-08-23T16:55:49+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

ram_more_enemy.png (91.96 KiB) Viewed 155 times


I recently noticed that some of the models not found by the Search feature seem to be available in the game's RAM. 
I think the cause is that the files of the battle scene, including the audio, are encrypted. It has been decrypted in memory.
Through this discovery, more models may be available.
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-08-23T18:28:38+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

> Reply from einherjar007 ↑Tue Aug 24, 2021 12:55 am at Tue Aug 24, 2021 12:55 am
>
> 
I recently noticed that some of the models not found by the Search feature seem to be available in the game's RAM.

Interesting find. Does model search work on the ram dump?
## Post #25
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-08-23T19:41:38+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

> Reply from einherjar007 ↑Tue Aug 24, 2021 12:55 am at Tue Aug 24, 2021 12:55 am
>
> 
ram_more_enemy.png
I recently noticed that some of the models not found by the Search feature seem to be available in the game's RAM. 
I think the cause is that the files of the battle scene, including the audio, are encrypted. It has been decrypted in memory.
Through this discovery, more models may be available.

Nice. Could be useful for get even more rare models or audio on the future
## Post #26
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-08-24T00:16:31+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

Yesterday, My country time was past midnight and I couldn't write the details  

I was trying to find a model that is not yet available, other than the one that is currently available with the search function or the one that is available in Anatomia. 
When I dumped pcsx2 with process hacker, I was able to find the model header (FPS) of VP2. I noticed that I could get the model by splitting files it and loading it into the VP2 Viewer. 
However, the memory dump spans several GB, which is a waste of time. We also discovered that the model can be obtained from the game's state save. * eeMemory.bin in the p2s file (this is a zip). 

At first I tried to cut with "\x46\x50\x53". In this case, 50% of the models loaded normally and 50% did not. I thought the VP2 Viewer wasn't compatible with the battle scene model. 
However, when I looked at the header of the model that had already been discovered by the search function,
I noticed that the FPS file contained more FPS. So I tried "\x46\x50\x53\x00\x00" and "\x46\x50\x53\x00\xC0".
These are the data that is often used in FPS headers. By splitting the file with this, I finally succeeded in obtaining the battle model.



ram_more_enemy2.png (31.32 KiB) Viewed 136 times


Other examples of models obtained from RAM that cannot be obtained by the search function 

-------------------------

> Reply from akderebur ↑Tue Aug 24, 2021 2:28 am at Tue Aug 24, 2021 2:28 am
>
> 
einherjar007 wrote: ↑Tue Aug 24, 2021 12:55 am
I recently noticed that some of the models not found by the Search feature seem to be available in the game's RAM. 


Interesting find. Does model search work on the ram dump?
Unfortunately it didn't work. The combat model has an FPS in the header, so I use it by splitting it. 

> Reply from Darkhowlings ↑Tue Aug 24, 2021 3:41 am at Tue Aug 24, 2021 3:41 am
>
> 
Nice. Could be useful for get even more rare models or audio on the future
The audio is unconfirmed, but it might be possible to obtain it by dividing it with the PS2 sound format SEQW.
## Post #27
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-08-24T03:55:14+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

I got better information so I will replay it instead of editing it. 

The information in the FPS header was very random and it was difficult to find the correct answer, but I found a way to get the correct header more reliably.
There is p@Ck(\x70\x40\x43\x6B) at the end of the FPS fileset. 

Split at \x70\x40\x43\x6B, and if you have a relatively large file, edit it and use the "FPS" that follows "p@Ck" as the header. Then you can almost certainly load the model in VP2Viewer.

*This method sounds like you can't get the contents of the very first FPS and p@Ck in the very RAM, but you only have to manually get the data from the very first FPS to the next FPS.

---------

And the good news is, yes, the audio is stored in RAM. You can get audio with PSound by splitting with SEQW.
As a matter of fact, I once received a decrypted SEQ file from someone who was parsing VP2. But now that it turns out that it can be retrieved from memory, anyone can retrieve the file.
*EDIT
PSound seems to automatically search for SEQW specify a file without split it.
## Post #28
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2022-07-26T15:29:59+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

Just wanted to pop in and say thanks to OP for their awesome work. Guy in my server clued me in on a VP2 4K upscale project, so I'm looking at the game again after a few years and now that I'm a reverse-engineering nerd, I was hoping there was already some groundwork laid. This is more than I could've hoped. Has anyone catalogued which character model is who--eg. cp004 is Lezard, cp003 is Rufus, etc--or did I scroll past that?
## Post #29
- Username: daniel87
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 10, 2020 1:20 am
- Post datetime: 2022-08-14T20:10:28+00:00
- Post Title: Re: Valkyrie Profile 2: Silmeria Tool

me podrian pasar a hrist con las texturas para usar en blender por favor
