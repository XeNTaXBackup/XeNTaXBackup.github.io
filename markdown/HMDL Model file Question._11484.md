## Post #1
- Username: HOTDfan
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jan 30, 2014 11:10 am
- Post datetime: 2014-05-04T17:09:47+00:00
- Post Title: HMDL Model file Question.

How would I be able to import .HMDL files into a 3d model viewing program like 3ds Max or something similar? Or at 
least convert them to a more recognizable file format? I've been trying to do this for about several months now, 
with no success. Below is a decrypted sample file from a PS3 PSN game.

[https://www.dropbox.com/s/g9apare007fza ... Model.HMDL](https://www.dropbox.com/s/g9apare007fza5a/Magician%20Model.HMDL)

Should I also include the decrypted .HTEX(texture file) file that goes with this model?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-05T14:14:00+00:00
- Post Title: HMDL Model file Question.

The point cloud looks ok to me (picture's left part). Missing parts of leg/arm are contained in a 2nd smaller submesh, hell knows why.
For the mesh (pic's right part), well, too many uint16 face indices blocks interrupted by some unknown DWords -
hard to recover, yes.



ptCld.JPG (22.53 KiB) Viewed 333 times
## Post #3
- Username: HOTDfan
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jan 30, 2014 11:10 am
- Post datetime: 2014-05-07T19:42:15+00:00
- Post Title: HMDL Model file Question.

> Reply from shakotay2
>
> The point cloud looks ok to me (picture's left part). Missing parts of leg/arm are contained in a 2nd smaller submesh, hell knows why.
For the mesh (pic's right part), well, too many uint16 face indices blocks interrupted by some unknown DWords -
hard to recover, yes.
ptCld.JPG
Thanks SO much for the quick reply back, shakotay2. Sorry that the model file didn't turn out like I thought it 
would.

Just for reference, below is a screenshot of the character whose model you looked at.



Perhaps this model will turn out better. It's just a model of a chainsaw from the same game as the other model: The 
House of the Dead 4. This one is also decrypted, as well.

[https://www.dropbox.com/s/ni3skabchayws ... Model.HMDL](https://www.dropbox.com/s/ni3skabchaywsfq/Chainsaw%20Model.HMDL)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-07T22:18:24+00:00
- Post Title: HMDL Model file Question.

thx - sadly the problem remains the same.

There are 597 face indices with a range from 1 to 560, here's the first faces: 

standard triangles
f 67 38 85 
f 28 64 26 
f 81 41 72 
f 36 70 34 
f 74 30 78 
f 32 68 39 
f 461 451 443 
f 435 417 415 
f 381 389 284 
...

or as TriStrips
f 67 85 38
f 38 85 28
f 85 64 28
f 28 64 26
f 64 81 26
f 26 81 41
f 81 72 41
f 41 72 36
f 72 70 36
f 36 70 34
f 70 74 34
f 34 74 30
f 74 78 30
f 30 78 32
f 78 68 32
f 32 68 39
f 68 461 39
f 39 461 451
f 461 443 451
f 451 443 435
f 443 417 435
...

Maybe a very simple model like a box or a book could help.
Or a square stone.
## Post #5
- Username: HOTDfan
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jan 30, 2014 11:10 am
- Post datetime: 2014-05-09T15:40:43+00:00
- Post Title: HMDL Model file Question.

> Reply from shakotay2
>
> thx - sadly the problem remains the same.

There are 597 face indices with a range from 1 to 560, here's the first faces: 

standard triangles
f 67 38 85 
f 28 64 26 
f 81 41 72 
f 36 70 34 
f 74 30 78 
f 32 68 39 
f 461 451 443 
f 435 417 415 
f 381 389 284 
...

or as TriStrips
f 67 85 38
f 38 85 28
f 85 64 28
f 28 64 26
f 64 81 26
f 26 81 41
f 81 72 41
f 41 72 36
f 72 70 36
f 36 70 34
f 70 74 34
f 34 74 30
f 74 78 30
f 30 78 32
f 78 68 32
f 32 68 39
f 68 461 39
f 39 461 451
f 461 443 451
f 451 443 435
f 443 417 435
...

Maybe a very simple model like a box or a book could help.
Or a square stone.
Well, dang. I thought for sure that one would work. I'm starting to wonder if I used my quickBMS Scripts incorrectly. That's how I got the files from inside each IZCA archive file. However, the scripts I used for extracting files from inside IZCAs were geared mainly for the game "Valkyria Chronicles," which supposedly has a similar file structure to The House of the Dead 4. Should I ask around the "Code Talk" area of the forum to see if anyone would be willing to create a QuickBMS script(or scripts) geared for The House of the Dead 4?

Or here's another idea: During my searches, I saw that Xentax members Chrrox and Gomtuu created a python script for Blender that could import IZCAs and HMDL files from Valkyria Chronicles. Would it be possible for me to ask in the same section of the forum(Code Talk), to see if someone could help by creating a Blender Python script for House of the Dead 4 IZCAs? The reason I'm asking for help from others is because I've been wracking my brain for what seems like forever, trying to figure all this out, and have reached the limits of my knowledge already. I'm sorry if that sounds too loser-ish to whoever reads this. 

Finally, if you want I'll be glad to tell you what my goals are for all this.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-09T20:39:18+00:00
- Post Title: HMDL Model file Question.

I don't know whom/what to ask but from the mentioned blender script it seems like the Valkyria Chronicles (PS3) models use TriStrips with 0xFFFF as a block end marker. 

Don't see any hints that could help for HOTD4 face indices.
What about a simple model?
## Post #7
- Username: HOTDfan
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jan 30, 2014 11:10 am
- Post datetime: 2014-05-10T17:20:43+00:00
- Post Title: HMDL Model file Question.

> Reply from shakotay2
>
> I don't know whom/what to ask but from the mentioned blender script it seems like the Valkyria Chronicles (PS3) models use TriStrips with 0xFFFF as a block end marker. 

Don't see any hints that could help for HOTD4 face indices.
What about a simple model?
Okay. This last model is of a grenade pickup from the same game. If this one doesn't work, then I don't know what will, because it's the smallest, simplest thing I could think of.

[https://www.dropbox.com/s/4g3oi5j21qvyg ... Model.HMDL](https://www.dropbox.com/s/4g3oi5j21qvygor/Grenade%20Model.HMDL)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-10T21:04:15+00:00
- Post Title: HMDL Model file Question.

thx, but you'll understand that it's impossible to rebuild the faces from such a model 



Grenade.JPG (46.77 KiB) Viewed 255 times


manually as it should be with a square stone, a book or a plank which have 12 triangles only.
## Post #9
- Username: HOTDfan
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jan 30, 2014 11:10 am
- Post datetime: 2014-05-11T16:03:20+00:00
- Post Title: HMDL Model file Question.

> Reply from shakotay2
>
> thx, but you'll understand that it's impossible to rebuild the faces from such a model 
Grenade.JPG
manually as it should be with a square stone, a book or a plank which have 12 triangles only.
Okay. Will a model of a simple, primitive cube work? Because I've got one right here that was somehow included in the game's files.

[https://www.dropbox.com/s/e12dlhw8w17yhv3/Cube.HMDL](https://www.dropbox.com/s/e12dlhw8w17yhv3/Cube.HMDL)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-11T17:58:09+00:00
- Post Title: HMDL Model file Question.

thx - at least it should help to narrow down the problem.

These are the faces:
f 12 12 8 
f 20 13 13 
f 14 14 9 
f 23 6 6 
f 4 4 7 
f 1 10 10 
f 21 21 15 
f 18 24 24 
f 3 3 11 
f 17 19 19 
f 22 22 5 
f 16 2 1 
using 24 vertices.

This is a cube exported by blender, using 8 vertices:
v 1.000000 -1.000000 -1.000000
v 1.000000 -1.000000 1.000000
v -1.000000 -1.000000 1.000000
v -1.000000 -1.000000 -1.000000
v 1.000000 1.000000 -1.000000
v 0.999999 1.000000 1.000001
v -1.000000 1.000000 1.000000
v -1.000000 1.000000 -1.000000
f 5 1 4
f 5 4 8
f 3 7 8
f 3 8 4
f 2 6 3
f 6 7 3
f 1 5 2
f 5 6 2
f 5 8 6
f 8 7 6
f 1 2 3
f 1 3 4
(It's 6 triangulated quads.)

edit: ok, here you go:



HOTD4-cube.JPG (15.19 KiB) Viewed 232 times



After hours of calculating most complex formulas...
no, just kidding - the truth is: I just skipped one vertex.
(Would really be surprised if this worked for the other models, too.)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-11T18:08:18+00:00
- Post Title: HMDL Model file Question.

huuah, me, I'm such a dumbo... 



chainsaw_ok.JPG (21.95 KiB) Viewed 230 times


(Although there are some errorness faces left. Will check that later.)
## Post #12
- Username: HOTDfan
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jan 30, 2014 11:10 am
- Post datetime: 2014-05-11T21:41:09+00:00
- Post Title: HMDL Model file Question.

That's good news to hear!  So the cube turned out OK, even thought you skipped a vertex. Also, the chainsaw model is mostly recognizable, apart from the "errorness" faces you mentioned. Can't wait to see the final results.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-15T18:22:07+00:00
- Post Title: HMDL Model file Question.

here's the H2O file for the chainsaw:

```
Vb1
64 48
0xF7C 560
121000
0x0 255
```
you'll have to handle the errorness faces for yourself.

Also I didn't solve the magician's problem so far.
(be aware that its VBlockSize is 80)
## Post #14
- Username: HOTDfan
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jan 30, 2014 11:10 am
- Post datetime: 2014-05-16T17:13:20+00:00
- Post Title: HMDL Model file Question.

> Reply from shakotay2
>
> here's the H2O file for the chainsaw:
Code: Select all0x594 595
Vb1
64 48
0xF7C 560
121000
0x0 255you'll have to handle the errorness faces for yourself.

Also I didn't solve the magician's problem so far.
(be aware that its VBlockSize is 80)
Thank you for posting the H2O file for the chainsaw model.

Here's what I figured out from the code you posted:


0x594 595(Face indices start address/count)

Vb1(means press the "seq" button once so it says "VB" instead.)

64 48(Vertex Block size/UV position)

0xF7C 560(Vertices start address/count)

121000( ? )(I don't know what this number means...yet)

0x0 255(Start/Size UVB)

The only thing I was clueless about was the significance of the number 121000.

BTW, here's what I got when I applied the above settings to Hex2Obj.
[Chainsaw.jpg](https://xentaxbackup.github.io/file/7339_Chainsaw.jpg)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-17T10:11:13+00:00
- Post Title: HMDL Model file Question.

The H2O data is not intended to be entered manually.
So no need to "understand" "121000".

(btw the UV pos is wrong - 32 seems to fit better)

Create an empty txt file, copy the lines into it and save it as chainsaw.H2O for example.
Then load the model and the H2O file into hex2obj.
Save the mesh as obj.

This is how the imported obj looks in blender.



Chainsaw_2.49_bot_top.JPG (61.72 KiB) Viewed 167 times


Errorness faces, yes, as I wrote before.

(I used rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, 595, noesis.RPGEO_TRIANGLE_STRIP, 1) with Noesis -
got other face indices but no improvement with the displayed model.)
## Post #16
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2018-12-04T19:45:22+00:00
- Post Title: Re: HMDL Model file Question.

I know is a fairly old topic but I wanted to finally shed some light for anyone else who is interested.  Following the group of face indices are the counts and offsets of the where each index group starts; there really isn't a marker to where the index group ends so you'll have to use the counts to end each group.  For instance, a count of 6 will use 6 of the index numbers and create 4 tri strip faces and a count of 4 will make 2.  This is the easy part.  The hard part is that the indices are not in order from 0001 to FFFF, they jump around and can start midway into the vertex order.  The only way to figure this out is through a table later on the file that tells you how much to offset the index number by to match the correct vertex.  This would be simple for small objects since there's only 1 mesh group but it gets real messy to do it manually when there are 50+ meshes.  It took me weeks to finally figure everything out and I've uploaded all the HotD4 models (including Magician) to sketchfab.  I've also posted a video on yt of how my lua script extracts these cno and bnk files.  I can elaborate more on the file structure if anyone wants more info.
## Post #17
- Username: Argg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 21, 2018 4:14 pm
- Post datetime: 2020-11-08T11:41:15+00:00
- Post Title: Re: HMDL Model file Question.

Could've done with more samples for this one tbh - if importing has issues message me on discord (see link in readme or in the add-ons panels)
[GitHub link for blender add-on](https://github.com/Argx2121/Sega_NN_tools/releases)

Didn't know xentax had a thread for this too
