## Post #1
- Username: barquetin16
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Mar 21, 2017 12:16 am
- Post datetime: 2018-01-27T21:50:47+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

I was looking into the game files and find out that they are .c3d for the 3d models and astc.ccz for the textures, the textures are no problem but the .c3b are other story, i try the avengers academy script for noesis but it did not work. 
here are some samples:[https://drive.google.com/file/d/1Bb5_ZO ... 0-SWU/view](https://drive.google.com/file/d/1Bb5_ZONX4BzgkOydgZM0RdIstFF0-SWU/view)

the texture are already converted to .astc, it can easily be opened with noesis.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-01-28T14:15:58+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

checked for first submesh only:



c_Dumbledor_skin.jpg (250.97 KiB) Viewed 615 times
## Post #3
- Username: Vancete
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 23, 2014 8:03 am
- Post datetime: 2018-04-30T07:29:25+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

> Reply from barquetin16
>
> I was looking into the game files and find out that they are .c3d for the 3d models and astc.ccz for the textures, the textures are no problem but the .c3b are other story, i try the avengers academy script for noesis but it did not work. 
here are some samples:https://drive.google.com/file/d/1Bb5_ZO ... 0-SWU/view

the texture are already converted to .astc, it can easily be opened with noesis.

Can you give more info about extracting the .astc.ccz?

Thanks
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-30T07:51:05+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

i have not seen any of the ccz samples from this game but if they are
anything like "Avengers Academy" the instruction here should work.   

[viewtopic.php?p=133405#p133405](http://forum.xentax.com/viewtopic.php?p=133405#p133405)
## Post #5
- Username: Vancete
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 23, 2014 8:03 am
- Post datetime: 2018-05-01T16:33:17+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

> Reply from AceWell
>
> i have not seen any of the ccz samples from this game but if they are
anything like "Avengers Academy" the instruction here should work.   

viewtopic.php?p=133405#p133405

Thank you so much!

Now I'm trying the same with c3b models without success, it seems that the same method is not working
## Post #6
- Username: barquetin16
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Mar 21, 2017 12:16 am
- Post datetime: 2018-05-01T17:22:43+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

> Reply from Vancete
>
> AceWell wrote:i have not seen any of the ccz samples from this game but if they are
anything like "Avengers Academy" the instruction here should work.   

viewtopic.php?p=133405#p133405

Thank you so much!

Now I'm trying the same with c3b models without success, it seems that the same method is not working

The blender script for avengers academy works fine with model and maps but without bones
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-09-25T23:57:47+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

I was trying to load this models from Harry Potter: Hogwarts Mystery (v2.9.2) of ios.
models are loads fine though skeleton is not complete.
Mariusz (@Szkaradek123), can you take a look at this? I think it's not an error and skeleton is supposed to be loaded but according to the console you.. skip some bones because of name? Could it be bypass with a workaround?

script that I used: [viewtopic.php?f=16&t=16924&start=45#p138035](https://forum.xentax.com/viewtopic.php?f=16&t=16924&start=45#p138035)
files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1L6jrY-3jk-RvqcLM24_qoyHstbetl6W2?usp=sharing)
## Post #8
- Username: RaphaelWinchester322
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 05, 2021 3:34 am
- Post datetime: 2021-05-04T19:38:17+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

how did you find non released models for harry potter hogwarts mystery i can only find models that are in the game can you tell me
## Post #9
- Username: EthanArgent
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 04, 2021 3:52 am
- Post datetime: 2021-05-09T15:07:45+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

I really need help for extract models from hogwarts mystery... can you contact me on discord Ethan Argent#8832
## Post #10
- Username: RaphaelWinchester322
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 05, 2021 3:34 am
- Post datetime: 2021-05-10T17:41:33+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

@EthanArgent  i can do the models on blender but i cant do textures and i can only find the models that are on the game not the futures ones
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-17T19:29:06+00:00
- Post Title: Harry Potter: Hogwarts Mystery .c3b

Script from Mariusz for Avengers Academy (great work, as always  ), used for HP:HM (.c3b).
Skeleton hierarchy seems to be ok, but matrix values are not used:
.



c_Filch_skin_v7-c3b.png (67.85 KiB) Viewed 158 times


(I'm still fighting with python, as always  : "TypeError: list indices must be integers, not list")

The matrices are filled but not used, seems:

```
[0.897815, 0.348358, -0.269399, -0.000000](matrix [row 0])
[0.386700, -0.330965, 0.860770, 0.000000](matrix [row 1])
[0.210694, -0.876989, -0.431855, -0.000000](matrix [row 2])
[-44.947338, 89.331703, 2.805416, 1.000000](matrix [row 3])
```
