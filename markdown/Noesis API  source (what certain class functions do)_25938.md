## Post #1
- Username: eArmada8
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 26, 2022 2:13 am
- Post datetime: 2022-10-26T22:56:04+00:00
- Post Title: Noesis API / source (what certain class functions do)

Hi,

I apologize if this has been posted elsewhere, I've had no luck searching.  Are the Noesis functions (that are exposed to plugins) documented anywhere?  (I'm currently looking for the definition of noesis.mat43TransformPoint but I suspect eventually I'll need others.)

My current project is to try to transform a cloth mesh in Atelier Ryza (the so-called 4D mesh) into 3D coordinates in a manner identical to Joschuka's amazing fmt_g1m / Project G1M, so that I can import them using the 3dmigoto Blender plugin.  (I'm aware I can export with Noesis, but this isn't useful for re-injection back into the game as far as I know because the repack tools are designed to work with the 3dmigoto format files.)

When I saw this in Joschuka's fmt_g1m plugin:

```
Line 2017: p = boneMatrixTransform.transformPoint(p)
```

I assumed that meant [x,y,z] dot [[3x3 rotation matrix]] = new [x,y,z] that is rotated about the origin from the old [x,y,z].

But then I see this (unrelated) line:

```
Line 2029: updatedPosition = boneMatrixUpdateTransform.transformPoint(NoeVec3())
```

I interpreted that to [0,0,0] dot [[3x3 rotation matrix]], but that will always be [0,0,0], no?  If it will always be the origin, why call the function at all?  I was thinking maybe it adds the position row (4th row), but then again, what's actually changing??

I've tried looking on Noesis' website (lol), the online manual, plugins/python/__NPExample.txt, and have found nothing.  I'm very confused, and I would appreciate help.  Thanks!

EDIT: I figured it out.  noesis.mat43TransformPoint(self, other) is essentially ((self[3x3] dot other) + self[3]).  Which, now that I have read more and (roughly) understand the difference between rotation and transformation, makes sense.  Thanks!
## Post #2
- Username: eArmada8
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 26, 2022 2:13 am
- Post datetime: 2022-11-15T22:23:12+00:00
- Post Title: Noesis API / source (what certain class functions do)

Update:

I *think* the correct answer to my question above is that Noesis transposes the first 3 rows (the 3x3 rotation matrix) when converting to a 4x4 matrix for matrix operations such as inversion and multiplication.  This is my attempt at converting NoeMat43-type 4x3 matrix to a 4x4 matrix that works for matrix math:

```
import numpy

def Noe43toNml44 (matrix43):
    output = numpy.identity(4)
    output[0:3,0:3] = numpy.matrix.transpose(matrix43[0:3])
    output[3,0:3] = matrix43[3]
    return(output)

def Nml44toNoe43 (matrix44):
    return(numpy.vstack((numpy.matrix.transpose(matrix44[0:3,0:3]),matrix44[3,0:3])))

```


I'm sure someone who is more familiar with game engine programming can explain to me if I am right or wrong, and why.  I'm guessing it's a quirk of how game engines stores matrices in rows instead of columns or something?
## Post #3
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2023-04-16T07:59:11+00:00
- Post Title: Noesis API / source (what certain class functions do)

Hi,
I'm searching for the same answer.

Have you find the solution yet?
