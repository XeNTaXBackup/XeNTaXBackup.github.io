## Post #1
- Username: gasamsg12
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 02, 2019 5:57 pm
- Post datetime: 2019-10-22T17:51:05+00:00
- Post Title: I need help with COD MW3

Hi, please help me , I have a problem with animation and body and head position with models from COD MW3.
i import (head_delta_elite_b and body_delta_elite_assault_aa) to maya from COD MW3, the body has the correct position, but the head does not.
Then i import the animation (death_explosion_run_b_v1 or other animation). And the body has animation, but the head continues to be there and make only the movement of the jaw.
Please tell - How do I attach the head to the body.

1) [https://imgur.com/a/2sDmOxr](https://imgur.com/a/2sDmOxr)
2) [https://imgur.com/a/mQr6opI](https://imgur.com/a/mQr6opI) - With imported animation
3) [https://imgur.com/a/goXrx1y](https://imgur.com/a/goXrx1y) - Play animation

P.S. even if animate the head separately still it also continues to lie, and make only the movement of the jaw.
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-23T02:55:53+00:00
- Post Title: I need help with COD MW3

> Reply from gasamsg12 ↑Wed Oct 23, 2019 1:51 am at Wed Oct 23, 2019 1:51 am
>
> ...How do I attach the head to the body.
You need to make sure to parent any parts that character has before you import/apply any type of animation, look for the neck bone or what ever is the start bone of the head and parent it to the body while making sure to have proper hierarchy, this should help in giving you an idea what is that about, or simply go on YouTube and look for a better video about parenting in Maya.
[https://www.youtube.com/watch?v=6nRl5XW7MBk](https://www.youtube.com/watch?v=6nRl5XW7MBk)
