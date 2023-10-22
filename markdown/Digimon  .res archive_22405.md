## Post #1
- Username: res
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 11:05 pm
- Post datetime: 2020-07-15T16:16:01+00:00
- Post Title: Digimon  .res archive

hello everyone,

can someone help me extracting resources from a .res file the game is digimon rumble arena 2 

sample files: [https://mega.nz/file/Y6pjFagB#pnzP-r_6F ... LGS1qUD4MU](https://mega.nz/file/Y6pjFagB#pnzP-r_6FnhDQBce8sPxYx827PIXQfRYVLGS1qUD4MU)
## Post #2
- Username: res
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 11:05 pm
- Post datetime: 2020-07-15T16:23:06+00:00
- Post Title: Digimon  .res archive

if anyone is interested this is a bookmark file for some offsets i found in lua.res using hex workshop

[https://mega.nz/file/4qQlDCSD#q_rEXUzjL ... HMRFj8V4iA](https://mega.nz/file/4qQlDCSD#q_rEXUzjLUqH1QvWIihXVSRReT-lKnwBUHMRFj8V4iA)
## Post #3
- Username: res
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-15T21:43:05+00:00
- Post Title: Digimon  .res archive

Hello you can extract data using quickbms [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)
and this script [http://aluigi.org/bms/spiderman_web_shadows.bms](http://aluigi.org/bms/spiderman_web_shadows.bms)

[https://imgur.com/SPb66yo](https://imgur.com/SPb66yo)

I have also researched it a little and here is my documentation [https://github.com/bartlomiejduda/Tools ... 0Arena%202](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Digimon%20Rumble%20Arena%202)
## Post #4
- Username: res
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 11:05 pm
- Post datetime: 2020-07-16T03:32:47+00:00
- Post Title: Digimon  .res archive

thx for your reply and help i actually found that bms script while doing a research for the file format. i even downloaded some files of spider man web of shadows. they are very similar if not the same but as you can see that bms script does the same for both games. it does extract the files but they are all .dat files with no names and i dont know what to do with them 

i would like to add something that i found dont know if it helps but if you go to the offset after the "indx" word at the bottom of the file from the data offset. it will take you to the 23 lua files (repeated again dont know why) above the name table. the offset right before the lua is the offset of file name from that position. i hope i explained it correctly. sorry i am not that good in hex and again thanks for your help.
## Post #5
- Username: res
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-16T07:53:54+00:00
- Post Title: Digimon  .res archive

> it will take you to the 23 lua files (repeated again dont know why) above the name table
I think that it may be some misunderstending here, because there are no filenames in the RES archive,
so unpacking those files as DATs seems to be accurate in this case.

The only filenames you can see may be the ones you see in already extracted files.

So for example you can open file \Sample\lua_out\lua!\00000000.dat 
in hex editor, remove 8 bytes from the beginning and save it as "my_file.lua"
and you will have working lua script to deal with [https://imgur.com/a/WuFs8gO](https://imgur.com/a/WuFs8gO)
## Post #6
- Username: res
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 11:05 pm
- Post datetime: 2020-07-16T14:04:59+00:00
- Post Title: Digimon  .res archive

wow thx didnt know about that. but does this also work for other files as well like for example if i extract a wave file or texture or some other type if i remove the first 8 bytes and save as it was supposed to like file.wav well this work or is it just the lua file.

and yes the filenames i mean are the ones that normally get extracted in the strg file. but i can see them in the archive and the number of filenames match the number of files or am i missing something. sorry if it is too obvious.
[pic.PNG](https://xentaxbackup.github.io/file/18480_pic.PNG)
## Post #7
- Username: res
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-16T20:39:13+00:00
- Post Title: Digimon  .res archive

> but does this also work for other files as well

It depends on a file really. Like for example it seems
that wav files are handled automatically by the script [https://imgur.com/a/4FbMXhC](https://imgur.com/a/4FbMXhC)
or other example may be texture file that I have found in omnimon.res archive [https://imgur.com/a/VT2ObKM](https://imgur.com/a/VT2ObKM)
It looks like it has 64 bytes header and then you have palette and texture data.
But your samples are to small to tell if every texture can be viewed in the same way.

Lua were the easiest ones to extract and convert, because they are text files and you just see with your eyes where
is binary data and where text starts. Like here you can see that it starts with print statement [https://imgur.com/a/GfoINxS](https://imgur.com/a/GfoINxS)

> and yes the filenames i mean are the ones that normally get extracted in the strg file. but i can see them in the archive and the number of filenames match the number of files or am i missing something. sorry if it is too obvious.
Yeah, filenames in strg file may look like some kind of filenames dump. But I don't think they can be used for automatical renaming. 
Like in this example you have full paths on the beginning [https://imgur.com/a/p6uPgiT](https://imgur.com/a/p6uPgiT)
and then you can see some model data. So you have 4 filenames here, but there are many more files in omnimon.res archive
## Post #8
- Username: res
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 11:05 pm
- Post datetime: 2020-07-17T06:33:09+00:00
- Post Title: Digimon  .res archive

> But I don't think they can be used for automatical renaming.

yeah, it is really annoying that you have all these files (animations, models, ..etc) but cant really use them
i mean from your experience what do you think should i give up already or is there actually a way to get animation or model files from these archives??
and even as you mentioned the script should handle wav files but unfortunately, they are extracted as .dat files like the others
this is a sample audio file: [https://mega.nz/file/croHyaxA#r_Jv41KJG ... M76IA9Jo7k](https://mega.nz/file/croHyaxA#r_Jv41KJGb-BrIbjnHylr-0zdWW-wcitAM76IA9Jo7k)

> But your samples are to small to tell if every texture can be viewed in the same way.

the truth is i thought if i uploaded smaller files, they would be easier to understand and analyze LOL
dont know if that is true or not

this is basically all the files in the game, but since i didnt know which would be helpful. i uploaded the ones in the sample folder
 but if you find something of interest tell me and i will upload it



files.PNG (39.92 KiB) Viewed 90 times



and this is the largest one:  [https://mega.nz/file/EuwXiaTa#-CMSiODmV ... 2SYDu6BoaI](https://mega.nz/file/EuwXiaTa#-CMSiODmVGg8JuiMzImYAqDt8SBLIztFL2SYDu6BoaI)
i noticed that the repeated offset to number of files isnt repeated here and the following 4 bytes
after the offset are not zeros as other files.
image: [https://ibb.co/520DW8q](https://ibb.co/520DW8q)
## Post #9
- Username: res
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-17T20:38:13+00:00
- Post Title: Digimon  .res archive

> i mean from your experience what do you think should i give up already or is there actually a way to get animation or model files from these archives??

If you have enough time, you can try to learn how to get 3D models and animations
[viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

> the script should handle wav files but unfortunately, they are extracted as .dat files like the others
Yeah, now I see it. They look like headerless WAV files. So your option here is to open these
DAT files in Audacity, then import files as raw data and try to guess proper parammeters.

> the truth is i thought if i uploaded smaller files, they would be easier to understand and analyze LOL
>
> dont know if that is true or not

That is correct. Smaller samples are better for initial analysis.
## Post #10
- Username: res
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 11:05 pm
- Post datetime: 2020-07-17T22:30:59+00:00
- Post Title: Digimon  .res archive

> If you have enough time, you can try to learn how to get 3D models and animations

aweasome topic, i have been trying to find guides when i first started learning reverse engineering but there wasn't alot of them and the only videos i could find were mr.mouse videos which were very helpful.

again thank you very much for all your help, you don't know how much you helped me in understanding those files. one last thing if it is not a bother, could you share the program you used to open the textures in the onimon.res file. if you can't share the program for reasons. it is ok. i totally understand
## Post #11
- Username: res
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-18T06:27:29+00:00
- Post Title: Digimon  .res archive

> again thank you very much for all your help
No problem.   

> could you share the program you used to open the textures in the onimon.res file

Sure. I have shared a whole collection of such tools a while ago   
[viewtopic.php?p=124552#p124552](https://forum.xentax.com/viewtopic.php?p=124552#p124552)
