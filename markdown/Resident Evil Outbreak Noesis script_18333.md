## Post #1
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-07T19:19:19+00:00
- Post Title: Resident Evil Outbreak Noesis script

Hi everyone, I'm looking for help importing REO Models in noesis.

I have a noesis script but its Incomplete and only imports REO skeleton's at the moment so I'm looking for someone to help finish this noesis script. 
I uploaded some samples from REO here [http://www.mediafire.com/folder/jgti51rbb59pw/reo](http://www.mediafire.com/folder/jgti51rbb59pw/reo) . 

Also I didn't make this script.

```
import noesis
import rapi


def registerNoesisTypes():
	handle = noesis.register("Resident Evil Outbreak skeletons", ".AHI")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	noesis.logPopup()
	return 1



def noepyCheckType(data):
	f = NoeBitStream(data)
	if len(data) < 16:
		return 0
	return 1


def noepyLoadModel(data, mdlList):
	ctxt = rapi.rpgCreateContext()
	rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 0)
	f = NoeBitStream(data)
	
	boneList=[]
	
	unk1=f.read("i")[0]
	numBones=f.read("i")[0]
	fileSize=f.read("i")[0]
	unkA=f.read("4i")[0]
	for x in range(0,numBones-1):
		start=f.read("H")[0]
		unkB=f.read("H")[0]
		unkC=f.read("i")[0]
		boneSize=f.read("i")[0]
		boneID=f.read("i")[0]
		boneName="bone " + str(boneID)
		boneParent=f.read("i")[0]
		print (boneParent)
		boneParentName="bone " + str(boneParent)
		boneChild=f.read("i")[0]
		unkD=f.read("i")[0]
		scl=NoeVec3.fromBytes(f.readBytes(12))
		s4=f.read("f")[0]
		q=NoeQuat.fromBytes(f.readBytes(16))
		trans=NoeVec3.fromBytes(f.readBytes(12))
		t4=f.read(">f")[0]
		unkE=f.read("i")[0]
		unkF=f.read("i")[0]
		unkG=f.read("46i")[0]
		mtrx = q.toMat43(1)
		mtrx[0] *= scl
		mtrx[1] *= scl
		mtrx[2] *= scl
		mtrx[3] = trans
		
		if boneID==0:
			boneList.append(NoeBone(boneID+1, boneName, mtrx, None, boneParent))
		else:
			boneList.append(NoeBone(boneID, boneName, mtrx, None, boneParent))
	
		
		
		
	boneList = rapi.multiplyBones(boneList)
	mdl =  NoeModel()
	mdlList.append(mdl)
	mdl.setBones(boneList)
	
	
	rapi.rpgClearBufferBinds()
	
	return 23474868				#because I said so
```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-08T09:48:08+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from Steve666
>
> so I'm looking for someone to help finish this noesis script.i.e. a Noesis script that can import .amo meshes? (Don't want to be mean but I don't think that someone will write it.
Iirc Predator created a max script/tool to import Resident Evil 5 assets into 3dsmax. Maybe it supports amo, too.)

Anyways, you'll need someone to find out where's the bone ids and weights to be located, maybe in the amo file.

> Also I didn't make this script.Then who did?

I used Noesis to create an smd from the skeleton then imported it to blender:



P00_00_dkrl.jpg (92.59 KiB) Viewed 400 times
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-08T15:04:55+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> 
Anyways, you'll need someone to find out where's the bone ids and weights to be located, maybe in the amo file.
In the file "HE00_00.AMO" there is a data starting at 0x1B9CC, which I believe are bone ids and weights. The structure goes like this : number of entries / number of bones influencing the vertex (int), bone id (int), weight (float, 0 - 100 range).

Here is an example with 2 entries / bones.



re_bw.png (9.08 KiB) Viewed 389 times
## Post #4
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-08T18:56:46+00:00
- Post Title: Resident Evil Outbreak Noesis script

Thanks you akderebur for taking the time to help.
by the way i don't know how to write Noesis script so I still looking for help.

> Reply from shakotay2
>
> 
Steve666 wrote:Also I didn't make this script.Then who did? Its created by someone named "The dude" I found that script here [https://pastebin.com/kp1RgZNx](https://pastebin.com/kp1RgZNx)

> Reply from shakotay2
>
> 
I used Noesis to create an smd from the skeleton then imported it to blender: shakotay2 that method doesn't work on r0060100.AMO map files.
Also the nbdx_obj.exe doesn't export the r0060100.AMO map files correctly.
[Clipboard01.png](https://xentaxbackup.github.io/file/14579_Clipboard01.png)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-08T20:19:21+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from Steve666
>
> Its created by someone named "The dude" I found that script here https://pastebin.com/kp1RgZNx
Thanks, but I really don't get it why you removed this line from the script:
#Code is by TheDude

> Reply from Steve666
>
> shakotay2 wrote:
I used Noesis to create an smd from the skeleton then imported it to blender:
 shakotay2 that method doesn't work on r0060100.AMO map files.You should know that maps usually don't have skeletons (huuh?).
btw: there was no amo map file in your samples, was it?

edit/correction: okay, skeleton for a room, sounds funny:

> Reply from shadowmoy
>
> unsupported files are the AHI files that contain the scene bones /skeleton, in order to make the room look correct you need to load the ahi file and the bone id in each mesh block then transform/rotate the mesh according to the bone , same trick is used in re4 ps2 and pc version and maybe some other re games (not used in re5 or re6)

> Reply from Steve666
>
> Also the nbdx_obj.exe doesn't export the r0060100.AMO map files correctly.Use the quickbms script mentioned here: 
[viewtopic.php?f=16&t=9923&p=82047&hilit ... bms#p82047](http://forum.xentax.com/viewtopic.php?f=16&t=9923&p=82047&hilit=ResidentEvilOutbreak2AMOto3dsUV.bms#p82047)

(dunno whether it works with maps, though)
## Post #6
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-08T21:10:46+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> Use the quickbms script mentioned here: 
viewtopic.php?f=16&t=9923&p=82047&hilit ... bms#p82047

(dunno whether it works with maps, though)
I tried that method too, it doesn't export r0060100.AMO room files correctly either.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-09T08:22:08+00:00
- Post Title: Resident Evil Outbreak Noesis script

I see; it's required to apply skeleton data (translation from the smd file) to the submeshes, for example
  20 2925.000000 250.000000 5700.000000 0.000000 -0.000000 0.000000
(so x=2925.0 y=250.0 z=5700.0)
  21 2925.000000 199.999939 5250.000000 0.000000 -0.000000 0.000000

to 20.3ds and 21.3ds (benches) after import into blender.

Too busy atm to check it but should work for all 115 submeshes.
(SM 3 is the only one with rotation != 0 degrees, btw.)

(Seems there is some unwanted rotation with the quickbms 3ds creation, though, -90° counterclockwise related to x axis.
You could try to swap above y and z to circumvent his.)
## Post #8
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-09T18:30:22+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> I see; it's required to apply skeleton data (translation from the smd file) to the submeshes, for example
  20 2925.000000 250.000000 5700.000000 0.000000 -0.000000 0.000000
(so x=2925.0 y=250.0 z=5700.0)
  21 2925.000000 199.999939 5250.000000 0.000000 -0.000000 0.000000 Thanks shakotay2, that works.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-09T20:26:20+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from Steve666
>
> shakotay2 wrote:I see; it's required to apply skeleton data (translation from the smd file) to the submeshes, for example
  20 2925.000000 250.000000 5700.000000 0.000000 -0.000000 0.000000
(so x=2925.0 y=250.0 z=5700.0)
  21 2925.000000 199.999939 5250.000000 0.000000 -0.000000 0.000000
 Thanks shakotay2, that works.well, in which way does it work?

I made a blender python script to apply all 115 offsets and the meshes are not clumped any more but is this what it should look like?



r0060100-moved.jpg (127.32 KiB) Viewed 332 times

(I exchanged the applied offsets y and z but no improvement.)
About 12 parts were being "blasted away", i.e. sm 12 and sm 37 for example but dunno what the problem could be.
## Post #10
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-10T00:41:50+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> I made a blender python script to apply all 115 offsets and the meshes are not clumped any more but is this what it should look like? No its not supposed to look like that

> Reply from shakotay2
>
> in which way does it work? I copied the skeleton translation data on to one of the room meshes but that doesn't seem to work for all the room files

Didn't work for this room file.
[img]http://www.mediafire.com/convkey/44c1/ynqns4t9tt63gzrzg.jpg[/img]
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-10T13:48:10+00:00
- Post Title: Resident Evil Outbreak Noesis script

After I realized that blender's script generated sorted filelist spoils the indices it looks a little bit better (maybe one index off or something like that?):



REO1.jpg (54.28 KiB) Viewed 305 times

(I'd need an ingame screenshoot from that room to tell more.)
## Post #12
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-10T22:15:37+00:00
- Post Title: Resident Evil Outbreak Noesis script

I'm not sure what level that room is on. Also can you upload your blender script so i can try it out?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-11T10:09:09+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from Steve666
>
> Also can you upload your blender script so i can try it out?I need to find out the problem before (wouldn't like to release or pm scripts with stupid bugs  ).

Maybe you can send me your "best looking" room (blender screenshoot, *.amo and *.ahi file ) so that I can test the script?
## Post #14
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-11T18:24:14+00:00
- Post Title: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> Maybe you can send me your "best looking" room (blender screenshoot, *.amo and *.ahi file ) so that I can test the script? Okay, I uploaded the room file here [https://www.mediafire.com/folder/jgti51 ... i7vmde4uc8](https://www.mediafire.com/folder/jgti51rbb59pw/reo#gswi7vmde4uc8)
[img]https://www.mediafire.com/convkey/4bdf/oejtvjqcqtzqq3pzg.jpg?size_id=7[/img]
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-11T19:51:42+00:00
- Post Title: Resident Evil Outbreak Noesis script

well, seems you got it!   All I get is a mess, more or less. This is my nearest "hit":



R0150100.jpg (158.59 KiB) Viewed 268 times



> I copied the skeleton translation data on to one of the room meshes
Can you exactly explain that process, please?
## Post #16
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-11T22:32:58+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

> Can you exactly explain that process, please? The room skeleton and meshes are in the same order so just copy X,Y,Z translate from a skeleton to one of the meshes. Also that technique doesn't work for all of the room files. It takes way too long doing it that way, would prefer a import script.
[img]https://www.mediafire.com/convkey/f296/8r188164xhh1w21zg.jpg?size_id=7[/img]
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-12T16:07:07+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

> Reply from Steve666
>
> The room skeleton and meshes are in the same orderNope. For me they're not! (3ds files created with bms script).

That's the reason why I need your exact process of creating the meshes (sorry, when I was unclear).

> It takes way too long doing it that way, would prefer a import script.As soon as it works correctly you can have it.
## Post #18
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-12T18:43:02+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> Nope. For me they're not! (3ds files created with bms script).

That's the reason why I need your exact process of creating the meshes (sorry, when I was unclear). I thought you was creating an .amo and .ahi script for blender also blender 3ds import script would only work for one room file. 
I extracted the models with nbdx.exe and nbdx_obj_fix.exe.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-12T18:52:15+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

> Reply from Steve666
>
> Blender 3ds import script would only work for one room file.You mean, one 3ds file; this one is for multiple 3ds, the problem, as I wrote, is that it creates its "own order" (path needs adapting):

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows
path_to_3ds_dir = os.path.join('S:\\', 'REO\\r0060100')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_3ds_dir))

# get a list of files ending in '3ds'
obj_list = [item for item in file_list if item[-3:] == '3ds']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_3ds_dir, item)
    bpy.ops.import_scene.autodesk_3ds(filepath = path_to_file)
```

Then I tried it with an array list of files (1.3ds,.., 116.3ds) which were created by the bms script, but this order is wrong, too.

So I've to find out how to get the correct order maybe directly from the amo file?
## Post #20
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-12T18:59:58+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> So I've to find out how to get the correct order maybe directly from the amo file?
Yeah I think that would work
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-12T19:03:49+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

This one should work for you (R0150100 only) since you seem to have the correct mesh order in blender:
You need to find a method to get the bone positions into the arrays; i use 'C' so far, but the code/handling is not user friendly
edit: I've shifted the coords in the arrays by three to the left!

```
import os

xpos = [-100.000000, -700.000000, 700.000000, -700.000305, 760.000000, 0.000000, -0.027229, -3.536329, -2.081530, 2.326791, 3.596203, -0.000244, 0.069946, -765.113770, -20.000122, 762.751953, -635.709473, -640.251709, 727.946289, -785.405518, 0.000244, 0.000000, 0.000000, -0.000244, 0.000000, 0.000000, 0.000244, -177.846680, 0.000244, 0.000122, 49.999512, -137.598511, -137.587402, -89.009033, 18.950439, -1.169922, 352.408081, 105.000244, 84.999756, -351.997925, -104.822021, -85.878174, -525.005859, 525.004150, 0.001953, 609.675781, -612.512939, 0.003052, -0.000122, -186.250122, 186.249100, 288.609528, -2.849365, 0.000122, -582.205261, -599.000488, -599.000488, 599.002930, 599.002930, 1.706665, 164.398682, 0.000488, 49.999512, 4.201935, -50.000488, -575.000244, -654.387817, -652.080444, -575.000244, -384.999878, 0.001709, 385.000122, 575.000244, 600.000122, 600.001587, 575.000244, 684.881104, 684.881104, 684.881104, 684.881104, -725.284668, -725.284668, -725.284668, 413.934418, -701.876770, -701.876770, -701.876770, 8.344727, 667.232117, 667.232117, 667.232117, 667.232117, 2.430664, -490.494263, -620.652344, -681.873108, -569.835938, 455.013794, 455.013794, -709.293945, -142.530518, 124.498047, -136.929810, 0.000000, 0.071777, 0.333496, -38.095703, 0.000000, -57.500916, 0.055633, -0.925760, -3.120224, -0.925762, 2.624954, 2.624956, 0.000000, 0.000000, 0.000000]
ypos = [-300.000000, -400.000000, -300.000000, -299.999634, 100.000000, -300.000000, -305.598328, -306.488708, -307.886871, -307.825317, -306.358246, -296.068481, -143.611725, -49.999603, 262.500183, -30.821960, -237.015808, -165.977097, 217.744064, 217.602173, 672.012268, 63.583008, -50.249176, -99.999611, -257.304901, -244.999542, 85.000427, -202.499786, 525.000427, 102.388931, -307.499786, -250.712860, -236.057388, -168.191055, -172.121826, -301.830048, -258.406952, -258.406952, -308.406952, -258.406952, -258.406952, -308.406952, 150.000381, 150.000443, 150.000397, -73.584076, -73.411667, 42.717148, -187.499924, -118.406403, -118.406403, -82.249947, -149.999619, -375.314453, -350.588348, -189.387543, -145.033096, -150.681015, -206.776337, -147.736404, -299.000000, -6.364342, -339.499573, -298.999573, -530.276733, -495.723480, -543.960571, -450.000214, -347.461212, -449.999756, -450.000000, -449.999756, -395.723480, -449.999359, -480.276703, -495.723450, 300.152924, 300.152924, 300.152924, 300.152924, 299.974030, 299.974030, 299.974030, 1116.072754, 291.930634, 289.453705, 290.585907, 300.000000, 290.585907, 289.911163, 289.453705, 291.930634, 627.780884, -656.590515, -536.685120, -602.512146, -466.607483, -656.590515, -580.526489, 262.092316, -296.615082, -188.741364, -224.600006, -295.249786, -230.874573, -292.125153, -399.999573, -349.999573, -300.000000, -307.008087, -305.975037, -306.984222, -307.993378, -307.574921, -306.274139, 0.000000, 0.000000, 0.000000]
zpos = [1200.000000, 600.000000, 1150.000000, -350.000458, 1000.000488, -925.000000, 128.659042, 131.176575, 135.096680, 135.013596, 131.054565, -58.334961, 1178.579102, 400.000000, -4.000488, 1050.000000, 700.120117, -300.000000, 1049.999023, 99.994141, -1222.187012, 87.499023, 1187.896973, -150.000000, 99.500000, -399.999512, 1254.003906, 74.999023, 0.000000, 74.999268, 1149.997559, -304.902832, -510.002930, -399.114258, -357.881836, 102.500000, 859.999512, 942.841797, 897.500000, 859.999512, 942.841797, 897.500000, 87.499268, 87.501221, -1008.298645, 1100.000000, -300.000000, 1143.500488, 1220.000000, 1181.250488, 1181.250854, 1172.502075, 950.000000, -399.999023, 848.994751, 499.978027, -800.021729, -800.333984, 499.665527, -1098.999512, 1121.285645, 1159.000488, 929.995117, 924.995544, 792.499756, 500.000000, 185.398682, -657.100708, -800.000000, -1100.000000, -1027.500244, -1100.000000, -800.000000, -624.709106, 349.999847, 500.000000, -972.294922, -500.000977, -0.000977, 499.999023, -972.294922, -527.124023, 849.543457, 1099.998413, -973.177490, -527.479004, 849.260742, -1248.000977, 499.116364, -0.883648, -500.883850, -973.177795, -1220.352539, 499.999939, 698.147949, -304.306335, -805.190430, 499.999939, -799.999573, 100.738708, -190.215820, -190.205566, -513.561035, -127.250000, 860.000000, 291.500000, 349.998535, 100.000000, -650.002319, 132.176987, 129.338715, 132.185669, 135.032623, 133.957184, 130.457596, -502.704498, -502.704498, -502.704498, -502.704498, -502.704498, -502.704498, 0.000000, 0.000000, 0.000000]

i=0
for curSelObj in bpy.data.objects:

        # verts        
        #for i in bpy.context.selected_objects:
        if curSelObj.type == "MESH":
            print(curSelObj.name)

            for vertex in curSelObj.data.vertices:
                #print(vertex.co)           
                vertex.co.x += xpos[i]; vertex.co.y += ypos[i] ; vertex.co.z += zpos[i]
            i += 1
```
the meshes must be selected in object mode
## Post #22
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-12T19:34:13+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> This one should work for you (R0150100 only) since you seem to have the correct mesh order in blender:
You need to find a method to get the bone positions into the arrays; i use 'C' so far, but the code/handling is not user friendly What is 'C' ?
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-12T21:35:42+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

[https://en.wikipedia.org/wiki/C_%28prog ... anguage%29](https://en.wikipedia.org/wiki/C_%28programming_language%29)
## Post #24
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-12T23:32:35+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

> Reply from shakotay2
>
> https://en.wikipedia.org/wiki/C_%28prog ... anguage%29 Oh, I don't know how to code.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-13T14:52:22+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

well, I really can't believe it: it was just a matter of those damned indices, just a shift of three, how annoying, senseless, time-wasting:



r0150100-ok.jpg (219.41 KiB) Viewed 226 times



I've added a description of How-to-move-those-d'-rooms here:
[viewtopic.php?f=16&t=9923&p=142224&hili ... ak#p142224](http://forum.xentax.com/viewtopic.php?f=16&t=9923&p=142224&hilit=PS2+Resident+Evil+Outbreak#p142224)
It's a little bit tedious but better than copying 115 positions by hand.

And, sry, no, I don't have the time to create a one-click-solution.
(Whoever may complain, feel free to improve the process/scripts/whatever.)

I could image (but maybe I'm to dumb to find out) that it's possible in Noesis (or blender?) to drag that smd skeleton onto the loaded room scene to automatically apply translations (and rotations, if any).
## Post #26
- Username: Steve666
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jul 05, 2018 9:54 pm
- Post datetime: 2018-07-13T20:46:25+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

Thanks
## Post #27
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2019-01-20T17:55:45+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

SO SORRY TO BUMP THAT OLD THREAD FIRST xd

ok i am Codeman02Fr from invision board, most re series players/modders may know about me...

anyway i have a look at thoses files long time ago (old guy yeah i know lol)

so levels do use ahi files to translate/rotate models on the map as it is done in many modern game (re4 2k7 pc too)

so sad no one ever released some working noesis script for this game,
i have some free time so if any coder want to make this became true send me a PM.
i will work only with real coders / scripters , no time to waste with beginners as real life is more important.
and re7 engine models seems to need my time XD (mostly for incoming re2 game).

so lets get started ....
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-20T18:57:40+00:00
- Post Title: Re: Resident Evil Outbreak Noesis script

> Reply from shadowmoy
>
> so sad no one ever released some working noesis script for this game,There is a REO Noesis script from The Dude which I used in the workflow here:
[viewtopic.php?f=16&t=9923&p=142224&hili ... ak#p142224](http://forum.xentax.com/viewtopic.php?f=16&t=9923&p=142224&hilit=PS2+Resident+Evil+Outbreak#p142224)

This is a working solution (more or less, for me at least) and there's not too many people able/willing to create a full Noesis script.

Just my 2 cents.
