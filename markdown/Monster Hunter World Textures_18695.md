## Post #1
- Username: Atheos
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 13, 2018 6:28 pm
- Post datetime: 2018-08-17T06:52:16+00:00
- Post Title: Monster Hunter World Textures

Looking for some help on converting these textures. Never done anything like it before. Any insight, tools, methods, etc are very welcome!

[http://www.mediafire.com/file/hbxv3ashe ... MHWTex.rar](http://www.mediafire.com/file/hbxv3asherdn65z/MHWTex.rar)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-17T11:44:14+00:00
- Post Title: Monster Hunter World Textures

Looks like standard block compression. Using daemon1's tool : [viewtopic.php?f=18&t=16461](http://forum.xentax.com/viewtopic.php?f=18&t=16461)



Btw try asking questions related to textures in the "Graphic file formats" section. I think it would be better suited there.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-17T12:30:58+00:00
- Post Title: Monster Hunter World Textures

Here's a Noesis script to convert the sample images you uploaded:


 tex_MonsterHunterWorld_TEX.rar
(694 Bytes) Downloaded 113 times
## Post #4
- Username: Atheos
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 13, 2018 6:28 pm
- Post datetime: 2018-08-17T15:19:32+00:00
- Post Title: Monster Hunter World Textures

> Reply from Bigchillghost
>
> Here's a Noesis script to convert the sample images you uploaded:
tex_MonsterHunterWorld_TEX.rar

Do you know why some textures would come out oblong in the preview or low res? They still seem to match up to the UV's because they are just stretched but they seem low res. Here are some examples.

Edit: I should clarify that I wasn't only intending to rip the posted ones above. The main goal is ripping all of them and creating a directory for future rippers. 

[http://www.mediafire.com/file/72y3xtwjf ... amples.rar](http://www.mediafire.com/file/72y3xtwjfh85sk6/Examples.rar)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-18T04:24:17+00:00
- Post Title: Monster Hunter World Textures

> Reply from Atheos
>
> 
Do you know why some textures would come out oblong in the preview or low res? They still seem to match up to the UV's because they are just stretched but they seem low res.
They're not low res. That's how they were.

> Reply from Atheos
>
> 
The main goal is ripping all of them
Otherwise why would I write you a script?
## Post #6
- Username: Atheos
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 13, 2018 6:28 pm
- Post datetime: 2018-08-18T15:28:27+00:00
- Post Title: Monster Hunter World Textures

> Reply from Bigchillghost
>
> Atheos wrote:
Do you know why some textures would come out oblong in the preview or low res? They still seem to match up to the UV's because they are just stretched but they seem low res. 
They're not low res. That's how they were.
Atheos wrote:
The main goal is ripping all of them

Otherwise why would I write you a script?

Yeah after testing other things I realize that. There were just a few completely corrupt textures. Some normals with massive chunks missing that when ninja ripped were completely fine. So I'm guessing there is an issue with the way the script works. Same thing with using Raw texture cooker. It's only with a few textures but both your script and RTC do it to them so I'm not sure what the issue is doing it these ways VS NinjaRipper or Intel GPA working. Hope I wrote that in a way that makes sense and I greatly appreciate the script you wrote as its by far the best option.

[Edit] As for the lowres thing I had assumed the game had HD textures but I forgot it's a direct console port.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-21T02:35:09+00:00
- Post Title: Monster Hunter World Textures

> Reply from Atheos
>
> There were just a few completely corrupt textures. Some normals with massive chunks missing that when ninja ripped were completely fine. So I'm guessing there is an issue with the way the script works.
There's only one such image in the sample files you uploaded. 
Edit: 
Checked that file but the issue has nothing to do with the script. The blank area is the result from the null bytes of the file in the middle.
## Post #8
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2018-08-22T03:46:04+00:00
- Post Title: Monster Hunter World Textures

Yeah, it seems to be an issue with the current chunk tool floating around. There are quite a few normal maps that have those null chunks in the middle. I'm hoping the next revision of the tool fixes it.
