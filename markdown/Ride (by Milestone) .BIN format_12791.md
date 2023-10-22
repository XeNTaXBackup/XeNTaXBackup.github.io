## Post #1
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-04-22T14:37:37+00:00
- Post Title: Ride (by Milestone) .BIN format

Hello,

As requested by some others members in another topic, any help to get a script to import .BIN 3D file format from Ride would be awesome.

This game has a huge content, including more than 100 bikes (Yamaha, Ducati, Honda and more).

For example, here's a Bimota Tesi 3D render, just to show you how beautiful are thoses bikes :



Here's the complete game folder of a bike, including the .BIN, shaders and textures (in PICTURES folder).

[https://mega.co.nz/#!d4tRgIjC!ZJ4WF9OGr ... 6W3mC6EvpU](https://mega.co.nz/#!d4tRgIjC!ZJ4WF9OGryx7xpbm964qdp6PsSmBK4-b66W3mC6EvpU)

To be honest, just having the 3D without textures autmatically applied is perfect for me.

I really hope someone can help
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-22T15:53:41+00:00
- Post Title: Ride (by Milestone) .BIN format

yeah, is very likely to become my next Make_H2O project!
(If not anyone else will release a complete max, Noesis, whatever script...  )

chassis#chassis_0@Bike001



Bike001.JPG (133.61 KiB) Viewed 936 times



searching for the tables containing counts and offsets (if any).
Feel free to contribute otherwise it may take some time...

0 0xb5b bike_inc@Bike001

01 00 00 00
5B 2A 5D 01  
5D F0 33 FB  00 00 00 67  
00 00 0B 84  

5B 42 5D 01  
5E DE C8 FC  00 00 00 5B  

5B 42 5D 01  F7 0E 38 15  
00 00 00 4F  

5B 42 5D 01  
E3 FC E5 4D  00 00 00 3F  

5B 42 5D 01  8B F2 DC D5  
00 00 00 33  

5B 42 5D 01  
BC 25 8A 42  00 00 00 27  

5B 42 5D 01  1A 74 A3 4B  
00 00 00 00  B2 5D DF ED  
69 86 4D 36  

1 0xbd5 BRAKE@Bike001

02 00 00 00  5B 2A 5D 01  
5D F0 33 FB  00 00 00 6C  
00 00 0B FB  5B 42 5D 01  
5E DE C8 FC  00 00 00 60  
5B 42 5D 01  F7 0E 38 15  
00 00 00 54  5B 42 5D 01  
E3 FC E5 4D  00 00 00 44  
5B 42 5D 01  8B F2 DC D5  
00 00 00 38  5B 42 5D 01  
BC 25 8A 42  00 00 00 2C  
5B 42 5D 01  1A 74 A3 4B  
00 00 00 00  64 9F 41 E7  
3D 48 E0 83  

2 0xc4c Brake_mask@Bike001

03 00 00 00  5B 2A 5D 01  
5D F0 33 FB  00 00 00 6B  
00 00 0C 77  5B 42 5D 01  
5E DE C8 FC  00 00 00 5F  
5B 42 5D 01  F7 0E 38 15  
00 00 00 53  5B 42 5D 01  
E3 FC E5 4D  00 00 00 43  
5B 42 5D 01  8B F2 DC D5  
00 00 00 37  5B 42 5D 01  
BC 25 8A 42  00 00 00 2B  
5B 42 5D 01  1A 74 A3 4B  
00 00 00 00  12 6B 4C 71  
EF A2 25 84
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-23T07:14:45+00:00
- Post Title: Ride (by Milestone) .BIN format

whoops. What a tedious task:



Bike000_wheels.JPG (210.24 KiB) Viewed 915 times


And that's the wheels only, different types, lods, whatever.
## Post #4
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-04-23T08:22:44+00:00
- Post Title: Ride (by Milestone) .BIN format

Whahoo!   

I was a bit worried because in this gme vehicles can be customised (wheels, exhaust, mirror and some other little things).

I'm a complete noob in reverse engeneering 3D models but if any help is needed feel free to ask 

Anyway, thanks a lot for taking time for this game
## Post #5
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-04-23T16:30:36+00:00
- Post Title: Ride (by Milestone) .BIN format

The BML file called BIKE001_GC seems to talk about rims. Not sure if it helps though.

EDIT : Maybe got an idea that could be easier : 

Maybe we could extract the bike itself (without wheels) and extract all customisable parts somewhere else. Then, if someone want a specific bike he extract it and add the customised parts manually in his 3D scene.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-23T20:00:42+00:00
- Post Title: Ride (by Milestone) .BIN format

> Reply from RiccoChicco
>
> [...] and extract all customisable parts somewhere else.to extract all the parts is the problem atm: the ones left from the black line are crappy and a whole bunch seems to be missing:



Bike000_parts.JPG (73.01 KiB) Viewed 883 times
## Post #7
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-04-23T20:23:01+00:00
- Post Title: Ride (by Milestone) .BIN format

Mmmh yeah that's a bit weird
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-24T15:15:54+00:00
- Post Title: Ride (by Milestone) .BIN format

made some progress:
[](http://www.pic-upload.de/view-26822525/Bike000_chassis_exhaust.jpg.html)

Attached some H2O files. You'll need hex2obj_023e.exe to create obj files from them.
(Archive hex2obj_0.22.zip required, too).

Load Bike001.bin into hex2obj then one of the H2O files. Press the 'mesh' button.


 BIKE001.BIN_H2O.zip
(3.29 KiB) Downloaded 104 times
## Post #9
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-04-24T15:40:53+00:00
- Post Title: Ride (by Milestone) .BIN format

Great news! And great work! I'm gonna have a look! Thanks again.
## Post #10
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-04-30T17:43:47+00:00
- Post Title: Ride (by Milestone) .BIN format

Hi!

I really don't want to bother you, but is there any news?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-30T21:05:55+00:00
- Post Title: Ride (by Milestone) .BIN format

It's a whole bunch of H2O files (246 atm) I'm stepping through from time to time
because there's still some point clouds I don't have the suiting face indices blocks for:



Bike_pointClouds_.JPG (68.69 KiB) Viewed 838 times



Those H2O files generate 800 MB of data. That's a little bit unhandy.
I could recalculate the face indices from absolute to relative ones to get rid of redundant data
but understanding the hierarchy has higher priority.

edit: the news is: found a tire
## Post #12
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-04-30T23:17:11+00:00
- Post Title: Ride (by Milestone) .BIN format

Thanks for you answer, really appreciated! Really interesting and very impressive.

About your point clouds, they really look like front lights and mirrors of the bike.

Thanks again for you help
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-01T16:24:41+00:00
- Post Title: Ride (by Milestone) .BIN format

good news: for some unknown reason   it imports the accessories at the correct positions.
Wouldn't have expected this. Great.

A new version of hex2obj was required to handle absolute/relative face indices.

Maybe I can upload it together with a set of H2O files for the accessories next week (for one bike only).



Bike_chain_mirror.JPG (115.31 KiB) Viewed 826 times
## Post #14
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-05-01T16:59:23+00:00
- Post Title: Ride (by Milestone) .BIN format

Amazing! Really good news!
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-07T13:19:18+00:00
- Post Title: Ride (by Milestone) .BIN format

finally - (well, not really but I think that's all what I want to do):
--------------

To get hex2obj working you'll need 

1) the zipped version 0.22 and
2) hex2obj_0.23g.exe

from Xentax: [viewtopic.php?f=29&t=10894](http://forum.xentax.com/viewtopic.php?f=29&t=10894)

Extract the first zip to a folder of your choice. Then copy hex2obj_0.23g.exe into it.

--------------------

There are 247 H2O files of which each can used by hex2obj to create a bike's submesh.

If you decide to use hex2obj's multimesh feature on ALL H2Os at once
be sure to have the RelFI checkBox checked (view pic below) else about 800 MB of obj data will be created!

YOU have been WARNED!

With the RelFI checkbox checked there will be 20 MB only.

Naming of the submeshes by numbers only is a little bit poor, admitted.
To give you some overview I've sorted the H2O files into subfolders.

Load the BIKE001.BIN (8.7 MB, not included) into hex2obj_0.23g then select any H2O file in
the example_bike subfolder (view attachment).

Then choose File "SaveAs Mmesh".
Some obj files will be created in the folder where the *.bin file resides.

Use the load_multi_obj_blender2.69.py python script
to get the obj files loaded into blender.

```
make sure to have set "path_to_obj_dir" to YOUR *.bin/*.obj directory.

Just replace ('O:\\', 'Eigene Dateien\\Downloads\\Samples\\Ride')

Alt-p should import the obj files in that folder into blender.

(Make sure that there's no obj contained in a maybe existing subfolder.)

(numbering in the outliner window of blender 2.49 is a little bit weird; 
in blender 2.69 you can be sure that BIKE001_128 represents BIKE001_128.obj)
```


(There are 8 objx files with a vertex count of 0. They are created for debugging purposes only.)

Numbering of H2O and obj files is async. First line in each obj file reveals its H2O "source".

Some H2O files may contain an incorrect vertex start address. Feel free to fix this.



example_bike.JPG (191.96 KiB) Viewed 796 times


The H2O files to be used with hex2obj:
[http://www.uploadmb.com/dw.php?id=1431003501](http://www.uploadmb.com/dw.php?id=1431003501)
## Post #16
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-05-07T17:31:41+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Really, really thank you Shakotay. It's very impressive and I'm very happy to see that you've found so many things for this file format. 

I'm thinking about other bikes, I know that it will be a bit different to get each bike because of different numbers of accessories, but do you plan any way to let us import whatever bike we need? Like a small tutorial to get the H20s files by looking in the .bin. I think it will be difficult (I really understand, no problem with that ) but that would be great. But I don't want to bother you, looking a the forum you're a very busy man   

Again, if any help is needed such as doing boring and repeating tasks feel free to ask. I'll be happy to help in any way.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-13T07:51:04+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

> Reply from RiccoChicco
>
> [..] but do you plan any way to let us import whatever bike we need? Like a small tutorial to get the H20s files by looking in the .bin.that would require a deeper (time consuming) understanding of the file format (other than the more or less blind scan that I invoked). Maybe I'll give it another try in 6 weeks or so.

> Again, if any help is needed such as doing boring and repeating tasks feel free to ask. I'll be happy to help in any way.You could support the "H2O idea" by creating your own bike001 (means another example_bike folder) and share it with others.

edit: sadly I've spoiled hex2obj_v23f.exe. Use it for 'Ride' only! (or better use v0.24)
I've fixed two H2O files, numbers 170 and 171. (170 to 178 should be moved from misc subfolder to mirrors_glass):



170_H2O.JPG (108.71 KiB) Viewed 429 times
## Post #18
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-07-31T08:56:58+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Are there any news on this? I've been dying to get my hands on some nice old and new bikes from this game. I can get models with Intel GPA, but they don't have UV and no texture extracted. A maxscript to import the models would solve everything, i guess.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-02T17:45:39+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

> Reply from REDZOEU
>
> A maxscript to import the models would solve everything, i guess.yeah, as simple as that!
But a maxscript has to be written before it can solve anything.  

If you sent me your preferred model (one sample only!) I could have a look at but I can't promiss anything.
I remember the first sample I converted to obj being very time consuming and time is growing more precious than I ever thought of.
(For RL concerns, of course.)
## Post #20
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-08-04T16:11:09+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

The last version of Ninja Ripper solves an old problem. Since then, we can finally rip the last Milestone's games   

However, importing the 3D in 3ds max is not easy, because all parts don't have the same UV coordinates so you have to import mesh one by one to check the UV. Some scaling on the unwrapping might be necessary too
## Post #21
- Username: SPIFR
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 19, 2019 3:00 am
- Post datetime: 2019-04-18T19:06:14+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Does any one know how to import textures in to the game (Ride 3). I see that there are textures of different types, but when i go to the page to do my own its limited on the graphics. i notice that there are bikes from others that have different graf but are not in the library provided.  

thanks: SPIFR
## Post #22
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2019-10-14T12:34:58+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Hi ALL! Can i ask would this method work on Sebastien Loeb EVO Rally? its not the best of games, but has a few choice cars id like hands on, it seems the .mix format changed but aside of that i have no ideas. Any help is helpful
## Post #23
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-10-29T01:26:38+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Hello shakotay2,Could you help me apply the textures to the 3d model of game ride in 3ds max or blender ?
I extracted the model with the ninja ripper,but I can't apply the textures.
the textures don't appear on the model, could you help me? 
i exported in 3ds max the 3d model for obj
so i imported the 3d model in 3ds max and blender
but I couldn't apply the textures
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-29T10:16:58+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

> Reply from vanilla1 ↑Tue Oct 29, 2019 9:26 am at Tue Oct 29, 2019 9:26 am
>
> I extracted the model with the ninja ripper,but I can't apply the textures.Sometimes nr doesn't create correct uv data, afair.
You can't apply textures without having uv data, as simple as that.
## Post #25
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-10-29T23:10:41+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

shakotay2,I can't find hex2obj_0.23 g .exe to download, can you help me?
I found only the zipped version 0.22
## Post #26
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2019-10-29T23:19:31+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

friend, doing the step by step, that you put here on xentax May 7th, 2015 I will be able to extract the 3d models?
thank you very much..
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-30T08:59:51+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

> Reply from vanilla1 ↑Wed Oct 30, 2019 7:10 am at Wed Oct 30, 2019 7:10 am
>
> 
shakotay2,I can't find hex2obj_0.23 g .exe to download, can you help me?
I found only the zipped version 0.22last version should do (view link in my sig).

> Reply from vanilla1 ↑Wed Oct 30, 2019 7:19 am at Wed Oct 30, 2019 7:19 am
>
> 
friend, doing the step by step, that you put here on xentax May 7th, 2015 I will be able to extract the 3d models?
thank you very much..Should work for BIKE001.BIN, and only for this model.
## Post #28
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2020-06-20T06:43:19+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Hi all, i was wrong about Sebastien Loeb Evo Rally.. the MIX format did not change, however the .bin file inside, gives errors when importing to 3ds max.

MAXSCRIPT MACROSCRIPT ERROR EXCEPTION
--No "">"" function for undefined.

i include an example (extracted .mix) .bin and .bml files and textures. 
[https://mega.nz/file/Hxdg3aKC#K9tPVM3SP ... C227V2xt2M](https://mega.nz/file/Hxdg3aKC#K9tPVM3SPfprYH6DK71o9uo0T-qAjxB9dC227V2xt2M)

this is as far as i got before i hit the import error. Can one of you take a look and give me a few pointers please? 
Any help would be massively appreciated.
## Post #29
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2021-06-29T02:34:03+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

that work on sebastian loeb game?
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-29T11:26:51+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Obviously not - or did I miss something?  

What usually works is own research, especially for formats where only few people are interested in.
(I checked it from a quick glance only so don't blame me if the parameters are not correct.)
.



CAR551-BIN.png (110.9 KiB) Viewed 109 times



Yeah, obviously I'm obsessed by this 3D format. 

```
  2  0x10d0 2 cockpit_l@Car551
  3  0x114a 3 cockpit_n@Car551
  4  0x11c4 4 dirt_n@Car551
  5  0x123b 5 Dirt@Car551
  6  0x12b0 6 inner_glass_l@Car551
  7  0x132e 7 paint_n@Car551
  8  0x13a6 8 rim_dirt_m@Car551
  9  0x1421 9 flat_black@Car551
  a  0x149c 10 chassis_l@Car551
  b  0x1516 11 dirt_mask@Car551
  c  0x1590 12 chassis_scratch_n@Car551
  d  0x1612 13 rim_dirt_blur_m@Car551
  e  0x1692 14 tyre_d@Car551
  f  0x1709 15 tyre_blur_d@Car551
 10  0x1785 16 tyre_l@Car551
 11  0x17fc 17 tyre_dirt_m@Car551
 12  0x1878 18 tyre_blur_n@Car551
 13  0x18f4 19 tyre_blur_l@Car551
 14  0x1970 20 tyre_n@Car551
 15  0x19e7 21 tyre_dirt_blur_m@Car551
 16  0x1a68 22 gauge_fake_d@Car551
 17  0x1ae5 23 gauge_fake_inc@Car551
 18  0x1b64 24 engine_d@Car551
 19  0x1bdd 25 engine_n@Car551
 1a  0x1c56 26 engine_l@Car551
 1b  0x1ccf 27 glass_d@Car551
 1c  0x1d47 28 glass_broke_n@Car551
 1d  0x1dc5 29 flat_n@Car551
 1e  0x1e3c 30 glass_l@Car551
 1f  0x1eb4 31 glass_dirt_mask@Car551
 20  0x1f34 32 inner_glass_d@Car551
 21  0x1fb2 33 chassis_d@Car551
 22  0x202c 34 glasslight_d@Car551
 23  0x20a9 35 glasslight_l@Car551
 24  0x2126 36 headlight_d@Car551
 25  0x21a2 37 headlight_i@Car551
 26  0x221e 38 headlight_l@Car551
 27  0x229a 39 headlight_n@Car551
 28  0x2316 40 noc_glass_d@Car551
 29  0x2392 41 noc_glass_l@Car551
 2a  0x240e 42 noc_group_lights_d@Car551
 2b  0x2491 43 noc_group_lights_inc@Car551
 2c  0x2516 44 noc_group_lights_l@Car551
 2d  0x2599 45 noc_group_lights_n@Car551
 2e  0x261c 46 rim_g_blur_d@Car551
 2f  0x2699 47 rim_g_blur_l@Car551
 30  0x2716 48 rim_g_blur_n@Car551
 31  0x2793 49 rim_g_d@Car551
 32  0x280b 50 rim_g_l@Car551
 33  0x2883 51 rim_g_n@Car551
 34  0x28fb 52 rim_s_blur_d@Car551
 35  0x2978 53 rim_s_blur_l@Car551
 36  0x29f5 54 rim_s_blur_n@Car551
 37  0x2a72 55 rim_s_d@Car551
 38  0x2aea 56 rim_s_l@Car551
 39  0x2b62 57 rim_s_n@Car551
 3a  0x2bda 58 rim_t_blur_d@Car551
 3b  0x2c57 59 rim_t_blur_l@Car551
 3c  0x2cd4 60 rim_t_blur_n@Car551
 3d  0x2d51 61 rim_t_d@Car551
 3e  0x2dc9 62 rim_t_l@Car551
 3f  0x2e41 63 rim_t_n@Car551
 40  0x2eb9 64 steering_wheel_d@Car551
 41  0x2f3a 65 steering_wheel_l@Car551
  0  0x1cb49 66 b_rim_ext_g#rim_tarmac_loda@Car551
  0  0x80c2c 67 b_rim_ext_g_blur#rim_tarmac_blur_loda@Car551
  0  0x8150c 68 b_rim_ext_s#rim_tarmac_loda@Car551
  0  0x833ea 69 b_rim_ext_s_blur#rim_tarmac_blur_loda@Car551
  0  0x83cca 70 b_rim_ext_t#rim_tarmac_loda@Car551
  0  0x85ba8 71 b_rim_ext_t_blur#rim_tarmac_blur_loda@Car551
  2  0x86488 72 bl_grid_chassis#car_alpha_loda@Car551 <- this relates to the point cloud in the picture above
  
  2  0x405bc2 73 bl_grid_chassis#car_alpha_lodb@Car551
  2  0x405d63 74 br_grid_chassis#car_alpha_loda@Car551
  2  0x405f34 75 br_grid_chassis#car_alpha_lodb@Car551
  2  0x4060d5 76 f_grid_bumper#car_alpha_loda@Car551
  2  0x4062e0 77 f_grid_bumper#car_alpha_lodb@Car551
  0  0x406473 78 f_rim_ext_g#rim_tarmac_loda@Car551
  0  0x408351 79 f_rim_ext_g_blur#rim_tarmac_blur_loda@Car551
  0  0x408c31 80 f_rim_ext_s#rim_tarmac_loda@Car551
  0  0x40ab0f 81 f_rim_ext_s_blur#rim_tarmac_blur_loda@Car551
  0  0x40b3ef 82 f_rim_ext_t#rim_tarmac_loda@Car551
  0  0x40d2cd 83 f_rim_ext_t_blur#rim_tarmac_blur_loda@Car551
  2  0x40dbad 84 fl_grid_chassis#car_alpha_loda@Car551
  2  0x40dd2a 85 fl_grid_chassis#car_alpha_lodb@Car551
  0  0x40dea7 86 fl_lightglass_whole#f_light_loda@Car551
  0  0x4130f8 87 fl_lightglass_whole#f_light_lodb@Car551
  2  0x417fe5 88 fr_grid_chassis#car_alpha_loda@Car551
  2  0x418162 89 fr_grid_chassis#car_alpha_lodb@Car551
  0  0x4182df 90 fr_lightglass_whole#f_light_loda@Car551
  0  0x41d530 91 fr_lightglass_whole#f_light_lodb@Car551
  2  0x42241d 92 grid_boot#car_alpha_loda@Car551
  2  0x4227bc 93 grid_boot#car_alpha_lodb@Car551
  0  0x422a23 94 l_lightglass_boot_whole#car_alpha_loda@Car551
  0  0x424956 95 l_lightglass_boot_whole#car_alpha_lodb@Car551
  2  0x425c93 96 noc_group_glass#noc_group_glass@Car551
  0  0x425eb9 97 r_lightglass_boot_whole#car_alpha_loda@Car551
  0  0x427dec 98 r_lightglass_boot_whole#car_alpha_lodb@Car551
  2  0x429129 99 chassis#chassis_loda@Car551
  2  0x5a4456 100 chassis#cockpit_loda@Car551
  2  0x6b96f5 101 chassis#dashboard_loda@Car551
  2  0x6c43ae 102 chassis#chassis_lodb@Car551
  2  0x7dadcd 103 chassis#chassis_lodc@Car551
  2  0x831cf8 104 gearstick#cockpit_loda@Car551
  2  0x9d76ce 105 gearstick#chassis_lodb@Car551
  2  0x9d7a65 106 handbrake#cockpit_loda@Car551
  2  0x9d877a 107 handbrake#chassis_lodb@Car551
  2  0x9d8997 108 l_door#chassis_loda@Car551
  2  0x9e78fa 109 l_door#cockpit_loda@Car551
  2  0xa05db7 110 l_door#chassis_lodb@Car551
  2  0xa133ea 111 l_door#chassis_lodc@Car551
  2  0xa1a0b5 112 r_door#chassis_loda@Car551
  2  0xa28fd4 113 r_door#cockpit_loda@Car551
  2  0xa47429 114 r_door#chassis_lodb@Car551
  2  0xa5490c 115 r_door#chassis_lodc@Car551
  2  0xa5b4bf 116 steering_wheel#stering_wheel_loda@Car551
  2  0xa5f3ef 117 steering_wheel#chassis_lodb@Car551
  0  0xa5fc65 118 b_rim_g#rim_tarmac_loda@Car551
  0  0xa6046b 119 b_rim_s#rim_tarmac_loda@Car551
  0  0xa60c71 120 b_rim_t#rim_tarmac_loda@Car551
  2  0xa61477 121 b_wheel_g#wheel_gravel_loda@Car551
  2  0xa62851 122 b_wheel_s#wheel_snow_loda@Car551
  2  0xa63c29 123 b_wheel_t#wheel_tarmac_loda@Car551
  2  0xa65003 124 b_wheel_w#wheel_tarmac_loda@Car551
  2  0xa663dd 125 boot#chassis_loda@Car551
  2  0xab4b06 126 boot#chassis_lodb@Car551
  2  0xae3653 127 boot#chassis_lodc@Car551
  2  0xafa4f0 128 discbrake#discbrake_loda@Car551
  2  0xbfdc4c 129 discbrake#discbrake_lodb@Car551
  2  0xbff263 130 display#display@Car551
  2  0xc00a8e 131 engine#engine_loda@Car551
  2  0xc05dad 132 engine#engine_lodb@Car551
  2  0xc07da2 133 f_bumper#chassis_loda@Car551
  2  0xc10edd 134 f_bumper#chassis_lodb@Car551
  2  0xc16998 135 f_bumper#chassis_lodc@Car551
  2  0xc18e83 136 f_glass#car_glass_wipers_loda@Car551
  2  0xc1f070 137 f_glass#car_alpha_lodb@Car551
  2  0xc1f581 138 f_glass#car_alpha_lodc@Car551
  0  0xc1f876 139 f_rim_g#rim_tarmac_loda@Car551
  0  0xc2007c 140 f_rim_s#rim_tarmac_loda@Car551
  0  0xc20882 141 f_rim_t#rim_tarmac_loda@Car551
  2  0xc21088 142 f_wheel_g#wheel_gravel_loda@Car551
  2  0xc22462 143 f_wheel_s#wheel_snow_loda@Car551
  2  0xc2383a 144 f_wheel_t#wheel_tarmac_loda@Car551
  2  0xc24c14 145 f_wheel_w#wheel_tarmac_loda@Car551
  0  0xc25fee 146 glass_boot#car_alpha_loda@Car551
  0  0xc6cbf7 147 glass_boot#car_alpha_lodb@Car551
  2  0xc6d657 148 inner_glass#inner_glass@Car551
  0  0xc6dc65 149 l_glass#car_alpha_loda@Car551
  0  0xc6eaa0 150 l_glass#car_alpha_lodb@Car551
  2  0xc6f5e1 151 l_glass_mirror#mirrors_loda@Car551
  2  0xc6f7c7 152 l_mirror#chassis_loda@Car551
  2  0xc705fb 153 l_mirror#chassis_lodb@Car551
  2  0xc70d1b 154 l_mirror#chassis_lodc@Car551
  2  0xc71087 155 light#light_loda@Car551
  2  0xc8f904 156 light#light_lodb@Car551
  2  0xca2e09 157 light_boot#light_loda@Car551
  2  0xca4c75 158 light_boot#light_lodb@Car551
  2  0xca5c95 159 noc_group_lights#noc_group_lights@Car551
  2  0xca63b5 160 null_bl_wheelposition#bones@Car551
  2  0xca6740 161 null_br_wheelposition#bones@Car551
  2  0xca68d2 162 null_fl_wheelposition#bones@Car551
  2  0xca6a64 163 null_fr_wheelposition#bones@Car551
  0  0xca6bf6 164 r_glass#car_alpha_loda@Car551
  0  0xca7a31 165 r_glass#car_alpha_lodb@Car551
  2  0xca8572 166 shadow_roof#stering_wheel@Car551
  2  0xca8702 167 suspension#car_skin_nor_loda@Car551
  2  0xcb295d 168 suspension#car_skin_nor_lodb@Car551

# 168 names

```
## Post #31
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-07-14T03:49:21+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Is this the same type of .bin as the bike001.bin?

.bin file:[https://www.mediafire.com/file/0t8sl1wx ... S.rar/file](https://www.mediafire.com/file/0t8sl1wxfxghsnz/BIKES.rar/file) (allbikes.bin from Milestone's sbk 07 PSP)
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-14T12:48:30+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

I have no idea, BIKE001.BIN starts with signature "GARCHIVE" while ALLBIKES.BIN does not.
## Post #33
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-07-15T01:30:47+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Can you unpack or see what's inside the allbikes.bin?
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-15T10:06:05+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Chunks of low poly sub meshes? Little bit tedious/not very interesting (I may be wrong, though).
.



allbikes-bin-1.png (67.31 KiB) Viewed 71 times
## Post #35
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-07-15T10:50:53+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

Yes, it's low poly, also as far as I know there's multiple bike models in there (7), model format is .slf and the texture format is .sli or .txs
## Post #36
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-07-15T10:59:29+00:00
- Post Title: Re: Ride (by Milestone) .BIN format

I'm trying to swap the models with the one from MotoGP 08 ps2, which had the same format (.slf), but isn't compressed in .bin
