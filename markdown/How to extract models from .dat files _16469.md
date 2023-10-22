## Post #1
- Username: gary
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 29, 2017 10:27 am
- Post datetime: 2017-06-29T02:53:35+00:00
- Post Title: How to extract models from .dat files ?

Recently, I've downloaded and decompressed a game from NetEase.
But on my way to extract 3D models from the .npk files, I met some problem.

I extracted the .dat file and .xml. But I don't know how to extract the .dat.

I guess the models are in the .dat file because I opened the .dat files with UltraEdit and I saw some characters like "Biped" "bone",  so I'm pretty sure that the .dat contains what I need.
As all I know, the game is developed by it's own engine named "NeoX".

Is there anyone who knows how to know what file it use and how to extract 3D models from the .dat file?

Appreciated UR help !!!

Here is the .apk file:
[[color=#0000FF]https://h30.gdl.netease. ... k
[/color]]()

and .dat file:


 00003a86.rar
(103.63 KiB) Downloaded 57 times
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-29T06:52:40+00:00
- Post Title: How to extract models from .dat files ?

00003a86_dat.png (54.78 KiB) Viewed 698 times


there is a lot of data in that sample but i only see one block of indices so i guess there is no head in there
## Post #3
- Username: gary
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 29, 2017 10:27 am
- Post datetime: 2017-06-30T02:59:58+00:00
- Post Title: How to extract models from .dat files ?

> Reply from AceWell
>
> 00003a86_dat.png
there is a lot of data in that sample but i only see one block of indices so i guess there is no head in there

That's awesome!!!

I have many .dat files. So I guess the files contain the head.

As for the H2O, how do I know what the numbers should be filled in in the software?
I read the tut, but I'm still a little confused.
And, do I have to extract the models one by one? Is there any ways to extract them all by once?

Thanks again!!!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-02T20:05:30+00:00
- Post Title: How to extract models from .dat files ?

> Reply from gary
>
> As for the H2O, how do I know what the numbers should be filled in in the software?Try out/understand the sample extraction in the tutorial.

> I read the tut, but I'm still a little confused.why?

> And, do I have to extract the models one by one? Is there any ways to extract them all by once?
 the idea is to understand how to get "the numbers to be filled in" for one file/model
 then you need to understand the overall structure of the .dat files
 based on that someone could write a script (maxscript/ Blender or Noesis python)

Or using "C" ([viewtopic.php?f=29&t=15955](http://forum.xentax.com/viewtopic.php?f=29&t=15955)) which is the quickest approach for me.
## Post #5
- Username: Cassidy0307
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 19, 2021 2:19 am
- Post datetime: 2021-03-29T05:29:27+00:00
- Post Title: How to extract models from .dat files ?

Hi, I'm Cassidy. writes here because hopefully someone can extract the gr2 models, sound effects, and more from the DAT file. As you can see in the screenshot, I opened one file to show you that there are not only models, sounds, but also folders to dig into. I want to fix all the files are there: font, textures, gr2 models, sound effects etc. Why do I care so much about all these files to extract? I want to create animations from these models, if you have the ability to fix them, please send the repaired files to my e-mail: [karolinazelezinsska699@gmail.com](mailto:karolinazelezinsska699@gmail.com) (I have Windows 10, so I would be able to download program links). I also want you to send a notebook with links to open a file such as ogg, xml. If the files are repaired I will be grateful. Download Link: [https://drive.google.com/file/d/1aKhuQe ... sp=sharing](https://drive.google.com/file/d/1aKhuQeRXswNIUeeJty8w8Ng11LvqQ-7i/view?usp=sharing)



screen.png (96.41 KiB) Viewed 378 times
## Post #6
- Username: Cassidy0307
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-29T20:37:30+00:00
- Post Title: How to extract models from .dat files ?

Hello Cassidy. I was able to check your samples and here is a documentation for this format
[http://wiki.xentax.com/index.php/My_Rid ... enture_DAT](http://wiki.xentax.com/index.php/My_Riding_Stables_2:_A_New_Adventure_DAT)

And here is a tool for extracting all files from DAT archive with proper filenames
[https://github.com/bartlomiejduda/Tools ... AT_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/My%20Riding%20Stables%202/My_Riding_Stables_2_DAT_Tool.py)
## Post #7
- Username: Cassidy0307
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 19, 2021 2:19 am
- Post datetime: 2021-03-30T16:14:57+00:00
- Post Title: How to extract models from .dat files ?

Thank you for these links, I'm glad you made it . I have a small request, but this is the last one you will write to me in the points how to download these files? I don't know these pages and it would be easier for me.
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-30T17:30:35+00:00
- Post Title: How to extract models from .dat files ?

Yeah, sure, just click "Raw" button if you want to download this one script [https://i.imgur.com/aektcuz.png](https://i.imgur.com/aektcuz.png)
You can also go to main repository site and click Code > Download ZIP, to get everyting at once.


Then just download Python 3.7, change paths at the end of the script and run it.
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-06T22:21:55+00:00
- Post Title: How to extract models from .dat files ?

@PELAUDIA @Cassidy0307 Please don't create duplicate posts ever again. It is forbidden here.
If you want some help with my tool for extracting, you can ask here.
Also, why your posts are so similar? Can you explain? If it is multiaccount, then it is also forbidden and you should delete immediately one of your accounts.

Edit: Ok, I've got  report from Cassidy and it seems that it was just duplicate post. I have deleted it already from this topic.
