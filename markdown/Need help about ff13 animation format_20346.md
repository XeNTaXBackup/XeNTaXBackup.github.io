## Post #1
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2019-05-08T15:56:34+00:00
- Post Title: Need help about ff13 animation format

Hello everyone!I try to extract animation from ff13,i use noesis to export fbx successfully,but it is a many animation in one,but i check the e1.white.ps3.bin ,it look like it can generate animations,just look like this 


but i am a newer about fileformat,someone can give me some tips about this?

and i upload some samples from ff13(ps3),it can be open by noesis.
sample:[https://github.com/pgw00k/Bleach_Test/r ... sample.zip](https://github.com/pgw00k/Bleach_Test/raw/master/ff13sample.zip)
[1.jpg](https://xentaxbackup.github.io/file/16199_1.jpg)
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-05-09T03:45:00+00:00
- Post Title: Need help about ff13 animation format

> Reply from pgw00k ↑Wed May 08, 2019 11:56 pm at Wed May 08, 2019 11:56 pm
>
> ...but it is a many animation in one...
Since you are NOT clear in your current issue, or what exactly is your trying to achieve, next time make sure include in depth info as to what your trying to achieve, maybe someone with better experience might help.
So if I to deduce based on that, once you load your desired model and it has a multi-sequence of animations, on the export window you need to add following parameter 

```
-fbxmultitake
```
 to load them individually in your desired 3d software.

Also when you click Advanced commands on the right you'll see multiple option for many more formats FBX included.

have fun
[example.png](https://xentaxbackup.github.io/file/16204_example.png)
## Post #3
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2019-05-10T13:38:32+00:00
- Post Title: Need help about ff13 animation format

thanks momo24,I was a newer for file format coder,and i am interested in decode game archive,so i want to learn about this,anyway thanks!
