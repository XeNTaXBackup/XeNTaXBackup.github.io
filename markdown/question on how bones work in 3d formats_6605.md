## Post #1
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2011-05-12T05:49:57+00:00
- Post Title: question on how bones work in 3d formats

If you have only absolute bone matrices in the format, no structure info (parent/child bones) and no real bone info (base/tip) can you build bones in a 3d modeller which will at least have correct angles?
Because it seems for the format im working on, setting the matrix angles as the bone angles gives assymetric rotations between the left and right side of the model.
## Post #2
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-05-12T17:55:59+00:00
- Post Title: question on how bones work in 3d formats

An absolute matrix contains almost all of the info you need. The base of the bone is the origin of the transform (ie transform 0,0,0 with the matrix), rotating something just means passing it through the transform too, and the tip of the bone is actually useless for building bones (it a purely aesthetic editor-side info, and most of the time just the origin of a child bone. If there's not child, just choose an arbitrary length). Naturally though, it doesn't contain any hierarchical info, you'll have to rebuild that yourself, but if the transforms relly are absolute the bind pose will look correct as is.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-12T18:00:18+00:00
- Post Title: question on how bones work in 3d formats

post the model sample and say the game?
## Post #4
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2011-05-13T05:27:21+00:00
- Post Title: question on how bones work in 3d formats

> An absolute matrix contains almost all of the info you need. The base of the bone is the origin of the transform (ie transform 0,0,0 with the matrix), rotating something just means passing it through the transform too, and the tip of the bone is actually useless for building bones (it a purely aesthetic editor-side info, and most of the time just the origin of a child bone. If there's not child, just choose an arbitrary length). Naturally though, it doesn't contain any hierarchical info, you'll have to rebuild that yourself, but if the transforms relly are absolute the bind pose will look correct as is.
I found a Blender importer for a game by someone who seemed to manually rotate some bones because they "seemed" wrong, as he set the matrix rotations to bones. By this I think the models wont support the existing animations.
The bind pose does seem correct. The only issue are the angles and that the bones aren't connected. They really will be very hard to work with.
I thought I could improve the script by hardcoding the skeleton structures (there are only 2 in the game) and the bone matrices, so when I would write an exporter for the format, I would replace the bone matrices of Blender with the hardcoded ones. I don't see a better way. What do you think.
I could send you the script and some examples
