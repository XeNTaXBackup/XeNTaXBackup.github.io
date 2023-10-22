## Post #1
- Username: sierra14
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 01, 2017 3:19 am
- Post datetime: 2018-10-03T20:58:21+00:00
- Post Title: Converting Prey (2017) model cgf file to obj - help?

Hey all; so I've used the Prey pak extractor on one of the paks (think object-pak6 or whatever it's called) and got the cgf file, and have attempted to convert it using the cgf-converter - I used the code below in the command prompt, obviously after opening the powershell and setting the location to the place where the cgf-converter.exe is located

```
.\cgf-converter.exe neo_armchair_01.cgf -obj -objectdir D:\cgf-converter -obj
```


I can see from editing the obj file in a hex editor, that there is lots of data (as well as lots of zeros, but also lots and lots of actual data) but I can't open it in blender or sketchup et al - I've tried using a 'proper' obj file and trying to use it as a template for what the actual obj should look like - I've noticed that instead of having single full stops between sections of text (hex 0A) it has two (which turn out to be 0D 0A) but changing them all to 0D 0A's to 0A doesn't help. I can post the file somewhere if anyone wants to examine it - why can't I get a working model? 

obj file [https://ufile.io/nzx3w](https://ufile.io/nzx3w)

S
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-04T05:35:42+00:00
- Post Title: Converting Prey (2017) model cgf file to obj - help?

> Reply from sierra14
>
> I can't open it in blender or sketchup et al
Why? Your files completely adhere to OBJ syntax. 

> Reply from sierra14
>
> I've noticed that instead of having single full stops between sections of text (hex 0A) it has two (which turn out to be 0D 0A) but changing them all to 0D 0A's to 0A doesn't help.
It has nothing to do with the line feeds. The problem is about invalid position data because they're all ZERO so they all collapse to the origin.
## Post #3
- Username: sierra14
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 01, 2017 3:19 am
- Post datetime: 2018-10-04T11:31:37+00:00
- Post Title: Converting Prey (2017) model cgf file to obj - help?

so what am I doing wrong? why won't it come out correctly?
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-04T11:40:15+00:00
- Post Title: Converting Prey (2017) model cgf file to obj - help?

I have no idea coz I've never dealt with the game you're talking about, or the related tools. Where did you find the tools? Are they actually made for that game?
## Post #5
- Username: sierra14
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 01, 2017 3:19 am
- Post datetime: 2018-10-04T11:49:05+00:00
- Post Title: Converting Prey (2017) model cgf file to obj - help?

yes - it's a pak extractor ([viewtopic.php?f=10&t=16241](http://forum.xentax.com/viewtopic.php?f=10&t=16241)) and then a cgf-converter program ([viewtopic.php?f=33&t=13137](http://forum.xentax.com/viewtopic.php?f=33&t=13137))
## Post #6
- Username: sierra14
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 01, 2017 3:19 am
- Post datetime: 2018-10-04T14:44:19+00:00
- Post Title: Converting Prey (2017) model cgf file to obj - help?

It's alright, it turns out I needed an upgraded version of the cgf-converter, I just assumed that because it said it had been updated, it would be alright, but there was a separate exe 

Thanks anyway!
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-04T14:45:51+00:00
- Post Title: Converting Prey (2017) model cgf file to obj - help?

> Reply from sierra14
>
> then a cgf-converter program (viewtopic.php?f=33&t=13137)
So many parameters... Not sure if it's allowed to place them in different orders but you'd better stick strictly to its syntax.
So in this code you used:

```
.\cgf-converter.exe neo_armchair_01.cgf -obj -objectdir D:\cgf-converter -obj
```

Better not to place the "-obj" pram before the "-objectdir". And "D:\cgf-converter" is the location of the cgf file?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-04T15:33:18+00:00
- Post Title: Converting Prey (2017) model cgf file to obj - help?

> Reply from sierra14
>
> I can post the file somewhere if anyone wants to examine it - why can't I get a working model? 

obj file https://ufile.io/nzx3w

Syep, cgf urgently needed.

btw: I used the converter (cool tool, btw) like such:

D:\tmp\era>cgf-converter AEGS_Vanguard_Test.cgf -objectdir D:\tmp -obj
Input file set to AEGS_Vanguard_Test.cgf
Data directory set to D:\tmp
Output format set to Wavefront (.obj)
Output file is \...\AEGS_Vanguard_Test.obj

which produced a 457 MB obj file which was loaded into blender:



cgf-converter.png (100.54 KiB) Viewed 93 times
