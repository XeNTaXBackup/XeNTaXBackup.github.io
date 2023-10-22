## Post #1
- Username: Covet
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 01, 2020 1:31 am
- Post datetime: 2020-03-01T14:20:17+00:00
- Post Title: Need help with Yo-kai Watch 4 skeleton data (.g4mg, .g4pkm, .g4sk)

Hello! I'm currently trying to extract assets from Yo-kai Watch 4. I'm a beginner and don't know what to do about obtaining the skeleton, weights, and any potential animation data. Level-5 uses formats like .g4pkm, .g4sk and .g4mg for their assets and there's very little about them online.

The .g4mg file contains the mesh, but I can't find where in which file the bones are. The .g4pkm, .objbin and .g4sk mention parts of the skeleton, but I just have no idea what to do with them and I'm struggling to find resources to help. I just don't know which files contain what and what to do with their contents.

I've included a sample of files below. If anyone could take a look at them and point me in the right direction, I'd appreciate it. Thanks for your time.

[https://mega.nz/#!KDwGmSAQ!8LfmKakWk39H ... 9zezG8-BO0](https://mega.nz/#!KDwGmSAQ!8LfmKakWk39HAsR4JPnRr3X8AEu3NZhva9zezG8-BO0)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-01T21:10:45+00:00
- Post Title: Need help with Yo-kai Watch 4 skeleton data (.g4mg, .g4pkm, .g4sk)

What did you try out so far? I'd suggest to do it step by step:
.



y01020000.g4mg.png (159.07 KiB) Viewed 152 times


.
bone names from g4pkm:

c_global_0_0
c_ctr_1_0
c_c_1_0
c_c_1_1
r_s_2_0
r_l_2_0
r_l_2_1
r_foot_2_0
r_afir_2_0
l_s_2_0
l_l_2_0
l_l_2_1
l_foot_2_0
l_afir_2_0
c_n_1_0
c_head_1_0
r_lip2_1_0
l_lip1_1_0
l_lip2_1_0
r_lip1_1_0
l_ear_1_0
r_fir_1_0
c_lip1_1_0
r_ear_1_0
c_jaw_1_0
c_ton_1_0
r_lip3_1_0
l_lip3_1_0
r_lip4_1_0
c_lip3_1_0
l_lip4_1_0
l_eye1_1_0
r_eye1_1_0
l_fir_1_0
emofx01
pintage01
l_t_1_0
l_l_1_0
l_l_1_1
l_foot_1_0
l_laux_1_0
r_t_1_0
r_l_1_0
r_l_1_1
r_foot_1_0
r_laux_1_0

In a next step you'll need the matrices and the bones hierarchy (bone ids, parent ids).
## Post #3
- Username: Covet
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 01, 2020 1:31 am
- Post datetime: 2020-03-11T16:10:43+00:00
- Post Title: Need help with Yo-kai Watch 4 skeleton data (.g4mg, .g4pkm, .g4sk)

Thank you for your help so far.

I hadn't tried much by myself. I got as far as getting the character meshes, then trying to look for the bones, and then realised I was in over my head since I'm so new to this. Your post made me realise that I was under the completely wrong impression of how to handle the skeleton.

I found some posts you and other users have made as to how to get started and what my next steps should be, so I'll try from there and will post again if I have any updates or run into more difficulties. Thank you for pointing me in the right direction!
## Post #4
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2021-01-20T08:53:35+00:00
- Post Title: Need help with Yo-kai Watch 4 skeleton data (.g4mg, .g4pkm, .g4sk)

Any updates on g4pkm extraction still not alot of info out there
