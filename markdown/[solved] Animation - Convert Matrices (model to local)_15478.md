## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-10T12:27:03+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

I'm trying to animate my model with Three.JS (see [documentation](https://threejs.org/docs/#Reference/Math/Matrix4)), the animation file (see [file](https://rawgit.com/majimboo/kBr/master/examples/files/object.json)) I'm using only stores the bone transforms in modelspace 4x3 matrices (or 3x3 rotation matrix + position vector3). 

I'm guessing Three.JS needs it to be in localspace because it doesn't work if I use the matrices directly.

Problem is: I have no idea how to convert it. If anyone can help me understand the mathematical formulas and the whys, that would be great.

The following images are the expected results:


The actual result (problem) can be found on this fiddle = [https://jsfiddle.net/do4037kb/](https://jsfiddle.net/do4037kb/). (Note: you can move the camera around the model, and zoom)

I have also tried: (but still didn't work)

```
frameMatrix.multiply(boneMatrix);
var inverseParentMatrix = new THREE.Matrix4();
inverseParentMatrix.getInverse(root.getObjectByName(key).parent.matrix);
frameMatrix.multiply(inverseParentMatrix);

```

Any idea how I can fix my script? (see fiddle for code and result)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-10T15:47:13+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

> Reply from majidemo
>
> Any idea how I can fix my script? (see fiddle for code and result)umpf, well, not at a first glance.
I'd care for the transitions first.
Did you notice that if you comment out
frameMatrix.copy(rotation)
the moving cape is processed properly?

If you set frameBones.length to 2 in this line
for (var y = 0; y < frameBones.length; y++)
you can see that the mesh is displayed properly.



mesh_ok.JPG (56.36 KiB) Viewed 213 times


So I'd proceed step by step.

I'm looking for the part of your code which handles this (if required):

"while many games have the transform matrix in parent space, so you have to multiply the parent matrix by the child matrix to get the world [...] matrix. If it has multiple parents, all must be multiplied." (Bastien)
## Post #3
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-10T16:47:38+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

The mesh actually is ok if you click on the "stop animate". The transformation to the bones is the one making it deformed.

I did notice that the cape looked right, when I commented out "frameMatrix.copy", but removing the rotation component of the animation wouldn't be right.

Also, changing "frameBones.length" to 2 would only get the first 2 bone animation matrices. 

> "while many games have the transform matrix in parent space, so you have to multiply the parent matrix by the child matrix to get the world [...] matrix. If it has multiple parents, all must be multiplied." (Bastien)
The quoted is great advice too. Although, I'm not sure which matrices I have to multiply, the original bone matrices from the file? or the calculated bone matrices on the scene? and how would I do it for the animation?

I remember MrAdults telling me something similar in [this thread](http://forum.xentax.com/viewtopic.php?f=16&t=15065). He was talking about the animation matrices on my files:

> Reply from MrAdults
>
> 4) Unlike model bones, which are in modelspace, animation transforms are assumed to be in local space, so relative to the parent in the hierarchy. In addition to that, the frame transforms in the file are transposed. So you want to rework your whole frame loop to look something like this:
Code: Select all            for fi in range(0, numFrames): # frames
                modelSpaceTransforms = []
                modelSpaceInverseTransforms = []
                #first accumulate all of the transforms in modelspace
                for bi in range(0, numBones):
                    boneMat = bones[bi].getMatrix()
                    frameMat = NoeMat43.fromBytes(ani.readBytes(48))
                    modelSpaceMat = boneMat * frameMat.transpose()
                    modelSpaceTransforms.append(modelSpaceMat)
                    modelSpaceInverseTransforms.append(modelSpaceMat.inverse())
                #now run through and calculate local space transforms to use as the animation transforms
                for bi in range(0, numBones):
                    localSpaceMat = modelSpaceTransforms[bi]
                    if bones[bi].parentIndex >= 0:
                        localSpaceMat = localSpaceMat * modelSpaceInverseTransforms[bones[bi].parentIndex]
                    animFrameMats.append(localSpaceMat)

But I'll investigate further with the idea's you've given. And as always, I can't thank you enough for the help
## Post #4
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-11T03:00:48+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

I found this out: DirectX and OpenGL uses different conventions in dealing with matrix.

I read about it here: [http://www.mindcontrol.org/~hplus/graph ... ayout.html](http://www.mindcontrol.org/~hplus/graphics/matrix-layout.html)

> Traditional mathematicians, and OpenGL, tends to prefer colum vectors. Meanwhile, certain other legacies of computer graphics, as well as DirectX, tend to prefer row vectors, on the left. The confusion gets even more complete when you start talking about "pre-multiplying" and "post-multiplying" matrices. Pre-multiplying may mean multiplying it on the left (if you're the row vector type), or it may mean multiplying it on the right (if you're the OpenGL type) -- if by "pre" you mean that the pre-multiplied operation happens before the target matrix operation. If instead you mean, with pre-multplying, that the matrix you're pre-multiplying goes on the left, then it means that it happens afterward in the OpenGL notation, but it still means that it happens before in the DirectX notation
Considering that the game I'm working with uses DirectX, it is understandable that the matrices stored in the files follows DirectX convention... Three.JS on the otherhand uses WebGL or OpenGL ES 2... A different convention...

I have updated the fiddle but still not yet completely fixed, but seems to be a bit closer: [https://jsfiddle.net/do4037kb/21/](https://jsfiddle.net/do4037kb/21/)

This is the part where I tried to multiply the frame matrix with the bone and its parent bone.

```
modelSpaceMatrix.multiplyMatrices(root.skeleton.bones[y].userData.modelMatrix, frameMatrix);

inverseFramematrices.push(new THREE.Matrix4().getInverse(modelSpaceMatrix));

var parentId = root.skeleton.bones[y].userData.parentId;

if (parentId >= 0) {
  modelSpaceMatrix.multiplyMatrices(modelSpaceMatrix, inverseFramematrices[parentId]);
}
```


-------------------------

This is another good read but it's the opposite of what I wanted: [http://gamedev.stackexchange.com/questi ... to-directx](http://gamedev.stackexchange.com/questions/51319/rotation-matrix-from-opengl-to-directx)
So I guess, transposing the matrix should fix the directx/opengl problem.

-------------------------

Here is an example exporter from Blender into ThreeJS format: [https://github.com/mrdoob/three.js/blob ... ion.py#L56](https://github.com/mrdoob/three.js/blob/master/utils/exporters/blender/addons/io_three/exporter/api/animation.py#L56)
There should be something interesting there.
## Post #5
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-12T14:58:19+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

I finally figured this out. What MrAdults and Bastien said helped me get the answer. Thanks again, sir shakotay2.

#closed
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-12T16:35:21+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

that's great!  

Could you please give a brief survey about the main points to get your solution?
Or your final code.

Because there was transposing, multiplying and inversing matrices.

Transposing was only required to adapt the opengl matrices for DirectX, right?
## Post #7
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-14T02:14:26+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

That is right, I had to transpose the matrices to make it work with WebGL/OpenGL. 

The rest, like the multiplying and inverting was the part that converted the modelspace bones to localspace (heirarchy). I'm not very good in explaining, so I hope showing you the code will suffice 

```
frameMat.set(
  bone.rotationMatrix[0], bone.rotationMatrix[3], bone.rotationMatrix[6], bone.positionVector[0],
  bone.rotationMatrix[1], bone.rotationMatrix[4], bone.rotationMatrix[7], bone.positionVector[1],
  bone.rotationMatrix[2], bone.rotationMatrix[5], bone.rotationMatrix[8], bone.positionVector[2],
  0.0,     0.0,     0.0,     1.0
);

// var boneMat = new THREE.Matrix4().copy(_bone.userData.modelMatrix);
var boneMat = _bone.matrixWorld;

var modelSpaceMat = new THREE.Matrix4();
modelSpaceMat.multiplyMatrices(frameMat, boneMat);
_bone.userData.modelSpaceMat = modelSpaceMat;

var localSpaceMat = new THREE.Matrix4();
localSpaceMat.copy(modelSpaceMat);

if (parentId >= 0) {
  var inverseModelSpaceMat = new THREE.Matrix4().getInverse(_bone.parent.userData.modelSpaceMat);

  localSpaceMat.multiplyMatrices(inverseModelSpaceMat, modelSpaceMat);
}

```


1. I had to transpose the rotation part of frameMatrix.
2. Multiply the boneMatrix to the frameMatrix. (had to swap the factors so: frameMat * boneMat)
3. If the bone has a parent I also had to multiply the result of frameMat*boneMat to the parents inverted frameMat*boneMat.
4. The result is the localspace matrices.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-14T06:43:05+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

Thank you very much!  
Great to see your progress; seems you're walking a steep learning curve.
## Post #9
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-11-14T07:01:01+00:00
- Post Title: [solved] Animation - Convert Matrices (model to local)

True, been a long journey getting here. First time reversing a file format was the hardest, but thanks to your help I've progressed far enough. 

Now the only files left to unpack/extract are the weapons/shield and map datas like: stones, trees, grass...as the terrain was already completed (still with your help ;D). Characters, Npc's, monsters and other data are also done. 

I'll open another topic about the weapons (soon, if I still can't figure it out by myself), as I'm a bit confused about it. The weapons obj file doesn't seem to have any indices data.

Cheers!
