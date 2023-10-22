## Post #1
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-07-26T04:49:01+00:00
- Post Title: Crash Twinsanity .rmx

Hi, I was wondering if someone could help me out with this format - It's an archive I suppose, so all the textures and models are in one file. The models are dynamically loaded in-game. I'm not sure how the models are stored, perhaps there's something I could do with hex2obj?

[http://puu.sh/jbh5O.zip](http://puu.sh/jbh5O.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-26T18:37:58+00:00
- Post Title: Crash Twinsanity .rmx

there's some interesting point cloud - not sure about the face indices:



hubc_rmx.jpg (49.41 KiB) Viewed 64 times
## Post #3
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-07-27T19:50:22+00:00
- Post Title: Crash Twinsanity .rmx

What were your settings for that?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-27T19:53:17+00:00
- Post Title: Crash Twinsanity .rmx

copy these lines into an H2O file:
0x0 500
Vb1
16 99
0x1D0AA 3175
020000
0x0 255

and toggle the 'noPtC' button to 'PtCld' (point cloud)
