## Post #1
- Username: MadSquirrel
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 03, 2009 11:16 pm
- Post datetime: 2013-06-19T12:51:46+00:00
- Post Title: Bones matrix

Hi ! 

I'm trying to understand Firefall models format.  
3D models are in bMesh files. The global structure of these files are quite easy to understand (just a bunch of Nb of data / data sections)
Until now, I have the mesh object, and I'm trying to add the bones.

Each bones has a name, parent index, and 2 matrix 4x4. It's the first time I am playing with 3D file structures, and I don't know what to do with these matrix.
Both matrix look "standard" (from what I found on the web) :

```
[d e f 0]
[g h i 0]
[x y z 1]
```


(x, y, z) of the first matrix seems to be the coordinates of the head of the bone. What about tail coordinates ? length ? roll ? Does the matrix contains all these parameters ? What is the purpose of the second matrix ?

Can anyone point me in the right direction ? 

Thanks.

Can't attach sample file ... Will find another way to send it.
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-06-19T14:16:13+00:00
- Post Title: Bones matrix

The matrix you are talking here is a combined form of Translation, Rotation and Scale in 3D world.
[Look here for detail explanation](https://en.wikipedia.org/wiki/Transformation_matrix)
## Post #3
- Username: MadSquirrel
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 03, 2009 11:16 pm
- Post datetime: 2013-06-19T14:35:59+00:00
- Post Title: Bones matrix

Thanks for the link, it brings back memories ! 
It's about 15 years that I didn't "play" with matrix, so I know what is coded inside, but I just don't remember exactly how to use it.

To build my bone, I need head and tail coordinates. I got the head, but how can I get the tail ? I tried all kind of operations with the head vector and the matrix, without success. For "simple" bone chain, like a leg, or spine, I assume the tail of the parent bone should be at the same place as the head of the child. But with all my matrix manipulations, I could not find such result. I probably miss something obvious !

Moreover, why 2 matrix for each bone ?
## Post #4
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-06-20T18:17:54+00:00
- Post Title: Bones matrix

are you importing to blender?
as far as i know games usually have node based bones which do not have tails(required by blender), and in blender you have to find how many children a bone have and to decide which bones should be connected. but this messes things even more because the animation for node bones assumes by default that the bones vectors are pointing "down", and when you connect bones you change they're direction in space.

you shouldn't really count on this info. go google for "bones", "import" and "blender", or something like that to find out what is this all about...
## Post #5
- Username: MadSquirrel
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 03, 2009 11:16 pm
- Post datetime: 2013-06-20T21:28:38+00:00
- Post Title: Bones matrix

Thanks for the info 

Yes, I am working with Blender. I am not exactly "importing". I am writing an API to create blender files. So when it's ready, it should be quite easy to add an "export to .blend" function, in 3D viewers programs like Noesis, WowModelViewer, or 3D object converter for example.
I'm at the very begining, so now I can only create a blend file with meshes (from a list of vertex coords, and a list of faces).

Moreover, it's a long time I want to try "3D model reversing". So I decided to kill two birds with one stone, and decrypt Firefall 3D models to test my API. Maybe I was too greedy  I think I will give up Firefall for now, and test with WoW models. The format is well documented, and I already worked on WowModelViewer a few years ago, so it should be easier for me.

Just for information (maybe it can be useful to someone) :
- About Firefall bones : I didn't understand why they store 2 matrix 4x4 for each bone. Well, I still don't understand, but I found that the second matrix is the first one inverted ! Matrix inverse is a quite fast operation, so why not doing it at runtime ? Why storing both a matrix and its inverted ?
- About Blender bones : I converted a Firefall model (with bones) as blend file. Of course, bones were upside down (except heads on the correct position). I manually corrected a few bones position, and "explored" the resulting blend file. The matrix 4x4 in the blend file has many common values with the Matrix 4x4 of the Firefall file. Only 4 values seems to come from nowhere. This could be the rotation part of the matrix, and so, this could confirm your theory about the change of direction when connecting bones in Blender.

EDIT : A question suddenly comes to my mind : If games usually use node based bones, then only 3 coordinates are needed, to place the bone. So ... why a matrix 4x4 ?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-06-21T08:10:06+00:00
- Post Title: Bones matrix

> Reply from MadSquirrel
>
> EDIT : A question suddenly comes to my mind : If games usually use node based bones, then only 3 coordinates are needed, to place the bone. So ... why a matrix 4x4 ?The answer might be: quarternions:
[http://www.cprogramming.com/tutorial/3d ... nions.html](http://www.cprogramming.com/tutorial/3d/quaternions.html)
## Post #7
- Username: MadSquirrel
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 03, 2009 11:16 pm
- Post datetime: 2013-06-21T12:53:08+00:00
- Post Title: Bones matrix

Very interesting website, thanks !
## Post #8
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-07-06T02:27:33+00:00
- Post Title: Bones matrix

I had the same problem with blender, "how the hell get the tail position".
Now, did you verify that the first Matrix is the head position of each bone? The first bone is the root bone always and the rest might or might not be given in relative-to-the-parent space.
You can easily check that in blender by creating empties using the matrices provided.
But I read you already could import the bones ?

btw, creating a blend file sounds very interesting, I don't recall any other exporter like that, could be very useful.
## Post #9
- Username: MadSquirrel
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 03, 2009 11:16 pm
- Post datetime: 2013-07-11T12:39:17+00:00
- Post Title: Bones matrix

Yes, I "nearly" got the bones. The first matrix give the head position, but each vector in the matrix is normalized, so there is no way to get the tail position from the matrix. But it doesn't matter, only the bone direction is important. So I calculate the tail position from the direction vector (arbitrary, 1/20th of it). All the bones have the same length, but it souldn't be a problem. 
Now I just fight with math to get the roll angle of the bones 
[Firefall.jpeg](https://xentaxbackup.github.io/file/6517_Firefall.jpeg)
## Post #10
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-10-16T03:09:03+00:00
- Post Title: Bones matrix

These functions take the translations and give you the roll and tail positions. Since they are node bases, the bones will be pointing forward, not very nice for animation, but it's something. 
The [official SMD importer](https://developer.valvesoftware.com/wiki/Blender_SMD_Tools) for blender deals with making the bones very small and assigning a sphere shape.
Source: [BA](http://www.blenderartists.org/forum/showthread.php?260602-assigning-matrices-to-EditBones-in-2-5-2-6-solution)

I tried it for only one game and worked very well, only thing also is that all bones in blender are assigned in armature space, while many games have the transform matrix in parent space, so you have to multiply the parent matrix by the child matrix to get the world (armature space) matrix. If it has multiple parents, all must be multiplied.

Code:

```

def vec_roll_to_mat3(vec, roll):
    target = mathutils.Vector((0,1,0))
    nor = vec.normalized()
    axis = target.cross(nor)
    if axis.dot(axis) > 0.0000000001: # this seems to be the problem for some bones, no idea how to fix
        axis.normalize()
        theta = target.angle(nor)
        bMatrix = mathutils.Matrix.Rotation(theta, 3, axis)
    else:
        updown = 1 if target.dot(nor) > 0 else -1
        bMatrix = mathutils.Matrix.Scale(updown, 3)
        
        # C code:
        #bMatrix[0][0]=updown; bMatrix[1][0]=0.0;    bMatrix[2][0]=0.0;
        #bMatrix[0][1]=0.0;    bMatrix[1][1]=updown; bMatrix[2][1]=0.0;
        #bMatrix[0][2]=0.0;    bMatrix[1][2]=0.0;    bMatrix[2][2]=1.0;
        bMatrix[2][2] = 1.0
        
    rMatrix = mathutils.Matrix.Rotation(roll, 3, nor)
    mat = rMatrix * bMatrix
    return mat

def mat3_to_vec_roll(mat):
    vec = mat.col[1]
    vecmat = vec_roll_to_mat3(mat.col[1], 0)
    vecmatinv = vecmat.inverted()
    rollmat = vecmatinv * mat
    roll = math.atan2(rollmat[0][2], rollmat[2][2])
    return vec, roll


```


Usage:

```
axis, roll = mat3_to_vec_roll(mymatrix.to_3x3())
                
bone = armature.edit_bones.new('name')
bone.head = pos
bone.tail = pos + axis
bone.roll = roll

```
## Post #11
- Username: MadSquirrel
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 03, 2009 11:16 pm
- Post datetime: 2013-10-16T13:32:41+00:00
- Post Title: Bones matrix

I'll try it. Thanks
