## Post #1
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-01-08T02:21:29+00:00
- Post Title: [MATRIX HELP] Concatenating rotational matrices

Hi everyone,

Need a bit of help figuring out how to deal with Cryengine models.  They use a hierarchy of objects; the thigh objects is attached to the shin object.  The shin object is attached to the foot object.  You get the idea.

The translation part of a transformation matrix is the translation of the current object, plus the sum of all the parent objects, all the way to the root.  That's easy to do; they are usually just vectors (x,y,z).  Adding is simple.

However, the case I'm running into is that the rotation matrix (3x3 matrix) also seems to have this same structure.  So let's say the foot object rotation matrix is the identity matrix (no rotation).  But the shin object does have a bunch of values in the matrix.  I need to know how the math works on this.

Since matrix math isn't commutative, I'm assuming the order matters greatly.  And I'm not even sure if I should be multiplying it, or .... what are my other options?  My guess is that it is supposed to be something like this:

[M-foot] * [M-shin] * [M-thigh]

That seem right?
