## Post #1
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-25T14:50:31+00:00
- Post Title: [NOESIS] Titan Quest

I'm trying to create an importer for Titan Quest .msh models into Noesis, but I'm stuck on the bone importing.

I'm not quite sure how I should be importing the data through python.
I was using NoeMat43 but the armature never comes out right. I have been able to export the armature from another program to .dae and successfully import it into Noesis so I took a look at how the data was stored in the .dae file.

this is the bone axis+ position data for "Bone_Root"
Blue = Axis data, Green = Position data. The number correspond to the numbers in the 010 editor template in the next picture.



The .dae seems to use a 4*4 matrix while the .msh seems to use a 4*3.

I was using the following to import the bonedata into noesis and tried swapping everything and whatnot around but it never aligns with the mesh itself.

```
boneMat.append(NoeMat43.fromBytes(boneBuff))
```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T14:56:17+00:00
- Post Title: [NOESIS] Titan Quest

Never worked with bones (yet) but since the DAE file stores it as a 4x4 matrix maybe you can try converting it using `toMat44` and see if it is as you expect as a 4x4?
## Post #3
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-25T15:19:47+00:00
- Post Title: [NOESIS] Titan Quest

I did 

```
boneMat.append(NoeMat43.fromBytes(boneBuff))
boneMat[i] = NoeMat43.toMat44(boneMat[i])
```


bute then the NoeBone() function throws a 
```
RuntimeError: Invalid type provided for bone matrix"
```
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-25T16:32:23+00:00
- Post Title: [NOESIS] Titan Quest

Post a pic of the results. If you see the bones as a mirror image across all axes then you didn't setup your inverse bind matrix right. Also, some games have transform nodes that may need to be applied to the bones; it was like this with neptunia mk2. Every game is kind of different; you need to post more source and example. Also, parenting... are you doing it? I see two unknown parameters that you aren't using. With a little more source and posting a file example, I'm sure we can get the bones out for you.
## Post #5
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-25T17:41:11+00:00
- Post Title: [NOESIS] Titan Quest

How it should be:


how it is:


The best I can make out of it:


Those 2 "unknowns" aren't unknown, they're 2 ints, first one stands for the first ChildBone, the second one for how many ChildBones it has.
According to those 2 ints I parented all the bones, I figured it out with the help of this "pic" i made.


Bone_index: Bone_name, child_index, numChildren

just to explain it a little: (for the example we start at index 27: bone_r_forearm)

children is not 0 so we jump to the child index (29)
29: bone_r_wrist children is not 0 (4) so we jump to the index (31) and the following 3 bones (indexes 31 -34)
they all have 0 children so the link stops there.

I checked all the bones in Noesis and they have their parents set correctly.

now for how far I got with loading them. I read the x/y/z position info seperately from the axis data and had to swap the y and Z data to get it to stand upright.

```
x=self.inFile.readBytes(4)
y=self.inFile.readBytes(4)
z=self.inFile.readBytes(4)

boneMat.append(NoeMat43.fromBytes(boneBuff+x+z+y))

```


then I thought it seemed like the position info was relevant to the parent's position and not the actual position so i added them to gether starting from the second bone (bone_root) and that's where I'm stuck.

bonelinks = dictionary with each bone bone stating it's parent's index and name
bonenames = list with all the bonenames sorted according to their indexposition

```
   BoneData = boneMat[i]
   BoneDataP= boneMat[bonelinks[bonenames[i]][0]]

   for HKey in range(len(BoneData)):
      for key in range(len(BoneData[HKey])):
	  boneMat[i][HKey][key] = boneMat[i][HKey][key] + BoneDataP[HKey][key]

```


in the .rar: 3 .msh files, a 010 editor template (hardcoded for the ancestralwarriorA.msh) and the .dae i exported (ancestralwarriorA.msh)
[http://www.mediafire.com/?x0z8yhp5tfl21re](http://www.mediafire.com/?x0z8yhp5tfl21re)
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-25T18:30:15+00:00
- Post Title: [NOESIS] Titan Quest

Hmmm doesn't look like an absolute vs. Relative problem... If it was you would still see the symmetry, the bones would just be extended all over the place.. Are the joint positions in absolute or relative coordinates? If absolute you will have to convert. I will be home later tonight to try out your sample. But it doesn't look like the data is an IBM so loading it as bytes doesn't work. If no one helps by tonight I'll look at it when I get home.
## Post #7
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-25T18:52:42+00:00
- Post Title: [NOESIS] Titan Quest

If only the Noesis .dae import script was written in Python, then this would be easy since the data is basically the same, I just need to know what the .dae script does with the data and apply it to the .msh script.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-25T18:56:34+00:00
- Post Title: [NOESIS] Titan Quest

Look in the dae and find the node hierarchy. What are the translation markup values for the root and the first child? That should tell you what noesis does.
## Post #9
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-25T19:10:19+00:00
- Post Title: [NOESIS] Titan Quest

```
        <matrix>1 0 0 0 0 1 0 0 0 0 1 0 0 0 0 1</matrix>
        <node id="MoveAXIS" name="MoveAXIS" sid="_MoveAXIS" type="JOINT">
          <matrix>1 0 0 0 0 0 1 0 0 -1 0 0 0 0 0 1 </matrix>
          <node id="Bone_Root" name="Bone_Root" sid="_Bone_Root" type="JOINT">
            <matrix>-8.25632E-08 1.557356E-09 1 2.524711E-09 0.03770908 0.9992887 1.55722E-09 0.003163912 -0.9992887 0.03770908 -8.25632E-08 1.503546 0 0 0 1 </matrix>
```


The exporter added the "dummy" AncestralWarrior_rig to the Dae so I added that one as well.
The data for the Bone_root is exactly the same as the one in the .msh apart from the [0 0 0 1] added on the end of the matrix. But with this I still don't know how to make Noesis use the data.
## Post #10
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-25T20:23:32+00:00
- Post Title: [NOESIS] Titan Quest

Don't know much about bones yet but the  MoveAXIS looks weird

```
0 0 -1 
0 1 -0 
0 0 -0
```


That swapping the y,z axis and inverting the z axis?
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-26T06:54:43+00:00
- Post Title: [NOESIS] Titan Quest

Yeah ninja, if you look at the data in his first post and you look at the DAE output you see the DAE output would have to be a column-major matrix to match up with his data. 

<matrix>-8.25632E-08 1.557356E-09 1 ...</matrix>

Collada, however, is row-major order. Should be

<matrix>-8.25632E-08 0.03770908 ...</matrix>

Feed noesis a Mat3x4 instead of a Mat4x3 if you can and see what happens. I am about to test it out myself right now in my own code.
## Post #12
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-26T09:44:18+00:00
- Post Title: [NOESIS] Titan Quest

I don't know how to do that, I usually look at the inc_noesis.py that comes with Noesis itself to look up functions or run a "vars()" on the class.
## Post #13
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-26T16:43:32+00:00
- Post Title: [NOESIS] Titan Quest

You can swap and move around array elements or load the floats one by one instead.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-26T17:37:07+00:00
- Post Title: [NOESIS] Titan Quest

ya, I don't know a fast way to move stuff around, so I just import struct and be like

```
for ...
   matrix += struct.pack("f", new_float)

```

lol
## Post #15
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-26T22:38:21+00:00
- Post Title: [NOESIS] Titan Quest

I've tried following the offsets but the best I can make out of it is that Xvalue gets added Zvalue, Y value gets subtracted by Xvalue and Z -Y, which to me doesn't make sense.

I'll just wait and see if perhaps MrAdults can shine some light on the DAE importing.
I can't load the .dae in blender but I can in 3ds max 2011, so if all else fails I'll try looking for some source for that script and see how they work their magic.
## Post #16
- Username: GoatSquared
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 29, 2011 10:43 am
- Post datetime: 2012-02-27T22:58:26+00:00
- Post Title: Re: [NOESIS] Titan Quest

Hey there, Demonsangel.  Are you using Tamschi's Toolbox/Viewer to get that bone data out?  If so, you might also want to look at [this thread](http://forum.xentax.com/viewtopic.php?f=16&t=6118) if you haven't already seen it.  It's for Blender 2.49b.  The importer that Szkaradek123 wrote works almost perfectly...except bones on the character/creature's right hand side get borked.  But only on the right hand side.  However everything else works well, for the most part.  Maybe it could help you out a little?
## Post #17
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-28T12:27:05+00:00
- Post Title: Re: [NOESIS] Titan Quest

Thanks, I'll have a look at it.

Edit: Win!


Turns out actually putting

```
BoneMat = BoneMat.__mul__(BoneMatP)
```

instead of

```
BoneMat.__mul__(BoneMatP)
```

helps.   

Now to implement textures and animations.
## Post #18
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-28T20:19:17+00:00
- Post Title: Re: [NOESIS] Titan Quest

For the textures, they're stored in a .tex file, would it be better to let the user convert these to .tga.jpg/psd or use the commandline option the textureviewer has to autoload the .tex files and auto output to .tga? (For the time being, I haven't researched the .tex format at all)
## Post #19
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-28T20:45:04+00:00
- Post Title: Re: [NOESIS] Titan Quest

If there is already an exe to convert the textures, yes, use the createprocess equivalent in python. Show us your mad skillz lol. Anything that makes our lives easier is a plus. There are some people around here who can't even use the command line lol. It's not a big thing for the person who wants a model or two from the game, but for the person who wants everything running cmd or drag and dropping thousands of tex files, ouch!
## Post #20
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-28T21:34:16+00:00
- Post Title: Re: [NOESIS] Titan Quest

Mhm, but I'm trying to see what would be the best approach for getting user input. Noesis doesn't have a Tkinter or tkFileDialog module so if Noesis doesn't have a native method for user input I'll have to include those modules or make users edit an ini manually. Or just tell them to put the TExtureViewer.Exe in a plugins\subFolder.
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-28T23:12:55+00:00
- Post Title: Re: [NOESIS] Titan Quest

Upload some of those tex files.
I would just ask users to convert the images and put it in a certain places.

And ya, I don't think many methods modify the original data just like that. Most of them return the desired values.
## Post #22
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-29T14:07:59+00:00
- Post Title: Re: [NOESIS] Titan Quest

[http://www.mediafire.com/?wvccjp1nlfy4vzu](http://www.mediafire.com/?wvccjp1nlfy4vzu)
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-29T15:35:31+00:00
- Post Title: Re: [NOESIS] Titan Quest

Looks like it just has a regular DDS file, except the DDS header has 0x52 at the end instead of 0x20.

```
dword numTex? 
byte null
dword imageSize
bytes[imageSize] <texture>

```
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-29T18:02:06+00:00
- Post Title: Re: [NOESIS] Titan Quest

Hmm I was wrong, it also includes all the mipmaps I think.
So you will have to parse the DDS header and get what you want.

Some sample code: [http://db.tt/THzrhex8](http://db.tt/THzrhex8)

Compare/contrast



Of course you can pursue alternative methods that run external programs if it seems more suitable.
## Post #25
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-29T18:48:26+00:00
- Post Title: Re: [NOESIS] Titan Quest

Was just about to post the same image xD.

[http://i.minus.com/ibkFVrL05gSyf4.png](http://i.minus.com/ibkFVrL05gSyf4.png)

For running the TextureViewer, Noesis doesn't run subprocess.Popen(), but I still have to try other methods.
This is going slow because I'm new at loading textures so even with knowing half the format I can't load them in Noesis yet.

It'd be wayyyyy easier if the plugins were in .py and not .dll.
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-29T19:30:11+00:00
- Post Title: Re: [NOESIS] Titan Quest

there are tons of samples to load textures in noesis whats the problem?
there are several .py examples of texture loading.
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-29T21:38:19+00:00
- Post Title: Re: [NOESIS] Titan Quest

All c++ plugins come with source.
## Post #28
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-29T23:50:57+00:00
- Post Title: Re: [NOESIS] Titan Quest

> Reply from chrrox
>
> there are tons of samples to load textures in noesis whats the problem?
there are several .py examples of texture loading.

Yea? can u extract Textures from here in Noesis?   

[http://www.4shared.com/rar/z9DNyfgf/Extraidos.html](http://www.4shared.com/rar/z9DNyfgf/Extraidos.html)

Ironman 2 x360.
## Post #29
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-03T17:30:07+00:00
- Post Title: Re: [NOESIS] Titan Quest

Here's some info on the animation frames that's currently not in the TQ.Animation.dll source:

Basically, each frame is an array of 14 32bit floats.

0, 1, 2: Position offset vector. Default: {0, 0, 0}
3, 4, 5: These seem to rotate the bone. The bone changes size if you use more than one. Default: {0, 0, 0}
6: No idea, but it has something to to with the rotation vector. Default: 1
7, 8, 9: Scaling factors for the individual axes. Default: {1, 1, 1}
10, 11, 12: These seem to shear the vertices around the bone's axes. Default: {0, 0, 0}
13: Seems to be a multiplier for the shearing values. Default: 1

The game uses float4x4 matrices in the shaders, so there's some way to calculate one from each frame. The transforms are relative to the parent bones.

[There's a lot of correlation between the values.](http://dl.dropbox.com/u/5013896/forum/graphs/index.html) (Each dot is an animation frame from the game.)

No guarantees for correctness, I found these by trial-and-error back when I had no clue about 3D maths.

Also, the coordinate space of the normal maps is the opposite of what is usually used. (You probably have to reverse the winding order too, if you haven't done so already.)
## Post #30
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-03T23:09:38+00:00
- Post Title: Re: [NOESIS] Titan Quest

Thanks man!

I'm still busy with the textures though, didn't have the time to work on it today.
## Post #31
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-04T17:10:43+00:00
- Post Title: Re: [NOESIS] Titan Quest

Ok, so Noesis can now load the .tex files (Tamschi's source was a great help!), but I do need some help on Noesis functions on how to load them more efficiently.

After loading the file into memory and correcting the data I don't know what to do with the raw ( DXT5 compressed) pixel data, so I basically write everything back into NoeBitStream, get the buffer from this load that bitstream asif it was a dds file.

```
		file=NoeBitStream()
		file.writeBytes(b"\x44\x44\x53\x20")
		file.writeBytes(noePack("<1i",self.header.DefaultSize))
		file.writeBytes(noePack("<1i",self.header.Flags))
		file.writeBytes(noePack("<1i",self.header.Height))
		file.writeBytes(noePack("<1i",self.header.Width))
		file.writeBytes(noePack("<1i",self.header.LinearSize))
		file.writeBytes(noePack("<1i",self.header.Depth))
		file.writeBytes(noePack("<1i",self.header.MipmapCount))
		file.writeBytes(noePack("<11i",*self.header.Reserved1))
		file.writeBytes(noePack("<1i",self.header.PixelFormat.DefaultSize))
		file.writeBytes(noePack("<1i",self.header.PixelFormat.Flags))
		file.writeBytes(b"\x44\x58\x54\x35")
		file.writeBytes(noePack("<1i",self.header.PixelFormat.RGBBitCount))
		file.writeBytes(noePack("<1i",self.header.PixelFormat.RBitMask))
		file.writeBytes(noePack("<1i",self.header.PixelFormat.GBitMask))
		file.writeBytes(noePack("<1i",self.header.PixelFormat.BBitMask))
		file.writeBytes(noePack("<1i",self.header.PixelFormat.ABitMask))
		file.writeBytes(noePack("<1i",self.header.Caps))
		file.writeBytes(noePack("<1i",self.header.Caps2))
		file.writeBytes(noePack("<1i",self.header.Caps3))
		file.writeBytes(noePack("<1i",self.header.Caps4))
		file.writeBytes(noePack("<1i",self.header.Reserved2))
		self.header.Images[0].reverse()
		for l in range(self.header.Layers):
			for m in range(self.header.MipmapCount):
				file.writeBytes(self.header.Images[l][m])
		return file
```


```
tex = rapi.loadTexByHandler(buffer, '.dds')
	if tex: texList.append(tex)
```


So I have the data, now how do I "decompress" it or whatever I need to do so I could use this instead:

```
texList.append(NoeTexture("TQTex",dds.header.Width,dds.header.Height,dds.header.Images[0][10],noesis.NOESISTEX_RGBA32))
```
## Post #32
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-04T17:33:55+00:00
- Post Title: Re: [NOESIS] Titan Quest

I don't know if this works, but there are noesis.NOESISTEX_DXT1, noesis.NOESISTEX_DXT3 and noesis.NOESISTEX_DXT5 constants that you can use instead of noesis.NOESISTEX_RGBA32.
The format should be somewhere in the DDS header.

A few .tex files don't have reversed mip maps, so you have to check that flag to choose the right image.
## Post #33
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-04T18:54:45+00:00
- Post Title: Re: [NOESIS] Titan Quest

Noesis still crashes when trying to display the texture.

Edit: What am I doing wrong to load the texture in my model script? Neither the .dds/.tga/.tex work when trying the following:

```
mdl=rapi.rpgConstructModel()
matList=[]
texList=[]
material = NoeMaterial("AW01","")
material.setTexture("ancestralwarrior02.tga")
matList.append(material)
mdl.setModelMaterials(NoeModelMaterials(texList, matList))
mdl.setBones(self.bones)
mdlList=[]
mdlList.append(mdl)
```


The material is set in Noesis but no texture appears. After exporting the model to blender/3ds max the UV coordinates are correct.
## Post #34
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-06T16:17:44+00:00
- Post Title: Re: [NOESIS] Titan Quest

Tamschi, I'm having trouble understanding the function you sent to get the vertex weight, especially with the info about shaders. Couldn't I just get the vertex weight out of the vertex data?
## Post #35
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-06T16:37:02+00:00
- Post Title: Re: [NOESIS] Titan Quest

> Reply from Demonsangel
>
> Tamschi, I'm having trouble understanding the function you sent to get the vertex weight, especially with the info about shaders. Couldn't I just get the vertex weight out of the vertex data?

No, that won't work. The bone indices in the vertex data map to the bone slots in the draw call, not the bone array.

For each vertex, you have to find the draw call that uses it and change each bone index in the vertex' weights so that

newBoneIndex = boneListInDrawCall[oldBoneIndex];

If you want to export the mesh, you have to make sure that there aren't more than 27 bones in each draw call's bone list, otherwise Titan Quest and the Viewer crash with an invalid memory access.

The skinning shaders all take exactly 27 matrices for bone transformations. Any more than that and there's an array overflow in the animation code.
## Post #36
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-06T19:08:33+00:00
- Post Title: Re: [NOESIS] Titan Quest

Would it be alright for me to adjust the current NoeBones' indexes (using NoeBone.index) to match the index in the drawcall? I parented them via bonenames and not indexes.
Or would this be asking for disasters to happen.
## Post #37
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-06T19:24:00+00:00
- Post Title: Re: [NOESIS] Titan Quest

If there is more than one draw call, the same bone id in the vertex weights can point to different bones. You really need to edit the weights to make it 100% compatible.

A bone id of 255 in the vertex weights means no bone, but the weight value isn't always 0.0 if the id is 255.
## Post #38
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-06T19:45:50+00:00
- Post Title: Re: [NOESIS] Titan Quest

So if I get it right I need to parse the drawcalls.

For each drawcall I need to know which triangles it uses and for each triangle which vertices it uses.
These vertices then belong to the current drawcall and the current drawcall's bonelist?

I need then need to use the boneindex listed in the vertexdata use it to get the correct actual bone index by using the drawcalls bonelist.

Who comes up with this stuff.
## Post #39
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-06T20:01:14+00:00
- Post Title: Re: [NOESIS] Titan Quest

It makes perfect sense if you only want to push the mesh to the GPU. Otherwise you'd have to rearrange the weights each time the mesh is loaded into the game.
## Post #40
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-06T23:04:41+00:00
- Post Title: Re: [NOESIS] Titan Quest

I only just now noticed this thread. It's pretty common for games to use a per-draw bone palette. Bullet Witch does too. You can look at the Bullet Witch Python script with Noesis to see how that's managed, there's already an existing function to let you feed your bone palette into the Noesis RPG interface so you don't even have to deal with mapping the indices yourself.

Also, it looked to me like you ended up doing your own hierarchical bone transforms for the skeleton. You can let Noesis do that for you too. Just set up your NoeBones with standard parent-relative matrices and then call rapi.multiplyBones. (syntax is "boneList = rapi.multiplyBones(boneList)")
## Post #41
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-09T18:04:01+00:00
- Post Title: Re: [NOESIS] Titan Quest

I have a mesh with 2 drawcalls
1) 3041 faces, 27 bones
2) 323 faces, 7bones

My importer errors out when trying to parse vertex 5422 (and others following it)
vertex 5422 belongs to face 3065 which means the second drawcall.
vertex 5422's boneindices are (0,12,4,255) and weights(0.84,0.12,0.04,0)

 So this vertex is asking for bone index 12 in drawcall 2 but there are only 7 indices and the weight for the bone is not zero.

What went wrong?
## Post #42
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-09T18:37:42+00:00
- Post Title: Re: [NOESIS] Titan Quest

Wich one is it? I'll try to open it in MeshView.
## Post #43
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-09T19:12:14+00:00
- Post Title: Re: [NOESIS] Titan Quest

ancestralwarrior01a.msh 
[http://www.mediafire.com/?szc8862k1886s1b](http://www.mediafire.com/?szc8862k1886s1b)
## Post #44
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-09T19:42:09+00:00
- Post Title: Re: [NOESIS] Titan Quest

Face 3065 is {3538, 3537, 3526}.
## Post #45
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-09T19:47:55+00:00
- Post Title: Re: [NOESIS] Titan Quest

Means I can calculate all the triangles myself as well, Noesis gives me Tri 3065(5421,5422,5423)

Edit: okies that worked so far.
## Post #46
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-09T19:57:59+00:00
- Post Title: Re: [NOESIS] Titan Quest

That's a pretty big difference in indices they're storing...
Did you release any code?
## Post #47
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-09T20:07:19+00:00
- Post Title: Re: [NOESIS] Titan Quest

Not yet, both the .tex and .msh files are 1 big pile of unorganized code atm 

I did get the triangles after rapi.constructmodel with Triangles = mdl.meshes[0].indices though, instead of the raw triangles.
## Post #48
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-09T20:55:53+00:00
- Post Title: Re: [NOESIS] Titan Quest

Hmm that's interesting actually. I would've thought both methods should ideally produce the same results, given the same index buffer lol
## Post #49
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-09T21:04:42+00:00
- Post Title: Re: [NOESIS] Titan Quest

Ok so I corrected all the boneindices for the weights and turned it back into bytes using struct.pack

then called 

```
rapi.rpgBindBoneWeightBufferOfs(self.vertBuff, noesis.RPGEODATA_FLOAT, self.vertLength, self.boneWeightOffset, 4)
```


weightIdx = 6015 vertices * 4 indices length worth of bytes. I checked it and It has the correct length and data
self.vertBuff is the global buffer I also used for my UV/XYZ/normals so this should be correct , including the Offset.

This is called after my UV/XYZ/normal/tri's but before my

```
if not mdl.meshes[0].weights: print("you fail")
mdl.setModelMaterials(NoeModelMaterials(self.texList, self.matList))
mdl.setBones(self.bones)
mdlList=[]
mdlList.append(mdl)
```


but nothing happens. What's the format for the weightList? I'll create it myself if needed.
## Post #50
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-09T21:25:10+00:00
- Post Title: Re: [NOESIS] Titan Quest

> Reply from Demonsangel
>
> Ok so I corrected all the boneindices for the weights and turned it back into bytes using struct.pack
rapi.rpgSetBoneMap is provided specifically so that you don't have to do that...

> Reply from Demonsangel
>
> but nothing happens.
Make sure you're binding your vertex weight buffers before you actually commit the triangles. If you aren't seeing weight influences at all, you aren't doing things in the right order, or the data you're feeding in is invalid. I'm just assuming the order you're doing things in is likely to be the problem, because it was your problem with the materials, and I'm forced to make assumptions because you've only posted snippets of your whole script.

> Reply from Demonsangel
>
> What's the format for the weightList? I'll create it myself if needed.
It's not needed. Using the rpg interface is cleaner, simpler, and more computationally efficient. (much the same as remapping bone indices in Python yourself is also far slower than using rpgSetBoneMap)
## Post #51
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-10T10:33:00+00:00
- Post Title: Re: [NOESIS] Titan Quest

is rapi.rpgSetBoneMap able to hold 2 lists and how do I make the vertices pick the correct list?

In other words how do I put the info in the following image into  a bonemap?


What is the index for "nobone" for noesis rpgBindBoneIndexBufferOfs? In the .msh a weight of 0 or an index of 0xFF means nobone, but I have been binding these to the rootbone instead.

And it seems something has to be wrong with the data because the order is right, but only the root bone(MOVEAXIS) and the 2 claviculae are being added to the skin modifier.

And since you want the full code: they're attached below.
I haven't rewritten it yet so it's a mess with a lot of redundant code.

[https://www.dropbox.com/sh/7pn17bxhwo9gwgu/cORIt1nsc_](https://www.dropbox.com/sh/7pn17bxhwo9gwgu/cORIt1nsc_)
## Post #52
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-10T20:10:08+00:00
- Post Title: Re: [NOESIS] Titan Quest

How would I go about adding multi .msh file monsters?
For instance the automai has a body and a head. Both have a bone named "Bone_Neck01". How do I make these play nice?

As far as I can tell the Position info for the bone is the same, but the bone in the head.msh is "parented" to 1 which is root and I assume I'm supposed to 'update' the bonelist by just adding the new bone( Bone_head) to the already existing Bone_Neck01.

Tamschi, do you happen to know in what file the link is between both meshes? I assumed it's in the actual ingame monster data since there are 3 mesh files:(body + 2 heads) which allows for variety.
## Post #53
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-10T20:40:07+00:00
- Post Title: Re: [NOESIS] Titan Quest

There's a Bone_Head in the body mesh too. I'm pretty sure you can just use the bones from the body mesh and only use the data from the attached mesh for the bone map.

It's the same with helmets and most armor. Weapons are attached to the AttachPoints from the text data instead.
## Post #54
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-10T21:55:41+00:00
- Post Title: Re: [NOESIS] Titan Quest

Then I have a look in how to import more than 1 mesh and make sure the torso goes in first.
## Post #55
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-10T21:58:56+00:00
- Post Title: Re: [NOESIS] Titan Quest

it should not matter what mesh gets imported first.
what i did for rumble roses which is the same is just import all the files in a folder.
then as you import the model you will have access to all the bones and won't have to create the bone that exists already again.
just on bone creation check if it exists before creating it and if it does exist just add it to your bone list instead of re creating it.
## Post #56
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-10T22:05:29+00:00
- Post Title: Re: [NOESIS] Titan Quest

I'll try that, though I need to seriously rewrite the script before I can do anything like that.
Thanks.
## Post #57
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-11T00:58:31+00:00
- Post Title: Re: [NOESIS] Titan Quest

You don't need 2 lists, it only applies to the current draw. You call rpgSetBoneMap for each draw every time you commit triangles. The list is a map that converts the per-vertex bone index to an index into the global bone list.

There should never be a vertex without a bone weight. If you want something that's static and not weighted to any part of the main skeleton, you should create a new bone for it outside of the main hierarchy and weight that static stuff to that, or just split it into a separate NoeModel with no skeleton. Or, don't bind vertex weight buffers at all, but that will require faces with no weights to be drawn in their own draw calls. No format should ever really be using static/boneless verts in the same mesh as weighted verts unless it's already internally assigning them to a bone/matrix with an assumed weighting of 1.0, because that would screw up any kind of shader/hardware transform path.
## Post #58
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-11T09:36:44+00:00
- Post Title: Re: [NOESIS] Titan Quest

Not really vertices without any weights, but with boneindices like (10,255,255,255). I'm not sure if the weights for all the 255 are zero so it might try to add the vertex to a nonexisting bone along with the bone #10, unless Noesis treats 255 as nobone as well?
But I'll make it loop over the data first to see if it does this before I start worrying over this.

For the drawcalls, I'll split the triangle list into 2 (which should be easy) and commit them seperately, but what do I do with the vertex list, can I keep committing them as 1 big list?
## Post #59
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-11T12:07:59+00:00
- Post Title: Re: [NOESIS] Titan Quest

read them as signed numbers and the 255 will be -1 instead of 255.
## Post #60
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-11T12:45:18+00:00
- Post Title: Re: [NOESIS] Titan Quest

That's what I was doing at first but changed it back to normal.

While rewriting the script it seems rapi.multiplyBones doesn't position the bones correctly so I'm just going to rewrite my current function and if someone could take a look at it later it'd be much appreciated.

Edit:[https://www.dropbox.com/sh/7pn17bxhwo9gwgu/cORIt1nsc_](https://www.dropbox.com/sh/7pn17bxhwo9gwgu/cORIt1nsc_)
Updated the texture importer to correctly load all textures for each drawcall.

Vertex-Boneweight seems to be correct atm but I'm calling the bindboneIndex/Weight on the full vertex list

```
rapi.rpgBindBoneIndexBufferOfs(self.vertBuff, noesis.RPGEODATA_UBYTE, self.vertLength, self.boneIndexOffset, 4)
rapi.rpgBindBoneWeightBufferOfs(self.vertBuff, noesis.RPGEODATA_FLOAT, self.vertLength, self.boneWeightOffset, 4)
rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx*3, noesis.RPGEO_TRIANGLE, 1)

```

for each drawcall because I'm not sure how to cut the vertex list.

Also how would I go about loading bumpTextures?
which of the following is a bumptex?
```
def setSpecularTexture(self, texName):
def setOpacityTexture(self, texName):

```
## Post #61
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-11T19:24:25+00:00
- Post Title: Re: [NOESIS] Titan Quest

multiplyBones performs a hierarchical transform for the bones. If your matrices aren't parent-relative or your hierarchy isn't fed to Noesis correctly, it won't give you the results you're looking for.

Noesis will automatically recognize that 255 is an invalid bone index if it's out of range and you're using noesis.RPGEODATA_UBYTE as the data type when binding your bone index buffer.
## Post #62
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-11T19:34:00+00:00
- Post Title: Re: [NOESIS] Titan Quest

Guess I'll have to play around with it and see what works.

I tried loading 2 files into noesis which it does by creating a .noesis file

```
version 1
physicslib      ""
defaultAxis      "0"
sharedAnims      "1"

object
{
   model      "monster\automatoi\automatoi01.msh"
   offset      "(0 0 0)"
   rotate      "(0 0 0)"
}

object
{
   model      "monster\automatoi\automatoiheada.msh"
   offset      "(0 0 0)"
   rotate      "(0 0 0)"
} 

```

It imports them correctly but creates a different boneset for each of them. Can I force them to use a joined boneset through the .noesis file or do I have to do it in the .msh script?
## Post #63
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-12T12:55:35+00:00
- Post Title: Re: [NOESIS] Titan Quest

Tamschi: For the drawcalls is it defined somewhere when I'm supposed to read bone indices? Some files don't have bones and so they skip that part. I'm thinking of looping through the entire file once listing all the sections and then seeing if there's a section 6 for bones in the file, but if it's defined somewhere that might be better.
## Post #64
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-13T00:14:24+00:00
- Post Title: Re: [NOESIS] Titan Quest

There isn't a shared skeleton option. I could probably add that functionality without too much effort, though, if you can guarantee that the skeletons match in bone counts and order.
## Post #65
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-13T01:37:00+00:00
- Post Title: Re: [NOESIS] Titan Quest

> Reply from Demonsangel
>
> Tamschi: For the drawcalls is it defined somewhere when I'm supposed to read bone indices? Some files don't have bones and so they skip that part. I'm thinking of looping through the entire file once listing all the sections and then seeing if there's a section 6 for bones in the file, but if it's defined somewhere that might be better.

I don't think there is a flag, but the bone map in the draw call has length 0 if the mesh isn't skinned. The vertices shouldn't have weight or bone information either; I can't check anything currently though, because I managed to wreck my Visual Studio installation.

It's possible that the game gets some information from the shader files. They seem to be a list of flags and shader code, but I don't know how to read them.
## Post #66
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-13T12:28:51+00:00
- Post Title: Re: [NOESIS] Titan Quest

Currently I'm looping over the file and if Section 6(bones) the Size UInt() has a  size of 4bytes or less I know there is no bonemap.
But I could try and see if the vertex data always precedes the drawcalls and see if the vertex data has bone info.

MrAdults: the models do not have the same amount of bones, it's usually a main file (torso+arms+legs) and then a seperate file (body armor / head / helm / weapon) and these contain only a few of the bones the "main" file has.

I assume "shared skeleton" means the models have to be in 1 "mdl" else each mdl will have its own boneset, so I was thinking of just going through all files at once and adding all the vertex/bone/triangle data to buffers and doing them all at once. Though I don't see how I would do the bonemaps then, unless I try adjusting them to contain the correct link to the main boneset and then committing the bonemap.
## Post #67
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-14T17:41:29+00:00
- Post Title: Re: [NOESIS] Titan Quest

For loading multiple models into 1 mesh, would it be best to just load all the .msh files in a folder or to create a new sort of file like the .noesis (eg .msh.ini) and tell noesis which models to load from that/a folder based on the ini?
## Post #68
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-14T21:48:20+00:00
- Post Title: Re: [NOESIS] Titan Quest

I bet the game already has data formats which hook all those mesh pieces together and tell where they're bolted and such in varying character configurations. Using that data to decide which mesh files to load into a single model would be the best solution.

Barring that, just take whichever approach makes sense I suppose. If all mesh files in a folder together are meant to go together in a single model, then I would have the script load all meshes in the folder. Otherwise, if you have situations where it isn't appropriate to do that, I would offer the option of letting people use .noesis files, or yeah, you could roll your own .noesis-like file and have them load that if you want. I would go with whichever viable solution requires the least amount of user effort. That's my general design rule for everything in Noesis, even though my laziness sometimes overrides it.
## Post #69
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-15T17:20:30+00:00
- Post Title: Re: [NOESIS] Titan Quest

[https://www.dropbox.com/sh/7pn17bxhwo9gwgu/cORIt1nsc_](https://www.dropbox.com/sh/7pn17bxhwo9gwgu/cORIt1nsc_)
TQ_MUL.py (needs TQ_Tex.py to load .tex files)
Loader.mshini

```
path=malepc01.msh
offset=0,0,0
rotate=1,1,1
```


Loader.mshini

```
path=malepc01.msh
offset=0,0,0
rotate=1,1,1
[MODEL1]
path=c_torso08m.msh
offset=0,0,0
rotate=1,1,1
```



For now you can only add meshes that are in a subfolder where the *.mshini is located but the textures won't load because the script currently only looks in the .mshini folder for them.

[MAIN] is the root model which contains the complete armature, so for now make sure you put these meshes first.

Loading torso armor meshes can cause an error because I'm still using my own Parenting function which errors out on these.

This is still a WiP so todo:
[*] Add bones from meshes that aren't yet in the global armature and hopefully disable the need for a MAIN model.
[*] Enable the translation to actually do something (mostly for weapons).
[*] Support both relative and absolute Path to Meshes and their Textures.
[*] Whatever comes up.
## Post #70
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-16T16:22:06+00:00
- Post Title: Re: [NOESIS] Titan Quest

Was trying to get weapons to be imported at the correct offsets according to left or right hand. Figured this info would be stored into the .mif files.

weapon.mif holds:

```
{
    name   = "L Hand"
    parent = "Bone_L_Weapon"
    origin = (0.000000, 0.000000, 0.000000)
    xAxis  = (1.000000, 0.000000, 0.000000)
    yAxis  = (0.000000, 1.000000, 0.000000)
    zAxis  = (0.000000, 0.000000, 1.000000)
}
AttachPoint
{
    name   = "R Hand"
    parent = "Bone_R_Weapon"
    origin = (0.000000, 0.000000, 0.000000)
    xAxis  = (1.000000, 0.000000, 0.000000)
    yAxis  = (0.000000, 1.000000, 0.000000)
    zAxis  = (0.000000, 0.000000, 1.000000)
}
```


the body mesh.mif holds (along with a loooooot more):

```
{
    name   = "L Hand"
    parent = "Bone_L_Weapon"
    origin = (0.000000, 0.000000, 0.000000)
    xAxis  = (1.000000, 0.000000, 0.000000)
    yAxis  = (0.000000, 1.000000, 0.000000)
    zAxis  = (0.000000, 0.000000, 1.000000)
}


RigidBodyDescription
{
    parentName = "Bone_L_Wrist"
    childName = "Bone_L_Finger01"
    parentOrigin = (-0.061454, 0.003351, -0.001135)
    parentXAxis  = (1.000000, 0.000000, 0.000000)
    parentYAxis  = (0.000000, 1.000000, 0.000000)
    parentZAxis  = (0.000000, 0.000000, 1.000000)
    childOrigin = (0.061453, -0.003351, 0.001135)
    childXAxis  = (0.997545, -0.017286, -0.067870)
    childYAxis  = (-0.067860, 0.001176, -0.997694)
    childZAxis  = (0.017326, 0.999850, 0.000000)
    extents = (0.090000, 0.160000, 0.190000)
    collides = "false"
    density = "50.000000"
    playFallSound = "false"
    FusedBone
    {
        name = "Bone_L_FingerPoint01"
        origin = (0.061997, 0.005730, 0.069628)
        xAxis  = (0.971893, -0.016841, 0.234819)
        yAxis  = (0.234783, -0.004069, -0.972039)
        zAxis  = (0.017326, 0.999850, -0.000001)
    }
    FusedBone
    {
        name = "Bone_L_Thumb01"
        origin = (-0.036732, -0.016195, 0.082482)
        xAxis  = (0.615897, -0.010672, 0.787755)
        yAxis  = (0.787637, -0.013648, -0.615989)
        zAxis  = (0.017326, 0.999850, -0.000001)
    }
    FusedBone
    {
        name = "Bone_L_Weapon"
        origin = (0.022023, -0.037607, 0.015022)
        xAxis  = (0.999889, 0.014922, 0.000000)
        yAxis  = (0.014922, -0.999889, 0.000001)
        zAxis  = (0.000000, 0.000000, -1.000000)
    }
}
```


The offsets given for the FusedBone "Bone_L_Weapon" are the same as the actual bone offsets given in the bone data.
Would this mean I'd best put a "rpgSetPosScaleBias" with the bone's absolute position and axis as data?

I also found some 

```
{
    rigidBody0 = "17"
    rigidBody1 = "21"
    jointType = "universal"
    jointConnection = "1"
    jointAxis0 = "y"
    loStop0 = "-2.128240"
    hiStop0 = "2.671010"
    jointAxis1 = "z"
    loStop1 = "-1.775452"
    hiStop1 = "-0.982813"
    breakable = "false"
    breakChance = "0"
}
```


But don't really know what it does. If anyone has seen anything like this before and could shed some light on the subject it'd be much appreciated.

Then, for animations I get 3 floats for XYZ and 3 floats for axis, but NoeAnim wants a 4*3 matrix. are the axis floats Euler Angles and do i need to "decode" them or something?
## Post #71
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-17T09:30:29+00:00
- Post Title: Re: [NOESIS] Titan Quest

The only things that should matter for weapon attachments are the AttachPoint values in the body mesh. It's basically just another bone that marks the origin of the attached entity.
The matching attachment point in the weapon mesh may be an additional transformation. I don't know anything about that though.

The RigidBodyDescription is only for ragdoll physics. It describes a box that can be simulated more efficiently and the transformations for the mesh that is animated along with the physics ragdoll. The density should be for floating in water, mostly.

The JointDescription is only a ragdoll joint. It's probably not important for animation, but it limits ragdoll movements. There's something very similar in the Source engine's smds.
## Post #72
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-18T07:31:38+00:00
- Post Title: Re: [NOESIS] Titan Quest

> Reply from Demonsangel
>
> Then, for animations I get 3 floats for XYZ and 3 floats for axis, but NoeAnim wants a 4*3 matrix. are the axis floats Euler Angles and do i need to "decode" them or something?
I think Tamschi answered everything but this. (not sure about the accuracy of his answers, but I couldn't answer definitively either, although I know density typically affects a lot more than just water behavior, it affects all forces being applied to the object including gravity in most physics engines) For angles, you can use NoeAngles and convert that to a NoeMat43 using one of the provided conversion functions. Or if your angles are in a convention that doesn't have a method exposed for it (I need to address that at some point) you can do it manually. Something like:

```
m = m.rotate(angles[0], NoeVec3(1.0, 0.0, 0.0))
m = m.rotate(angles[1], NoeVec3(0.0, 1.0, 0.0))
m = m.rotate(angles[2], NoeVec3(0.0, 0.0, 1.0))
```


You'll have to change the rotation order based on which convention your angles are using. People use all kinds of varying conventions when it comes to Euler angles, but XYZ is most common, so I would try that NoeAngles conversion function first and see if it saves you the trouble.
## Post #73
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-18T10:10:25+00:00
- Post Title: Re: [NOESIS] Titan Quest

You're right, I didn't notice that there was no "mass" parameter.

The animations don't use Euler angles, at least not directly.
I at some point had a program to output an animation where one bone's rotation values would increase at different speeds and the bone was rotating around the axes but also stretched along its axes prior to rotation.

Each frame for each bone in the animations is actually 14 floats: 3 for position, 3 for scaling and 2 * 4 floats that somehow are involved with rotation and shearing but can also scale the bone.
## Post #74
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-21T21:19:29+00:00
- Post Title: Re: [NOESIS] Titan Quest

Oh, k. I'll try out some stuff and see what happens.
Been occupied so I only fixed some tiny bugs.
## Post #75
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-22T17:46:46+00:00
- Post Title: Re: [NOESIS] Titan Quest

For NoeAnim the matrices, would it be for example for a 3bone 2 frame animation:
bone1 bone2 bone3 bone1 bone2 bone3 or bone1 bone1 bone2 bone2 bone3 bone3
## Post #76
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-22T20:54:05+00:00
- Post Title: Re: [NOESIS] Titan Quest

> Reply from Demonsangel
>
> bone1 bone2 bone3 bone1 bone2 bone3
That one.
## Post #77
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-23T18:50:54+00:00
- Post Title: Re: [NOESIS] Titan Quest

I'm oblivious as what I'm supposed to be doing with the animations.
I basically read the positions and angles and put them into a mat43.

create the animation: NoeAnim("walk", self.bones, numFrames, frameMat, FPS)

and it comes out like this

So I figured I was doing my Mat43's wrong and started multiplying them, the first frame I multiplied with the matrix of the bones. The following frames I multiplied with the previous frame.
First frame came out like this:


Changing the angles doesn't seem to actually effect anything significant atm.

Don't know if it'll help but here's the raw position info for the first frames

```
(0.14962191879749298, -0.00534363929182291, -2.316098424159918e-09)
(-9.8387658908905e-08, 1.387635872873716e-08, 3.293631711223828e-14)
(5.372397637870563e-08, -6.738577251752531e-09, -1.0794913140460549e-13)
(1.9564912179248495e-07, 2.4569342116365078e-08, 4.960473763519768e-13)
(-4.312672530204509e-08, -5.385255619216878e-08, 3.333727066102965e-13)
(3.496630895938324e-08, 6.641565519771575e-09, 2.379064056867719e-09)
(2.7545311809262785e-08, 3.905058054698429e-09, 3.860357034035644e-10)
(0.03554629907011986, 0.08017075806856155, -7.877627439256685e-08)
(-1.8355015640736383e-07, 2.4650452346008933e-08, 1.937892051273593e-07)
(2.1736765276614278e-08, 3.062447007096125e-08, -1.6018371695736278e-07)
(0.035993222147226334, 0.07500851899385452, -7.446584238124387e-09)
(-4.413537091352282e-09, -1.9153316088704742e-07, 2.1141575246019784e-07)
(5.3303590874520523e-08, -1.1442565117647518e-08, -6.808340202724139e-08)
(-5.941072522830382e-09, -7.996898254702955e-09, -2.3549111105580778e-08)
(1.481507894141032e-07, -1.1377987618743646e-07, -1.3762331718680798e-07)
(1.0442823139555912e-07, -7.164797466430173e-08, -3.856521005318747e-12)
(1.521200516663157e-07, -1.0614267154096524e-07, -1.4187689600930753e-07)
(-6.125354445885023e-08, -3.9537052742844025e-08, 1.1431549751250714e-07)
(-3.084172917056094e-08, -3.3520187514568534e-08, 6.005618047311145e-08)
(2.682209014892578e-07, -1.9424078345764428e-07, 1.7329865542592415e-08)
(8.940696716308594e-08, -2.754945569449774e-07, 8.612432367272049e-08)
(9.019845492730383e-08, 8.471759116446265e-08, 9.43741866876735e-08)
(4.3218520318077935e-08, -3.6637638345382584e-07, 7.605304119806533e-08)
```
## Post #78
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-03-23T20:08:01+00:00
- Post Title: Re: [NOESIS] Titan Quest

The animations should transform the existing bones for each frame.

To play an animation, a program has to do the following:

1. Transform all vertices with the inverse bone matrix so the bones all equal the unit vector. (Noesis already does this, judging by the screenshots.)

The mesh resulting from step 1 is constant, so this is usually the one uploaded to the graphics card.

2. Transform all vertices with the transformed bone matrix to get the skinned mesh in object space.

In this case:

boneTransform = transformationFromAnimation x untransformedBone.

boneToObjectSpaceTransform = parentBoneToObjectSpaceTransform x boneTransform

vertexInObjectSpace = sum(boneWeight * boneToObjectSpaceTransform x vertexFromStep1)



It's possible that a boneToScreenSpaceTransform (= objectToScreenSpaceTransform x boneToObjectSpaceTransform) is used, as this is a constant for each rendered frame.
Titan Quest seperates them though, at least in the uniform parameters. Step 3 would be vertexInScreenSpace = objectToScreenSpaceTransform x vertexInObjectSpace in this case.

There's a similar calculation for the vertex in world space, wich is used for lighting, as well as for the normals. I'm pretty sure the normal calculation can be combined with the position calculation if matrices are used, I don't know how TQ does it though. (I can't read shader assembly.)


Anyway, what's missing are these calculations from step 2:

boneTransform = transformationFromAnimation x untransformedBone.

boneToObjectSpaceTransform = parentBoneToObjectSpaceTransform x boneTransform

I couldn't find the documentation, but this is extremely common, so it's possible that it's supported by Noesis.
## Post #79
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-24T02:59:44+00:00
- Post Title: Re: [NOESIS] Titan Quest

Looks like the animation matrices need to be multiplied against the bone matrix or some kind of base yeah, but Noesis still wants animation matrices in parent-relative space. So most likely you want correctedBoneMatrix * inverseCorrectedParentMatrix. As to how to get correctedBoneMatrix, that's up to the peculiarities of TQ. I know nothing about its data so I can't really help out there. The first shot is what makes me say those matrices need to be based on something else, they don't look like they're in the same scale as the vertices/base skeleton, and animation matrices are already part of the hierarchical transform Noesis-side during rendering so you should not feed anim matrices to Noesis in model space. Bone matrices should be in model space though, as I mentioned a little while ago in this thread, that's an intentional difference between model bone matrices and animation bone matrices.
## Post #80
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-24T14:35:59+00:00
- Post Title: Re: [NOESIS] Titan Quest

Yeah, this is chinese to me. I can't even create an animation that keeps pose mode/doesn't move or rotate the bones.

Also, when exporting to .dae to 3ds max (second screenshot) i noticed the rootbone was scaled to 39% but I didn't actually scale anything?
## Post #81
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-24T19:58:28+00:00
- Post Title: Re: [NOESIS] Titan Quest

A lot of COLLADA importers automatically scale on import. Some of them you can instruct not to do so, some of them you can't. I've become kind of frustrated with the whole situation there and started using FBX in place of COLLADA, but then you have another set of issues to deal with. Hopefully the upcoming semi-rewrite of the FBX SDK and resulting semi-update of the FBX standard will result in FBX support sucking significantly less everywhere. (but my experience with Autodesk sadly leads me to believe it will lead to FBX support sucking significantly more everywhere, for another 3-4 years until they finally manage to make it almost work like it should, shortly before deciding on another major architectural change that destroys everything all over again)
## Post #82
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-03-24T20:04:10+00:00
- Post Title: Re: [NOESIS] Titan Quest

I thought about that, but I noticed, like in the second screenshot how all the mesh parts are so seperated. When I imported it into 3ds max it looked the same as in the screenshot and when I scaled them back to 100% they just need a bit of rotation/positioning and it was okish.

So I'm not sure if it's me doing anything wrong or if it's the .dae importer, but i'll have a look for the scaling option if it's there.
## Post #83
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-04-21T06:14:29+00:00
- Post Title: Re: [NOESIS] Titan Quest

I've got the complete animation frame format now (all values in bone space and not premultiplied):

```
Vec4    Rotation1 (xyzw Quaternion)
Vec3    Scale (xyz)
Vec4    Rotation2 (xyzw Quaternion)
```
## Post #84
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-04-21T17:18:12+00:00
- Post Title: Re: [NOESIS] Titan Quest

Thanks, but I'm not experienced enough with bones/animations. Having a hard time figuring it out.
Same for another format I'm working on, I have all the data, I just don't know what to add/mul/sub/div with what.
## Post #85
- Username: Tamschi
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 26, 2011 4:43 am
- Post datetime: 2012-04-21T18:09:48+00:00
- Post Title: Re: [NOESIS] Titan Quest

Here's the link to the site that made me finally understand quaternions today: [http://iquilezles.org/www/articles/quat ... rnions.htm](http://iquilezles.org/www/articles/quaternions/quaternions.htm)

The data from the animations is in joint space as far as I can tell and not parent-relative, so you have transform (multiply) it with the bone matrix from the mesh to make it parent-relative in the end.

The multiplication order depends on the python environment and matrix alignment, so I don't know whether it's right-to-left or left-to-right.

The frames are independend, so don't multiply them with previous ones.

As MrAdults already said, the bone matrix construction depends on the game, so you'll have to experiment with the order you apply the transformations from the animation frame in.
## Post #86
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-04-22T18:50:06+00:00
- Post Title: Re: [NOESIS] Titan Quest

I was already calculating the animations vs the bone matrices, but at a certain point my imagination just runs out of combinations to try.

But I'm guessing it's because I don't know how to correctly use the NoeAnim().
I checked the data for the root bone and it's first child. The matrix for the root stayed the same while for the child there was only a minor change on the x-offset. However the result was the bone being totally rotated around every axis. (Not even child-parent multiplied)
