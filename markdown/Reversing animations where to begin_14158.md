## Post #1
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2016-03-29T09:32:23+00:00
- Post Title: Reversing animations: where to begin?

Hello,

While searching for reversing advice I found lots of resources pertaining to reversing 3d models but not so much about animations.

Is there a general tutorial or list of common structures (and possibly mathematical explanations?) or patterns to look for when reversing anim files? Thanks guys
## Post #2
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-17T07:48:54+00:00
- Post Title: Reversing animations: where to begin?

What do you mean by "reversing" animations? Are you talking about literally playing the animation backwards?
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-17T12:54:58+00:00
- Post Title: Reversing animations: where to begin?

animation formats will have a strong link to models they attach to - and models using skeletons will have a hierarchical bone list, etc

so i start by looking for numbers - using the model we have bone counts to compare to. another useful number is the number of frames the animation is, or run length.

depending on the animation technique this may use keyframes - so expect groups of matrices (floats/half-floats, normally 4x4) in your data

hope this helps
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-04-19T00:13:34+00:00
- Post Title: Reversing animations: where to begin?

[out]
