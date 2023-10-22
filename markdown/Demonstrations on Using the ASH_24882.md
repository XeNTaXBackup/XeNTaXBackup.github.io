## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T13:53:35+00:00
- Post Title: Demonstrations on Using the ASH

This topic is intended for demonstrations on exploiting the main features of ASH, short for [Amateur Skeleton Hunter](viewtopic.php?f=16&t=24881). It's also served to be an extent on the topic [Approaches of Parsing Bone Representations](viewtopic.php?f=29&t=19429). 
The sample files used can be found here.
[Samples.7z](https://xentaxbackup.github.io/file/21449_Samples.7z)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:10:58+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=148200#p148200).

```
Bone Count: 71
Sibling Layouts:
Address: 0x4

long     skip[3]
float    Rotation[4] // Quaternion
float    Translation[3]
long     skip
long     parentIndex
long     skip

Address: 0xe70

char    boneName[?]

// Little Endian
// Quaternion
// Row-major
// Local Space
// Z, Y, X
```

There's a list of strings storing the bone names in the same order as each bone. A simple way to handle this is to place it in the String Pool Bone Name Object Layout:


Another workaround is to consider it as a normal sibling object in which way you don't need to specify the count twice.



The converted results would be identical:
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:12:37+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=148201#p148201).

```
Bone Count: 28
Sibling Layouts:
Address: 0x4

long     parentIndex
float    Translation[3]
float    Rotation[9] // Matrix
long     length
char     boneName[length]
long     skip

// Big Endian
// Matrix
// Local Space
// Column-major
// Meter
// Z, -Y, X

```

It has all the attributes that you need within a single layout, which is delightful. The Scene Unit is set to Meter for a proper scale during preview.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:17:56+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=148203#p148203).

```
Bone Count: 137
Sibling Layouts:
Address: 0x14

long     boneIndex
long     parentIndex
long     boneNameAddress
float    TransformMatrix[16]

Address: 0x28C0

long     boneNameIndex

// Sibling/Pooled (indexed/addressed(relative)) BoneName
Address: 0x2AE4

char     boneName[?]

// BigEndian
// Matrix
// WorldSpace
// Column-major
// InverseTransformation
// Meter
// Y, Z, X

```

Similarly the name list can be handled as a sibling object like we did before:




The boneNameIndex can be omitted since it's just a copy of the corresponding bone index.

There's also a relative address of the bone name in the first layout so another workaround is to use the by address mode of the pooled name object layout.


The converted results would be identical:
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:18:48+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=148523#p148523).

```
Bone Count: 117
Sibling Layouts:
Address: 0x4

long     skip[3]
long     parentIndex
float    Rotation[4] // Quaternion
float    Translation[3]
float    Scaling[3]
long     skip[3]
long     length
calc     length[+][1]
char     boneName[length]

// Quaternion
// Local Space
// Row-major
// Z, Y, X

```

Also a delightful format, except that the recorded length of the boneName doesn't include the null-delimeter, which however provides an opportunity to demonstrate the "calc" statement.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:22:13+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=148524#p148524).

```
Bone Count: 42
Sibling Layouts:
Address: 0x2BC

long     skip[2]
long     boneIndex
long     parentIndex
long     skip[4]
float    Scaling[3]
float    Rotation[3] // Radian
float    Translation[3]
long     skip[12] // TransformMatrix[12]
long     skip[27]

// EulerRadian/Matrix
// Local Space
// Row-major
// Y, Z, X

```


A delightful yet redundant format, in our perspective. It stores both the individual TRS components and the combining transfromation matrix, so we have two workarounds here.

Using the individual TRS components:


Using the combining transfromation matrix:

```
long     skip[2]
long     boneIndex
long     parentIndex
long     skip[4]
long     skip[9]
float    TransformMatrix[12] // row-major
long     skip[27]

```



The converted results look identical:
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:22:55+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=148525#p148525).

```
Bone Count: 116
Sibling Layouts:
Address: 0x2

long     length
char     boneName[length]
short    parentIndex
long     skip[7]
float    Translation[3]
float    Rotation[4] // Quaternion

// Quaternion
// Local Space
// Column-major
// Z, -Y, X

```

Enought said. Just another delightful format.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:24:40+00:00
- Post Title: Demonstrations on Using the ASH

```
Bone Count: 79
Sibling Layouts:
Address: 0x4

long     skip[2]
long     parentIndex

Address: 0x3BC

float    Rotation[4] // Quaternion
float    Translation[3]
float    Scaling[3]

// Quaternion
// Local Space
// Row-major
// Z, X, -Y

```

A less delightful format, but still acceptable for a lazy man.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:26:14+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=153657#p153657).

```
Bone Count: 220
Sibling Layouts:
Address: 0x2

byte    parentIndex

Address: 0xDE

char    boneName[32]

Address: 0x1C5E

float   TransformMatrix[16]

// Matrix
// WorldSpace
// Column-major
// Y, Z, -X

```

Well, straightforward as it may seem, but just means more typing and clicking to us.
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:27:20+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=156835#p156835).

```
Bone Count: 214
Sibling Layouts:
Address: 0x4

long    boneIndex
long    skip[2]
char    boneName[0x20]
long    parentIndex
byte    skip[0x9C]
float   TransformMatrix[16]
byte    skip[0x10]

// BigEndian
// Matrix
// WorldSpace
// Column-major
// InverseTransformation
// RotationOrder::ZYX
// Y, Z, X

```

A different rotation order other than XYZ is required to avoid gimbal lock. Here we just use the ZYX instead.
(Edit: this is no longer necessary.)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:28:55+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=156897#p156897).

```
Branch 0
Bone Count: 45
Sibling Layouts:
Address: 0xC

float    Rotation[4] // Quaternion
float    Translation[3]
float    Scaling[3]
byte     parentIndex
byte     skip[3]

Branch 1
Bone Count: 5
Sibling Layouts:
Address: 0x7C8

float    Rotation[4] // Quaternion
float    Translation[3]
byte     parentIndex
byte     skip[3]

// BigEndian
// Quaternion
// Local Space
// Column-major
// Meter
// Y, Z, X

```

This is a case where the concept of Branch is involved.



Since the scaling component is omitted in the second Branch, we can't handle it with a single layout while preserving all the explicit attributes, but there's a workaround if we just skip the scaling component.

```
Bone Count: 50
Sibling Layouts:
Address: 0xC

float    Rotation[4] // Quaternion
float    Translation[3]
test     length[<][45]
long     skip[3]
calc     length[+][1]
byte     parentIndex
byte     skip[3]

```



The converted results would be identical:
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:30:06+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=163558#p163558).

```
Bone Count: 72
Sibling Layouts:
Address: 0x4

char     boneName[0x20]
float    Rotation[9] // column-major
float    Translation[3]
short    parentIndex

// Matrix
// WorldSpace
// Column-major
// InverseTransformation
// Y, Z, -X

```

Just another humble candidate among the vast majority of delightful formats. Though it's so desperate to draw your attention by using an inversed transformation of detached components.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:30:52+00:00
- Post Title: Demonstrations on Using the ASH

[Related post](viewtopic.php?p=174620#p174620).

```
Bone Count: 50
Sibling Layouts:
Address: 0x4

word     length
char     boneName[length]
byte     skip // null-delimeter
long     parentIndex
float    Translation[3]
float    Rotation[3] // Quat3

// Quaternion
// WorldSpace
// Row-major
// Z, -Y, X

```

An example of a case where vec3 quaternion is used.
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:31:36+00:00
- Post Title: Demonstrations on Using the ASH

```
Bone Count: 65
Sibling Layouts:
Address: 0x4

long     length
char     boneName[length]
long     length
char     parentName[length]
byte     skip[5]
float    Rotation[9] // Matrix
float    Translation[3]

// Matrix
// WorldSpace
// Column-major
// Z, -Y, X

```

An example of a case where parentName proved its value with the absence of the parentIndex.
