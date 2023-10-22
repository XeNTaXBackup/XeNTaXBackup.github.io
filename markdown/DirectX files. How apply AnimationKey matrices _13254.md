## Post #1
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-29T11:34:51+00:00
- Post Title: DirectX files. How apply AnimationKey matrices ?

From frames matrices i got combine frames matrices.
I sort SkinWeights names and SkinBone matrices in the order.
Then multiply SkinBoneMatrices on combine frames matrices. I got correct Bind Pose and 3d model looks right.
But how apply AnimationKeys matrices (I am using only matrices, not quaternions) ?
I think:
1) SkinBoneMatrices multiply on AnimationKeys matrices = AnimMatrices 
2) combine frames matrices multiply on AnimMatrices

or 

1) combine frames matrices multiply on AnimationKeys matrices = AnimMatrices 
2) SkinBoneMatrices multiply on AnimMatrices
## Post #2
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2015-08-30T08:43:54+00:00
- Post Title: DirectX files. How apply AnimationKey matrices ?

Or Combine AnimationKeysMatrices and multiply SkinBoneMatrices on Combine AnimationKeysMatrices
And not using combine frame matrices.
