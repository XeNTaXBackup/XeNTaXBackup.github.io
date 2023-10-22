## Post #1
- Username: sfynx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 01, 2014 12:39 am
- Post datetime: 2014-03-01T18:13:22+00:00
- Post Title: Bots .bsc

Hey,

First of all I am kind off new to this. So forgive me for stupid mistakes.

I need some help with writing a noesis plugin. I saw some other thread about this here:
[viewtopic.php?f=16&t=9092](http://forum.xentax.com/viewtopic.php?f=16&t=9092)

Allthough I didn't want to bump that since it is kinda old.
Anyway I started writing a script with the information supplied by chrrox.
I have made a mistake somewhere I guess and that is the reason I can't read out the models like it should...
I only can't seem to find the mistake.
I wrote a standalone py script to decrypt the files and a noesis script.
They both don't work xD

fmt_bots_bsc.py -> is the noesis plugin
fmt_bots2_bsc.py -> is the standalone script
obj_ordener.py -> is used to be able to read the object files it supplies.
I supplied them in the attachments. Help is very much appreciated.

the standalone script doesn't draw or do anything. It only makes the file readable as obj.

Thanks in advance,
[bots.rar](https://xentaxbackup.github.io/file/7056_bots.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-02T12:19:13+00:00
- Post Title: Bots .bsc

> Reply from sfynx
>
> Hey,

First of all I am kind off new to this. So forgive me for stupid mistakes.Mistakes are part of scripting.
I don't see any stupid mistakes (well, you shouldn't forget to close files.)

> I need some help with writing a noesis plugin.I always lose too much time trying it with Noesis
(though it's a cool tool once you know how to use it.)
I know Alsair made a complete Noesis Bout/bsc py script. So ypu may ask him for it since I didn't find it in his threads any more.

> fmt_bots2_bsc.py -> is the standalone script
I changed this script so that it can read gr_010_arm.bsc

This is the result:
[](http://www.pic-upload.de/view-22425848/gr_010_arm_bsc.jpg.html)

I don't have the time to fiddle out the startup thingie so I skipped all bytes before the counts:
os.read(fil,0x347)       # The offset 0x347 does apply to gr_010_arm.bsc only!
important: the folder path for the bsc file has to be changed.
(I also changed the drive letter for the arm.obj to D:  - so I was sure where to search for it).

```
Created on 31 okt. 2013

@author: Jeroen

------------------------------------Information about decoding.------------------------------------
all decoding is being done by os.read
@    native    native    native
=    native    standard    none
<    little-endian    standard    none
>    big-endian    standard    none
!    network (= big-endian)    standard    none

'''
import os
import struct

'''The file to decode.'''
#fil=os.open("C://Users//Jeroen//Documents//core//T-BOT//data//models//gr_010_body.bsc",os.O_BINARY)
fil=os.open("O://Eigene Dateien//Downloads//ModelFiles//gr_010_arm.bsc",os.O_BINARY)	

'''first output.'''
fil2=open("D://arm.obj",'w')

'''the number of meshes.'''
#meshcount=struct.unpack("<b",os.read (fil,1))[0]
#print ("meshcount ",meshcount);

#unkcount=struct.unpack(">b",os.read (fil,1))[0]
#print ("unkcount ",unkcount)
#Null=struct.unpack("<b",os.read (fil,1))[0]
#print (Null)

'''the number to skip before actually reading important data.'''
#Skip=os.read (fil,12*(int(unkcount) + 1))
#print (Skip)

'''bonename is just a skip.'''
#bonename=os.read(fil,0x42)
#print (bonename)

os.read(fil,0x347)
'''read the number of vertices.'''
vertcount=struct.unpack("<l",os.read (fil,4))[0]
print (vertcount)
writevert= '# ' + str(vertcount) + ' vertices'
fil2.write(str(writevert) + "\n")

'''read the number of faces'''
facecount=struct.unpack("<l",os.read (fil,4))[0]
print (facecount)
writefacei= '# ' + str(facecount) + ' Ungrouped triangles'
fil2.write(str(writefacei) + "\n")
os.read(fil,24)
vert=0

'''loop to read all vertices vert normals and texture coods.'''
while vert<vertcount:
    vert +=1
    vertpos1=struct.unpack("<f",os.read (fil,4))[0]
    vertpos2=struct.unpack("<f",os.read (fil,4))[0]
    vertpos3=struct.unpack("<f",os.read (fil,4))[0]
    print (vertpos1, " ", vertpos2, " ", vertpos3)
    writevertpos= 'v ' + str(vertpos1) + ' ' + str(vertpos2) + ' ' + str(vertpos3) + ''
    fil2.write(str(writevertpos) + "\n")
    vertnorm1=struct.unpack("<f",os.read (fil,4))[0]
    vertnorm2=struct.unpack("<f",os.read (fil,4))[0]
    vertnorm3=struct.unpack("<f",os.read (fil,4))[0]
    print (vertnorm1, " ", vertnorm2, " ", vertnorm3)
    writevertnorm= 'vn ' + str(vertnorm1) + ' ' + str(vertnorm2) + ' ' + str(vertnorm3) + ''
    fil2.write(str(writevertnorm) + "\n")
    vertcolor=os.read (fil,4)
    vertUV1=struct.unpack("<f",os.read (fil,4))[0]
    vertUV2=struct.unpack("<f",os.read (fil,4))[0]
    writevertUV= 'vt ' + str(vertUV1) + ' ' + str(vertUV2)
    fil2.write(str(writevertUV) + "\n")
    vertnull=os.read (fil,8)

'''the faces ungrouped triangles'''
face=0
while face<facecount/3:
    face +=1
    print (face)
    face1=struct.unpack("<h",os.read (fil,2))[0] +1
    face2=struct.unpack("<h",os.read (fil,2))[0] +1
    face3=struct.unpack("<h",os.read (fil,2))[0] +1
    
    writeface= 'f ' + str(face1) + '/' + str(face1) + '/' + str(face1) + ' ' + str(face2) + '/' + str(face2) + '/' + str(face2) + ' ' + str(face3) + '/' + str(face3) + '/' + str(face3)
    fil2.write(str(writeface) + "\n")
os.close(fil)
fil2.close()
```
## Post #3
- Username: sfynx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 01, 2014 12:39 am
- Post datetime: 2014-03-02T20:28:42+00:00
- Post Title: Bots .bsc

thanks very much it functions now. I can read out heads.
didn't test other stuff but will manage it.
Wouldn't have figured out myself what to change with reading the faces :D
## Post #4
- Username: sfynx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 01, 2014 12:39 am
- Post datetime: 2014-03-31T14:08:40+00:00
- Post Title: Bots .bsc

Well it has been some time. I finished the script to read out all meshes, unfortunately there is a problem left.
I now want to read out the bones and connect them properly and I found the file extension .cal kinda properly for now.
Pre's for me are that files are being put together in one file. Meaning I don't need to change very much about the way I am reading out now. 
I just read out the meshes subdivide them in singled out files convert them with a third program and dump the names of the mesh files in the cal file.
And since the bones are saved in another file then within the model file. It seemed to be more logical to choose this.
If another extension would be better then this I'd like to know.

Now the major problem is I don't know to much about bones. How do they exactly connect to vertices and how is the information being saved(for .csf files, or your suggested extension)?

and for the bone files from bots. They seem to be saved weirdly. The same bonenames appear multiple times. Junk bytes are right after them which makes me suggest the start of the bone name skip is still intact with 0x42 bytes. Allthough what I came across with while checking it was 64 bytes long like here:

```
42 6F 6E 65 30 32 00 CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC 42 6F 6E 65 30 31 00 CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC CC
```

Also sometimes one11 or something appears and I don't know if it shouldn't be read or if it is just a normal bone?
further I don't know. 

I could definetly use some help with the layout for this. 
Help of any kind is very much appreciated.

Link to general bone file: [http://www.filedropper.com/azbone](http://www.filedropper.com/azbone)

Thanks in advance, Sfynx
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-31T21:45:43+00:00
- Post Title: Bots .bsc

you can find a short dump of gr_bone.bon in my post as of Fri Jun 28, 2013 11:06 pm
in this thread: [viewtopic.php?f=16&t=10549](http://forum.xentax.com/viewtopic.php?f=16&t=10549)

Since Alsair seemed to have solved all problems I stopped further investigations.

(Imho bsc/bon files are not the very best examples to learn/understand rigging.)
## Post #6
- Username: sfynx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 01, 2014 12:39 am
- Post datetime: 2014-04-01T11:10:54+00:00
- Post Title: Bots .bsc

Okay so not focusing on the .bon file from bots. 
What I see from your dump is that bones excist out of 4 variables?
How does an extension like cal or something else know what the bones are connected to?

And what would you suggest to look at to know a bit more about rigging bones from seperate general bone files, before trying to work on the bon files?

Do you have the noesis scrypt that finale made? 
I think some posts are lost/deleted at the link you provided last?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-01T14:49:31+00:00
- Post Title: Bots .bsc

> Reply from sfynx
>
> What I see from your dump is that bones excist out of 4 variables?Not sure which vars you mean. The bones have a position and and 3 angles (rotations).

> How does an extension like cal or something else know what the bones are connected to?Not sure if I got what you mean. The game engine "knows" which data to be read from which kind of files.
Often the mesh, the weights and the skeleton are to be found in a model file and the animations in seperate files.

> And what would you suggest to look at to know a bit more about rigging bones from seperate general bone files, before trying to work on the bon files?Well, search for 'bones' in the forums. You'll get about 1413 matches. Then in the Search these results box type 'parent'.
You'll get 80 hits. Guess reading the threads these posts are contained in will help a little bit.

> Do you have the noesis scrypt that finale made?Which script are you talking of?
Or do you mean 'Alsair'?

Yes, I have his Noesis py script. But since he deleted it from the before mentioned thread I guess he didn't want it to be public any more.
So please ask Alsair himself for it.
## Post #8
- Username: sfynx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 01, 2014 12:39 am
- Post datetime: 2014-04-02T09:44:08+00:00
- Post Title: Bots .bsc

Okay understandable. I will look into rigging and bone stuff now.
I sent alsair a message although he doesn't seem to be very active on these forums anymore nor on skype.
I will wait some longer, but have to ask you maybe in the future, to make the decision: if you could share it with me as I allready have the python scrypt without noesis...?
Owh and do you know some kind off layout for the general bone files on how to read them out?
Allthough I don't know to much about it, it would be nice to know at least how it is saved in there(if you at least know if not no problem).

Thanks anyway
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-05T05:57:39+00:00
- Post Title: Bots .bsc

gr_trans_110.bon
# 1.   0x15708:
bone_RArm05x 
D0 73 73 05 
0x1574c: -0.000001   -1.000000 -0.000000 0.000000
-0.000194   -0.000000 -1.000000 0.000000
1.000000   -0.000001 -0.000194 0.000000
-45.501106   -775.255371 -5.227972 1.000000

0x1578c: -0.000001   -1.000000 -0.000000 0.000000
-0.000194   -0.000000 -1.000000 0.000000
1.000000   -0.000001 -0.000194 0.000000
-45.501106   -775.255371 -5.227972 1.000000

0x157cc: -0.000001   -1.000000 -0.000000 0.000000
-0.000194   -0.000000 -1.000000 0.000000
1.000000   -0.000001 -0.000194 0.000000
-45.501106   -775.255371 -5.227972 1.000000

fbx file:

```
		Version: 232
		Properties70:  {
			P: "ScalingMax", "Vector3D", "Vector", "",0,0,0
			P: "DefaultAttributeIndex", "int", "Integer", "",0
			P: "Lcl Translation", "Lcl Translation", "", "A",-45.501106262207,-775.25537109375,-5.22797203063965
			P: "Lcl Rotation", "Lcl Rotation", "", "A",89.9999906653331,-90,0
			P: "Lcl Scaling", "Lcl Scaling", "", "A",1.00000001885026,0.999999761582062,0.999999840070283
		}
		MultiLayer: 0
		MultiTake: 1
		Shading: Y
		Culling: "CullingOff"
	}

```

[,,,]

# 2.   0x22ecc:
bone_LArm05x 
88 4B 74 05 
0x22f10: 0.000001   1.000000 0.000000 0.000000
0.000188   0.000000 -1.000000 0.000000
-1.000000   0.000001 -0.000188 0.000000
45.605835   -775.255371 -5.227972 1.000000

0x22f50: 0.000001   1.000000 0.000000 0.000000
0.000188   0.000000 -1.000000 0.000000
-1.000000   0.000001 -0.000188 0.000000
45.605835   -775.255371 -5.227972 1.000000

0x22f90: 0.000001   1.000000 0.000000 0.000000
0.000188   0.000000 -1.000000 0.000000
-1.000000   0.000001 -0.000188 0.000000
45.605835   -775.255371 -5.227972 1.000000

```
		Version: 232
		Properties70:  {
			P: "ScalingMax", "Vector3D", "Vector", "",0,0,0
			P: "DefaultAttributeIndex", "int", "Integer", "",0
			P: "Lcl Translation", "Lcl Translation", "", "A",45.6058349609375,-775.25537109375,-5.22797203063965
			P: "Lcl Rotation", "Lcl Rotation", "", "A",89.9999872502361,90,0
			P: "Lcl Scaling", "Lcl Scaling", "", "A",1.000000256045,1.0000000000006,1.00000001763712
		}
		MultiLayer: 0
		MultiTake: 1
		Shading: Y
		Culling: "CullingOff"
	}
```

[...]

# 3.   0x30690:
bone_cutter01 
40 23 75 05 
0x306d4: 1.000000   0.000000 0.000000 0.000000
0.000000   0.000000 -1.000000 0.000000
0.000000   1.000000 0.000000 0.000000
-0.377932   -775.242371 -5.277328 1.000000

0x30714: 1.000000   0.000000 0.000000 0.000000
0.000000   0.000000 -1.000000 0.000000
0.000000   1.000000 0.000000 0.000000
-0.377932   -775.242371 -5.277328 1.000000

0x30754: 1.000000   0.000000 0.000000 0.000000
0.000000   0.000000 -1.000000 0.000000
0.000000   1.000000 0.000000 0.000000
-0.377932   -775.242371 -5.277328 1.000000

```
		Version: 232
		Properties70:  {
			P: "ScalingMax", "Vector3D", "Vector", "",0,0,0
			P: "DefaultAttributeIndex", "int", "Integer", "",0
			P: "Lcl Translation", "Lcl Translation", "", "A",-0.377931505441666,-775.242370605469,-5.27732849121094
			P: "Lcl Rotation", "Lcl Rotation", "", "A",89.999989754715,-0,0
			P: "Lcl Scaling", "Lcl Scaling", "", "A",1,0.999999880790726,0.999999880790726
		}
		MultiLayer: 0
		MultiTake: 1
		Shading: Y
		Culling: "CullingOff"
	}
```


Iirc the fbx file was exported from gr_trans_110.bsc

bon file should contain animation frames.
Seems like there are about 862 of them with constant values. So the object won't move. Strange...
## Post #10
- Username: sfynx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 01, 2014 12:39 am
- Post datetime: 2014-04-05T07:18:51+00:00
- Post Title: Bots .bsc

Well from what I understand from the previous topic and from you is that the layout for the bone dat is kinda:

```
find bone name in bone file
skip from start of bone name 64 (or hex 0x40)
2 bytes damage hitbox data
2 bytes distance jump data
repeat(x3) 
for full bone data(x4):
3 floats bones location data
1 float as weight.
```


What I don't get is why do bone names excist multiple times and why do they give multiple times the same data?
Something I haven't found in the trans files is that bone names excist twice, because they have added x01 or x02. This is different in the general bone file where they do excist twice and data differences even at the repeats. which could be logical but every different mesh piece gets a different bone name. Meaning different bones. Unless the repeating data is the animation?
## Post #11
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2014-05-05T00:37:53+00:00
- Post Title: Bots .bsc

Sorry for not signing in sooner, anyways I indeed have solved almost all of this. However, the one thing I'm puzzled about is whether it can be automatically be mapped to some sort of skeleton. Since each frame has static position for each mesh piece, I wasn't completely sure.

When I Imported the fbx model into Cinema4D I noticed that there are no actual "bones" connecting each mesh piece, but rather they're all floating around with each position being different from each frame.

I'm not sure if I'm missing something in noesis to enable these bones, or if these models are not capable of this.

I have the animation and everything working just fine, but the meshes aren't connecting see here (after importing to Sunburn engine):
## Post #12
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2014-05-05T06:56:20+00:00
- Post Title: Bots .bsc

> Reply from shakotay2
>
> gr_trans_110.bon
# 1.   0x15708:
bone_RArm05x 
D0 73 73 05 
0x1574c: -0.000001   -1.000000 -0.000000 0.000000
-0.000194   -0.000000 -1.000000 0.000000
1.000000   -0.000001 -0.000194 0.000000
-45.501106   -775.255371 -5.227972 1.000000

0x1578c: -0.000001   -1.000000 -0.000000 0.000000
-0.000194   -0.000000 -1.000000 0.000000
1.000000   -0.000001 -0.000194 0.000000
-45.501106   -775.255371 -5.227972 1.000000

0x157cc: -0.000001   -1.000000 -0.000000 0.000000
-0.000194   -0.000000 -1.000000 0.000000
1.000000   -0.000001 -0.000194 0.000000
-45.501106   -775.255371 -5.227972 1.000000

fbx file:
Code: Select all	Model: 34314488, "Model::bone_RArm05x", "LimbNode" {
		Version: 232
		Properties70:  {
			P: "ScalingMax", "Vector3D", "Vector", "",0,0,0
			P: "DefaultAttributeIndex", "int", "Integer", "",0
			P: "Lcl Translation", "Lcl Translation", "", "A",-45.501106262207,-775.25537109375,-5.22797203063965
			P: "Lcl Rotation", "Lcl Rotation", "", "A",89.9999906653331,-90,0
			P: "Lcl Scaling", "Lcl Scaling", "", "A",1.00000001885026,0.999999761582062,0.999999840070283
		}
		MultiLayer: 0
		MultiTake: 1
		Shading: Y
		Culling: "CullingOff"
	}

[,,,]

# 2.   0x22ecc:
bone_LArm05x 
88 4B 74 05 
0x22f10: 0.000001   1.000000 0.000000 0.000000
0.000188   0.000000 -1.000000 0.000000
-1.000000   0.000001 -0.000188 0.000000
45.605835   -775.255371 -5.227972 1.000000

0x22f50: 0.000001   1.000000 0.000000 0.000000
0.000188   0.000000 -1.000000 0.000000
-1.000000   0.000001 -0.000188 0.000000
45.605835   -775.255371 -5.227972 1.000000

0x22f90: 0.000001   1.000000 0.000000 0.000000
0.000188   0.000000 -1.000000 0.000000
-1.000000   0.000001 -0.000188 0.000000
45.605835   -775.255371 -5.227972 1.000000
Code: Select all	Model: 34318168, "Model::bone_LArm05x", "LimbNode" {
		Version: 232
		Properties70:  {
			P: "ScalingMax", "Vector3D", "Vector", "",0,0,0
			P: "DefaultAttributeIndex", "int", "Integer", "",0
			P: "Lcl Translation", "Lcl Translation", "", "A",45.6058349609375,-775.25537109375,-5.22797203063965
			P: "Lcl Rotation", "Lcl Rotation", "", "A",89.9999872502361,90,0
			P: "Lcl Scaling", "Lcl Scaling", "", "A",1.000000256045,1.0000000000006,1.00000001763712
		}
		MultiLayer: 0
		MultiTake: 1
		Shading: Y
		Culling: "CullingOff"
	}
[...]

# 3.   0x30690:
bone_cutter01 
40 23 75 05 
0x306d4: 1.000000   0.000000 0.000000 0.000000
0.000000   0.000000 -1.000000 0.000000
0.000000   1.000000 0.000000 0.000000
-0.377932   -775.242371 -5.277328 1.000000

0x30714: 1.000000   0.000000 0.000000 0.000000
0.000000   0.000000 -1.000000 0.000000
0.000000   1.000000 0.000000 0.000000
-0.377932   -775.242371 -5.277328 1.000000

0x30754: 1.000000   0.000000 0.000000 0.000000
0.000000   0.000000 -1.000000 0.000000
0.000000   1.000000 0.000000 0.000000
-0.377932   -775.242371 -5.277328 1.000000
Code: Select all	Model: 34321848, "Model::bone_cutter01", "LimbNode" {
		Version: 232
		Properties70:  {
			P: "ScalingMax", "Vector3D", "Vector", "",0,0,0
			P: "DefaultAttributeIndex", "int", "Integer", "",0
			P: "Lcl Translation", "Lcl Translation", "", "A",-0.377931505441666,-775.242370605469,-5.27732849121094
			P: "Lcl Rotation", "Lcl Rotation", "", "A",89.999989754715,-0,0
			P: "Lcl Scaling", "Lcl Scaling", "", "A",1,0.999999880790726,0.999999880790726
		}
		MultiLayer: 0
		MultiTake: 1
		Shading: Y
		Culling: "CullingOff"
	}

Iirc the fbx file was exported from gr_trans_110.bsc

bon file should contain animation frames.
Seems like there are about 862 of them with constant values. So the object won't move. Strange...
I also notice 4 bytes that aren't used for each bone - could it be possible it uses these four bytes to link to another bone?
## Post #13
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-05-13T20:40:43+00:00
- Post Title: Bots .bsc

All you've gotta do to define a skeletal hierarchy in Noesis is set the NoeBone's parent. Your format wouldn't actually need a hierarchy as the anim matrices are in model space rather than local space. But maybe they store it anyway.
## Post #14
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2014-05-13T22:28:18+00:00
- Post Title: Bots .bsc

I'm trying to figure out how it's stored, that way I can link them to form a proper skeleton.
