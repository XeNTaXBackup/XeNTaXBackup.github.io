## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-20T16:32:10+00:00
- Post Title: *Geom DestinyDB

UPDATE:
So far we have learned that you can use Offzip to take the geom file from the cache for the site DestinyDB, and you can use Hex2OBj to analyze the data and create a OBJ data file from this. However the only flaw it seems with helmets so far at least is that you end up with degenerated faces by trying to decipher the hex code.
## Post #2
- Username: Nintendude
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-21T00:15:04+00:00
- Post Title: *Geom DestinyDB

its just zlib compressed.
just run offzip on it
offzip.exe -a c:\my.model c:\extract 0
and you will get a decompressed file.
## Post #3
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-21T00:34:42+00:00
- Post Title: *Geom DestinyDB

-snip-
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-21T01:41:10+00:00
- Post Title: *Geom DestinyDB

copy offzip.exe and your geom into a folder, say I:\xxx, then

I:\xxx>offzip -a 2994845057.geom I:\xxx 0

you should get  00000004.dat in I:\xxx

console output:
Offset file unzipper 0.3.3
by Luigi Auriemma
e-mail: [aluigi@autistici.org](mailto:aluigi@autistici.org)
web:    aluigi.org

- open input file:    2994845057.geom
- enter in directory: I:\xxx
- zip data to check:  32 bytes
- zip windowBits:     15
- seek offset:        0x00000000  (0)

+------------+-------------+-------------------------+
| hex_offset | blocks_dots | zip_size --> unzip_size |
+------------+-------------+-------------------------+
  0x00000004 ................................................................ 13
0996 --> 627552


- 1 valid zip blocks found



Guardian.jpg (91 KiB) Viewed 292 times
## Post #5
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-21T03:01:24+00:00
- Post Title: *Geom DestinyDB

-snip-
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-21T09:05:52+00:00
- Post Title: *Geom DestinyDB

> Reply from Nintendude
>
> Shakotay I think I love you.Love you, too, now for not giving up. 

btw: offzip is a genius program from genius aluigi, so don't damn it.  .

The directory thingie is a little bit confusing because the usage hint says:
"<output/dir>"
whilst the console log says: "in directory"

I was not sure whether the path to be included in <input> so I tried it quick&dirty as explained above.
## Post #7
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-21T20:20:14+00:00
- Post Title: *Geom DestinyDB

Well hit a snag, we can successfully export OBJ files from Hex2OBJ, the only downside to this is we have a lot of degenerated faces as the result.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-21T21:01:55+00:00
- Post Title: *Geom DestinyDB

well, with blender the helmet is displayed properly.
If you meet an outside-in behaviour of the mesh it normally can be fixed by inverting the normals (edit mode, mesh tools, flip normals in blender 2.49b).

Another caveat might be the tristripss algo used in hex2obj which is creating too many faces (I'll include another algo some day).



Agema_helmet.jpg (165.36 KiB) Viewed 235 times
## Post #9
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-21T21:09:16+00:00
- Post Title: *Geom DestinyDB

Flipping the normals that I get, but it's not that it's creating additional faces I don't think. I think faces are just being pulled out of where they should be causing a distorted model in the process.

EDIT: You;'re right I'm wrong it was making unneeded faces when it did the model, you just have to delete them one at a time to clean the model. Well now I just feel stupid.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-22T00:14:02+00:00
- Post Title: *Geom DestinyDB

0x1A105 is simply the wrong start address for the face indices - using 0x1A103 improves things 



wrongAddr4FaceIndices.jpg (137.44 KiB) Viewed 224 times
## Post #11
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-22T01:08:17+00:00
- Post Title: *Geom DestinyDB

Yep that fixed the inverted model problem in the Hex2OBJ program. Funny how just a couple numbers off changes things. Maybe with the Max script it will make doing these models much much easier. I was able to do a weapon from the site files earlier today as well if you want to have that for testing. For some reason I can't get it to work right in the H2O program. 
[http://www.uploadmb.com/dw.php?id=1416618470](http://www.uploadmb.com/dw.php?id=1416618470)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-22T13:11:24+00:00
- Post Title: *Geom DestinyDB

> Reply from Nintendude
>
> Maybe with the Max script it will make doing these models much much easier.

With hex2obj my fault was putting the handling of normal tristrips and tristrips with FFFF end marker 
into one function.
Together with the endian handling and some other checkings (don't know anymore why I introduced them)
this ended up in very confusing code.

Now the maxscript tristrips algo looks too simple to produce correct indices, haha.
You might check this obj:


 AgemaType3.dat.zip
(18.66 KiB) Downloaded 28 times


Thx for the weapon - it does not load but I'm not surprised since I had an odd offset for the helmet:
fSeek stream 15 #seek_cur
that should be the reason. Now I need to know how to calculate this offset. edit: lol, there's a DWord before


remark: as for WebGL models one should take care of copyrights and not puplicly upload exported obj.
But if I understood Nintendude correctly the author of this helmet doesn't mind?
## Post #13
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-22T13:45:31+00:00
- Post Title: *Geom DestinyDB

Same issue I ran into with the weapon not sure how to fix it as I don't have that much knowledge of this.
Someone I asked was able to get that OBJ I posted cleaned up took a long time, but the one you posted looks strange, was that with the maxscript? It's like every other face is inverted. But that's no problem to fix manually with a 3d program.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-22T16:37:02+00:00
- Post Title: *Geom DestinyDB

> Reply from Nintendude
>
> but the one you posted looks strange, was that with the maxscript?yep.
In blender it looked good to me - seems that damned blender obj importer repairs everything magically. 



AgemaType3_b.jpg (48.92 KiB) Viewed 196 times

(ok, smoothing doesn't work.)
But there's no superfluous faces anymore - is it?

> It's like every other face is inverted. But that's no problem to fix manually with a 3d program.
ok, I could start with an inverted face winding

edit: as for the weapon (shield) you uploaded: it has another structure, vertex block size is 40:
This is the H2O file for the first submesh (copy the 6 lines into a text file  and name it shield_0.H2O for example)
0x3402 503
Vb1
40 99
0x132E 210
021000
0x0 255
## Post #15
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-22T18:55:50+00:00
- Post Title: *Geom DestinyDB

If you mean if it's still creating the extra faces, well if you look at this image the two faces in the middle (looks like a long nose) are the extra faces I mentioned. But like I said it would be quite easy to fix after exporting as a obj after using the maxscript. I think the extra faces are not being generated by Hex2OBJ I think they are just part of the 3D model itself when it's extracted from the site. 

I wouldn't really worry about the inverted faces, that's an easy fix with a 3d program as well. So I'm guessing this maxscript will allow a person to import the .dat into 3ds max and export as a obj from that?

Guessing this is what you got as well when running the numbers too for the Vex Mythoclast weapon? Not sure why it looks like a shield but that's better than what I had when I tried.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-22T19:35:35+00:00
- Post Title: Re: *Geom DestinyDB

> Reply from Nintendude
>
> So I'm guessing this maxscript will allow a person to import the .dat into 3ds max and export as a obj from that?check your PM

> Guessing this is what you got as well when running the numbers too for the Vex Mythoclast weapon? Not sure why it looks like a shield but that's better than what I had when I tried.yep. How should it look like?

(Keep in mind that I'm handling the first submesh only.)

So this is the next submesh:
0x42AF7 8687
Vb1
48 99
0x137B3 4028
021000
0x0 255



mythoplast_.jpg (238.13 KiB) Viewed 136 times
## Post #17
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-23T03:50:10+00:00
- Post Title: Re: *Geom DestinyDB

I think I'll just put the weapons on hold for a while. I may try to convert the pistols as they may only be 1 submesh, but I wouldn't know where to start about combining these submeshes together. 

Still toying with the maxscript and had one file with an issue so far that I sent you a link for tha didn't work well with the script but not sure why.

Is it funny that only me, you and Chrrox are the only ones that have commented on this, but it's had nearly 300 views? Wish cra0 would join in on this, especially with some of the tools they have been creating for other things.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-23T09:14:25+00:00
- Post Title: Re: *Geom DestinyDB

> Reply from Nintendude
>
> Still toying with the maxscript and had one file with an issue so far that I sent you a link for tha didn't work well with the script but not sure why.I've PMed you a quick hack for the HelmetOfTomorrow.
(btw: forget to mention this unk var to be used now:
delta = readlong stream -- 03 000000 ?	
fSeek stream delta #seek_cur)

But as I wrote: a full format description will be required because there are many different Vertex block sizes in the .dat files.

> Is it funny that only me, you and Chrrox are the only ones that have commented on this, but it's had nearly 300 views? Wish cra0 would join in on this, especially with some of the tools they have been creating for other things.As chrrox wrote somewhere, there are many, about 99% of them,  who want things to be solved by others.
There is no way around to learn scripting for yourself . For me maxscripts (though debugging is a little bit limited) seems to be one of the easiest ways to get models converted into obj, for example. (besides hex2obj, hahaha).

My time with .dat has expired more or less. Feel free to ask questions concerning my hacky maxscript
but I'll stick to hex2obj now to improve the triangle strip algo used by it.

Here's the helmet of tomorrow:
[helmetOfTomorrow.jpg](https://xentaxbackup.github.io/file/8131_helmetOfTomorrow.jpg)
## Post #19
- Username: Varekai
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 05, 2014 7:54 am
- Post datetime: 2014-11-24T12:54:19+00:00
- Post Title: Re: *Geom DestinyDB

hello everyone first post here. just wanted to say thanks to everyone working on this. Nintendude i saw your other posts on the other forumns. i don't know much about scripting and such but i am learning slowly as work is pretty heavy and i dont have much time when i get home.
