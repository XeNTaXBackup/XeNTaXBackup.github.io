## Post #1
- Username: mio2610
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 13, 2018 11:38 am
- Post datetime: 2019-12-10T04:18:23+00:00
- Post Title: Forever 7th Capital textures

Hi! 

First, I'm sorry if my bad English may cause any confusion for you.
I've been trying to rip models from F7C by using: [viewtopic.php?f=16&t=17982&sid=d9a9403e ... 38b22b2c04](https://forum.xentax.com/viewtopic.php?f=16&t=17982&sid=d9a9403e0aee19758c78c738b22b2c04)

Though I was able to rip the models with in-game rig, the only problem I have is the textures, I somehow managed to export .ktx using quickbms, but no program can read it. 

Can anyone please help me with this? Thank you so much!

Attached is the sample I've been working on:
[https://drive.google.com/file/d/1zMt6lg ... sp=sharing](https://drive.google.com/file/d/1zMt6lg4HO0IxLuksKRgllgjpHg76IcvP/view?usp=sharing)
[Screenshot_9.png](https://xentaxbackup.github.io/file/17173_Screenshot_9.png)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-12-10T18:28:45+00:00
- Post Title: Forever 7th Capital textures

> Reply from mio2610 ↑Tue Dec 10, 2019 12:18 pm at Tue Dec 10, 2019 12:18 pm
>
> 
somehow managed to export .ktx using quickbms, but no program can read it.
No wonder. That is not a valid ktx file. Same iqe file but first 128 bytes xored. You are not supposed to use the bms script on the iqe.

Check the F7C File Extractor in the first post of my thread. It was able to extract the texture fine, last time I was testing.
## Post #3
- Username: mio2610
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 13, 2018 11:38 am
- Post datetime: 2019-12-11T04:48:56+00:00
- Post Title: Forever 7th Capital textures

Thank you!

I've tried many times, but whenever I exported .iqe to other programs (like blender or noesis) the file didn't carry the texture with it. Have I done something wrong?
[Screenshot_9.png](https://xentaxbackup.github.io/file/17176_Screenshot_9.png)
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-12-11T06:23:47+00:00
- Post Title: Forever 7th Capital textures

> Reply from mio2610 ↑Wed Dec 11, 2019 12:48 pm at Wed Dec 11, 2019 12:48 pm
>
> 
whenever I exported .iqe to other programs (like blender or noesis) the file didn't carry the texture with it.

Iqe does not have any texture data. It is just model skeleton/geometry. You have to get the textures from the npk archive. They are separate files.
## Post #5
- Username: mio2610
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 13, 2018 11:38 am
- Post datetime: 2019-12-11T17:28:50+00:00
- Post Title: Forever 7th Capital textures

Thank you so much!! I finally figured out the textures!
## Post #6
- Username: rudoga
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 04, 2014 12:36 pm
- Post datetime: 2020-12-22T03:24:48+00:00
- Post Title: Forever 7th Capital textures

> Reply from mio2610 ↑Thu Dec 12, 2019 1:28 am at Thu Dec 12, 2019 1:28 am
>
> 
Thank you so much!! I finally figured out the textures!
could you offer how to rip model's texture from this game. thx
