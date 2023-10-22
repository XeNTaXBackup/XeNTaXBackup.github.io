## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-01T06:42:23+00:00
- Post Title: Background Knowledge of Bone Stuffs

Guess it's better to start a separate thread for this, for the sake of management.
Join with the in-depth discussion of parsing bone data [here](http://forum.xentax.com/viewtopic.php?f=29&t=19429).

Here I'll list all the knowledge I've got so far, and it might be extended in the future. Of course, any advice/feekback is welcome.
Coordinate System:
There're two Cartesian coordinate systems for describing the physical world in the field of computer graphics, which're known as the right-handed and the left-handed coordinate system. 

The left-handed orientation is shown on the left, and the right-handed on the right.

An object in a left-handed coordinate system would appear mirrored in the right-handed coordinate system, but they should be the same object to the physical world, so you'll need to convert its coordinates from one to the other system your 3D app is using. For static objects, it can be achieved by changing the sign of the coordinates of any one of the 3 axies, or by swapping any two of the 3 axies. But the former way won't affect the orientation of the rotation so it doesn't work for converting a left-handed skeleton to a right-handed one.
Representation of Bone:
Basically bones are merely a set of nodes containing linking and transformation info. When nodes are linked from one to another, they form a tree structure called a skeleton. Bones are assigned with unique IDs and names so that they can be referred and linked to other bones. 
Transformation is described as translation, rotation and scaling. Translation defines the position of a node, while rotation defines the orientation of this node, and scaling can affect the size of the mesh bound to this node. Depending on the reference coordinate system the bone format uses, it results in the concept of world space and parent space.
If bones are referenced to world space, the rotation info of a parent bone does not influence the position of its child, but it does if they're referenced to parent space.

So far there're 3 ways to represent rotation, that is, Euler angle, rotation matrix and quaternion.
Euler angle: rotation angles along X, Y and Z axis in degrees.
Rotation matrix: the position of a point after application of rotation can be calculated by multiplying its original positions represented as a column vector, with a 3x3 rotation matrix.
The rotation matrix of rotating along X, Y, or Z axis by Rx, Ry, and Rz degrees is respectively as
Code: Select allMx =
[ 1		0		 0       ]
[ 0		cos(Rx)		-sin(Rx) ]
[ 0		sin(Rx)		 cos(Rx) ]

My =
[ cos(Ry) 	0		sin(Ry) ]
[ 0 		1		0       ]
[ -sin(Ry)	0		cos(Ry) ]

Mz =
[ cos(Rz)	-sin(Rz)	0 ]
[ sin(Rz)	cos(Rz) 	0 ]
[ 0		0		1 ]

For different orders how the rotation are performed, the result of the matrix can also be different. 
So altogether there're 6 rotation orders: XYZ, XZY, YZX, YXZ, ZXY and ZYX. 
Note that the multiplication are performed in an opposite order so for rotation order XYZ the final rotation matrix Mr = Mz * My * Mx.
Quaternion: an alternative to Euler angles and rotation matrices, and doesn't result in gimbal lock.

Usually you need to convert quaternion to Euler angle/rotation matrix or rotation matrix to Euler angle to make use of the info properly.

Transform matrix:
If rotation is defined as matrix, it can also be combined with the translation and scaling info and be stored as a 3x4/4x4 matrix.
Say the translation vector to be [Tx Ty Tz]', 
the scaling matrix to be
Code: Select all[Sx 0 0]
[0 Sy 0]
[0 0 Sz]
the rotation matrix to be
Code: Select all[R11 R12 R13]
[R21 R22 R23]
[R31 R32 R33]
the 3x4 transform matrix can be represented as
Code: Select all[	[R11 R12 R13]   [Sx 0 0]			Tx	]		 [ R11*Sx, R12*Sx, R13*Sx, Tx ]
[	[R21 R22 R23] * [0 Sy 0]			Ty	]	=	 [ R21*Sy, R22*Sy, R23*Sy, Ty ]
[	[R31 R32 R33]   [0 0 Sz]			Tz	]		 [ R31*Sz, R32*Sz, R33*Sz, Tz ]
or in the form of a 4x4 matrix:
Code: Select all[ R11*Sx, R12*Sx, R13*Sx, Tx ]
[ R21*Sy, R22*Sy, R23*Sy, Ty ]
[ R31*Sz, R32*Sz, R33*Sz, Tz ]
[ 0	, 0	, 0	, 1  ]
Linear Storage of Matries:
Mathematically we read a matrix by row from left to right, but when it is stored in memory as a linear array, it results in two different orders of storing the elements.
Row-major order: elements stored by row.
Column-major order: elements stored by column.

wikipedia wrote:As exchanging the indices of an array is the essence of array transposition, an array stored as row-major but read as column-major (or vice versa) will appear transposed.
