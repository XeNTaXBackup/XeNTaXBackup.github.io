## Post #1
- Username: Lynx
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 14, 2015 4:08 pm
- Post datetime: 2015-09-14T11:38:00+00:00
- Post Title: 3d-gr2 model error foot movement

how do i disable the animation of the feet?

in 3dsmax looks good, but when it is exported...

[https://www.youtube.com/watch?v=yU_Fc2VpO3o](https://www.youtube.com/watch?v=yU_Fc2VpO3o)

pls help
## Post #2
- Username: Lynx
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 14, 2015 4:08 pm
- Post datetime: 2015-09-15T10:02:08+00:00
- Post Title: 3d-gr2 model error foot movement

no one?
## Post #3
- Username: Lynx
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 14, 2015 4:08 pm
- Post datetime: 2015-09-17T16:42:44+00:00
- Post Title: 3d-gr2 model error foot movement

bump
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-17T18:58:15+00:00
- Post Title: 3d-gr2 model error foot movement

don't get it what you mean by "bug"

You could set translation and rotation frames of a foot bone to constant values and tell us what happens
(dunno whether it will work but it's worth a try)
## Post #5
- Username: Lynx
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 14, 2015 4:08 pm
- Post datetime: 2015-09-18T00:28:38+00:00
- Post Title: 3d-gr2 model error foot movement

> Reply from shakotay2
>
> don't get it what you mean by "bug"

You could set translation and rotation frames of a foot bone to constant values and tell us what happens
(dunno whether it will work but it's worth a try)

thank you very much for answering

what should i do to correctly position the feet?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-18T01:02:01+00:00
- Post Title: 3d-gr2 model error foot movement

You didn't answer my "question" - so I don't know what the problem is.

Anyway, this is an excerpt from an DirectX anim file:

```
    {Bip01_L_Foot}
    AnimationKey {
      4;
      41;
      0; 16; 0.999475,0.023210,0.022590,0.000000,-0.020955,0.995217,-0.095413,0.000000,-0.024697,0.094890,0.995181,0.000000,17.597597,-0.000000,-0.000000,1.000000;;,
      1; 16; 0.999475,0.023210,0.022590,0.000000,-0.020955,0.995217,-0.095413,0.000000,-0.024697,0.094890,0.995181,0.000000,17.597597,-0.000000,-0.000000,1.000000;;,
      2; 16; 0.999411,0.025908,0.022514,0.000000,-0.023648,0.995157,-0.095413,0.000000,-0.024877,0.094825,0.995183,0.000000,17.597597,-0.000000,-0.000000,1.000000;;,
...
      39; 16; 0.999317,0.029428,0.022336,0.000000,-0.027171,0.995067,-0.095414,0.000000,-0.025034,0.094742,0.995187,0.000000,17.597597,-0.000000,-0.000000,1.000000;;,
      40; 16; 0.999475,0.023210,0.022590,0.000000,-0.020955,0.995217,-0.095413,0.000000,-0.024697,0.094890,0.995181,0.000000,17.597597,-0.000000,-0.000000,1.000000;;;
    }
  }
```
As u can see the first and the last frame are identical. So u could set all frames of Bip01_L_Foot to the same values.
