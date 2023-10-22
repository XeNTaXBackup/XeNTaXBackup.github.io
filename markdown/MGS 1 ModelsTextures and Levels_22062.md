## Post #1
- Username: Sseast
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 25, 2020 11:19 pm
- Post datetime: 2020-04-25T15:51:26+00:00
- Post Title: MGS 1 Models/Textures and Levels

Hello everyone,

I have been trying for the past 3 days to extract those files, without success regarding models and levels.

I've downloaded around 12 versions of MGS, Gamecube, PC, Playstation...

and no matter what .DAT file I open with Konami DAT utility, it fails,statting that "This is not a compatible dat file"


Then I've tried to use GzsTool to open thoses .DAT file, but here again it fails, Command Prompt closes as soon as it opens and no files are produce during this milisecond.

So I cloned the Git repository, built my own .exe tool and same thing goes.

Even tried with every release of the repository that existed but same result.

In despair I started to recreate from scratch that level where Meryl gets shot using Maya, but texturing is a mess it would be so much easier otherwise.



Can anyone help ?

Thank you
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-25T16:26:08+00:00
- Post Title: MGS 1 Models/Textures and Levels

one or two .dat samples?

(In case it's a matter of a changed "file encyption key" you're lost, I fear.)
## Post #3
- Username: Sseast
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 25, 2020 11:19 pm
- Post datetime: 2020-04-25T17:22:54+00:00
- Post Title: MGS 1 Models/Textures and Levels

Well apparently many people seems to have succeeded, I hope it is still possible   

FACE.DAT
BRF.DAT
RADIO.DAT
[https://gofile.io/?c=YQ78iQ](https://gofile.io/?c=YQ78iQ)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-25T18:01:26+00:00
- Post Title: MGS 1 Models/Textures and Levels

Thanks! Well, seems it reads a filecount at offset 0x00000008, xored with xorMask2 = 0x11C22050.
Gives a funny high number!  

First 8 (or 16) bytes of your .dat files don't seem to have the same structure - so not surprising that the tool can't handle them.

Seems you need  any .dat file that can be handled by the GZStool.
Only then there's a chance to compare to your uploaded .dat files.

> Reply from Sseast ↑Sun Apr 26, 2020 1:22 am at Sun Apr 26, 2020 1:22 am
>
> 
Well apparently many people seems to have succeeded, I hope it is still possibleAny chance to get a .dat file they used?
## Post #5
- Username: Sseast
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 25, 2020 11:19 pm
- Post datetime: 2020-04-25T18:26:17+00:00
- Post Title: MGS 1 Models/Textures and Levels

Then I'll try to put my hands on other .DAT files.

> Reply from shakotay2 ↑Sun Apr 26, 2020 2:01 am at Sun Apr 26, 2020 2:01 am
>
> Any chance to get a .dat file they used?

Unfortunately many forums links are cleaned or expired by now, I'll have to keep digging   

Thanks for your help.

If anyone has heard about another .dat file opener or method, don't hesitate to reach me, I'd love to make a diorama out of mgs, I did it for halflife, such a pleasure  



mansion2.jpg (50.76 KiB) Viewed 184 times
## Post #6
- Username: Sseast
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 25, 2020 11:19 pm
- Post datetime: 2020-04-27T09:23:44+00:00
- Post Title: MGS 1 Models/Textures and Levels

I finally suceeded   , I stopped trying with the .dat file, instead I tried with the .mgz file created after MGS setup.

[](https://www.casimages.com/i/200427113503316566.png.html)

Inside, there were .kmd files that I then converted to .obj using [http://secaproject.com/kmd2obj_2_51](http://secaproject.com/kmd2obj_2_51)

I also found the textures files contained inside which were .pcx that I batch converted to .png using IrfanView (.pcx files where contained inside a .dar file, opened using unmassw_092.exe).

But the textures name don't seem to match and I end up with untextured model   

On one hand, .pcx textures files name are very explicit and seem normal :
- m03_wc_flo1 (m probably stands for material, 03 for level 3 then wc floor.
- m3r_path_door1
- m3r_tu_wall2
...

But the .obj textures filenames looks jamed, I am not sure if it is caused by the converter but there is definitly something off :

```
usemtl Material_00a_2018
f 3/3/1 2/2/1 1/1/1 4/4/1
f 5/7/1 3/6/1 4/5/1 6/8/1

```


usemtl Material_00a_2018 doesn't ressemble to the naming system by .pcx texture files

So before I try to mannually repath over 300 textures, did anyone ever encounter this kind of issue ?

Here's an upload if someone is up to investigate   
[http://www.mediafire.com/folder/mbmpa8l ... 6r9/shared](http://www.mediafire.com/folder/mbmpa8lbity7uyz,ybduqtusi1mr6r0,7lmytrdb3buo3ic,lz8huc0lsh4y7of,4j7prpfy4yip6r9/shared)

Edit : 

Even the .mtl file refers to an unkwnown naming system/file :

```
Ns 10.000002
Ka 1.000000 1.000000 1.000000
Kd 0.005000 0.559000 0.034000
Ks 0.000000 0.000000 0.000000
Ke 0.000000 0.000000 0.000000
Ni 1.450000
d 1.000000
illum 1
map_Kd 03b\\0153.png
```
## Post #7
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-04-27T20:49:45+00:00
- Post Title: MGS 1 Models/Textures and Levels

Hello Sseast,
If you wait a bit before he release his tool, my friend Secaproject works on MGS in Blender:
[https://www.youtube.com/watch?v=zZ5XsHtazGY](https://www.youtube.com/watch?v=zZ5XsHtazGY)
The textures "names" are hashs, the real filenames are only on the PC version (MGSI).
Example: "m03_wc_flo1" = "8206"
## Post #8
- Username: Sseast
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 25, 2020 11:19 pm
- Post datetime: 2020-04-28T06:29:57+00:00
- Post Title: MGS 1 Models/Textures and Levels

Your friend is a bless, I love the tools he developped   

Well I think I'll be finished any time soon, but I'd definitely take a look for other levels I'd like to work onto.

I am actually working through a mgsi folder, I've exctracted both textures/models using stage.mgz as I have no success with .dat

How did you know that 8206 = to m03_wc_flo1  ?

If you have a hash table to share, I'd be interested to have it too as I am repathing a little blindly 

Also, I noticed that there were polygons missing sometimes, not sure what is causing it but it requires doing some poly reconstruction and UV mapping, not so fantastic   

[](https://www.casimages.com/i/200428083906734481.png.html)
