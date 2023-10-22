## Post #1
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-01T19:11:43+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

Greetings everyone,a long time has passed since the last research on this game,so i hope you can help me
Currently i successfully extracted contents of movie.dat and vox.dat using demux + Vgmstream from MGS toolset ( [viewtopic.php?f=33&t=10156](http://forum.xentax.com/viewtopic.php?f=33&t=10156)& )
Only models are left,and i hope this is possible to extract them,because none of tools which are in toolset can't extract contents of stage.dat (i hope this file contains models)
Sample:
[https://mega.nz/#!Ds4EwIZD!NdW6ZJexMENg ... 9cqkbZ377k](https://mega.nz/#!Ds4EwIZD!NdW6ZJexMENgVxRaDNFVQv7YDlPV-Elsd9cqkbZ377k)
Thanks.

P.S I tried to rip through emulator but model aren't t-posed..

EDIT: After searching a forum and internet almost for 2 days i found what this file (stage.dat) is cannot be open and encrypted,so i had to download MGS HD collection which have no encryption in files. I extracted all files from psarc archive and used this script ( [viewtopic.php?f=16&t=11502](http://forum.xentax.com/viewtopic.php?f=16&t=11502) )  to import models into 3ds max but imported models are broken,have broken uvs and normals..i hope someone can write script for noesis.
Samples: [https://mega.nz/#!O45xlDzD!8hwCup0dUaYi ... l5UIEAE3z0](https://mega.nz/#!O45xlDzD!8hwCup0dUaYivOAm3v68cJw9ds3fASFsBl5UIEAE3z0)
## Post #2
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-03T15:53:19+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

I'm sorry for bump but as far as i understand the stage.dat from PS2 version is encrypted as hell,and no one through years is don't managed to open it.
So i had to download MGS HD collection to look into files,and stage files looks like unencrypted and everything can be extracted successfully,but i have the problem.
The script for 3ds max which JayK made ( [viewtopic.php?f=16&t=11502](http://forum.xentax.com/viewtopic.php?f=16&t=11502) ) have some problems with models importing,normals,poygons,uvs and etc. are broken,i hope someone can write script for Noesis.
If you wanna help take a look at new samples above
Thanks.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-08T12:23:44+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

here is first draft of Noesis python script for your "MGS HD collection PS3" samples  


 fmt_MetalGearSolidHDcollection_cmdl.zip
(1021 Bytes) Downloaded 90 times


supports geometry and UVs

i don't know what problems you had with the maxscript but this is the best i can do for now.
i couldn't test UVs because there were no textures included, and every other triangle
has flipped normals, so you have to unify them in your 3d program.
i'm pretty sure some of the larger files have more than one material group and the data
shouldn't be read in a single array but that is how it is for now, hope this helps a little.  

edit
since the normals array had 4bytes stride i was thinking maybe they are encoded in 2 shorts
like descibed in slowerthanlight's post so i played around a bit with decodeNormals32 but i'm 
not sure if i even used it right!  
[viewtopic.php?p=119352#p119352](http://forum.xentax.com/viewtopic.php?p=119352#p119352)
## Post #4
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-08T13:54:56+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

I've had the following problems with the 3ds max script
[http://i.imgur.com/J2et8kS.png](http://i.imgur.com/J2et8kS.png)
bad smoothing and uvs (i won't count normals,because they are fixable)

and i have the same uvs and smoothing problems with your Noesis script after model import into 3ds max.
maybe it's just me? and everything is ok with both scripts?
[http://i.imgur.com/ZoUSynT.png](http://i.imgur.com/ZoUSynT.png)

anyways here a few snake texture samples,if you need them.
[https://mega.nz/#!L4ZABIoa!iRPksZmeZlE_ ... 3tg6fGhMq4](https://mega.nz/#!L4ZABIoa!iRPksZmeZlE_sPrh2hXeF_8GJZ6_6odgX3tg6fGhMq4)
Thanks.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-08T15:14:55+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

yeah see thats what i mentioned before, the UVs are correct but that file has many material
groups and i would need to break it up into submeshes, this is not a quick fix for me because i
have not found where this information is stored yet.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-08T21:16:27+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

hi Ace,
dunno whether it helps a bit but creating groups for the rat all modulo 100 fi numbers created none overlapping uvs (apart from a few):



rat_SMs.JPG (82.51 KiB) Viewed 409 times


btw: where do you have this function from? NBuf = rapi.decodeNormals32() , searched the pluginsource folder at no avail.
I know there's some normals compression algo (11,11,10= 32 bits for example); 
in the link you gave the post as of Thu Jun 09, 2016 12:10 pm is the one you referred to?

(When I export the rat with your script from Noesis to obj the vns are bogus, what do I miss? Mesh and uvs look ok.)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-08T23:59:11+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

I made use of an existing C routine and it seems to work (although there's vn components >= 3.0):


 Make_Rat_normals.zip
(3.59 KiB) Downloaded 38 times


while there's probs with the face culling. Obviously some faces have the wrong winding, since some normals are "inside".
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-09T01:59:09+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

you're saying and asking too many things at once that i don't fully understand yet.   
the script is a work in progress and definitely not perfect but i think the rat is not a good 
example of the issue because it is too simple, you must look to the character models,
like camoufla-dc_dododo etc

i don't know what you mean here:

> creating groups for the rat all modulo 100 fi numbers created none overlapping uvs"all modulo 100 fi numbers" -guess i have to look that up.   

i think the *.tri file might be the key to material groups here, for the rat the UVs produced by the 
script in Noesis look like 2 overlayed sets and 00713a4f.tri has two 160 byte blocks of data.   

> When I export the rat with your script from Noesis to obj the vns are boguslikely yes because like i said i wasn't sure how they are handled here,
i could just avoid the normals but i was just playing around trying to get them working,
you should probably just comment that part out of the script (line 44 at least).
i don't know what to do about the winding issue, maybe they are really quads?   

> in the link you gave the post as of Thu Jun 09, 2016 12:10 pm is the one you referred to?just click the link and it will take you directly to slowerthanlight's post, 
the info i was reading is near the bottom of that post.   

basically decode 2 shorts into 3 floats and run some algo on them, 
i thought decodeNormals32() probably is what this was for.   

rapi.decodeNormals32() is briefly described in the __NPReadMe.txt

> I made use of an existing C routine and it seems to workcan you post this routine?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-09T08:17:09+00:00
- Post Title: Metal Gear Solid 3: Snake Eater (PS2) .dat

> Reply from AceWell
>
> "all modulo 100 fi numbers" -guess i have to look that up.it simply means to put a g SM_number_x before f 100 101 102, before f 200 201 202 and so on
and g SM_number_0 before f 1 2 3

> i think the *.tri file might be the keymay be. But it belongs to the *.mdl file, not the *.cmdl file, doesn't it?

> i don't know what to do about the winding issue, maybe they are really quads?could PYNOECONSTN(RPGEO_QUAD_STRIP) help?

> can you post this routine?it's a slight modification of this one: [viewtopic.php?f=16&t=8630&p=97015&hilit ... lag#p97015](http://forum.xentax.com/viewtopic.php?f=16&t=8630&p=97015&hilit=+axisflag#p97015)

(I'd PM you, but you switched it off.  )
(I wouldn't like to make it public before it works in my FH3 project.)

Also I'm not sure whether I maybe fooled myself.  
copy/pasted the results from the decompression into the obj file created by Noesis then imported it into blender.

There's a good chance that blender autocreates normals in case it doesn't like the ones provided, not sure. 

edit: sum of squares is not 1.0 (even not constant) as it should be for normals
