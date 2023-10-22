## Post #1
- Username: Ventrue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 9:28 pm
- Post datetime: 2010-12-13T20:59:03+00:00
- Post Title: Question about rigged models from JKA/JK3

Hi!

I'd like to ask that is there any way of extracting models from Jedi Knight: Jedi Academy with ingame bones?

Thanks in advance, and sorry, if it has been already answered.
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-12-14T14:32:09+00:00
- Post Title: Question about rigged models from JKA/JK3

Noesis can do this, but requires the .gla for the model to be in the same directory as the .glm in order to retrieve the skeletal data.

It should be noted that we flattened parts of the skeleton in JA for the production assets (although they are less flattened than they were in JK2), so the skeleton you end up with will not be very nicely set up for creating custom animations.
## Post #3
- Username: Ventrue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 9:28 pm
- Post datetime: 2010-12-16T08:58:58+00:00
- Post Title: Question about rigged models from JKA/JK3

I see. Thank you!

Will the flattening affect something in a realtime posing program like XNALara?
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-12-16T14:54:56+00:00
- Post Title: Question about rigged models from JKA/JK3

Yes, but the skeleton should already be unflattened enough to allow you to do basic posing, so you might be fine. In JA, we had some cheesy and terrible ragdoll, which required us to unflatten the basic arm/leg/neck joint hierarchies. So you'll see flattened bones in between the proper hierarchies, but if you manipulate the right bones, you can pose the model pretty effectively. Just not as effectively as the original animators. With the JK2 skeleton, you'd have no hope, and would have to re-attach the hierarchies yourself to pose it.
## Post #5
- Username: Ventrue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 9:28 pm
- Post datetime: 2010-12-17T17:01:48+00:00
- Post Title: Question about rigged models from JKA/JK3

Thank you very much for your help!
I'm looking into it at the moment, I tried out the Taun-Taun and it worked pretty nicely. You made a man very happy today!
