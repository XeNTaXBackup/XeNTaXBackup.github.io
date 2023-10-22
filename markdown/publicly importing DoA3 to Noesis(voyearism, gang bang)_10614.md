## Post #1
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-13T09:59:57+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

hi all.  
I'm a lazy person, and it's only getting worse. I want to make a DoA3 importer(python), to learn how to make a noesis plugin, and how to do both "the right way"(if there is any), but my laziness is killing me.
So I decided to do this on public, so there would be a chance to be publicly embarrassed and this won't let me relax too much. Also i hope you guys can help me if I'm stuck.
My plan is to:
- Reverse the doa3 "xpr" and "cat" formats (and maybe "mot")
- Import as much information as possible to noesis
- Write a nice descriptive code, with functions and whatever the real programmers use to make programs.
- Use advices of the xentax community when stuck.

As you see this is a very clever plan, with many idealistic goals. I'll post each time I'll have a progress, thus I'll double/triple post, so in the first place i ask for permission to create this thread.
My second question is pure technical - does Noesis support morphing animation?

I hope i can have your assistance when I'll have a question.
## Post #2
- Username: b0ny
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-07-13T10:19:31+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

noesis does support morph targets.
[http://www.youtube.com/watch?v=vgkKprVyQl8](http://www.youtube.com/watch?v=vgkKprVyQl8)
## Post #3
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-13T11:57:47+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from chrrox
>
> noesis does support morph targets.
http://www.youtube.com/watch?v=vgkKprVyQl8
Thanks. Good news for me 

______________________

First of all i downloaded latest version of Noesis(and "PyScripter" for editing python scripts.)
Copypasted the template for Noesis python plugin from forum.xentax.com/viewtopic.php?t=7760(thank you Chrrox one more time). Found that bs.read("I") will read a tuple and bs.read("I")[0] will read an int, and also bs.readUInt() will read an int.

I have a request for Señor Casaroja. To add to reading functions like bs.readUInt() the functionality of bs.seek()
when importing you have to read a lot from file. this will make things more convenient. so this code

```
nameForOffset = bs.readUInt()
bs.seek(nameForOffset)
bs.readFloat()
```
could be written like this

```
bs.readFloat(bs.readUInt(0x28))
```
and the function without arguments(bs.readUInt()) will behave like it does now
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-13T13:17:51+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

That wouldn't make much sense. If anything, you'd want that argument to be size in the native type (so, count) instead of bytes, that's the point of using typed reads. You're also trying to read a float from a list of 0x28 ints, you wouldn't just seek to 0x28 and then read a single int, as that would also be unintuitive default behavior for the argument. If you want behavior like that, I'd suggest making your own passthrough class around NoeBitStream and using that instead. That way you can do whatever kind of madness with your arguments that you want. Or you can use an entirely different bit/byte reader class, it's up to you. You're given the raw bytearray representing the data, so you can do whatever you want.

I'd also suggest not getting caught up on semantics as you dive into things, it will only hold you back and give you an excuse to delay tackling the hard stuff.
## Post #5
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-13T14:16:12+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from MrAdults
>
> That wouldn't make much sense. If anything, you'd want that argument to be size in the native type (so, count) instead of bytes, that's the point of using typed reads. You're also trying to read a float from a list of 0x28 ints, you wouldn't just seek to 0x28 and then read a single int, as that would also be unintuitive default behavior for the argument. If you want behavior like that, I'd suggest making your own passthrough class around NoeBitStream and using that instead. That way you can do whatever kind of madness with your arguments that you want. Or you can use an entirely different bit/byte reader class, it's up to you. You're given the raw bytearray representing the data, so you can do whatever you want.

I'd also suggest not getting caught up on semantics as you dive into things, it will only hold you back and give you an excuse to delay tackling the hard stuff.
My logic tells me that every seek is always followed by a read, and making them one, is what my logic desires. I thought that could help beginners that only start to make python scripts (thats imho)

I'm stuck - where can i find information on "rapi" methods?
I need to deswizzle xbox1 images,
and i need to find the Noesis plugin folder to use the doa3 skeletons ripped from the executable,
what dds formats are supported by Noesis
## Post #6
- Username: b0ny
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-13T14:24:53+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

I know why you want it, it just doesn't make sense as a default argument for those functions. You can take any of the approaches I mentioned instead.

Xbox is just morton order tiling. chrrox has some scripts that demonstrate how to untile using noesis.morton2D, like his Naughty Dog one.

All the info that exists for the rapi and noesis modules is in __NPReadMe.txt and scattered throughout these forums.

Lots of DDS pixel formats are supported, but I'm guessing you meant DXT. DXT1-5, BC4, BC5, and some custom packing methods are supported. DXT1, 3, and 5 are natively supported as texture formats, others need to be decoded (before passing back as native texture data) using imageDecodeDXT.
## Post #7
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-13T15:53:47+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

I know I'm pretty slow and I need to be faster if I don't want to loose all my precious voyeurs...
At this point this script can import textures:

```

from inc_noesis import *
import noesis
import rapi #rapi methods should only be used during handler callbacks

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
    handle = noesis.register("Dead or Alive 3", ".xpr")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
    noesis.logPopup()
        #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
    return 1

loadDoA3Only = False #doa3 only or also doa2u and doax

#check if it's this type based on the data
def noepyCheckType(data):
    bs = NoeBitStream(data)
    if bs.readUInt() != 0x30525058: #'XPR0' magic
        print("no xpr0 magic(30525058)")
        return 0
    bs.seek(0x14) #Seek to MDL
    if bs.readUInt() != 0x4C444D: #'MDL' magic
        print("no mdl magic(4c444d)")
        return 0
    if loadDoA3Only:
        bs.seek(0x28)
        OBJoffset = bs.readUInt()
        bs.seek(OBJoffset + 8)
        if bs.readUInt() != 0:#OBJoffset + 8 = 0 for doa3 and 4 for doax doa2u
            print("no obj+8", OBJoffset + 8)
            return 0
    return 1

#load the model
def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    print("hi there")

    #importing code goes here
    bs.seek(0) #start from the file beginning
    xprMagic        = bs.readUInt()
    xprSize         = bs.readUInt()
    dataBlockOffset = bs.readUInt()

    #parse xbox1 xpr chunks
    vertexBuffersOffsets = []
    imagesInfos = []
    while True:
        chunkBase = bs.tell()
        chunkID = bs.readUInt()
        #80000000-MDL; 40001-texture; 800001-vbuf; 830001-???
        chunkSize = {0x800001:0xC, 0x40001:0x14, 0x830001:0xC}.get(chunkID, -1)

        if chunkID == 0x80000000:
            chunkSize = bs.readUInt() + 8

        elif chunkID == 0x800001:
            vertexBuffersOffsets.append(dataBlockOffset + bs.readUInt())

        elif chunkID == 0x40001:
            textureOffset  = bs.readUInt()
            unknownAlways0 = bs.readUInt()
            flags          = bs.readUInt()
            imagesInfos.append((dataBlockOffset + textureOffset, flags))#absolute offset and flags

        elif chunkID == 0xffffffff:
            break

        elif chunkID != 0x80000000:
            print("not a doa3 chunk %x"%chunkID)
            break

        bs.seek(chunkBase + chunkSize)#seek to next chunk

    #load images
    texList = []
    texNames = []
    cleanName = rapi.getInputName()
    cleanName = cleanName[cleanName.rfind("\\")+1: -4]#get the file name without extension
    for textureIndex, (textureOffset, flags) in enumerate(imagesInfos):
        doafmt =       (flags &     0xFF00) >> 8
        Width  = 1 << ((flags &   0xF00000) >> 20)
        Height = 1 << ((flags &  0xF000000) >> 24)
        bpp = {6:4, 0x28:2, 0x19:1,  0xC:0.5, 0xF:1}[doafmt]    #6-ARGB32  28-GB16  19-A8  C-DXT1  F-DXT5
        noMipSize = int(Width * Height * bpp)

        bs.seek(textureOffset)
        textureData = bs.readBytes(noMipSize)
        textureName = cleanName + "_%02d"%textureIndex

        if doafmt == 0xC:
            textureFormat = noesis.NOESISTEX_DXT1
        elif doafmt == 0xF:
            textureFormat = noesis.NOESISTEX_DXT5
        elif doafmt in (6, 0x28, 0x19):
            argbfmt = {6:"b8g8r8a8", 0x28:"b8g8", 0x19:"r8"}[doafmt]#why argb is reversed, big endian?
            untwid = bytearray()
            for x in range(Width):
                for y in range(Height):
                    idx = noesis.morton2D(x, y)
                    untwid += textureData[idx*bpp:idx*bpp+bpp]
            textureData = rapi.imageDecodeRaw(untwid, Width, Height, argbfmt)
            textureFormat = noesis.NOESISTEX_RGBA32
        else:
            print("Unsuported texture format - %x"%doafmt)

        texList.append(NoeTexture(textureName, Width, Height, textureData, textureFormat))
        texNames.append(textureName)

    #find doa version (3/2U/X)
    doaVesion = 0
    bs.seek(0x28)
    OBJoffset = bs.readUInt()
    bs.seek(OBJoffset + 8)
    if bs.readUInt() != 0:#[OBJoffset + 8] = 0 for doa3 and 4 for doax doa2u
        doaVersion = 3 #doa3
    else:
        doaVersion = 2 #doa2U (or doaX)

    if doaVersion != 3:#stop parsing if not doa3
        mdl = NoeModel([])
        mdl.setModelMaterials(NoeModelMaterials(texList, []))
        mdlList.append(mdl)
        rapi.rpgClearBufferBinds()
        return 1

    #test load the vertex buffers
    pass

    #end
    rapi.rpgClearBufferBinds()
    return 1
```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-13T20:45:11+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from MrAdults
>
> I'd also suggest not getting caught up on semantics as you dive into things, it will only hold you back and give you an excuse to delay tackling the hard stuff.My today's deja-vu!  (Last monday morning: my teamleader speaking to me.)

> Reply from b0ny
>
> hi all.  
I'm a lazy person, and it's only getting worse.The teamleader is watching you, dude!
## Post #9
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-14T04:44:28+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from shakotay2
>
> MrAdults wrote:I'd also suggest not getting caught up on semantics as you dive into things, it will only hold you back and give you an excuse to delay tackling the hard stuff. My today's deja-vu!  (Last monday morning: my teamleader speaking to me.)
b0ny wrote:hi all.  
I'm a lazy person, and it's only getting worse.The teamleader is watching you, dude! I'm not sure if someone can do something with this situation  
_______________

I'm confused with importing normals to Noesis:
where do i put the normals when using this function?

```
mesh = NoeMesh(faces, vertices, meshName, meshName)
```


```
rapi.rpgBindNormalBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 0x20, 12)
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 0x20, 24)
rapi.rpgCommitTriangles(facesdata, noesis.RPGEODATA_USHORT, int(len(facesdata)/2), noesis.RPGEO_TRIANGLE, 1)
```
 rpgCommitTriangles wants binary buffer with triangles, while i have a tristrip buffer, i converted manually this tristrip buffer by operating with pairs of bytes to emulate shorts length. this doesn't look right too me with my list of tristrips.
(i just realized the concept of bindings - the vertex data layers can be in different buffers)

the doa3 xpr format looks like this:

```
  obj1:
      vertex buffer 1 (pos,normal,uv):
          number of verteices
          vertex buffer offset
          number of indices
          tristrip buffer offset
      vertex buffer 2 (?)
      vertex buffer 3 (pos,color,uv)
      vertex buffer 4 (?)
      material 1:
          material color
          texture index
          used vertex buffer
          range of used tristrip indices(startindex, number of indices)
      material 2
      material 3 
  obj2
  obj3

```
my idea is to iterate through the materials that use the same vertex buffer and create a mesh, but how do i assign images then. if only one material per mesh can be used then it will be a pain to create a new list of vertices used by a material, to create an object with a single material

[edit]
ARRRRGH! this gang bang is ruined!
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-14T23:03:55+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

You can set normals on a NoeMesh after creating it, but you shouldn't be making NoeMeshes yourself. Stick to the rpg interface.

For triangle strips, simply use RPGEO_TRIANGLE_STRIP instead of RPGEO_TRIANGLE.

The rpg interface will allow you to specify materials on a per-triangle basis. Just use rpgSetMaterial before the commit.
## Post #11
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-15T05:30:46+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from MrAdults
>
> The rpg interface will allow you to specify materials on a per-triangle basis. Just use rpgSetMaterial before the commit.Isn't this this just a convention - I still have to load the data per material(one material - one commit)?

Is there any way to load the materials post factum(after committing), I mean not [one mesh/commit one material] but [one mesh/commit many materials]. Though maybe inside the Noesis, when the data is loaded using the rpg interface, it uses multiple materials per mesh, this rpg interface puts the entire model in one mesh, which is bad for exporting, coz you don't have per mesh names in this case. Is this possible somehow to "make commits to different meshes"?
What am I doing wrong?
## Post #12
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-16T02:23:08+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

You're misunderstanding something. You can specify per triangle materials with the RPG interface. Simply commit different sections of your index buffer with different rpgSetMaterial calls.

You refer to "multiple materials per mesh", which makes no sense. Either you're confusing "material" and "texture", or you want to do blended multi-pass rendering, which is what NoeMaterial's setNextPass is for.
## Post #13
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-16T07:46:03+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from MrAdults
>
> You're misunderstanding something. You can specify per triangle materials with the RPG interface. Simply commit different sections of your index buffer with different rpgSetMaterial calls.

You refer to "multiple materials per mesh", which makes no sense. Either you're confusing "material" and "texture", or you want to do blended multi-pass rendering, which is what NoeMaterial's setNextPass is for.
I see... But inside noesis each of this commits is saved to a separate mesh(if a material is set for it) for which I have to specify a unique name. It's like the mesh is some property of the maerial and not viceversa.

DoA3 model is splited in a lot of meshes(bodyparts like: hand,wrist,forearm,elbow,arm,...), and has tons of materials per mesh(one material per texture), if exporting souch a model from noesis and importing somewhere else you'll get tons of objects, it will get a lot of time to understand where each of these pieces goes.

The only program I made importing scripts for is Blender, and it allows me to load the mesh and then iterate through triangles and set a certain material for it. Maybe i should be more flexible and nor complain about one program using it's own way(Blender has it's own flaws i can complain about all day long  )

Anyway Noesis is a great program. But I'm not good enough for it, I need some time to get better, find a more decent job and get more responsible. Then I'll have a happy long life with you - Noesis.

Sorry guys, this show is over seems like I'm not the guy
## Post #14
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-16T15:43:08+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

That's incorrect. Commits are pooled in a context buffer. You can do as many commits for a single material as you want.
## Post #15
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-17T15:52:20+00:00
- Post Title: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from MrAdults
>
> That's incorrect. Commits are pooled in a context buffer. You can do as many commits for a single material as you want.ok.

MrAdults, can you please help me with something. i now you know a lot about vectors and things, and i lack qualification to fix this.

the story is - the doa3 tristrip is split in "subsets", some of those subsets have a counterclockwise winding and it's impossible to now for sure if it's cw or ccw.(the model looks like this)

so i thought that i could generate a normal from the cw winding and compare it with normals of vertices for the first face, to find out if i need to reverse the winding to point in the "right" direction.

but when calculating the angle between the generated normal and vertice's normals i get a complex number, and python gives me an error because of this. how do i fix the angle function to avoid these complex numbers.
this code bellow will repeat the error i get. please help me fix this. thanks

```
#-----------------
#Calculate the cross product of two vectors
def cross(a, b):
    c = [a[1]*b[2] - a[2]*b[1],
         a[2]*b[0] - a[0]*b[2],
         a[0]*b[1] - a[1]*b[0]]
    return c

def sub(u, v):
    return [ u[i]-v[i] for i in range(len(u)) ]

def normalize(v):
    magnitude = math.sqrt(sum(v[i]*v[i] for i in range(len(v))))
    return [ v[i]/magnitude  for i in range(len(v)) ]

#Calculates the angle between two vectors
def angle(a,b):
    dotproduct = sum([a[i]*b[i] for i in range(len(a))])
    veclengtha = sum([a[i] for i in range(len(a))])**.5 #Calculates the size of a vector
    veclengthb = sum([b[i] for i in range(len(b))])**.5 #Calculates the size of a vector
    print(dotproduct/(veclengtha*veclengthb),dotproduct,veclengtha,veclengthb)
    return math.acos(min(max(dotproduct/(veclengtha*veclengthb),1),-1))# (dotproduct/(veclengtha*veclengthb) is a complex number and i don't now what to do

def getwinding(v):
    print(v)
    #generate a normal from triangle winding
    windnorm = normalize(cross(sub(v[2][0],v[0][0]), sub(v[1][0],v[0][0])))
    #compare generated normal to each of three vertice's normals(if angle is higher than 90 for more then one vertices then CCW)
    if sum([(1 if (angle(windnorm,v[i][1]) * 57.2957795) < 90 else -1) for i in range(3)]) > 0: return True
    return False

def main():
    face = [((-0.05612413212656975, 0.09935212135314941, -0.03539071977138519), #position1
            (-0.8244166374206543, -0.3322310745716095, -0.45821359753608704)),  #normal1
            ((-0.06070474162697792, 0.12217497825622559, -0.038759298622608185),#position2
            (-0.8547890186309814, -0.10589562356472015, -0.5080569386482239)),  #normal2
            ((-0.07193990796804428, 0.12713682651519775, -0.005527373403310776),#position3
            (-0.9910546541213989, -0.08559581637382507, -0.10239160805940628))] #normal3

    winding = getwinding(face)

if __name__ == '__main__':
    main()

```
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-17T16:40:12+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from b0ny
>
> but when calculating the angle between the generated normal and vertice's normals i get a complex number, and python gives me an error because of this. how do i fix the angle function to avoid these complex numbers.python console: "ValueError: negative number cannot be raised to a fractional power"
This is python 2.6.2.

python 3(?): "TypeError: unorderable types: int() > complex()"
So, yes, old pythons message is "straight forward", new one is too sophisticated, isn't it?

> veclengtha = sum([a for i in range(len(a))])**.5 #Calculates the size of a vector
There's the square missing for the vector components. This ends up in the square root of a negative number.
## Post #17
- Username: b0ny
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-18T00:59:23+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

There's no reason to be doing any of that. Use NoeVec3/NoeMat43/etc. It performs better and isn't as ugly.
## Post #18
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-20T06:06:47+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

Noesis import script for Dead or Alive 3 characters (thanks guys for helping me with this script)

importing for now mesh only, character skins only (optionally textures from doax/doau)

so:
 - Noesis supports only cubemap environment textures, while doa3's environmet textures are 2d matcap like.

 - some doa3 headers of the cat files have an unknown encryption

 - kasumi00 is missing heaps joints and some foot parts - should find why is that so
 - zack01 crashes if calculating vector's angle with Noesis built in functions - to do

 - team ninja in doa3 format don't use weights for bending, they use the some shit that works on the morphing principle by replacing the location/normal vector from the vertex buffer with some calculated value.
it multiplies the matrices of the bodyparts the joint is joining then operates with some scale and bending(?) vectors from the joint's data(for doao is called some d3d9 method i can't identify), then it's added to some base (?morph)target and swaps the location vector shown in the indices list.

has anyone before broke in the doa joints format?
## Post #19
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-21T17:23:33+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

If you mean an actual crash where Noesis exits completely, please send the script, model, and anything else I may need to reproduce it.
## Post #20
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-07-22T13:35:18+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

i don't now why i used this word. it just shows a python error window with zero division error. i haven't detected any stability problems with noesis
## Post #21
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2013-07-24T12:43:02+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

Thanks a lot 4 script!
Have you any plan to make also *.olk SC2 support (like Greed Xplorer) or even SC3?!
## Post #22
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-08-09T07:51:26+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from Doronetty
>
> Thanks a lot 4 script!
Have you any plan to make also *.olk SC2 support (like Greed Xplorer) or even SC3?!
i started this "project" to discover the potential of noesis, and research on the doa3 format. and i'm not really interested in doa3 format - i'm only interested in porting it correctly to doao(doa2u), and documenting joints format(too dumb though to do that).

but i'm not interested in soul calibur at least for now. why not using greed xplorer(pcsx2) and capture the 3d model from it's viewport with a directx(opengl?) ripper. also i think i've seen mariokarts64 modding a version of soul calibur, you should check on his channel on youtube...
## Post #23
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-11T05:42:22+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

That's completely wrong, again. And on export, too, you can use globally-indexed mesh data. I think you have the problem of miscomprehending most of what I try to tell you and moving on under your poor assumptions instead of taking the time to reprocess.
## Post #24
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-08-11T16:42:17+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from MrAdults
>
> That's completely wrong, again. And on export, too, you can use globally-indexed mesh data. I think you have the problem of miscomprehending most of what I try to tell you and moving on under your poor assumptions instead of taking the time to reprocess.ok. then fix for me, to see what i'm doing wrong, this example script to load both materials in one mesh:

```
from inc_noesis import *
import noesis
import rapi #rapi methods should only be used during handler callbacks
import struct

def registerNoesisTypes():
    handle = noesis.register("test script", ".txt")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
    noesis.logPopup()
    return 1

def noepyCheckType(data):
    return 1

def noepyLoadModel(data, mdlList):
    vtxdata = struct.pack("<20f", 1,1,0, 1,1,  1,-1,0, 1,-1,  -1,-1,0, -1,-1,  -1,1,0, -1,1)#four vertices with location and uv
    mat1idxdata = struct.pack("<3H", 2,1,0)#first triangle uses the material mat1
    mat2idxdata = struct.pack("<3H", 0,3,2)#second triangle uses the material mat2

    matList = []
    material = NoeMaterial("mat1", "")
    material.setDiffuseColor(NoeVec4([0.0, 0.0, 1.0, 0.0]))
    material.setDefaultBlend(0)
    matList.append(material)
    material = NoeMaterial("mat2", "")
    material.setDiffuseColor(NoeVec4([1.0, 0.0, 0.0, 0.0]))
    matList.append(material)

    ctx = rapi.rpgCreateContext()
    meshname = "meshwithtwomats"
    rapi.rpgSetName(meshname)
    rapi.rpgSetMaterial("mat1")
    rapi.rpgBindPositionBufferOfs(vtxdata, noesis.RPGEODATA_FLOAT, 20, 0)
    rapi.rpgBindUV1BufferOfs(vtxdata, noesis.RPGEODATA_FLOAT, 20, 12)
    rapi.rpgCommitTriangles(mat1idxdata, noesis.RPGEODATA_USHORT, 3, noesis.RPGEO_TRIANGLE, 1)

##    rapi.rpgSetName(meshname)
    rapi.rpgSetMaterial("mat2")
    rapi.rpgCommitTriangles(mat2idxdata, noesis.RPGEODATA_USHORT, 3, noesis.RPGEO_TRIANGLE, 1)#not allowing to add this data to the same mesh
    rapi.rpgClearBufferBinds()

    mdl = rapi.rpgConstructModel()
    mdl.setModelMaterials(NoeModelMaterials([], matList))
    mdlList.append(mdl)
    return 1
```
## Post #25
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-11T19:05:06+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

You're misunderstanding what a "mesh" is at the fundamental level. It's just a draw. For multipass draws on the same mesh you use additional passes in the material. This reflects the way every piece of dedicated graphics hardware has operated over the last 20 years.

If you then want the model as a flat vertex/index array on export (you're still going to have to specify unique draws for each material, just like DOA does), you can just use the model's globalVtx and globalIdx lists. That's why they exist. So that you can be lazy.
## Post #26
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-08-12T05:26:30+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from MrAdults
>
> If you then want the model as a flat vertex/index array on export (you're still going to have to specify unique draws for each material, just like DOA does), you can just use the model's globalVtx and globalIdx lists. That's why they exist. So that you can be lazy.can you be more detailed about globalVtx and globalIdx lists? can't find any description anywhere. how to access these from rapi interface? are those per mesh or per the whole model? maybe some links to more detailed description...
## Post #27
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-12T13:35:40+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

That wasn't mean, it was blunt. And they're just Python lists. Print them out and investigate, and/or see remarks in inc_noesis.py. They're a couple of the many thousands of things lacking documentation in Noesis.
## Post #28
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-08-12T18:40:27+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from MrAdults
>
>  And they're just Python lists. Print them out and investigate, and/or see remarks in inc_noesis.py.yeah, i've seen the inc_noesis.py, but these are part of "mesh" class and i don't have a mesh object when using the rapi interface.(right?)

> Reply from MrAdults
>
> They're a couple of the many thousands of things lacking documentation in Noesis.*sigh*
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-13T08:18:30+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from b0ny
>
> see i'm right and you are wrongEhm, well, you're partially right, b0ny.

Noesis is a strong tool if you know how to use it.

I'd like to start reading this thread from the beginning again to see whether I could contribute a little bit.

But seeing you're coding things that are usually hidden in a graphics library (or blender or Noesis) I'm seeing your dilemma. (Which is mine, too.)

I would like to check your Noesis script - but I'm lacking in a DOA3 sample.
So if you don't mind sending me one via PM?
If so I could have a look and maybe help. But don't expect too much.

(A documentation for Noesis covering all the special aspects of 3D coding you and alsair are wanting to implement would be a dream. And it will be, I guess.)
## Post #30
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-08-13T16:46:56+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

trololo post
## Post #31
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2013-08-13T18:01:41+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from b0ny
>
> yeah, i've seen the inc_noesis.py, but these are part of "mesh" class and i don't have a mesh object when using the rapi interface.(right?)

Just butting right in because I can. I haven't read the entire thread so I don't know why you need the lists from the rapi interface instead of reading/compiling them from the model format file, but you could just feed everything into rapi and then after the appropriate rapi.CommitTriangles etc you call mdl = rapi.ConstructModel() where mdl is classtype NoeModel and you then do globalIdx = mdl.globalIdx

I don't remember seeing you acting like a little bitch before, but I hesitated to actually try and help.
I also think there aren't enough actual  Noesis scripters for us to bother MrAdults with asking for detailed documentation which will occupy a shitton of time. Sure it'll help new scripters, but learning the hard way isn't impossible and beginners will find practically everything needed in our scripts already published.
One way to learn it, would be to take an easy format we already finished and reverse it again and follow the steps we did.
## Post #32
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-14T02:02:46+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

Noesis provides a useful framework for helping you handle lots of different data types. It's a very intuitive framework (relative to blender) if you're familiar with the technical workings of realtime rendering and previous-to-current-gen game development. That's all it is. It isn't going to magically make you understand things you don't already understand.

This guy seems more interested in making a spectacle than accomplishing anything (who would have guessed), so there isn't much point in this thread anymore.
## Post #33
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-08-14T04:28:19+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

i was bored. i'm guilty and i'm sorry...

> Reply from Demonsangel
>
> b0ny wrote:yeah, i've seen the inc_noesis.py, but these are part of "mesh" class and i don't have a mesh object when using the rapi interface.(right?)


I don't know why you need the lists from the rapi interface instead of reading/compiling them from the model format file, but you could just feed everything into rapi and then after the appropriate rapi.CommitTriangles etc you call mdl = rapi.ConstructModel() where mdl is classtype NoeModel and you then do globalIdx = mdl.globalIdxi need globalIdx and globalVtx per object not per model or per noemesh(read material), and i start understanding that noesis just doesn't provide this feature. i need to use python for that, and on exporting i'll need to use tricks with mesh names to find which mesh belongs to what object.

> Reply from Demonsangel
>
> learning the hard way isn't impossible and beginners will find practically everything needed in our scripts already published.
One way to learn it, would be to take an easy format we already finished and reverse it again and follow the steps we did.is there a place to find all noesis python scripts? if not, maybe we need one...
## Post #34
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2013-08-14T09:14:07+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

Eh???

model == object? and each model is built from one or more meshes? What other objects are there that meshes could belong to? I see why MrAdults says you should read up on what everything means, you seem to be confusing terms.
## Post #35
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-08-15T13:53:40+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from Demonsangel
>
> Eh???

model == object? and each model is built from one or more meshes? What other objects are there that meshes could belong to? I see why MrAdults says you should read up on what everything means, you seem to be confusing terms.where did you get this equation from?
3d models(at least doa does) use this hierarchy:

```
  object:
    material
    material
  object:
    material
...
```
noesis doesn't have "objects"...
## Post #36
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2013-08-15T14:12:19+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

Are you kidding me?
## Post #37
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-05-11T18:05:14+00:00
- Post Title: Re: publicly importing DoA3 to Noesis(voyearism, gang bang)

> Reply from b0ny
>
> 

Noesis import script for Dead or Alive 3 characters (thanks guys for helping me with this script)

importing for now mesh only, character skins only (optionally textures from doax/doau)

so:
 - Noesis supports only cubemap environment textures, while doa3's environmet textures are 2d matcap like.

 - some doa3 headers of the cat files have an unknown encryption

 - kasumi00 is missing heaps joints and some foot parts - should find why is that so
 - zack01 crashes if calculating vector's angle with Noesis built in functions - to do

 - team ninja in doa3 format don't use weights for bending, they use the some shit that works on the morphing principle by replacing the location/normal vector from the vertex buffer with some calculated value.
it multiplies the matrices of the bodyparts the joint is joining then operates with some scale and bending(?) vectors from the joint's data(for doao is called some d3d9 method i can't identify), then it's added to some base (?morph)target and swaps the location vector shown in the indices list.

has anyone before broke in the doa joints format?
Hello, my friend, can you share your Noesis script, we look forward to your doa3 script appeared, thank you
