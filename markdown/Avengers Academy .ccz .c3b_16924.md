## Post #1
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-25T06:25:38+00:00
- Post Title: Avengers Academy .ccz .c3b

.c3b - Models and anims 
.ccz - textures  
Samples: [https://www.sendspace.com/file/qzjev8](https://www.sendspace.com/file/qzjev8)
Thanks in advance,i hope it's possible to open these files
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-25T08:27:59+00:00
- Post Title: Avengers Academy .ccz .c3b

c_FoggyNelson_L1_skin_v1-c3b.jpg (164.3 KiB) Viewed 598 times


edit: H2O file for the body

0x25FF6 6750
Vb1
64 24
0x13E 2315
020000
0x0 255
## Post #3
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-25T11:00:21+00:00
- Post Title: Avengers Academy .ccz .c3b

> Reply from shakotay2
>
> c_FoggyNelson_L1_skin_v1-c3b.jpg
Cool,is this file (c_FoggyNelson_L1_skin_v1) contains only head? or the body too? 
Thanks.
## Post #4
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-08-27T01:25:39+00:00
- Post Title: Avengers Academy .ccz .c3b

Been futzing with this for a long time as well. Cocos2d-x is supposed to be the suite to work with these but I had a heck of a time just getting that set-up. At any rate though maybe a good place for anyone looking to find coding to look. This app as well is supposed to be able to load the files.
[https://www.amazon.com/gp/product/B00RQ ... nSuccess=1](https://www.amazon.com/gp/product/B00RQVAR8G?%5Burl%5Die=UTF8&keywords=luis%20revilla&path=%2Fgp%2Fproduct%2FB00RQVAR8G&qid=1420486447&ref_=mas_buy_sign_in&s=mobile-apps&sr=1-4&useRedirectOnSuccess=1)&[/url]
## Post #5
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-27T05:06:23+00:00
- Post Title: Avengers Academy .ccz .c3b

> Reply from SickAlice
>
> Been futzing with this for a long time as well. Cocos2d-x is supposed to be the suite to work with these but I had a heck of a time just getting that set-up. At any rate though maybe a good place for anyone looking to find coding to look. This app as well is supposed to be able to load the files.
https://www.amazon.com/gp/product/B00RQ ... nSuccess=1&[/url]
Nope,it doesn't work. 
Btw,by googling i find information what VisEcad viewer can open .ccz textures.
If this program really work with .ccz textures,then we will only need noesis (or 3ds max) script for .c3b models and all characters files from the game folder (Android/data/com.tinyco.avengers) 
Edit: I found tool which can convert fbx to .c3b,is this a possible to edit tool and make it able to convert c3b files to fbx? 
Tool link : [https://github.com/cocos2d-x/fbx-conv](https://github.com/cocos2d-x/fbx-conv)
## Post #6
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-08-28T10:27:20+00:00
- Post Title: Avengers Academy .ccz .c3b

I've looked into the files to see if I could create a script for Noesis to load the files but haven't got very far. If anyone wants to help with looking, I've looked in c_FoggyNelson_L1_skin_v1 and found that the face indices counts are at:
0x24412
0x25FF2
## Post #7
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-28T12:42:25+00:00
- Post Title: Avengers Academy .ccz .c3b

> Reply from TRDaz
>
> I've looked into the files to see if I could create a script for Noesis to load the files but haven't got very far. If anyone wants to help with looking, I've looked in c_FoggyNelson_L1_skin_v1 and found that the face indices counts are at:
0x24412
0x25FF2
It's would be a good to see a script for Noesis,here are more samples,i hope they can help in script creation
[https://www.sendspace.com/file/28h0cv](https://www.sendspace.com/file/28h0cv)
Thanks
## Post #8
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-29T05:19:24+00:00
- Post Title: Avengers Academy .ccz .c3b

Excuse me for double post but i found some interesting files ( they have no extension,and can be compressed or something like that ) inside game folder + some character textures in .png format from Apk
So i hope this can help
[https://www.sendspace.com/file/at8gtg](https://www.sendspace.com/file/at8gtg) 
Thanks in advance!

P.S if png and ccz files can be compared to make a script for textures (because i'm not 100 % sure  what VisEcad viewer are able to open these textures) i attached some ccz files too.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-29T06:29:43+00:00
- Post Title: Avengers Academy .ccz .c3b

> Reply from Rutabaga
>
> P.S if png and ccz files can be compared to make a script for textures (because i'm not 100 % sure  what VisEcad viewer are able to open these textures) i attached some ccz files too.
use this bms script to extract the astc compressed textures from the ccz files 

```

endian big
comtype zlib_dynamic
get ZSIZE asize
math ZSIZE - 0x10
get NAME basename
idstring "\x43\x43\x5a\x21"
goto 0xc
get SIZE long
clog NAME 0x10 ZSIZE SIZE

```

then you should be able to convert the astc files to tga with the astc-encoder tool here
[https://github.com/ARM-software/astc-encoder](https://github.com/ARM-software/astc-encoder)

if your astc files are next to the exe, from command line use this

```
astcenc -d yourfile.astc yourfile.tga
```

or make a bat file with this and place it next to the exe and run it

```
for %%G in (*.astc) do astcenc.exe -d "%%G" "%%G.tga"
```


edit
i almost forgot Noesis has support for astc format now, so you can open the astc files with it too!
## Post #10
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-29T08:01:17+00:00
- Post Title: Avengers Academy .ccz .c3b

Thanks a lot,now only script for c3b models (and anims if this possible) are left
## Post #11
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-08-29T08:06:47+00:00
- Post Title: Avengers Academy .ccz .c3b

Check this out!
[https://taylormousegamedev.blogspot.com ... -here.html](https://taylormousegamedev.blogspot.com/2017/05/new-model-viewer-can-be-downloaded-here.html)
## Post #12
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-08-29T08:10:56+00:00
- Post Title: Avengers Academy .ccz .c3b

That only shows one mesh of the model, works good but not enough to get everything.
## Post #13
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-08-29T22:46:48+00:00
- Post Title: Avengers Academy .ccz .c3b

True, but its progress. Perhaps one could ask the person that made it for notes to use in a script for Noesis or something. Noting that I do know it's based on the core Cocos3d code. I see you said you tried that app, I was figuring it probably wouldn't load a model proper as it seems basic but has anyone gotten the actual Cocos suite working? I have an issue with it, I think it's not compatible with my video card or something. Anyways it does look like your getting closer. I'm trying to dedicate a bit to learning how to write Noesis py's as well this is one of the formats I'm putting a bit of research into. I'll note more when I get there.
## Post #14
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-08-29T23:22:58+00:00
- Post Title: Avengers Academy .ccz .c3b

I'll take a look at Cocos tomorrow, my main problem right now in the file is finding the vertex count location, without that I don't really know how to create a script. There may be a way around it but I don't have enough knowledge to know about that. If anyone knows where this is found in the file or has any information that can help, that would be great.
## Post #15
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-30T05:25:40+00:00
- Post Title: Avengers Academy .ccz .c3b

> Reply from SickAlice
>
> True, but its progress. Perhaps one could ask the person that made it for notes to use in a script for Noesis or something.
Ok,i've sent personal message to Taylor Mouse (he has an account here) i hope he will respond soonly
## Post #16
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-08-30T08:54:22+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I may have figured the vertex count but how they work this for both meshes is what's confusing me. 0x13A = 37,040. 37,040/16=2,315. That's the vertex count for the 2nd submesh, maybe they use this value for both meshes somehow. This seems to work with the other files provided too - the value after "VERTEX_ATTRIB_BLEND_INDEX".
## Post #17
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-08-30T13:55:50+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Sorry for the double post (and for the red/orange background on the screenshots, that's how I like my Noesis layout lol) but:




The script works on every sample given but c_Daredevil_L1_skin_v2. It definitely needs tidying and refining, this was made just against testing one file, but it works with multiple instead. I'll look into making it work with others, and maybe look into bones/weights. 

Edit - Reason why Daredevil's L1 skin doesn't work is because it has 3 meshes, I did manually checking with the first revision of the script so the script has been updated to fix that problem. I will get more/the rest of the models if I can and check to see if anything isn't working.

```
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("Marvel's Avengers Academy", ".c3b")
	noesis.setHandlerTypeCheck(handle, c3bCheckType)
	noesis.setHandlerLoadModel(handle, c3bLoadModel)
	noesis.logPopup()
	return 1

def c3bCheckType(data):
	td = NoeBitStream(data)
	return 1

class c3bFile: 
         
	def __init__(self, bs):
		self.texList   = []
		self.vtxList   = []
		self.matList   = []
		self.boneList  = []
		self.loadAll(bs)
		
	def loadAll(self, bs):
		self.readC3B(bs)
		
	def readC3B(self, bs):
		bs.seek(0xA, NOESEEK_ABS)
		namesizeA = bs.readUInt()
		matnameA = bs.readBytes(namesizeA).decode("ASCII")
		skip = bs.readBytes(8)
		namesizeB = bs.readUInt()
		matnameB = bs.readBytes(namesizeB).decode("ASCII")
		skip = bs.readBytes(248)
		vertex_count = bs.readUInt()
		vertBuff = bs.readBytes (vertex_count * 4)
		numSubmesh = bs.readUInt()
		for i in range(numSubmesh):
			namesizeC = bs.readUInt()
			meshname = bs.readBytes(namesizeC).decode("ASCII")
			face_count = bs.readUInt()
			faceBuff = bs.readBytes (face_count * 2)
			skip = bs.readBytes(24)
			vertex_stride = 64
			rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 0)
			rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 12)
			rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 64, 24)
			rapi.rpgCommitTriangles(faceBuff, noesis.RPGEODATA_USHORT, face_count, noesis.RPGEO_TRIANGLE, 1)
			
	def loadMeshNames(self, bs):
		pass
		
def c3bLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	c3b = c3bFile(NoeBitStream(data))
	try:
		mdl = rapi.rpgConstructModel()
	except:
		mdl = NoeModel()
	mdl.setModelMaterials(NoeModelMaterials(c3b.texList, c3b.matList))
	mdlList.append(mdl); mdl.setBones(c3b.boneList)	
	return 1
```
## Post #18
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-30T15:40:56+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Thanks a lot! I will test the script as soon as i will get access to my laptop.
Now i need to know how to download all game assets (if this a possible of course)
P.S Script for anims would  be also good,i know what reverse anims it' hard,but it's only one thing what are left.
## Post #19
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-08-30T15:44:47+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Animations is definitely something I can't/won't do. I can possibly get bones and weights but animations are something I've never looked into.
## Post #20
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-31T05:10:51+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Ok,and big thanks for the script
If any anyone can take a look here are animations in c3b format
[https://www.sendspace.com/file/p2fgfe](https://www.sendspace.com/file/p2fgfe) 
Also,i'm wondering if this method can be used to get all assets from the game,without playing it. 
[viewtopic.php?f=29&t=16055](http://forum.xentax.com/viewtopic.php?f=29&t=16055)
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-31T21:08:48+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from Rutabaga
>
> ,i know what reverse anims it' hard,but it's only one thing what are left.no, it's not. You'll need the skeleton first before dealing with animations, without it doesn't make any sense for me.

Dealing with the skeleton of c_FoggyNelson_L1_skin_v1.c3b is just a waste of time&life, again.  

There's 24 head bone names and 30+59 body bone names, where the latter contains head bone names, too, weird.
(The two body bones blocks share some names, too, so not to get nuts I restarted with the bone index 0.
It's not 113 bones because of these doubles.)
Head
0 "jt_head_bind" -1
1 "jt_l_brow_in_bind" 0
2 "jt_r_brow_in_bind" 0
3 "jt_l_brow_mid_bind" 0
4 "jt_l_brow_out_bind" 0
5 "jt_l_cheek_bind" 0
6 "jt_nose_bind" 0
7 "jt_nostrils_bind" 0
8 "jt_l_lip_bind" 0
9 "jt_lowerlip_bind" 0
10 "jt_jaw_bind" 0
11 "jt_upperlip_bind" 0
12 "jt_neck_bind" 0
13 "jt_chest_bind" 0
14 "jt_l_upperlid_bind" 0
15 "jt_l_lowerlid_bind" 0
16 "jt_r_brow_mid_bind" 0
17 "jt_r_brow_out_bind" 0
18 "jt_r_cheek_bind" 0
19 "jt_r_lip_bind" 0
20 "jt_r_upperlid_bind" 0
21 "jt_r_lowerlid_bind" 0
22 "jt_l_eye_bind" 0
23 "jt_r_eye_bind" 0

body, part1
0 *jt_chest_attach_bind* -1
1 *jt_midspine_bind* 0
2 *jt_hips_bind* 0
3 *jt_l_thumb_base_bind* 0
4 *jt_l_wrist_bind* 0
5 *jt_l_forearm_bind* 0
6 *jt_l_index_base_bind* 0
7 *jt_l_index_mid_bind* 0
8 *jt_l_middle_base_bind* 0
9 *jt_l_middle_mid_bind* 0
10 *jt_l_toes_bind* 0
11 *jt_l_ankle_bind* 0
12 *jt_l_knee_bind* 0

13 *jt_l_clavicle_bind* 0
14 *jt_l_upperarm_bind* 0
15 *jt_neck_temp_bind* 0
16 *jt_l_thigh_bind* 0
17 *jt_r_thigh_bind* 0
18 *jt_r_thumb_base_bind* 0
19 *jt_r_wrist_bind* 0
20 *jt_r_forearm_bind* 0
21 *jt_r_index_base_bind* 0
22 *jt_r_index_mid_bind* 0
23 *jt_r_middle_base_bind* 0
24 *jt_r_middle_mid_bind* 0
25 *jt_r_toes_bind* 0
26 *jt_r_ankle_bind* 0
27 *jt_r_knee_bind* 0

28 *jt_r_clavicle_bind* 0
29 *jt_r_upperarm_bind* 0

body, part2
partially added parent IDs manually 
0 "jt_all_head_bind" -1
1 "jt_chest_bind" 0
2 "jt_neck_bind" 1
3 "jt_head_bind" 2
4 "jt_l_eye_bind" 1
5 "jt_l_upperlid_bind" 0
6 "jt_l_lowerlid_bind" 0
7 "jt_l_brow_in_bind" 0
8 "jt_l_brow_mid_bind" 0
9 "jt_l_brow_out_bind" 0
10 "jt_l_cheek_bind" 0
11 "jt_l_lip_bind" 0
12 "jt_upperlip_bind" 0
13 "jt_lowerlip_bind" 0
14 "jt_jaw_bind" 0
15 "jt_nostrils_bind" 0
16 "jt_nose_bind" 0
17 "jt_r_eye_bind" 0
18 "jt_r_upperlid_bind" 0
19 "jt_r_lowerlid_bind" 0
20 "jt_r_brow_in_bind" 0
21 "jt_r_brow_mid_bind" 0
22 "jt_r_brow_out_bind" 0
23 "jt_r_cheek_bind" 0
24 "jt_r_lip_bind" 0
25 "jt_all_bind" 0
26 "jt_hips_bind" 25
27 "jt_midspine_bind" 26
28 "jt_chest_attach_bind" 1
29 "jt_neck_temp_bind" 2
30 "jt_head_temp_bind" 3
31 "jt_l_clavicle_bind" 0
32 "jt_l_upperarm_bind" 31
33 "jt_l_forearm_bind" 32
34 "jt_l_wrist_bind" 33
35 "jt_l_thumb_base_bind" 34
36 "jt_l_index_base_bind" 34
37 "jt_l_index_mid_bind" 36
38 "jt_l_middle_base_bind" 34
39 "jt_l_middle_mid_bind" 38
40 "jt_r_clavicle_bind" 0
41 "jt_r_upperarm_bind" 40
42 "jt_r_forearm_bind" 41
43 "jt_r_wrist_bind" 42
44 "jt_r_thumb_base_bind" 43
45 "jt_r_index_base_bind" 43
46 "jt_r_index_mid_bind" 45
47 "jt_r_middle_base_bind" 43
48 "jt_r_middle_mid_bind" 47
49 "jt_l_thigh_bind" 26
50 "jt_l_knee_bind" 49
51 "jt_l_ankle_bind" 50
52 "jt_l_toes_bind" 51
53 "jt_r_thigh_bind" 26
54 "jt_r_knee_bind" 53
55 "jt_r_ankle_bind" 54
56 "jt_r_toes_bind" 55
57 "jt_shadow_bind" 0
58 "jt_prop_bind" 0
## Post #22
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-09-01T03:53:54+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from shakotay2
>
> You'll need the skeleton first before dealing with animations, without it doesn't make any sense for me.

Dealing with the skeleton of c_FoggyNelson_L1_skin_v1.c3b is just a waste of time&life, again.
Excuse me,because i didn't checked the script and i didn't know if script has bones support.
## Post #23
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-09-16T22:14:13+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Hey TRDaz, you are awesome! <insert thumbs up here>

Note I've been using the basic set. Any standard models load as do any lodes. The only one that crashed for me thus far is Falcon and Weeny Cap. I'll update with more if you wish as I explore the event specific ones.
## Post #24
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-09-18T04:55:19+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I agree with Alice,it's awesome to finally have script to extract models from this game.  
Now bones are left  i hope daz will add bones support soonly
## Post #25
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-09-18T16:15:10+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Would be nice to know which ones don't work and if you could, send them to me so I can check them (I have Falcon, I saw he doesn't work too, need to try and find a fix). Rutabaga sent me a couple from the Inhumans event and I saw that Lockjaw doesn't work with the current version of the script.

I'm still trying with the bones, have never really worked with them in scripts before so it's a little harder for me, currently a bit busy in real life too so I don't have any estimate on when it will be finished.

Edit: I have Falcon and Lockjaw working now, send any more along that you find not working since I'd like to have most models working before posting this version if possible! I don't plan on supporting props/random other models YET since they probably would make the script too confusing, the game seems to like having different headers a lot, might check them out once the character models and bones are sorted.
## Post #26
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-09-19T12:59:56+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I was wrong on Cap Weenie. He has the "d_" prefix. Falcon was the only for me. As there's a lot of files I'll list the ones that have worked so far. These are the static "c_" prefixed as well their lod's and alternate costumes. None of the animation files have worked for me. Some of the fx so far have though I only went through all of the "c_" files thus far and checked the caches from several different versions.

working: Ares, Abomb, Baron Zemo, Black Panther, Black Widow, Captain America, Chitauri, Drax, Enchantress, Gamora, Groot, Hank Pym, Hulk Weenie, Hydra, Holo-Loki, Iron Man, Leader, Loki, Madame Hydra, Ms.Marvel, Nebula, Nick Fury, Odin, Quake, Red Hulk, Rescue, Rocket Raccoon, Ronan, Scientist Supreme, Spider-woman, Star-Lord, Ultron, Vision, War Machine, Wasp, Yondu.

a few others I got so far are the dj table, the ant and the anthill. Will list more when I get through them. Thank you again though and massive props for this.
## Post #27
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-09-19T19:38:30+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

No idea what the "d_" prefix represents, I have Cosmo The Dog with a name like that, and a flower bed item, no idea what they have in common unless they are just items you can place down. I've only looked at the "c_" files and those are the ones I focus on since they are the main characters, most other things probably won't work, animations definitely not.

Looks like a lot are working though which is great, I can look into other things once the "c_" files are sorted but those are my focus right now, along with the bones.
## Post #28
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-09-20T04:29:49+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from TRDaz
>
> No idea what the "d_" prefix represents, I have Cosmo The Dog with a name like that, and a flower bed item, no idea what they have in common unless they are just items you can place down. I've only looked at the "c_" files and those are the ones I focus on since they are the main characters, most other things probably won't work, animations definitely not.

Looks like a lot are working though which is great, I can look into other things once the "c_" files are sorted but those are my focus right now, along with the bones.
_d is a dialouge,i think (probably dialouge only character)

> Reply from SickAlice
>
> Some of the fx so far have though I only went through all of the "c_" files thus far and checked the caches from several different versions.
These caches has a lot of character files? If yes,can you share me some caches or tell me the where you are downloaded them?
Thanks.
## Post #29
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-09-22T05:30:57+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Sorry for double post.
I've uploaded more c3b samples,i hope they can help.
[https://www.sendspace.com/file/1uxoo5](https://www.sendspace.com/file/1uxoo5)

Also,here are files with no extension,can they contain info about event chars or something like that?
[https://www.sendspace.com/file/7e53kr](https://www.sendspace.com/file/7e53kr)
## Post #30
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-09-22T07:05:35+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Thanks for the model files, looks like the Falcon model in there doesn't work with the updated version I have for the other Falcon model, which is weird. Everything else does though, I'll check that out later when I have time.

Those unknown files don't seem to be related to models so I don't think they are useful.
## Post #31
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-09-23T04:28:54+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from TRDaz
>
> 
Those unknown files don't seem to be related to models so I don't think they are useful.
Can these files compressed or something like that?
## Post #32
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-09-23T07:52:22+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I don't see why they would be, the model files are all there just not downloaded yet so anything else isn't of interest to me.
## Post #33
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-09-28T05:23:41+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

A lot of c3b samples from Inhumans event.
[https://www.sendspace.com/file/zu9vxa](https://www.sendspace.com/file/zu9vxa)
Would be good if someone can check if these files work on current version of the script. 
Thanks
P.S the files which i mentioned above was encrypted.. 
[http://zenhax.com/viewtopic.php?f=9&t=5010](http://zenhax.com/viewtopic.php?f=9&t=5010)
## Post #34
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-09-28T08:44:22+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I've checked a lot of files and they work. Bones are in progress thanks to some help from chrrox, don't have parents or positions yet but they are loading in random positions and weights are working slightly.

I don't think the encrypted files are anything related to models though, so I'm not really interested in looking into them.
## Post #35
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-10-01T04:42:38+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Last models from inhumans event (Auran,3* Black Bolt,Secret War Quake),i hope they will work too. 
[https://www.sendspace.com/file/1p60qp](https://www.sendspace.com/file/1p60qp)

Ok,looks like i should find other method....i hope chrrox method to download all game assets without playing it will work
## Post #36
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-10-07T10:40:49+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I went through everything after getting a 100% unlock on the Inhumans Event and updating to the Halloween one. Just focusing on the static character models "c_*" these are the only ones I found that do not yet work with the script.

- Anchor Woman
- Falcon L1 v5
- Falcon S3
* the rest of the Falcon models load fine
- Frigga
- Lockjaw (any)

@rutabaga: yes all of those work. If any native files are needed ask and I'll provide. I still have some of the basic characters to unlock but as far as I've seen when one is unlocked any models from previous events also come with them including discontinued costumes. Else I will have the files for the Halloween event as it ends as well.
## Post #37
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-10-08T05:41:44+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

All outfits from current halloween event.
I hope Black widow,enchantress and tigra c3b files has right skins because i couldn't find any models named properly.
[https://www.sendspace.com/file/zrwhwk](https://www.sendspace.com/file/zrwhwk)

@SickAlice: Well,i need a lot of models.. but for begining i would like to get character models from Sun Surf and Mischelf,Gamma Attack and British Invasion events and l3 wasp.
I hope you have them,thanks.
Previously i asked a lot of people for their game files in other sites but no one couldn't help me..

P.S little off-topic but does script support UV's?
## Post #38
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-10-08T07:59:50+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

There is a version of the script back in the thread which you can test to see if there are UVs. But yeah, it does support them.
## Post #39
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-10-09T05:34:40+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I can't test the script because i temporarily have no access to my laptop.
## Post #40
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-10-09T10:29:21+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I just said it does support them lol. I wouldn't want to have a script that doesn't support UVs, would be pretty useless for me.
## Post #41
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-10-10T04:42:50+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Excuse me,i did read your post not attentively   
Btw,i have a few characters from all-new halloween event,i hope they will work with current script version,especially Mephisto and Hit-Monkey 
[https://www.sendspace.com/file/y1mxa0](https://www.sendspace.com/file/y1mxa0) 

Thanks for all your hard work.
## Post #42
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-10-18T10:47:01+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Sorry for the delay. I was in the hospital again, my body sucks. I'll get em up in a package by tonight sometime/early next morning. If you want I can just as well do the full volume from Inhumans. For Halloween 2017 currently I have everything up until Episode 2 but sand Mockingbird. Damn glitch awarded me the costume but skipped the character recruitment so I'm waiting on the techs at Tiny Co. to fix it so I can progress. I'll put a file link here tonight if that's acceptable?
## Post #43
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-11-13T14:48:13+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

So I haven't given an update on how the progress is going for a while because I haven't had too much time to work on it, but I have the bones in their correct positions now. Unfortunately the weights still assign wrong for some parts (I believe because they load as one mesh, and I have no idea why), and I haven't found the parents for the bones yet. If anyone has any insight on anything including where the parents are in the files, that would be great.



The texture was manually applied, it wasn't automatically loaded. Might try adding that feature after the bones are done. The hair bones also are off for some reason, not sure why that happens.
## Post #44
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-01-29T18:55:44+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

I've been playing at this for sometime coming up with results:

- TRDaz's Noesis script can import most C files. Exceptions are Falcon, all animal type models and Jarvis's v2 and v3 skins. They can be exported then to whatever, I've been trying psk mostly though they do not retain bones of course. Also one needs tick the invert texture button upon export. Noted Loki's Winter costume also does not load.

- The model viewer I linked on page one can import any letter type (B,C,D,FX and P) with varied results depending. Most P type single objects like weapons and such will come out complete. Some buildings will come intact usually if they do not have additional animated model components in them (courthouse for example). Most C character models can be handled though many will just be the head though usually the same head missing in Noesis. Also in C types the nodes for bone assignment will generally be retained upon the OBj export.

- Lastly sometimes models found on the map will come up flat. This isn't an error as the developers use 3d sprites for whatever reason on occasion in this game.
## Post #45
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-29T19:09:05+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from SickAlice
>
> - AceWells Noesis script ....
i think you mean TRDaz
## Post #46
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-01-30T17:26:46+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Fixed. Late night. *shrug*

@TRDaz: A information post bumped back to page 3. Added if it helps you in animating asides from the nodes being retrievable (for weighting of course) a bit of research tells me these are almost identical in structure to Netimmerse files, near exact to the ones from the 2nd Freedom Force actually. The model files themselves contain 3d, node and texture pointer info. The core models contain a detailed model as well two LOD files each to control anims and boundries. The animation files contain no graphical information rather just animation sequence information to direct a models nodes very much like keyframe files. I'm working on the models but will try some experiments at a later date with all this.

- adding a little more reading back, those pesky texture files can be opened and converted with this program. It's GUI now. All you got to do is go under Tools > PVR Viewer and browse and open the file. Then in the Viewer save it as a different format.
## Post #47
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-02-18T05:28:18+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from TRDaz
>
> I may have figured the vertex count but how they work this for both meshes is what's confusing me. 0x13A = 37,040. 37,040/16=2,315. That's the vertex count for the 2nd submesh, maybe they use this value for both meshes somehow. This seems to work with the other files provided too - the value after "VERTEX_ATTRIB_BLEND_INDEX".

Question since you know what your doing. I'm trying to learn the scripting process. From what I understand at least there is a way to change this count but not the how or why of it. I know the threshold if that is the right term is too low for this game. It doesn't account for certain meshes of a high poly count nor most of the map models which are larger. For example I have an exported ship in my 3d program right now. I only have the landing pads of the ship yet the outline of where the rest of the model is supposed to be is present in blank vertices. Thanks for any help in advance.
## Post #48
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2018-02-19T15:19:29+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

i can't help with noesis script, but if you want to import skinned models with Blender 249 , here is a blend.
Install Blender version 249 (32bits) and Python version 2.6.x (32 bits)
Unpack zip file and in "Blender249[AvengersAcademy][mobile][c3b][2018-02-19]" double click Blender249.blend.
In Blender Text Window press alt+p, select "*.c3b" file with "skin" inside filename and press "import".
Scale for models or armatures x=1.97 or 1/x.
You must manual parenting bones and meshes.

C3b file is split by section:
2-nodes - bones, bone maps for meshes 
3-animations
16-materials
34-meshes

Bone format:
 - bone name [ string ]
 - unk flag [ 1 byte ]
 - matrix4x4 [ 64 bytes as 16 floats ]
 - unk integer [ 4 bytes as integer]
 - children count [ 4 bytes as integer]

So for parenting use recursive function, like this:

```
	def getChildren(parent):
		bone=Bone()
		bone.parentName=parent.name
		skeleton.boneList.append(bone)
		bone.name=g.word(g.i(1)[0])	
		a=g.B(1)
		bone.matrix=Matrix4x4(g.f(16))	
		b=g.i(1)[0]
		for m in safe(g.i(1)[0]):
			getChildren(bone)




```


If you want to play with animations, i can send a blend but i cant't solve a problem with object's scale.
[Blender249[AvengersAcademy][mobile][c3b][2018-02-19].zip](https://xentaxbackup.github.io/file/13932_Blender249[AvengersAcademy][mobile][c3b][2018-02-19].zip)
## Post #49
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-02-19T18:40:57+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Tight! Exact version of Blender I use, thank you much!
## Post #50
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-02-22T18:43:36+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Tested all the above. Works like a charm. Outstanding work people, this is what makes this a good community. All that's left is to crack the map buildings and extents and everything is done.
## Post #51
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-05-22T06:26:20+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

here is Noesis python script to decompress on the fly and open the *.ccz textures  


 tex_MarvelAvengersAcademy_iOS_Android_ccz.zip
(681 Bytes) Downloaded 133 times


so no need to use the bms script [here](http://forum.xentax.com/viewtopic.php?p=133405#p133405) any more.   
it should open Android *.pvr.ccz and iOS *.astc.ccz files, although i didn't have any *.astc.ccz samples to test it on.
## Post #52
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2019-02-02T22:49:49+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Still working away on these and sharing them on Devart. Looking for data caches from the earlier V.1 games if anyone has them. I didn't start until right before V.2 myself and am missing a few files. Ty.
## Post #53
- Username: Roseweave
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 26, 2019 6:43 am
- Post datetime: 2019-09-25T22:46:15+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Hi, does anyone have a model of Viv Vision from this game? She hasn't appeared in any of the other Marvel games yet.
## Post #54
- Username: Maechen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 22, 2019 11:37 pm
- Post datetime: 2019-12-22T15:50:16+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Hello, I use your blender script for Harry Potter - Hogwarts Mystery game and I have a problem for some .c3b files (not for all)
The error is : 

```
  File "starter.py", line 186, in Parser
    c3bParser(filename,g)
  File "starter.py", line 50, in c3bParser
    bone.matrix=Matrix4x4(g.f(16)).invert()
ValueError: matrix does not have an inverse
```


You can see your script work fine for this file : [https://uptobox.com/nsra8swyyaqb](https://uptobox.com/nsra8swyyaqb)
But not for this one : [https://uptobox.com/fg6y8t1rp0vm](https://uptobox.com/fg6y8t1rp0vm)

Other Error :

```
Traceback (most recent call last):
  File "starter.py", line 186, in Parser
    c3bParser(filename,g)
  File "starter.py", line 56, in c3bParser
    f1=g.i(e[0])
  File "F:\HP Hogwarts Mystery\blender\newGameLib\myLibraries\binaresLib.py", line 116, in i
    data=struct.unpack(self.endian+n*'i',self.inputFile.read(n*4))
MemoryError
```


This error happened in these files :
[https://uptobox.com/btmlsudxqijd](https://uptobox.com/btmlsudxqijd)
[https://uptobox.com/3mo9i3rivxsa](https://uptobox.com/3mo9i3rivxsa)

If you can help me by edit your script or tell me what I can do for make it work ! Thanks in advance
## Post #55
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-22T18:22:50+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from Maechen ↑Sun Dec 22, 2019 11:50 pm at Sun Dec 22, 2019 11:50 pm
>
> If you can help me by edit your script or tell me what I can do for make it work ! Thanks in advanceIt's Mariusz' script and it's not as easy as you may think of. You need some decent understanding of the starter.py script (which may take weeks) or some intuitive proceeding.
You may or may not understand it from this patch which is only working for b_WeasleysHouse_Int_skin_v27.c3b:

```
		sectionName=g.word(g.i(1)[0])
		unk,offset=g.i(2)
		back=g.tell()
		if i==0:
			offset=0x32A290;unk=16
		g.seek(offset)
```


```
						#bone.matrix=Matrix4x4(g.f(16)).invert()
						bone.matrix=Matrix4x4(g.f(16))
```

.



b_WeasleysHouse_Int_skin_v27-c3b.png (63.99 KiB) Viewed 393 times
## Post #56
- Username: Maechen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 22, 2019 11:37 pm
- Post datetime: 2019-12-23T17:34:40+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Hello, thank you very much for your answer and your time. 

I've some skill in python (but I never use python in blender or for 3D so I don't understand any particularities for see the problems)
So I will work for understand the script with your clues and for understand the MemoryError

Have a pleasant christmas and thanks again !
## Post #57
- Username: pappopa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 11, 2020 5:55 am
- Post datetime: 2020-03-10T22:31:48+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

hello, I'm using the blender script to convert the .c3b file from the harry potter hogwarts mystery game, for now it seems its work correctly, but I have a problem, I wanted to use the same script to extract the animations (same .c3b extension). for what I know some people are using this script to successfully export them without problem, the same person who it say has extracted them correctly has tryed to helped me, but with no success.
if I'm correct he say to import the model and after this the animation and voilà, but everytime that I have tryed, nothing..
I have tryed many time and even changing something before trying again.. but really nothing, I even tryed on xp sp3..
in the console I can see a log update, when a model has imported, but with the animation I can only see the name and nothing.



maybe this doesn't mean anything.
has someone an idea on what I'm doing wrong?
I'm using blender 2.49b (x86), installed python 2.6.6 (x86) (and other 2.x.x to see if there are some improvements), win 8.1 pro (or win xp sp3) and this script "Blender249[AvengersAcademy][mobile][c3b][2018-02-19].zip" with the bone name long and uvflip modified.
thanks

edit:
I have solved it
## Post #58
- Username: Maechen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 22, 2019 11:37 pm
- Post datetime: 2020-03-14T00:02:06+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from pappopa ↑Wed Mar 11, 2020 6:31 am at Wed Mar 11, 2020 6:31 am
>
> 
I have solved it

Hey, how did you manage to export the animations? I am really interested in your solution     thanks in advance !
## Post #59
- Username: pappopa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 11, 2020 5:55 am
- Post datetime: 2020-03-14T12:57:10+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

> Reply from Maechen ↑Sat Mar 14, 2020 8:02 am at Sat Mar 14, 2020 8:02 am
>
> 
pappopa wrote: ↑Wed Mar 11, 2020 6:31 am
I have solved it


Hey, how did you manage to export the animations? I am really interested in your solution     thanks in advance !

I've sent you a PM
## Post #60
- Username: lucas10058
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 14, 2019 5:51 am
- Post datetime: 2020-03-29T04:32:27+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Hi, could someone help me extracting the models and textures of these 4 characters from a digimon game? i have no idea how to use pyton 
[http://www.mediafire.com/file/derk7ysj9 ... 8.rar/file](http://www.mediafire.com/file/derk7ysj95x9qvu/785-788.rar/file)
## Post #61
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-29T10:37:17+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Point clouds are all we have:  
.



chr785-c3b.png (39.46 KiB) Viewed 124 times
## Post #62
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-09-25T23:59:44+00:00
- Post Title: Re: Avengers Academy .ccz .c3b

Mariusz (@Szkaradek123), I've posted files for hogwarts mystery [here](https://forum.xentax.com/viewtopic.php?f=16&t=17626&p=167117#p167117). skeleton is not loaded fully because of bone names, can you help to bypass this to load full model with skeleton or even with animations?
