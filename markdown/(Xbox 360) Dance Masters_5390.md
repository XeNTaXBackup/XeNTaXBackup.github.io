## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-15T00:17:44+00:00
- Post Title: (Xbox 360) Dance Masters

Here is a quickbms script to extract the arc files i am working on a max script for the models now.

```
get magic long
get version long
get files long
get null long
savepos tablestart
for i = 0 < files
goto tablestart
get nameoff long
get offset long
get size long
get zsize long
savepos tablestart
goto nameoff
get name string
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i

```
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-15T04:27:35+00:00
- Post Title: (Xbox 360) Dance Masters

almost done just need to finish weights then i am all set and ill post the script.
## Post #3
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-15T07:09:24+00:00
- Post Title: (Xbox 360) Dance Masters

Wow another Magnificent work from chrrox
Oh yeah chrrox if you have time can you make a script for star ocean 4 too
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-17T01:05:08+00:00
- Post Title: (Xbox 360) Dance Masters

The contents of this post was deleted because of possible forum rules violation.
[dance masters.rar](https://xentaxbackup.github.io/file/3613_dance masters.rar)
## Post #5
- Username: dongliang28
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 17, 2010 8:11 pm
- Post datetime: 2010-11-17T14:13:19+00:00
- Post Title: (Xbox 360) Dance Masters

i am new here.
thanks for your shareing.
what software i could use to open your ".model" file?
## Post #6
- Username: jooped
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 25, 2010 3:30 am
- Post datetime: 2010-11-17T19:39:46+00:00
- Post Title: (Xbox 360) Dance Masters

> Reply from dongliang28
>
> i am new here.
thanks for your shareing.
what software i could use to open your ".model" file?

3ds max
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-19T03:57:19+00:00
- Post Title: (Xbox 360) Dance Masters

Here is an updated script it shows how the bone id's are called in the files but i am not sure how the weighting is stored in the vertex section so any help would be great.
[dance masters.rar](https://xentaxbackup.github.io/file/3618_dance masters.rar)
## Post #8
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-11-19T09:34:07+00:00
- Post Title: (Xbox 360) Dance Masters

Just taking a quick peek, found out the meaning of a few things.

unk35 = FileSize lol not that useful but its something for now

I'm not used to converting maxscript into C++ (for 010 Editor templates)

Anyways here's my current progress on converting it to C++. I'll work on it more tomorrow.

```
//--- 010 Editor v3.1 Binary Template
//
// File: MODELTemplate.bt
// Author:
// Revision:
// Purpose: 
//--------------------------------------

struct Matrix3
{
    float m11, m12, m13, m14; // Row 1
    float m21, m22, m23, m24; // Row 2
    float m31, m32, m33, m34; // Row 3
    float m41, m42, m43, m44; // Row 4
};

struct Bone_t
{
    float A[2];
    int B[2];

	Matrix3 tfm;
	Matrix3 tfm2;

    float C[3];
    int D;
    float E[3];

	int BoneParentID;
};

struct MeshInfo_t
{
    int A[6];
    int NumBoneIds;
    int B[14];
    float C[3];
};

BigEndian(); // Say the file is in big-endian format
char FileIdent[8]; // File Identifier
int unk01; // Probably Version Major?
int unk02; // Probably Version Minor?
int unk03;
int unk04;
int BoneCount;
int BoneOff;
int BoneIDTableCount;
int BoneIDTableOffset;
int MeshInfoCount;
int MeshInfoOffset;
int T20SectCount;
int T20SectOffset;
int TNullSectCount;
int TNullSectOffset;
int T60SectCount;
int T60SectOffset;
int TA0SectCount;
int TA0SectOffset;
int T50SectCount;
int T50SectOffset;
int unk21;
int unk22; // Is a offset
int unk23; // Is a offset
int unk24;
int unk25;
int unk26; // Is a offset
int unk27; // Is a offset
int unk28;
int TMeshSectOffset;
int TMeshSectCount;
int unk31; // Is a offset
int unk32;
int unk33;
int unk34; // Is a offset
int FileSize;
int unk36;


FSeek(BoneOff);
Bone_t BNArr[BoneCount];

FSeek(MeshInfoOffset);
MeshInfo_t NumBoneIds_array[MeshInfoCount];

FSeek(BoneIDTableOffset);
local int test<hidden=true> = 0, test2<hidden=true> = 0, a<hidden=true>;
local int Boneid2_array[MeshInfoCount];
for (a = 0; a < MeshInfoCount; a++)
{
    if (NumBoneIds_array[a].NumBoneIds != test) {
        test2 = FTell();
        FSeek(FTell() + (NumBoneIds_array[a].NumBoneIds * 2));
    }
    if (NumBoneIds_array[a].NumBoneIds == test)
        test2 = FTell() - (NumBoneIds_array[a].NumBoneIds * 2);
    Boneid2_array[a] = test2;
    test = NumBoneIds_array[a].NumBoneIds;
}
```
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-08T14:07:16+00:00
- Post Title: (Xbox 360) Dance Masters

Here is the new max script with weights 
Thanks to fatduck for helping figure it out.
[dance masters.rar](https://xentaxbackup.github.io/file/3882_dance masters.rar)
## Post #10
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-08T14:19:27+00:00
- Post Title: (Xbox 360) Dance Masters

wow fantastic chrrox
How's the MGS 4 going ??
## Post #11
- Username: nightsqual05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 26, 2010 11:38 am
- Post datetime: 2011-03-19T11:54:36+00:00
- Post Title: (Xbox 360) Dance Masters

can u extract dance central 3d models too?
