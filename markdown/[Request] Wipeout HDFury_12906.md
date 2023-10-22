## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-05T00:30:09+00:00
- Post Title: [Request] Wipeout HD/Fury

I was wondering if someone could make a noesis plugin or maxscript for the Wipeout HD models.
The models are in *.rcsmodel files. Here is a ship from the demo
[https://www.dropbox.com/s/byn9zt17jl6ca ... s.zip?dl=0](https://www.dropbox.com/s/byn9zt17jl6cay5/icaras.zip?dl=0)

I can get the models easy enough with hex2obj, though some kind of importer would be great since the ships have quite a few submeshes.
Any help is greatly appreciated.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-05T11:15:23+00:00
- Post Title: [Request] Wipeout HD/Fury

ship.JPG (111.97 KiB) Viewed 278 times
## Post #3
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-05T12:41:27+00:00
- Post Title: [Request] Wipeout HD/Fury

Neat, I didn't know that was a thing. Slightly confusing though since I don't know too much about C, but I will try it out.
Thanks.
## Post #4
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-06T13:58:07+00:00
- Post Title: [Request] Wipeout HD/Fury

Alright i'm able to get the models now, but i'm still hoping for some kind of importer. 
The messes don't import at the proper places so those need manual adjusting and the meshes are ShortAll with HF UVs so manually fixing about 30+ objs is very time consuming.

I found 3 different vertex block types so far. 14, 18, and 22 with the UVs starting at 10, 14, and 18 respectively. 
there is also a header at the beginning of each mesh telling how many submeshes there are and where they start and such. It also looks like the it tells the number of meshes at 0x1c and going to the offset at 0x20 will show where each is located.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-06T16:29:16+00:00
- Post Title: [Request] Wipeout HD/Fury

> Reply from o0DemonBoy0o
>
> The messes don't import at the proper places so those need manual adjustingyeah, that's "messing"  
Does it apply to all submeshes of a spaceship?

> the meshes are ShortAll with HF UVs so manually fixing about 30+ objs is very time consuming.I've PMed you a quickhacked version that should handle this.

btw: there's vertex count and face indices count, too. Would make sense to create a Make_H2O project of it.
But the positioning problem has to be solved before...
## Post #6
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-06T16:46:12+00:00
- Post Title: [Request] Wipeout HD/Fury

Thanks, it works great.

An object and it's submeshes will all fit together, but the next object and meshes need adjusting to fit with the others.
It's kind of annoying finding out the exact placement of each object especially the underside of the ship.

Here is another ship and all the h2o files for it, if it's of any use.
[https://www.dropbox.com/s/gnzz20a1qfi5n ... r.zip?dl=0](https://www.dropbox.com/s/gnzz20a1qfi5nzs/Feisar.zip?dl=0)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-06T17:34:32+00:00
- Post Title: [Request] Wipeout HD/Fury

> Reply from o0DemonBoy0o
>
> Thanks, it works great.yeah, that's true.  
Tried out your Feisar H2Os with File/SaveAs Mmesh (version 0.24x required)
then used load_multi_obj_blender2.49.py from the Make_H2O project to load all created obj files at once.

> An object and it's submeshes will all fit together, but the next object and meshes need adjusting to fit with the others.
Could you explain what is an "object" and what are the "submeshes" for Feisar, please?
(in "Feisar" model the pattern 83xx1010101010 to be found 41x, but only 33 H2Os?)
edit: upps, used wrong ship.rcsmodel, it's 33 for "Feisar"

> It's kind of annoying finding out the exact placement of each object especially the underside of the ship.
Maybe there's a hierarchy with relative coordinates?

btw: for the Feisar the placing doesn't seem to look too bad, does it?
ok, well, see, the pilot's too deep and the cabin, that's not nice...
## Post #8
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-06T18:11:53+00:00
- Post Title: [Request] Wipeout HD/Fury

> Reply from shakotay2
>
> 
Could you explain what is an "object" and what are the "submeshes" for Feisar, please?
Feisar has 17 objects.
h2o 0 is object 1
1 is object 2
2 is object 3
3 is object 4
4-5 is object 5
6-7 is object 6
8-11 is object 7
12 is object 8
13 is object 9
14-20 is object 10
21 is object 11
22 is object 12
23 is object 13
24-26 is object 14
27 is object 15
28 is object 16
29-32 is object 17

> ok, well, see, the pilot's too deep and the cabin, that's not nice...
Yeah, it's like the for every ship it seems. The stages use the same model format too, but I can't imagine having fix the placement of every mesh for that.

Edit: Seems i was wrong about the data a couple posts ago? The more I look at it the more I get confused.
In Feisar's ship model it says that there are only 14 objects but I found 17?

Each object starts with 
00 00 00 ?? 00 00 00 00 FF FF FF FF 00 00 00 00
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-06T19:31:00+00:00
- Post Title: [Request] Wipeout HD/Fury

> Reply from o0DemonBoy0o
>
> Feisar has 17 objects.thx! (I'll look at this after "the game is over" - Barca versa Juve)

> Edit: Seems i was wrong about the data a couple posts ago? The more I look at it the more I get confused.
>
> In Feisar's ship model it says that there are only 14 objects but I found 17?Who is "it"?  

Don't worry. Seems I'd 41 founds in your first model upload (they're all called "ship.rcsmodel", damned)

I've started a Make_H2O project and this is the first result for the "Feisar":
(some counts are little bit different to the ones in your H2Os)
v: 344, FI: 702, 1230
v: 344, FI: 702, 3610
v: 232, FI: 714, 5a10
v: 472, FI: 1056, 7130
v: 1264, FI: 4455, 9c50
v: 496, FI: 1083, f530
v: 1256, FI: 4749, 14510
v: 192, FI: 621, 19d60
v: 1256, FI: 4641, 1d7f0
v: 1312, FI: 2229, 23040
v: 1304, FI: 2721, 28c80
v: 912, FI: 1791, 2e830
v: 160, FI: 558, 38290
v: 72, FI: 144, 390f0
v: 1256, FI: 4542, 39c80
v: 1264, FI: 4257, 3f4d0
v: 1296, FI: 2976, 44db0
v: 1296, FI: 3150, 4a8d0
v: 1288, FI: 3222, 503e0
v: 1296, FI: 3084, 55e70
v: 384, FI: 1410, 5b990
v: 280, FI: 1098, 68820
v: 64, FI: 192, 6a100
v: 528, FI: 1443, 6a810
v: 1224, FI: 3384, 6dae0
v: 1248, FI: 2406, 74410
v: 256, FI: 621, 7af30
v: 168, FI: 561, 7f8c0
v: 40, FI: 51, 80a00
v: 1304, FI: 2607, 80f00
v: 1296, FI: 3093, 86a90
v: 1312, FI: 2202, 8c5b0
v: 552, FI: 1116, 921e0

 assumed magic tables: 33
(searching for 83 xx 10 10 10 10 10 00 )
## Post #10
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-07T01:40:20+00:00
- Post Title: [Request] Wipeout HD/Fury

I meant the data in feisar's ship.rcsmodel

At offset 0x1C it has 0E and going to the address shown at 0x20 (0x500) it will show the start of 14 objects before going to some unknown values.





Maybe i'm wrong and it means something else.

there is also the 24 bytes of data at the end of each object like this

Not sure if that means anything
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-07T08:07:27+00:00
- Post Title: [Request] Wipeout HD/Fury

> Reply from o0DemonBoy0o
>
> Maybe i'm wrong and it means something else.Don't think so. Great find!
From the table at 0x500 it looks like there are 14 objects:

```
 1 v: 344, FI. 702, 3610
 2 v: 232, FI. 714, 5a10
 3 v: 472, FI. 1056, 7130
 4 v: 1264, FI. 4455, 9c50
	v: 496, FI. 1083, f530
 6 v: 1256, FI. 4749, 14510
	v: 192, FI. 621, 19d60
 8 v: 1256, FI. 4641, 1d7f0
	v: 1312, FI. 2229, 23040
	v: 1304, FI. 2721, 28c80
	v: 912, FI. 1791, 2e830
12 v: 160, FI. 558, 38290        obj 8
	v: 72, FI. 144, 390f0
14 v: 1256, FI. 4542, 39c80      obj 9
	v: 1264, FI. 4257, 3f4d0
	v: 1296, FI. 2976, 44db0
	v: 1296, FI. 3150, 4a8d0
	v: 1288, FI. 3222, 503e0
	v: 1296, FI. 3084, 55e70
	v: 384, FI. 1410, 5b990
21 v: 280, FI. 1098, 68820       obj 10
	v: 64, FI. 192, 6a100
23 v: 528, FI. 1443, 6a810	    obj 11
24 v: 1224, FI. 3384, 6dae0	   obj 12
	v: 1248, FI. 2406, 74410
	v: 256, FI. 621, 7af30
	v: 168, FI. 561, 7f8c0
28 v: 40, FI. 51, 80a00		    obj 13
29 v: 1304, FI. 2607, 80f00	   obj 14
	v: 1296, FI. 3093, 86a90
	v: 1312, FI. 2202, 8c5b0
	v: 552, FI. 1116, 921e0
```


> there is also the 24[h] bytes of data at the end of each object like thisMaybe it's the translation/rotation offsets we're missing, it's 8 floats and a DW (startaddress of object's header).

Still missing: type identifier of vertex blocks (i.e. FVF, flexible vertex format)

Maybe at header offset 0x61: 0x20: 18/14
0x40: 22/18
0x80: 14/10 (just a wild guess)

edit: nope, doesn't work for 21.H2O, for example
## Post #12
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-07T09:41:28+00:00
- Post Title: [Request] Wipeout HD/Fury

This bit after the start of each object might be it


09 C0 = A VB size of 22
0A 50 = 18
0A E0 = 14

it's matched up with everything i looked at so far.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-07T11:19:01+00:00
- Post Title: [Request] Wipeout HD/Fury

yep. When it's zero I used the previous type in Make_H2O 
It creates 33 H2Os automatically.

Sadly the vertex counts differ by 3 or 4 from the correct ones (which are in your uploaded H2Os).
Any ideas?
## Post #14
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-07T12:46:20+00:00
- Post Title: [Request] Wipeout HD/Fury

From what I can tell, it has something to do with the extra 00s at the end of the meshes vertex data.



Maybe the verticies in the header of the object is rounded up depending on the VB size and the number of extra 00s at the end of the vertex data?
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-07T12:55:14+00:00
- Post Title: [Request] Wipeout HD/Fury

yeah, data alignment is a feature of Make_H2O, but it doesn't work here.

I calculated (where FVFsize is former VBsize, and next_FIaddr is reduced back to address with first non zero byte)
vertexCount= (next_FIaddr - addrVerts) / FVFsize
but works for a few H2Os only:

0: CORRECTION vertex count (344->340) ok
1: CORRECTION vertex count (344->338) ok
2: CORRECTION vertex count (232->229) ok

4: CORRECTION vertex count (1264->1755)!  WRONG!
...
(correction wrong for 22 H2Os!)

Seems as if a correction is allowed/required for the last submesh of an object only.

So I have to deal with the object hierarchy. (Thought I was done without using it.)
Turns out to be an endless story again? (as always  )

well, guess I need one "simple" formulae only, but which?
The actual one gives this only:

2: CORRECTION vertex count (232->229)!
12: CORRECTION vertex count (160->155)!
21: CORRECTION vertex count (280->277)!

yeah, whole life is only a formulae   (S. Stallone)

0. -64, addrFI: 2f80, vStart: 1230 CORRECTION vertex count (344->340)!
1. -32, addrFI: 5380, vStart: 3610 CORRECTION vertex count (344->338)!
2. 32, addrFI: 6a80, vStart: 5a10 CORRECTION vertex count (232->229)!
3. 32, addrFI: 9280, vStart: 7130 no corr.
4. 8912, addrFI: 11800, vStart: 9c50 --
5. -16, addrFI: 11800, vStart: f530 CORRECTION vertex count (496->491)!
6. 3488, addrFI: 1ab00, vStart: 14510 --
7. 32, addrFI: 1ab00, vStart: 19d60 CORRECTION vertex count (192->188)!
8. 63424, addrFI: 32800, vStart: 1d7f0 --
9. 39808, addrFI: 32800, vStart: 23040 --
10. 16336, addrFI: 32800, vStart: 28c80 --
11. -80, addrFI: 32800, vStart: 2e830 CORRECTION vertex count (912->905)!
12. 48, addrFI: 38b80, vStart: 38290 CORRECTION vertex count (160->155)!
13. 96, addrFI: 39780, vStart: 390f0 no corr.
14. 122800, addrFI: 5d480, vStart: 39c80 --
15. 100048, addrFI: 5d480, vStart: 3f4d0 --
16. 76720, addrFI: 5d480, vStart: 44db0 --
17. 53392, addrFI: 5d480, vStart: 4a8d0 --
18. 30224, addrFI: 5d480, vStart: 503e0 --
19. 6896, addrFI: 5d480, vStart: 55e70 --
20. -16, addrFI: 5d480, vStart: 5b990 CORRECTION vertex count (384->377)!
21. 16, addrFI: 69780, vStart: 68820 CORRECTION vertex count (280->277)!
22. 0, addrFI: 6a580, vStart: 6a10023. 80, addrFI: 6cd80, vStart: 6a810 no corr.
24. 33136, addrFI: 7c580, vStart: 6dae0 --
25. 5680, addrFI: 7c580, vStart: 74410 --
26. 80, addrFI: 7c580, vStart: 7af30 no corr.
27. -16, addrFI: 80480, vStart: 7f8c0 CORRECTION vertex count (168->164)!
28. -48, addrFI: 80c00, vStart: 80a00 CORRECTION vertex count (40->33)!
29. 56784, addrFI: 94880, vStart: 80f00 --
30. 33488, addrFI: 94880, vStart: 86a90 --
31. 9872, addrFI: 94880, vStart: 8c5b0 --
32. -48, addrFI: 94880, vStart: 921e0 CORRECTION vertex count (552->549)!
## Post #16
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-07T13:47:43+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Well that's about as much as I can figure out. I can't think of anything else to try.
Hopefully this is all figured out soon as the models in this game are really nice looking.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-07T15:50:34+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

cool colors! Like it.

Here's a Make_H2O.exe for Wipeout - tested with Feisar only.
(As you know you'll need Hex2obj_0.24x.exe for correct uvs.)


 Make_H2O-Wipeout.zip
(86.63 KiB) Downloaded 78 times


Four H2Os are corrected by Hex2obj and the resulting obj files renamed to .objx.
Simply rename them back to .obj. (Too tired to check that problem.)

(Read the How-to-use file!)

edit: seems to work with Feisar only. Other model was displayed, well, "§$%&!

Main issue seems to be that the FVF type isn't recognized correctly, since 0AE0 refers
to a FVF (VB) size of 18 instead of 14 for the other model. (made a 2nd exe for the 'other' models)

Another one is a superfluous FI start address spoiling the order. edit: done
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-07T20:30:14+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

the sample from the first post:



other.JPG (82.59 KiB) Viewed 529 times


H2O files:
[http://www.uploadmb.com/dw.php?id=1433708887](http://www.uploadmb.com/dw.php?id=1433708887)

use them with hex2obj as explained in attachment of previous post.
(rename .objx to .obj)
## Post #19
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-06-07T23:37:29+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Thanks.
The only other thing I can think of is maybe the ship.vex file. It looks like it has information on bones as well as the objects.

Here is the one for Feisar to look at.
[https://www.dropbox.com/s/3ms8wjpec9eo0ad/ship.vex?dl=0](https://www.dropbox.com/s/3ms8wjpec9eo0ad/ship.vex?dl=0)


Edit:
The program works great and saves a bit of time, though sometimes it will get the start of faces wrong.
In another model I tested it had the start of faces as 0x25c40 instead of 0x26300
I'm guessing it searches for 00 00 00 01 00 02 instead of going to the offset here?



Just something I thought I would point out.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-08T08:34:24+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from o0DemonBoy0o
>
> [...]and saves a bit of timea bit?  
Seems you've got a faster method for these corrections by Make_H2O:

```
1. 196496, last addrFI (act.): 3c580 (3c580), vStart: 6c80 --
2. 173312, last addrFI (act.): 3c580 (3e400), vStart: c5f0 --
3. 150752, last addrFI (act.): 3c580 (3ff80), vStart: 12050 --
4. 127280, last addrFI (act.): 3c580 (42400), vStart: 178a0 --
5. 103808, last addrFI (act.): 3c580 (43980), vStart: 1d450 --
6. 80624, last addrFI (act.): 3c580 (44e00), vStart: 23000 --
7. 57440, last addrFI (act.): 3c580 (46900), vStart: 28a90 --
8. 33984, last addrFI (act.): 3c580 (48480), vStart: 2e510 --
9. 10368, last addrFI (act.): 3c580 (49a00), vStart: 340c0 --
10. 16, last addrFI (act.): 3c580 (4ac80), vStart: 39cf0 CORRECTION vertex count (576->571)!
11. -48, last addrFI (act.): 4bd80 (4bd80), vStart: 4b5d0 CORRECTION vertex count (144->138)!
12. -32, last addrFI (act.): 4c300 (4c300), vStart: 4c050 CORRECTION vertex count (40->36)!
13. 7136, last addrFI (act.): 53a00 (53a00), vStart: 4c540 --
14. -64, last addrFI (act.): 53a00 (55c00), vStart: 51e20 CORRECTION vertex count (400->396)!
15. 32, last addrFI (act.): 57200 (57200), vStart: 564c0 CORRECTION vertex count (240->234)!
16. 80, last addrFI (act.): 57c80 (57c80), vStart: 57a20 no corr.
17. 32, last addrFI (act.): 57f00 (57f00), vStart: 57dc0 no corr.
18. 64, last addrFI (act.): 5b500 (5b500), vStart: 58070 CORRECTION vertex count (744->742)!
19. 32, last addrFI (act.): 5ee80 (5ee80), vStart: 5c940 CORRECTION vertex count (528->525)!
20. 16, last addrFI (act.): 64f80 (64f80), vStart: 5fae0 CORRECTION vertex count (984->980)!
21. 39456, last addrFI (act.): 75500 (75500), vStart: 65fc0 --
22. 15984, last addrFI (act.): 75500 (76b80), vStart: 6bae0 --
23. 0, last addrFI (act.): 75500 (78000), vStart: 71690 CORRECTION vertex count (888->887)!
24. 48272, last addrFI (act.): 8a600 (8a600), vStart: 78ee0 --
25. 24800, last addrFI (act.): 8a600 (8bf80), vStart: 7e970 --
26. 1472, last addrFI (act.): 8a600 (8d480), vStart: 84520 --
27. -80, last addrFI (act.): 8a600 (8ec80), vStart: 8a020 CORRECTION vertex count (88->83)!
28. 48, last addrFI (act.): 91880 (91880), vStart: 8ef40 CORRECTION vertex count (584->581)!
29. -32, last addrFI (act.): 92800 (92800), vStart: 92270 CORRECTION vertex count (104->98)!
30. 98768, last addrFI (act.): b1900 (b1900), vStart: 92ca0 --
31. 71152, last addrFI (act.): b1900 (b2f00), vStart: 99720 --
32. 43872, last addrFI (act.): b1900 (b4100), vStart: a0310 --
33. 16432, last addrFI (act.): b1900 (b5880), vStart: a6d90 --
34. -112, last addrFI (act.): b1900 (b6c80), vStart: ad8d0 CORRECTION vertex count (752->745)!
35. 112, last addrFI (act.): b9780 (b9780), vStart: b78d0 no corr.
36. 64, last addrFI (act.): bbb00 (bbb00), vStart: b9c80 no corr.
37. -64, last addrFI (act.): c0a00 (c0a00), vStart: bc000 CORRECTION vertex count (864->859)!
38. 41968, last addrFI (act.): d2b00 (d2b00), vStart: c1bd0 --
39. 14512, last addrFI (act.): d2b00 (d3e80), vStart: c8710 --
40. 80, last addrFI (act.): d2b00 (d5200), vStart: cf250 CORRECTION vertex count (656->654)!
```
(well, forgot about auto correction of hex2obj. Seems I've wasted time with the formulae...  )

> I'm guessing it searches for 00 00 00 01 00 02 instead of going to the offset here?yep. Updated the download link above.
## Post #21
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2015-06-12T12:21:05+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Always loved those wipeout model, nice guys !
## Post #22
- Username: modes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 05, 2011 11:18 am
- Post datetime: 2015-10-25T19:02:07+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

thanks for the infos

my problem is in the maxscript fast complet

problem next model of object in the maxscript.

problem ship pose for the objects.

shakotay2 thanks for the hexobj programm this programm is very very nice thanks  
[Zwischenablage01.jpg](https://xentaxbackup.github.io/file/9919_Zwischenablage01.jpg)
## Post #23
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-11-19T00:49:41+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Hey shakotay2, Make_H2O crashes on some of the ships. Here are a couple examples 
[https://www.dropbox.com/s/zwytulqqi5xpe ... s.zip?dl=0](https://www.dropbox.com/s/zwytulqqi5xpe21/ships.zip?dl=0)

I can't seem to find out why it crashes on these and not others.
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-19T21:14:02+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Hi o0DemonBoy0o,
thanks for reporting.
From a first glance I can see that for goteki.rcsmodel for example
a wrong FVFsize is chosen (18 instead of 22). (Despite the crash 15 H2O files are being created.)

Determining the type is a little bit confusing as you can see from this code snippet:

```
                    //case 0x0C00:
                case 0x09C0: strcpy(lines[2], "22 18") ; lastFVF= 22 ; break ;
                    //case 0x0AE0:
                case 0x0A50: strcpy(lines[2], "18 14") ; lastFVF= 18 ; break ;
                    //case 0x0B70:
                case 0x0AE0: strcpy(lines[2], "14 10") ; lastFVF= 14 ; break ;  // set to 0AE1 for 'other'
                case 0x0: break ;                                   // leave last type
                default: fprintf(stream, "ERROR with H2O%d: unknown FVFtype %x\n", cnt, FVFtype[cnt]) ;
            }
```

There's 3 possibilities to circumvent this:
 find the type byte in the model if any (very time consuming)
 let the customer choose manually from 14, 18, 22 (very ugly)
 find a cool formula (nice thing, not easy to invent, but my most preferred method)

ok, "a simple  formulae" thingie didn't work (vertex blocks of two submeshes glued together for example, weird)

So I decided to introduce a user editable parameterfile: WipeOut.txt- hope, you'll love it.  
There's a word flag I used to decide which FVFsize to use. Works in most cases.

For unknown FVFtypes a size of 18 is used as default (doesn't work always).

You may expand the WipeOut.txt by further entries.
But don't touch these three entries: 0xFF14, 0xFF18 and 0xFF22. NEVER.

From the pic you maybe can see that for triakis the flag 0x0a90 has to be added
in the 0xFF22 section (FVFtype=22)

because of this line in the MakeH2O_log.txt file:
> CHECK H2O14: unknown FVFtype a90
14. 1120, last addrFI       : 74200       , vStart: 72a80 (FVFsize: 18) --
(which had set a default FVFsize of 18 for unknown types, see above)



goteki.JPG (195.32 KiB) Viewed 405 times



Here's the WipeOut.txt from the zipped file:
0xFF14
0x08C0
0x0AE0
0x0AA0
0x1370
0xFF18
0x0000
0x0A10
0x0A50
0x1490
0xFF22
0x0980
0x09C0
0x0A90
0x1400

and here's the "special one" for triakis where the 0x0000 entry was moved:
0xFF14
0x08C0
0x0AE0
0x0AA0
0x1370
0xFF18
0x0A10
0x0A50
0x1490
0xFF22
0x0000
0x0980
0x09C0
0x0A90
0x1400

Not sure about the handling of 0x0000. Maybe using the FVFsize of the previous submesh in this case is the better choice?

(Did not check previous models with this exe version so keep that one from earlier in this thread.)
[Make_H2O-WipeOut.zip](http://www.uploadmb.com/dw.php?id=1447966225)

Watch out for objx files. Rename to .obj and adjust vertex count and/or FVFsize if required.

(Keep in mind that the concerning H2O file number can be found in the first line of an obj file created by hex2obj.)

(Use File/SaveAs Mmesh to create the obj files and the load_multi_obj_blender2.49.py (or...2.69.py) script to load them.)

And, as you know you'll need Hex2obj_0.24x.exe for correct uvs. Yeah, I know, that's totally ugly;
I'd like to make a max script for this in my next life...
## Post #25
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-11-21T21:51:09+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Thanks again. I think I might have found a solution for the FVFtype that seems to work on most if not all ships.

Looks like all we had to was not use those numbers as identifiers but go to that address itself. 
goteki for example, if you go 0x0980, 0x0a10, 0x0aa0, you will get XX 16, XX 12, and XX 0E which is thier FVFsize.
And yeah if it's 0x0000 the using the FVFsize of the previous submesh seems to work out just fine.

Also does Make_H2O have a limit on how many h2o files it can make? I wanted to try extracting a stage but those can have hundreds of meshes.
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-21T23:41:48+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from o0DemonBoy0o
>
> Thanks again. I think I might have found a solution for the FVFtype that seems to work on most if not all ships.

Looks like all we had to was not use those numbers as identifiers but go to that address itself.cool finding!
(Wish you had told me this before I introduced that awful WipeOut.txt file.  )

> Also does Make_H2O have a limit on how many h2o files it can make? I wanted to try extracting a stage but those can have hundreds of meshes.It's limited to 99 submeshes which I thought to be sufficient for normal models.
Guess 1999 submeshes would be enough for stages, won't it?
## Post #27
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-11-22T00:09:53+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

I just found that out today after looking though some of the models again.
I'm not sure why I didn't see it sooner. I've also seen model with FVFsizes of 10 and 26.
for 26 the UV pos is 22 but i'm not sure about 10.

As for the stages, the largest one has around 2630 submeshes.
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-22T12:05:45+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

new version of Make_H2O for Wipeout:
[Make_H2O_Wipeout.zip](http://www.uploadmb.com/dw.php?id=1448193741)

(untested: FVFsize:10, uv-pos:6; 26/22;
 maximum submesh count: 3000)

(Wipeout.txt isn't used anymore.)
## Post #29
- Username: modes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 05, 2011 11:18 am
- Post datetime: 2015-12-07T17:55:07+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

here is my maxscript not complett pleas help complette script.

thanks all  
[WHDF-test.rar](https://xentaxbackup.github.io/file/10129_WHDF-test.rar)
## Post #30
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2016-02-17T19:08:11+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Hi guys, first of all sorry if I revived an old post, today I was trying to extract the tracks from WHD Fury (moa therma) following your steps, but I ended with a pile of "garbage"    (I think i ended up with "this" because i didn't found the face index, or mb because is a big object with multiple meshes) so i ended up taking a little help and upload the track file asking for your good guidance.

And ty for your guide on how to do it with the feisar ship, so far i got it looking nice with quixel suite and i want to make a wipeout with UE4 for free to enjoy it on our pcs

Here is the rcsmodel file: [https://www.dropbox.com/s/t3bgnunlrgyse ... model?dl=0](https://www.dropbox.com/s/t3bgnunlrgyselh/track.rcsmodel?dl=0)
And here is the pic of the Livery 

[3b07f8fee0790cead3ee03459bd14e19.png](https://xentaxbackup.github.io/file/10501_3b07f8fee0790cead3ee03459bd14e19.png)
## Post #31
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2016-02-18T22:18:59+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from josema0890
>
> Hi guys, first of all sorry if I revived an old post, today I was trying to extract the tracks from WHD Fury (moa therma) following your steps, but I ended with a pile of "garbage"    (I think i ended up with "this" because i didn't found the face index, or mb because is a big object with multiple meshes) so i ended up taking a little help and upload the track file asking for your good guidance.

And ty for your guide on how to do it with the feisar ship, so far i got it looking nice with quixel suite and i want to make a wipeout with UE4 for free to enjoy it on our pcs

Here is the rcsmodel file: https://www.dropbox.com/s/t3bgnunlrgyse ... model?dl=0
And here is the pic of the Livery

Sorry for bumping the thread, but i think I have to make multiple h2O extracts and play with the fvf value in every case, cause i got some models looking pretty nice,plus I managed to extract the detonator ship, but is missing some faces on the bottom side (mb i need to use other value instead of 14 on the FVF?), so far so good is looking georgeous, now is time to work with the zone ship, and sorry for bumping the thread, but i need help with the track models
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-18T23:28:13+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Possible values for the FVFsize were 14, 18, 22 (and, untested: 10, 26), iirc.

I've never checked such a large model like track.rcsmodel.

Vaild obj files are 1 5 39 74 68 69 70 71 72 80 125 142 143 151 152 160 161 for example.
First line of track_160.obj reads:
# H2O parameter file: X:\..\tracks\track.rcsmodel_1141.h2o 
which you could  load seperately into Hex2obj_0,24c_WO.exe (contained in the Make_H2O zip for Wipeout only):



track_1141_H2O.JPG (41.93 KiB) Viewed 244 times



Spoiled submesh:
For track_246.obj the FVF size must be corrected from 18 to 22 (in track_rcsmodel_1219.H2O).

(This is clear to be seen if you check vertices at 0x7af5f0 in track.rcsmodel, The block ends at 0x7AF7FF.
Size 0x800-0x5F0= 528 dec. = 24 vertices x 22)

(If I have some spare time I maybe will check why it's wrongly set to 18.)
## Post #33
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2016-02-19T12:26:40+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

First, nice guys for the good work, keep it up !

Now, would be cool if we can get a Noesis script or something a bit easier to export (I mean a User-friendly one).

I'm starting to export wipeout things too, sadly, I don't know if it will be better to wait a little if some change gonna being made on the H20 wipeout export ?

And finally here a part of the ship loaded in webgl, you can clik the delivery button to switch the texture applied to the ship. (ps; I downsampled the texture to speed-up the loading process)

[http://gravitrek.com/forum/junkyard/wipeoutx/test.html](http://gravitrek.com/forum/junkyard/wipeoutx/test.html)

[](http://www.hostingpics.net/viewer.php?id=720679Sanstitre2.png)

For people interested by doing a remake/fangame of this Wipeout, you would be interested by this too: 

[https://docs.google.com/spreadsheets/d/ ... li=1#gid=0](https://docs.google.com/spreadsheets/d/1OuoR7FWMTvU9UcuJpfVS9bgF47rmG4GUMy_cM3JmbXA/edit?pref=2&pli=1#gid=0)
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-19T22:22:45+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from zaykho
>
> First, nice guys for the good work, keep it up !

Now, would be cool if we can get a Noesis script or something a bit easier to export (I mean a User-friendly one).
Coding "userfriendly" devours a lot of lifetime - so sry, no time for such.  
(Even if we had 500 instead of 16 interested people/downloaders here.)

> I'm starting to export wipeout things too, sadly, I don't know if it will be better to wait a little if some change gonna being made on the H20 wipeout export ?I'd vote for waiting a little...:



track_rcsmodel.JPG (82.71 KiB) Viewed 227 times
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-19T22:23:40+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

There's 676 obj renamed to objx. Read the former posts how to treat them.

Copy Make_H2O-Wipeout.exe to your unzipped Make_H2O-WipeOut folder (get zip from post as of Sun Nov 22, 2015 1:05 pm, read How-to-use_Wipeout.txt)

(Hex2obj_0.24d_WO.exe is a special version for Wipeout so don't use it for other games/models!)
Copy Hex2obj_0.24d_WO.exe to your hex2obj folder (view link in my sig to get the hex2obj basic zip).


 Make-WipeOut.zip
(229.96 KiB) Downloaded 41 times
## Post #36
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2016-02-20T00:09:50+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from shakotay2
>
> 
Coding "userfriendly" devours a lot of lifetime - so sry, no time for such.  
(Even if we had 500 instead of 16 interested people/downloaders here.)

No problem, I can understand it.   

> Reply from shakotay2
>
> I'd vote for waiting a little...:

Ok, well I will make test and see what is broken or not before doing full-rip. Thanks again for your work !

Thanks for the new Make-WipeOut, I will start testing map now.
## Post #37
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2016-02-22T19:16:30+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Well zaykho, to extract the track (not the buildings or ships), u can use the original maya files (most of the maya files that the devs used in the game, ships, tracks, billboards, etc) if you have an original copy of ps2 wipeout pulse, and extracting only the race track meshes (cause they are the same on all the versions (ps2,ps3 or psp) and then focus on the high-poly ps3 models from the ps3 version (building, race track bumps, all the environment and textures).

The path folder is this one: X:/PADZ2 (open it with winrar or 7zip, and woala)

Moatherma track PS2 version inside maya:
[https://i.gyazo.com/cf93b769455295f314c ... 2f0cb6.png](https://i.gyazo.com/cf93b769455295f314c8ff3f6a2f0cb6.png) (link cause img res is too big and f*ck up the theme)

Moatherma track PS2/PSP version with PS3 textures, testing out the mag shader on UE4:
[https://i.gyazo.com/d8849799fd11e70560c ... d02e74.mp4](https://i.gyazo.com/d8849799fd11e70560c827a1e0d02e74.mp4)

And thanks to shakotay2 and o0DemonBoy0o for working first on extracting the models from ps3 version, i got again the motivation to start again and finish it (that, and because i learned more things in ue4, now is time to focus on the physics coding)

EDIT: Yesterday night, I was thinking about the .rsc model and the PS2/PSP workflow of Studio Liverpool, so it came to my head if we are in front of a maya binary (or an .max/.fbx) file coded to be readable to ps3, so I was thinking if is a way to decrypt the file or maybe is harder to do than the H2O method.

Here is an image so you can see what i'm talking about: [http://i.imgur.com/TccGxnD.png](http://i.imgur.com/TccGxnD.png)
## Post #38
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2016-02-26T16:22:33+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Sorry if I didn't answered sooner, I was really busy.

So yes, thx for that info, I was already aware of the studio folder leak in the Wipeout pulse ps2 edition, long time ago a guy was talking about this in a blog.

I wasn't aware that the road of the track are the same in every editions, so thank you for that tips.

Still, we will need to work on most buildings, since yes, they are more high poly than the old versions. :p


> Reply from josema0890
>
> 
EDIT: Yesterday night, I was thinking about the .rsc model and the PS2/PSP workflow of Studio Liverpool, so it came to my head if we are in front of a maya binary (or an .max/.fbx) file coded to be readable to ps3, so I was thinking if is a way to decrypt the file or maybe is harder to do than the H2O method.

Here is an image so you can see what i'm talking about: http://i.imgur.com/TccGxnD.png

I don't know, but knowing that shakotay2 is pretty busy too, it would be better to stick to the H2O method.
## Post #39
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2016-02-27T03:27:36+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Well, i finally achieved to have an anti gravity system (with ag-sys ship   ) so far i tested it with the weird box that is under the ship and u can se that the collisions are fine, (i just selected all the track mesh from the maya file, and use complex collision on ue4, there are the results, tomorrow it's time to focus on line trace and have a working system that rotates and tilts the ships just like the track, and then made a "magnetic lock" and polish everything. Epic and Blueprints language are awesome.



T̶o̶m̶o̶r̶r̶o̶w̶ ̶i̶ ̶w̶i̶l̶l̶ ̶p̶o̶s̶t̶ ̶a̶ ̶g̶i̶f̶v̶ ̶o̶r̶ ̶a̶ ̶w̶e̶b̶m̶,̶ ̶i̶t̶'̶s̶ ̶t̶o̶o̶ ̶l̶a̶t̶e̶ ̶a̶n̶d̶ ̶i̶'̶m̶ ̶t̶o̶o̶ ̶t̶i̶r̶e̶d̶ ̶:̶(̶

Good night, or good morning  

woop, forget the tired thing, i just let it uploading while i was making some chocolate milk before sleep (don't mind the sparks, i was testing network replication with part. systems and i needed a place holder) 

[https://www.youtube.com/watch?v=JLTw-iL ... e=youtu.be](https://www.youtube.com/watch?v=JLTw-iL7ey8&feature=youtu.be)
## Post #40
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2016-02-27T05:10:50+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Really nice !!!  good progress !! Would be cool to have a website or place to see the progress on it. 

As for me, I want to do the same but with HTML5 and Webgl technology. I'm too busy right now.  : )

Keep the good work !
## Post #41
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2016-03-04T12:56:31+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

I finally found the Fury pads (weapons/boost) inside the tech da ra rscmodel after a long search hiding models, and then UV-mapped them with blender (not the best, but they are nice) for using it with ue4, here is a screenshot and a download link if someone wants to use them, improve them (i didn't do a perfect job uv-mapping them) or whatever, and you know, sharing is knowledge.

[https://drive.google.com/file/d/0B9dy0w ... sp=sharing](https://drive.google.com/file/d/0B9dy0wb-EfqPYTVLWWQyaHc0Yk0/view?usp=sharing)

Again, ty guys for this awesome post
## Post #42
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2021-03-06T17:58:07+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

It's been a long time.

Hi again 

Due to life circumstances, I ended up losing all the progress I had in the previous project because my hard drive broke   , and for personal reasons and because of my job I did not had time to restart the project, but now with the quarantine and having a lot of time, I have "resurfaced from the ashes " and get better progress.

Here is a little video, there is a lot to do, but is much better than the progress i had earlier.

[https://www.youtube.com/watch?v=Bi5i-Rcr06A](https://www.youtube.com/watch?v=Bi5i-Rcr06A)

I tried to fiddle with the guide of hex2obj to extract wipeout 2048 ships and tracks but i'm lost because i don't know where to start with the face index.

Here is a link to two models (Ag-sys ship and Sol track) and here are some screenshots i took while following the hex2obj tutorial, also i tried to use the makeH2O_Wipeout from the HD/Fury version but there is no luck because the model workflow have changed   

[https://drive.google.com/file/d/1YUgC2e ... sp=sharing](https://drive.google.com/file/d/1YUgC2eXQqkLrWjg9uiAXlnW93kGmiMap/view?usp=sharing)

Following the guide, on the ag-sys the scrambled alphabet starts on 0x2110, but i don't know where to start, let me explain it with a picture.

For example, on this pic, should i star from the first . after the gxt format or from the last dot after the space on the 0x20B0 row?



And i supose this is the end of the first face index



Now i'm stuck and watched a lot of tutorials from youtube but i end up on the same place and i don't know how to continue nor how to get the vertices or normals from a model
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-06T19:23:30+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

well, I just dived into the agsys_2048.rcsmodel and didn't find it too hard:
.



agsys_2048-rcsmodel.png (33.68 KiB) Viewed 65 times


(Maybe there's parts/blocks that are harder to understand - didn't have the time to check.)
## Post #44
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2021-03-07T01:33:05+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Hi. good night, or good morning, i don't know if i'm too dumb or what   , but i only got to display two models (the one you posted on the previous post and the other one mirrored) when i try to get more meshes all of them are messed up or they are empty like the one on the screenshot.

I followed this tutorial you made earlier that helped me got the two "wing" model from the ship.rcsmodel.

[viewtopic.php?t=14695#p120937](https://forum.xentax.com/viewtopic.php?t=14695#p120937)

Those are the steps i'm making, but getting an empty obj



First of all, find the faces indices, get to the first dot starting by 00 00, then 01 00, then find the end of the scrambled alphabet with three dots.

When i have the ending and the starting positions, I subtract the ending position +1 (c189 + 1) minus the starting position (c022) to get the face indices count, on this case, c18a - c022 = 168 / 2 = b4 or 180 dec, write the value on the step 1 count field and press go1.

After that, i get the max face index, on this case 128, and I write down that value on the step 3 count field.

Then, press go2 to get the Vertex block and then press mesh to view the mesh, but is appearing as empty.

Here is a succesfully shown submodel (the other one you posted earlier but mirrored)



Thanks a lot, at least now i know how to show something on the program.

Don't know if the empty model is for the version of Hex2Obj i'm using but uploadmb is down and i can't get the latest version so i'm using Hex2obj_0.24d_WO

Gn and  ty
## Post #45
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-07T06:49:48+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from josema0890 ↑Sun Mar 07, 2021 9:33 am at Sun Mar 07, 2021 9:33 am
>
> 
Hi. good night, or good morning, i don't know if i'm too dumb or what   , but i only got to display two models (the one you posted on the previous post and the other one mirrored) when i try to get more meshes all of them are messed up or they are empty like the one on the screenshot.Hi, good morning,
sometimes it's a little bit tricky to find the start of vertices.
From the tutorial you pointed to, concerning detecting floats it says:

> v: xx xx xx nn with nn= 42..44 (these are rough values only, can also be 3F, 40)

[agsys_2048.rcsmodel]
The starting address of vertices you chose (0xc18a) is in midst of the face indices block, so deadly wrong.  

Correct one is 0xe092:
.



start_of_vertices.png (28 KiB) Viewed 47 times



> When i have the ending and the starting positions, I subtract the ending position +1 (c189 + 1) minus the starting position (c022) to get the face indices count, on this case, c18a - c022 = 168 / 2 = b4 or 180 dec, write the value on the step 1 count field and press go1.Everything fine up to now, but, as mentioned above, you're still in the face indices block at 0xc18a. It ends at 0xe091.

Another trick is to find out the address where the face indices of the next sub mesh start.

> but uploadmb is downthanks for reporting - I hope this is temporarely only. (Otherwise I need to find another hoster...  )

> so i'm using Hex2obj_0.24d_WOwell, from 4 years ago? (Can't recall the differences to the actual version atm, need to dig for the related source code)

stay tuned!
## Post #46
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2021-03-07T12:47:34+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from shakotay2 ↑Sun Mar 07, 2021 2:49 pm at Sun Mar 07, 2021 2:49 pm
>
> 

Correct one is 0xe092:

Good morning again 

Well, you are damn right, didn't know that  i had to continue until the scrambled alphabet stops, proves that i'm dumb   

With your correction, i got the guns of the ship so that solves the mistery.



Thanks a lot again, have a good day 

Edit: So far so good i have extracted a couple of meshes, but i'm finding some ones that are a little tricky and they are giving me the model crushed on a plane, or scrambled, and i can't find what is my error, for example:

Start Addr: 1f666   Count: 6335

FVFsize: 28            UV pos: 99
0                           255

Start Addr: 227e2 Count: 2945



Found it, now the ship is almost complete
## Post #47
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2021-03-09T05:43:08+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Welp, here we are again on the stuck process.

Hi shakotay2 sorry for bothering you so much with this thread bumping, but i need your help again   

> Reply from josema0890 ↑Sun Mar 07, 2021 1:58 am at Sun Mar 07, 2021 1:58 am
>
> 
https://drive.google.com/file/d/1YUgC2e ... sp=sharing

I'm extracting the meshes from the sol_track.rcsmodel I posted earlier and i reached a point where the litE it's too small to continue with the process, so i switched to bigE and now the face indices are coherent but when i try to get the Vertex Blocks (go2) they are clunky and with a weird pattern instead of a good one.





How can i know how to get the correct number to use in FVFsize? (i tried increasing 1 by 1 until from 6 until i reached 255 but i didn't got any result, yes, i know i'm dumb but i had to try )

Am I missing some important step? 

Thanks again, and sorry for bumping the thread again.

This is so far what i got from the track.rscmodel (98 objects that are speed pads and weapon pads with their position)
## Post #48
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-09T08:06:53+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from josema0890 ↑Tue Mar 09, 2021 1:43 pm at Tue Mar 09, 2021 1:43 pm
>
> so i switched to bigE and now the face indices are coherentdon't switch the endianness! It usually remains the same for one and the same 3D format.

So it's little endian here, start address of face indices block is 0x1e0743. What changed is the FVFsize, it's 24 here.

(Learn to find patterns in vertex blocks, here from 0092C200 to the next 0092C200 there's an offset of 24 bytes.)

> How can i know how to get the correct number to use in FVFsize? (i tried increasing 1 by 1 until from 6 until i reached 255
It's usually modulo 4 for floats (because float vertices consist of 3 floats, i.e. 3x4 bytes), so try 12, 16, 20, 24, 28 and so on.

(When there's additional normals and uv data in an FVF block you have to start from 32, because 12+12+8=32)
## Post #49
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2021-03-09T22:02:07+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from shakotay2 ↑Tue Mar 09, 2021 4:06 pm at Tue Mar 09, 2021 4:06 pm
>
> 
josema0890 wrote: ↑Tue Mar 09, 2021 1:43 pmso i switched to bigE and now the face indices are coherentdon't switch the endianness! It usually remains the same for one and the same 3D format.

So it's little endian here, start address of face indices block is 0x1e0743. What changed is the FVFsize, it's 24 here.

(Learn to find patterns in vertex blocks, here from 0092C200 to the next 0092C200 there's an offset of 24 bytes.)
How can i know how to get the correct number to use in FVFsize? (i tried increasing 1 by 1 until from 6 until i reached 255
It's usually modulo 4 for floats (because float vertices consist of 3 floats, i.e. 3x4 bytes), so try 12, 16, 20, 24, 28 and so on.

(When there's additional normals and uv data in an FVF block you have to start from 32, because 12+12+8=32)

Hi Shakotay, thanks for the pointing out on how to get the FVF block size, now i'm going faster and getting more models, and i will try to do the tutorial to writting an obj converter from this tutorial to speed things and not going one by one.

[viewtopic.php?p=143182#p143182](https://forum.xentax.com/viewtopic.php?p=143182#p143182)

EDIT: I found you have a "crash course" too, i will have a look on that, but, for now i have 0 idea from what i read and inspected on the code.

[viewtopic.php?f=29&t=12756](https://forum.xentax.com/viewtopic.php?f=29&t=12756)

I don't know if i can get the UV's from the models, but for now it's a lot of help.

Thanks a lot again, i have no words for the help you gave me earlier.
## Post #50
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-11T15:50:33+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

Yeah, this beast of sol_track.rcsmodel has about 2690 sub meshes. Didn't find the word after the signature to define the FVFsize of each.
edit: found the counts, FVFsize still missing

I gathered a bunch of 353 H2O files which need a correction in most cases (they have a number offset of 3000 to get them filtered, so there's not 5684 sub meshes if you thought of that).

Required corrections:
vertex count -1
or FVFsize of 20 or 24 (28 is used as default)
or
vertex address -2

Or a mix of it.  

example sol_track_3314.h2o, corrected:

0x21DC37 1259
Vb1
24 99
0x21E60F 658
020000
0x0 255

_3337:

0x239FCB 1625
Vb1
20 99
0x23AC7F 670
020000
0x0 255

_3645:

0x2D6A63 3503
Vb1
20 99
0x2D85C3 1494
020000
0x0 255

Have fun!
.


 sol_track.rcsmodel_353.zip
(62.67 KiB) Downloaded 12 times



(Didn't care for uvs. First the FVFsizes must be clear.)
## Post #51
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-11T19:34:15+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

calculated those FVFsizes, got many boxes/squares, a little bit disappointing, lost some hundreds after blender met the first of 2 obj files that had NANs (not-a-number) in them.
.



sol_track.jpg (177.22 KiB) Viewed 164 times


I've cut the boxes down to their basements (lower part of pic), H2P files for it see my next post.
## Post #52
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2021-03-11T19:39:09+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

You are a beast

The thing i was thinking about the source code of MakeH2O for the WO2048 models, is that, when you check the FVFSize on hex2obj you got an address, and if you go to that address if is correct, usually the value is 00 and in some weird cases 01, if it's wrong usually you got 0X or XX maybe a 00.

Yesterday I started to write a list of FVFSizes that i used while extracting all the models 1 by 1, because i can't understand fully the source code, the ones i used mostly are (20,24,28,40) and some of those "rare ones" if i recall correctly are (10 maybe 14 or 16 and 1 time 80).

The trick i thought that maybe is useful is, using a loop that checks all of the fvf and if the address you got is 00 and the next one is 00 or 01, then do the model (step 3) and if the check it's not correct, try again with another FVFSize (maybe an array with all the known FVFSizes and go for the next one).

For example:

For this submesh/model the FVFSize is 28



But if we put a wrong FVFSize then the next address is pointing to a (vertex?) and not the start of the face indices



I don't know if this way of dealing with the FVFSize it's correct or you have in mind a better one, but that's what i could reach after extracting 746 submeshes by hand and dealing a lot with the model structure.

BTW, send me a paypal address or something, and i will send u the money you need for a pack of beers, you've earned it  

Thanks a lot, and have a nice week and weekend  

EDIT: list of models with the fvfsize fuck, i pressed submit instead of preview, i will finish it with a link to an imgur "folder" with the fvf sizes and the correct submesh shown, for now i leave a placeholder

[https://imgur.com/a/0NVq0DV](https://imgur.com/a/0NVq0DV)

Correct FVFSizes: 20, 24, 28, 40
## Post #53
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-11T20:15:12+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from josema0890 ↑Fri Mar 12, 2021 3:39 am at Fri Mar 12, 2021 3:39 am
>
> 
 You are a beastyeah, sometimes...  

> The thing i was thinking about the source code of MakeH2O for the WO2048 models, is that, when you check the FVFSize on hex2obj you got an address, and if you go to that address if is correct, usually the value is 00 and in some weird cases 01, if it's wrong usually you got 0X or XX maybe a 00.It can give you the idea but the code was for different wipeout models 5 years ago.

> The trick i thought that maybe is useful is, using a loop that checks all of the fvf and if the address you got is 00 and the next one is 00 or 01,you're going to become a coder!   But then the order has to be vBlock/FIblock, what we have is FIblock/vBlock, that's how it worked for me, at least. But my first try was similar but led to troubles because as you may have notice, the 0000 before the start of vertex block is not always there.

> I don't know if this way of dealing with the FVFSize it's correctI'm too exhausted to check that, and

> or you have in mind a better one,yeah, it's just subtracting addresses to get the v blocksize then divide it by vertex count -> result= FVFsize. (So you don't need to try out.)

> but that's what i could reach after extracting 746 submeshes by handI was in the fear you could do that.  

> BTW, send me a paypal address or something, and i will send u the money you need for a pack of beers, you've earned itthanks for the beer! (No other paying required.)

> Thanks a lot, and have a nice week and weekendyeah, thx, same for you!

I'll send you the code asap, maybe Saturday (too much to do tomorrow).

H2O files, only sub meshes with a vertex count > 250:


 sol_track.rcsmodel_410.zip
(73.05 KiB) Downloaded 13 times


(don't expect the numbering to be the same as in the previous zip!)

Keep in mind that the resulting obj files contain the number of the H2O file (they are created from) in their first line where 100.obj is NOT created by 100.h2o (sorry for the confusion  ).

And don't forget to use hex2obj's SaveAs Mmesh feature.

python script for blender, multiple obj import (change of path to obj required, example D:\\', 'Work\\my_obj_folder'):

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows ie C:\objects
#path_to_obj_dir = os.path.join('C:\\', 'objects')
path_to_obj_dir = os.path.join('D:\\', 'Work\\your_obj_folder')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```
## Post #54
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2021-03-11T21:02:21+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from shakotay2 ↑Fri Mar 12, 2021 4:15 am at Fri Mar 12, 2021 4:15 am
>
> you're going to become a coder!

Heh, ty   

> Reply from shakotay2 ↑Fri Mar 12, 2021 4:15 am at Fri Mar 12, 2021 4:15 am
>
> I was in the fear you could do that.

Well, i'm a little pigheaded   

> Reply from shakotay2 ↑Fri Mar 12, 2021 4:15 am at Fri Mar 12, 2021 4:15 am
>
> thanks for the beer! (No other paying required.)

But you deserve it after all of that work you did   

> Reply from shakotay2 ↑Fri Mar 12, 2021 4:15 am at Fri Mar 12, 2021 4:15 am
>
> I'll send you the code asap, maybe Saturday (too much to do tomorrow).

Don't rush it, take your time and rest a lot, that's more important.
## Post #55
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2021-04-02T08:36:08+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

I didn't posted here but, that's already months (if not a year ?) that I have reversed those.



Also imported some models on HD/Fury:




^ Video: [https://www.youtube.com/watch?v=Zug8HCl7kpc](https://www.youtube.com/watch?v=Zug8HCl7kpc)

I want the tool to be fully completed before releasing anything though.
## Post #56
- Username: josema0890
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 17, 2015 3:28 pm
- Post datetime: 2021-04-03T02:39:55+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from zaykho ↑Fri Apr 02, 2021 4:36 pm at Fri Apr 02, 2021 4:36 pm
>
> 
I didn't posted here but, that's already months (if not a year ?) that I have reversed those.

https://cdn.discordapp.com/attachments/ ... nknown.png

Also imported some models on HD/Fury:

https://cdn.discordapp.com/attachments/ ... nknown.png


https://www.youtube.com/watch?v=Zug8HCl7kpc

I want the tool to be fully completed before releasing anything though.

Wow that's freaking awesome, lmao   

Well, i got working my own version of shakotay's makeh2o for WO248 and even WOOC, i need to fine tune it better to automatically find and correct the fvfs (just found a 56 20 for the track park and there are two 24 FVF with different UV values, one with 16 and the other one with 20 ) and the start of the vertex address, so far so good this is the progress i got (i need to find a better gnf script than the one of noesis, it crashes with some textures when trying to export them to tga with transparency and seems it loses some info on the alpha channel) and where the game stores the metallic/roughness map.

The beast that corrects (or tries to correct   ) the vertex address I coded that I'm sure there is an easier way to already do this and without errors    

[https://i.imgur.com/BQzaWd7.png](https://i.imgur.com/BQzaWd7.png)


[https://i.imgur.com/qRK29nu.png](https://i.imgur.com/qRK29nu.png)


WO2048 Metro Park Track

[https://i.imgur.com/uUfH0NF.png](https://i.imgur.com/uUfH0NF.png)
## Post #57
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2021-04-03T08:50:47+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from josema0890 ↑Sat Apr 03, 2021 10:39 am at Sat Apr 03, 2021 10:39 am
>
> 

Well, i got working my own version of shakotay's makeh2o for WO248 and even WOOC, i need to fine tune it better to automatically find and correct the fvfs (just found a 56 20 for the track park and there are two 24 FVF with different UV values, one with 16 and the other one with 20 ) and the start of the vertex address, so far so good this is the progress i got (i need to find a better gnf script than the one of noesis, it crashes with some textures when trying to export them to tga with transparency and seems it loses some info on the alpha channel) and where the game stores the metallic/roughness map.

The beast that corrects (or tries to correct   ) the vertex address I coded that I'm sure there is an easier way to already do this and without errors

Very nice !
## Post #58
- Username: elfhundert
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 20, 2021 4:20 am
- Post datetime: 2021-05-21T23:33:03+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

guys is this thread here dead? I have some real trouble to export models and textures from wipeout HD fury. Somebody active ?
## Post #59
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-02T15:18:36+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from zaykho ↑Fri Apr 02, 2021 4:36 pm at Fri Apr 02, 2021 4:36 pm
>
> I want the tool to be fully completed before releasing anything though.Sure, take your time. (But you will never release, will you?  )

To be serious it's 6 years ago that I released what I had:
.

> Reply from shakotay2 ↑Sun Jun 07, 2015 11:50 pm at Sun Jun 07, 2015 11:50 pm
>
> 
(Not the best solution but it was a solution.)
## Post #60
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2021-06-02T17:03:42+00:00
- Post Title: Re: [Request] Wipeout HD/Fury

> Reply from shakotay2 ↑Wed Jun 02, 2021 11:18 pm at Wed Jun 02, 2021 11:18 pm
>
> 
zaykho wrote: ↑Fri Apr 02, 2021 4:36 pmI want the tool to be fully completed before releasing anything though.
Sure, take your time. (But you will never release, will you?  )

To be serious it's 6 years ago that I released what I had:
.
shakotay2 wrote: ↑Sun Jun 07, 2015 11:50 pm
(Not the best solution but it was a solution.)

I will lol   

The reason is that I make all my tools in Webgl, and I refuse to use anything server sided (so everything is 100% clientside, no nodejs or php), which require some black magic voodoo to stream all those assets correctly.

As it stand right now, I load everything in the RAM (I have 64gb of RAM) and do every modifications right into it, I can't release something like that yet.

Wipeout Omega eat like 40gb of RAM when I read, convert and extract everything, it's even worst for Driveclub........ that's why I need to finish some other tools before releasing it.



^ I also made a mini hex viewer that document all parts of the reverse process, so when it will be released, all the reverse information will be shared too.
