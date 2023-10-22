## Post #1
- Username: Prinsto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 17, 2013 1:16 am
- Post datetime: 2013-09-08T12:35:57+00:00
- Post Title: YOBJ to OBJ convert algorithm

Hey guys,

here in the board you can find the tool "RR OBJ Exporter" by Mike. Unfortunately he seems to be inactive for quite some time now. So I would like to ask for some help to find out the convert algorithm for converting .yobj models (from PS2 games by Yukes) to .obj models. I'm quite new in this kind of stuff. Anyway, I attached 2 small files. Both contain the same model, just in a different format.

I would really appreciate it, if you know how to do this and reply to this topic or if you have contact to Mike and give me contact information.

Thanks in advance 
Franz Wegner from Germany
[Models.zip](https://xentaxbackup.github.io/file/6603_Models.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-09T23:16:47+00:00
- Post Title: YOBJ to OBJ convert algorithm

> Reply from Prinsto
>
> So I would like to ask for some help to find out the convert algorithm for converting .yobj models (from PS2 games by Yukes) to .obj models. I'm quite new in this kind of stuff."quite new" means what exactly?
In this blend file from Szkaradek a python script is contained:

import-rumble-roses-ps2-2011-11-06.blend
[http://www.mediafire.com/?vtixhvkhtjklci7](http://www.mediafire.com/?vtixhvkhtjklci7)

And this is the 'magic' code snippet where the face data being created:

```
        for n in range(data[3]):
            f(8)
            i(40)
            var = i(4)#;print var
            face_data.append(var)
            #print plik.tell()
```
## Post #3
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2013-12-14T16:21:00+00:00
- Post Title: YOBJ to OBJ convert algorithm

> Reply from shakotay2
>
> 
import-rumble-roses-ps2-2011-11-06.blend
http://www.mediafire.com/?vtixhvkhtjklci7

Aww, Could you tell me how to use the script?
When I press alt+P, error occurred.
need anything else?  

And, where should the follows be added? 

> Reply from shakotay2
>
> 
And this is the 'magic' code snippet where the face data being created:
Code: Select all        face_data = []
        for n in range(data[3]):
            f(8)
            i(40)
            var = i(4)#;print var
            face_data.append(var)
            #print plik.tell()
[Image1.jpg](https://xentaxbackup.github.io/file/6840_Image1.jpg)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-14T20:10:50+00:00
- Post Title: YOBJ to OBJ convert algorithm

> Reply from porimac
>
> When I press alt+P, error occurred.
need anything else?Most (if not all) blender scripts of Mariusz Szkaradek were written for 
Blender 2.49 using Python 2.6
Blender versions >=2.50 are using Python 3.0.

> And, where should the follows be added??? It's an excerpt from the parser() function in the script.

Import of sample Model.yobj from the start post.
[](http://www.pic-upload.de/view-21626738/import_yobt.jpg.html)
## Post #5
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2013-12-14T20:40:01+00:00
- Post Title: YOBJ to OBJ convert algorithm

> Reply from shakotay2
>
> 
Most (if not all) blender scripts of Mariusz Szkaradek were written for 
Blender 2.49 using Python 2.6
Blender versions >=2.50 are using Python 3.0.
strange. I think so,too...
Please point out if I am something wrong.
[Image3.jpg](https://xentaxbackup.github.io/file/6842_Image3.jpg)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-14T21:33:17+00:00
- Post Title: YOBJ to OBJ convert algorithm

> Reply from porimac
>
> strange. I think so,too...
Please point out if I am something wrong.Sry, didn't see you're using the correct version.

The "invalid syntax" error in your previous pic mislead me.
I'm not sure what's your fault. I'm using XP,
this is blender's console output on loading the Model.yobj:

Compiled with Python version 2.6.2.
Checking for installed Python... got it!
Model.yobj
YOBJ
(3424, 0, 3424, 0, 0, 1, 0, 2, 64, 0, 3360, 3392, 1, 0, 0, 0, 0, 12)
64
0 (0, 0, 12, 1, 128, 1440, 0, 1, 512, 1296, 48, 9, 23)
object- 0
920
(0, 0, 0, 1813446816)
1304
(0, 0, 0, 1812071040)
0 (0.5, 0.5, 0.0, 0.0)
1 (0.80000001192092896, 0.20000000298023224, 0.0, 0.0)
2 (0.0, 0.0, 0.0, 6.2868983045605658e+26)
3 (0.5, 0.5, 0.0, 0.0)
4 (0.80000001192092896, 0.20000000298023224, 0.0, 0.0)
5 (0.0, 0.0, 0.0, 6.2869019939093806e+26)
6 (0.66666668653488159, 0.3333333432674408, 0.0, 0.0)
7 (0.5, 0.5, 0.0, 0.0)
8 (1.0, 1.0, 1.0, 1.0)
1464
1448
3352

and this is Mariusz' python script:

```
#Rumble Roses(PS2) yobj importer
#press alt+p and select folder with yobj files (example: '...\1200.pac')
#IMPORT:
#-geometry with uv split per material
#-bones
import bpy,struct,os
import Blender
from Blender import *
from struct import *
import math
from math import *
from Blender.Mathutils import *


def create_object_name():
    global model_id
    ids = []
    scene = bpy.data.scenes.active
    for mat in Material.Get():
        #print mat.name
        try:
            model_id = int(mat.name.split('-')[0])
            ids.append(model_id)
        except:pass
    try:
        model_id = max(ids)+1
    except:
        model_id = 0

def find_0(): 
    s=''
    while(True):
        litera =  struct.unpack('c',plik.read(1))[0]
        if  litera=='\x00':
            break
        else:
            s+=litera
    return s 


def word(long): 
   s=''
   for j in range(0,long): 
       lit =  struct.unpack('c',plik.read(1))[0]
       if ord(lit)!=0:
           s+=lit
           if len(s)>100000:
               break
   return s

def b(n):
    return struct.unpack(n*'b', plik.read(n))
def B(n):
    return struct.unpack(n*'B', plik.read(n))
def h(n):
    return struct.unpack(n*'h', plik.read(n*2))
def H(n):
    return struct.unpack(n*'H', plik.read(n*2))
def i(n):
    return struct.unpack(n*'i', plik.read(n*4))
def f(n):
    return struct.unpack(n*'f', plik.read(n*4))


def vertexuv():
    for m in range(nMat):
    #for m in range(nParts):
        mesh.materials+=[Material.New()]
    mesh.vertexUV = 1
    mesh.faceUV = 1
    for m in range(len(faceslist)):
        for n in range(3):
            uv_data = uvlist[m][n]
            v_id = faceslist[m][n]
            mesh.verts[v_id].uvco = Vector(uv_data) 
        f = mesh.faces[m] 
        f.uv = [v.uvco for v in f.verts]
        f.mat = uvlist[m][3] 
        
    mesh.update()   

def drawmesh(name): 
    global obj,mesh,scene
    mesh = bpy.data.meshes.new(name)
    mesh.verts.extend(vertexlist)
    mesh.faces.extend(faceslist,ignoreDups=True,smooth =1)
    scene = bpy.data.scenes.active
    obj = scene.objects.new(mesh,name)
    mesh.recalcNormals()
    mesh.update()
    Redraw()



def check_armature():
    global armobj,newarm
    armobj=None
    newarm=None
    scn = Scene.GetCurrent()
    scene = bpy.data.scenes.active
    for object in scene.objects:
        if object.getType()=='Armature':
            if object.name == 'armature':
                scene.objects.unlink(object)
    for object in bpy.data.objects:
        if object.name == 'armature':
            armobj = Blender.Object.Get('armature')
            newarm = armobj.getData()
            newarm.makeEditable()   
            for bone in newarm.bones.values():
                del newarm.bones[bone.name]
            newarm.update()
    if armobj==None: 
        armobj = Blender.Object.New('Armature','armature')
    if newarm==None: 
        newarm = Armature.New('armature')
        armobj.link(newarm)
    scn.link(armobj)
    newarm.drawType = Armature.STICK
    armobj.drawMode = Blender.Object.DrawModes.XRAY

def make_bone(): 
    newarm.makeEditable()
    for bone_id in range(len(bones)):
        bonedata = bones[bone_id]
        #bonename = str(bonedata[1][0])
        bonename = bonedata[0]
        eb = Armature.Editbone() 
        newarm.bones[bonename] = eb
    newarm.update()

def make_bone_parent():
    newarm.makeEditable()
    for bone_id in range(len(bones)):
        bonedata = bones[bone_id]
        parent_id = bonedata[1]
        bonename = bonedata[0]
        if parent_id!=-1:
            bone = newarm.bones[bonename]  
            #boneparent = newarm.bones[str(parent_id)]
            boneparent = newarm.bones[bones[parent_id][0]] 
            bone.parent = boneparent
    newarm.update()

def make_bone_position():
    newarm.makeEditable()
    for bone_id in range(len(bones)):
        bonedata = bones[bone_id]
        #bonename = str(bonedata[1][0])
        bonename = bonedata[0]
        pos = bonedata[2] 
        rot = bonedata[3] 
        rot = Euler(rot).toMatrix()
        bone = newarm.bones[bonename]
        if bone.parent:
           bone.head =   bone.parent.head+Vector(pos) * bone.parent.matrix
           tempM = rot*bone.parent.matrix
           bone.matrix = tempM
        else:
            bone.head = Vector(pos)
            bone.matrix = rot
        bvec = bone.tail- bone.head
        bvec.normalize()
        bone.tail = bone.head + 0.01 * bvec
    newarm.update()

def skeleton():
    check_armature()
    make_bone()
    make_bone_parent()
    make_bone_position()

def parser():
    global bones,vertexlist,faceslist,uvlist,nMat,nParts
    print word(4)
    offs = i(18);print offs
    
    bones = []

    plik.seek(offs[9]+8)
    for a in range(offs[6]):
        BoneName = word(16);print BoneName
        tx = f(1)[0]
        ty = f(1)[0]
        tz = f(1)[0]
        tw = f(1)[0]
        rx = (f(1)[0] * 180) / pi
        ry = (f(1)[0] * 180) / pi
        rz = (f(1)[0] * 180) / pi
        rw = f(1)[0]
        parent = i(1)[0]
        plik.seek(0xC,1)#seek_cur
        qx = f(1)[0]
        qy = f(1)[0]
        qz = f(1)[0]
        qw = f(1)[0]
        bones.append([BoneName,parent,[tx,ty,tz],[rx,ry,rz]])
        #tfm = (eulerangles rx ry rz) as matrix3
        #append tarr [tx,ty,tz]
        #append rarr tfm
        #append qarr [qx,qy,qz,qw]
        #append Barr BoneName
        #append Parr parent
    skeleton()


    plik.seek(offs[8])
    print plik.tell()
    meshdata = []
    for m in range(offs[5]):
        back = plik.tell()
        data = i(13);print m,data
        pos = f(3)
        meshdata.append([data,pos])
        plik.seek(back+64)
        #break

    for m in range(offs[5]):
    #for m in range(5):
        print 'object-',m
        vertexlist = []
        faceslist = []
        uvlist = []
        data = meshdata[m][0]
        plik.seek(data[8]+40)
        back = plik.tell()
        for n in range(data[12]):
            vertexlist.append(f(3))
            i(1)[0]
  
        print plik.tell()
        print i(4)      
        for n in range(data[12]):
            f(4)

        print plik.tell() 
        print i(4)      
        for n in range(data[11]):#weights
            print n,f(4)

        print plik.tell()
        plik.seek(data[5]+8)
        print plik.tell() 
        face_data = []
        for n in range(data[3]):
            f(8)
            i(40)
            var = i(4)#;print var
            face_data.append(var)
            #print plik.tell()
        nMat = data[3]
        for n in range(data[3]):#nMat
            #faceslist = []
            #uvlist = []
            plik.seek(face_data[n][2]+8)           
            for k in range(face_data[n][1]):
                k,i(4)      
                #back = plik.tell()      
            plik.seek(face_data[n][3]+8)
            nParts = face_data[n][1]
            for k in range(face_data[n][1]):#nParts
                #print m,plik.tell()
                var = B(32)#;print var  
                v1 = -1
                v2 = -1
                uv1 = -1
                uv2 = -1
                direct = -1
                for l in range(var[16]):#nFaces
                    direct*=-1
                    #mesh.verts[m].uvco = Vector(uvlist[m])
                    uv3 = [f(1)[0],1-f(1)[0]]
                    l,f(1),
                    v3 = i(1)[0]
                    #print v1,v2,v3
                    f(4)
                    if v1!=-1 and v2!=-1:
                        if direct>0:
                            faceslist.append([v1,v2,v3]) 
                            uvlist.append([uv1,uv2,uv3,n])
                            #uvlist.append([uv1,uv2,uv3,k])
                        else: 
                            faceslist.append([v1,v3,v2]) 
                            uvlist.append([uv1,uv3,uv2,n])
                            #uvlist.append([uv1,uv3,uv2,k])
                    v1=v2
                    uv1=uv2
                    v2=v3
                    uv2=uv3
        drawmesh('model-'+str(m))
        vertexuv()
        Blender.Redraw()
    print plik.tell()
        



def importer(filename):
    global plik,dirname,basename,skala,nbBones
    basename = sys.basename(filename)
    print basename
    dirname = sys.dirname(filename)
    for file in os.listdir(dirname):
        if file.split('.')[-1].lower()=='yobj':
            plik = open(dirname+os.sep+file,'rb')
            create_object_name()
            parser()
            Redraw()
            plik.close()

Window.FileSelector (importer)
```
## Post #7
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2013-12-14T23:14:28+00:00
- Post Title: YOBJ to OBJ convert algorithm

very sorry!
you were so right and I was dead wrong.
I was mistaken in blender extension associating
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-20T03:52:12+00:00
- Post Title: YOBJ to OBJ convert algorithm

> Reply from shakotay2
>
> And this is the 'magic' code snippet where the face data being created:
Code: Select all        face_data = []
        for n in range(data[3]):
            f(8)
            i(40)
            var = i(4)#;print var
            face_data.append(var)
            #print plik.tell()

Is that code really for creating face indices? i looked through the script but i could not follow it, 
i don't know what data[3], f(8), i(40) and i(4) mean/are.   
is there a way to newbify that so it can be reused? i think it would be useful with ps2 model formats.  

edit
okay i think the f(8), i(40) and i(4) are related to this part of the script

```
    return struct.unpack(n*'i', plik.read(n*4))
def f(n):
    return struct.unpack(n*'f', plik.read(n*4))

```
 

and struct.unpack() reads things from binary
f would be float and i would be integer? and 'plik' is just a substitute for 'bs'?
and 'n' would be whatever number is in parenthesis?

```
x	     pad byte	         no value	 	 
c	     char	             bytes of length 1          		 
b	     signed char	      integer	             1	
B	     unsigned char	    integer	             1	
?	     _Bool	            bool	                1	
h	     short	            integer	             2	
H	     unsigned short      integer	             2	
i	     int	              integer	             4	
I	     unsigned int	     integer	             4	
l	     long	             integer	             4	
L	     unsigned long	    integer	             4	
q	     long long	        integer	             8	
Q	     unsigned long       long integer	        8	
f	     float	            float	               4	
d	     double	           float	               8 	
s	     char[]	           bytes	 	 
p	     char[]	           bytes	 	 
P	     void *	           integer	 	
```

[https://docs.python.org/3.2/library/str ... characters](https://docs.python.org/3.2/library/struct.html#format-characters)
i still don't know what data[3] is referring to though
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-20T17:14:54+00:00
- Post Title: YOBJ to OBJ convert algorithm

> Reply from AceWell
>
> i still don't know what data[3] is referring to thoughMariusz' python scripts shall be used - not understood  
But you're on a good way so far - maybe insert print data[3] to get a clue.

there's
meshdata.append([data,pos])
in one loop

and 
data = meshdata[m][0]
in another

This is a little bit cryptic so you'll need about 3 hours to fully understand the whole script then another hour to recreate it in Noesis.

The more print cmds you insert into the script the more you'll understand it.
## Post #10
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-20T20:23:01+00:00
- Post Title: YOBJ to OBJ convert algorithm

> Reply from AceWell
>
> shakotay2 wrote: i still don't know what data[3] is referring to though

correct me someone if i'm wrong but i think that's the "python slice", like the third segment in that "data", yeah i think it's definitely slicing.
