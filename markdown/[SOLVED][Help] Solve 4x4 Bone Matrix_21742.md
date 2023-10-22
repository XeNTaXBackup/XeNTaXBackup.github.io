## Post #1
- Username: MilesPrower
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 10, 2020 4:54 pm
- Post datetime: 2020-02-12T05:03:48+00:00
- Post Title: [SOLVED][Help] Solve 4x4 Bone Matrix

I extracted Names, IDs, Parents and 4x4 Transformation Matrix. I try to import it into 3dsmax which uses 4x3 Matrices. The 4x4 Matrix seems to contain just values between -1 and 1. I Have to less Knowledge about this. It seems also that the Bones are relative to its parent ..

Does anybody know how to solve this Puzzle??

Edit 13.02.2020:
Changed to noesis..


Edit 14.02.2020
I add an exception for the the pelvis .. still some bones look strange... After stepping back parsing and analysing the animation data I found out that only 34 of 64 Bones got animation data.. so I just get rid of the rest.. now its usable and ready for animating.. I think the other bones are physic based driven.

[BONE_FORMAT.zip](https://xentaxbackup.github.io/file/17491_BONE_FORMAT.zip)
## Post #2
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2020-02-12T21:26:58+00:00
- Post Title: [SOLVED][Help] Solve 4x4 Bone Matrix

Looks like you're setting the local space matrix (relative to parent) as the world space matrix (relative to origin) of the bone. To get the world space matrix for bone X from the stored local space matrices you must multiply the local matrices for bone X and all of its parents in the right order.
