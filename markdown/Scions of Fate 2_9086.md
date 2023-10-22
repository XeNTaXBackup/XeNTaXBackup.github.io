## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-14T07:46:46+00:00
- Post Title: Scions of Fate 2

yulgang2

Client: [viewtopic.php?p=73513#p73513](http://forum.xentax.com/viewtopic.php?p=73513#p73513)

Model format: xac
tex format: xtex

Probably the same company that made war of dragon, DK Online, and argos online
I've updated the noesis xac parser to support these models, though no bones/animations

Someone want to add them?

[http://db.tt/JgPJByEt](http://db.tt/JgPJByEt)



unpacker

```
#yulgang2 .mpki
#from chrrox
#fix iaw

open FDDE mpki 1
set arcnum 0

goto 0x0c 1
get files long 1

goto 0x20001c 1

for i = 0 < files
    get offset long 1
    get zsize long 1
    get null3 long 1
    get size long 1
    get arcnum long 1
#   print "%arcnum%"
       
    get null1 long 1
    get null2 long 1

    get name string 1
    Padding 4 1
    get null long 1
    set ofile string "ko-kr"

if  name & ofile

    set NAME1 string "ko-KR_"
    set MYEXT string arcnum
    string NAME1 += MYEXT
    string NAME1 += .mpk
    open FDSE NAME1 0

else 

    set NAME1 string "Common_"
    set MYEXT string arcnum
    string NAME1 += MYEXT
    string NAME1 += .mpk
    open FDSE NAME1 0

endif

if zsize == size
        log name offset zsize
else
        clog name offset zsize size
endif
next i

```
## Post #2
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-06-14T10:59:34+00:00
- Post Title: Scions of Fate 2

This animation files?

> http://www.sendspace.com/file/r5qrsk
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-14T11:22:38+00:00
- Post Title: Scions of Fate 2

The main problem is I don't know how to piece together the data to form the skeleton lol
All I have is a pile of bones.

Here's a blender import for War of Dragons
[http://pastebin.com/VeY7GWYg](http://pastebin.com/VeY7GWYg)

The bone struct contains the transform, 4 integers (?, parent index, ?, ?), and the bone name.
After that, I'm not sure what to do with the vert weights and bone indices.
## Post #4
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-06-18T14:24:12+00:00
- Post Title: Scions of Fate 2

```
 16 floats{
   0,1,2,3 = quaterion
   8,9,10 = x,y,z
 }
 4 ints{unk,unk,parent,unk}

```



Getting there, just need to know why it's rotated -.-

EDIT: [https://www.dropbox.com/sh/qbct1tjyv7al ... K9p/Xentax](https://www.dropbox.com/sh/qbct1tjyv7alpoi/xFDZ2tEK9p/Xentax)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T18:40:32+00:00
- Post Title: Scions of Fate 2

Looks good. Maybe I'll figure out how bones work when I look at the code lol
## Post #6
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-01T18:47:56+00:00
- Post Title: Scions of Fate 2

I just noticed I never implemented the boneweights : D

If you have any questions about bones, just shoot and I'll do my best.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T19:17:54+00:00
- Post Title: Scions of Fate 2

I think the problem is that I've never actually worked with a 3D editor, like rigging a model, to get an idea what kind of things I'm working with.

Looking at existing code might give an idea which functions to use, but it doesn't really explain why they were used and what made you use them that way.

Reading a tutorial on how you take a pile of bones and figure out what to do with all of the information to build a skeleton would likely give a better idea on the general process. It would also make it clear which noesis functions I should be using for what, and when I should think about using them, since you probably took some time to figure that out.

There doesn't seem to be that much information either when working with skeletons; some ID's, a bunch of floats that need to be figured out, and some vertex weights?

I'd be interested in the general 1-2-3 process to building a skeleton. Something like 

1. find your bones
2. arrange them
3. connect the dots
4. build them

lol

It would likely be a useful tutorial, since we currently have chrrox's tutorials on getting the meshes out and texturing them, as well as working with compression, but nothing about skeletons and eventually animations.
## Post #8
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-01T20:14:42+00:00
- Post Title: Scions of Fate 2

Well, it's hard to write a tutorial because of how the bone data is given.
Sometimes it's a Quaternion(x,y,z,w), other times it's Euler angles(in radians 1 rad = ~57°) and if you're lucky they just give you a matrix itself and if you're unlucky the data needs to be calculated before anything can be done with it.

Then we also have the relative versus absolute data. Noesis wants parent-child relative data for animations but it doesn't matter for Bones itself.

For Noesis to understand the bonedata you need to put it in a matrix ( NoeMat43() )
which is 
```
[0 1 0]
[0 0 1]
[0 0 0]

```

for a default matrix which means no rotations (top 3 rows) and offsets = 0,0,0 (x,y,z)

You can also have data in a 4x4 matrix

```
[0 1 0 0]
[0 0 1 0]
[0 0 0 1]

```

but that doesn't change anything for our matrix.

Each of these can be turned into the other.
For the script above we were given a string of floats where 8,9,10 were the x,y,z offsets and floats 0-4 were floats for the Quaternion
so we have for the rootbone for the mo_ma_fe_be_graverobber__b00.xac

```
y = 0.96
z = -0.0004
rx = 0
ry = -0.71
rz = 0
rw = 0.71
```


So we take the data for the Quaternion and turn it into a 4x3 matrix:

```
quaternion = NoeQuat(quat)
matrix = quaternion.toMat43()

```


result:

```
[0.0       -1.016   0.0    ]
[-1.008  0.0       -0.008]
[0         0           0      ]

```

Depending on the data thay have given you you might need to invert the matrix.

```
matrix = matrix.inverse()
```

This was needed because of the first pic I posted earlier which made the armature rotate.
result:

```
[0.0     -0.98    0.0   ]
[-0.99   0.0      0.008]
[0         0        0      ]

```


that's our rotationmatrix but we still need to feed the bone it's offsets.

```
matrix.__setitem__(3,(x,y,z))

```

our matrix is now done. and we'll now create the bone

```

```


The none is for parentName but we're using the parentID which was also stored in the bone data.

I have to go atm, i'll post more later.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T20:33:22+00:00
- Post Title: Scions of Fate 2

Hmm, so start by putting together the information required to represent a bone, and then add the bones to a list.

Now we have a pile of bones that have the necessary data to build a skeleton with.

Next I would guess we need to run some function that will take our pile of bones, and it will conveniently construct the skeleton for me with the given information (where a bone goes, how it's rotated, and what it's connected to). The result would be the screenshot above, where you have a proper skeleton.

Looking at the added code, a single setBones call does the trick.

I see a call to multiplybones, which I'm thinking is the fact that the transform for one bone would also affect any bone that's attached to it, so that function just does all the math for you rather than having to manually multiply matrices recursively for every possible relation.

So the procedure is pretty straightforward

1: collect the bones
2: add them to a list
3: multiplyBones, if needed
4. mdl.setBones

The two things you've mentioned when interpreting bone data would be in step 1.
Aside from the math, what about the relative/absolute part? How does an absolute relationship look like?

From the sounds of it, after building the skeleton, we're pretty much done with the actual bones, and the next step would be to attach the skin to it through bone indices and vertex weights (does not sound simple, and seems like there are different types of weights eg: flat weights, etc.)

After that skinning process is done, is that it? Or are there other things to consider along the way?

Of course, there would need to be some way to verify that it is correct. Wonder how that would work.

Finally, after I figure out how to load the weights properly, I would then need to figure out how to deal with models that are split into smaller meshes across multiple files. With static meshes, I can afford to just toss everything into lists and then apply the materials in one call, but it seems like with bones it will be a little different.
## Post #10
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-01T21:33:13+00:00
- Post Title: Scions of Fate 2

rapi.multiplyBones is indeed for parent-child relationships IF the data is relative.
I corrected my mistake in the previous post where I said the data needs to be relative (which is true for animations but not bones)

Basically what multiplyBones does is take the matrix of the parent and multiply it by the relative matrix of the child and you get the absolute matrix of the child.
If you have an absolute child matrix you need to multiply it with the inverse matrix of the parent to get the relative child matrix. This needs to be done if the animation data is absolute.

The manual operator is 
```
Basically using the .__mul__() function of a NoeMat43()
```


Skinning data:

```
rapi.rpgBindBoneWeightBufferOfs(self.vertBuffer, noesis.RPGEODATA_FLOAT, 64, 52, 3)

```

this is an example from the Path of Exile script.
where the mesh holds 4 UBytes for boneID's and has 3 floats to define the weighting.
all the weights need to add up to 1 so in this case if 3 floats don't add up to 1 the remaining weight is for the 4th ID.
This needs to be called before rapi.rpgCommitTriangles

Sometimes the ID's in the vertex data doesn't match the default boneID you fed Noesis and you need to use rapi.rpgSetBoneMap

I hope this was helpful, but most of the time you'll need to use trial and error to get the correct result.

I just finished the Path of Exile animations where there were missing/empty frames in the animations so you have to add default matrices so the bones stay the same and where most animation was done by just rotation the parent bone and not using offset data.

It usually takes me a few hours to get the mesh deciphered and imported but days if not weeks until I get the bones right.
And PoE was the first time I managed to complete animations.

If anyone sees errors in what I said or has something to add, speak up because I'll be more than happy to learn.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T21:43:33+00:00
- Post Title: Scions of Fate 2

So actually applying the weights themselves is easy if the bone IDs and weights are just stored in each vertex, and the skeleton has been constructed.

For DK online you assumed the bones are just stored in some sequential order. Does this usually work when no bone ID is given?

I've noticed that there's an extra point at the bottom of every model when I view the skeleton. Is that supposed to be there?

Are there any "typical" values for weights? Cause I've noticed there are usually a bunch of floats in vertices (given that the weights are stored there) that are all in the e-05 to e-07 region.

Any simple way to test whether it's skinned properly?
Like maybe some "test" animations that don't really do much except move a bone up and down, and then just do a little setup to indicate which bone should be tested.
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-01T21:58:29+00:00
- Post Title: Scions of Fate 2

noesis has a built in animation test you can use. also you can rotate the bones in noesis.
all weights will add up to 1.0 because a vertex can not have more then 100% weight.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T22:05:07+00:00
- Post Title: Scions of Fate 2

I figured out how to rotate bones, but is the animation test a script call or something in the viewer?
## Post #14
- Username: errno
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-01T22:17:34+00:00
- Post Title: Scions of Fate 2

the command in the documentation
{"createProceduralAnim", Noesis_CreateProceduralAnim, METH_VARARGS, "generates a procedural animation. (OOi)"}, //args=NoeBone list, NoeProceduralAnim list, numFrames
## Post #15
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-02T10:24:53+00:00
- Post Title: Scions of Fate 2

I usually play around with all the data that I don't know what they're for to see if anything adds up.

I make Noesis print it all out like so:


and when I think I've got it I sometimes try to connect them (usually when bonenames don't make sense):
(Images aren't from the same format)


Mostly the bones have sequential ID's in the file but they somtimes require a boneMap to be linked to vertices.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-03T18:03:37+00:00
- Post Title: Re: Scions of Fate 2

I'm looking for a format that's relatively straightforward but can't find one lol
Maybe I'll go grab something that's already been done.
## Post #17
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-03T18:19:09+00:00
- Post Title: Re: Scions of Fate 2

I was considering taking some freeware models from the net and putting them in a custom format to use in a tutorial.

Too much effort imo 
When you do find a format you want to try let me know and I'll have a look at it as well but I won't be available for a while after this week.
