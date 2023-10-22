## Post #1
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-02-28T17:23:07+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

Hello everyone. After years of trying with no luck, I try to ask here. I am having a problem extracting correclty 3ds models from the game "hatsune miku: project mirai DX"
What is the problem?
Well, while character models and animations works just fine, sceneries/stages won't. What happens is the program picks up the 2nd uv as 1st uv, and does not export the 2nd uv, leaving you with the wrong uv and a missing uv, both are just as important. 
While other programs like SPICA displays the stage correctly, it still exports with the same exact issues.
My question is if anyone could fix the uv assignment and also make it so it exports both uvs and not just one.
Both programs are for windows
[https://github.com/gdkchan/SPICA](https://github.com/gdkchan/SPICA) spica source
[https://github.com/gdkchan/Ohana3DS-Rebirth](https://github.com/gdkchan/Ohana3DS-Rebirth) ohana source
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-01T10:11:04+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

> Reply from Makoto ↑Mon Mar 01, 2021 1:23 am at Mon Mar 01, 2021 1:23 am
>
> Well, while character models and animations works just fine, sceneries/stages won't. What happens is the program picks up the 2nd uv as 1st uv, and does not export the 2nd uv, leaving you with the wrong uv and a missing uv, both are just as important.Both uvs? Could you give an example (with textures, if possible)?
This looks ok, doesn't it? (2nd uv for bump map or something similar?)
.



snowman.png (249.38 KiB) Viewed 145 times
## Post #3
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-03-01T15:37:27+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

> Reply from shakotay2 ↑Mon Mar 01, 2021 6:11 pm at Mon Mar 01, 2021 6:11 pm
>
> 
Makoto wrote: ↑Mon Mar 01, 2021 1:23 amWell, while character models and animations works just fine, sceneries/stages won't. What happens is the program picks up the 2nd uv as 1st uv, and does not export the 2nd uv, leaving you with the wrong uv and a missing uv, both are just as important.Both uvs? Could you give an example (with textures, if possible)?
This looks ok, doesn't it? (2nd uv for bump map or something similar?)
.
snowman.png

Thank you so much for looking into it!
Sure, here a comparision(made with floor and houses to make the differences more evident)
[https://imgur.com/a/YhZrAVW](https://imgur.com/a/YhZrAVW)
i say 2 uvs, maybe even 3 because game uses diffuse, lightmaps and maybe vertex colors as well as a 3rd uv, I am sure about 1 and 2 being diffuse and lightmap(even if maybe inverted, since ohana for example picks up the lightmap uv as 1st uv and exports only that one)
[https://imgur.com/a/wSLHCSD](https://imgur.com/a/wSLHCSD) as you can see for the house, on the left you have the house texture, on the right you have the lightmap for the house
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-01T15:49:27+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

Thanks! Does that mean the tool does use the lightmap only here:
.



lightmap.jpg (131.09 KiB) Viewed 126 times


So it doesn't "know" internally about correct uv1?

(I could have a look at the code but I can't promise anything - because the author seems to be knowledgeable. There might be reasons why he used the lightmap as uv 1.)
## Post #5
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-03-01T15:59:59+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

> Reply from shakotay2 ↑Mon Mar 01, 2021 11:49 pm at Mon Mar 01, 2021 11:49 pm
>
> 
Thanks! Does that mean the tool does use the lightmap only here:
.
lightmap.jpg
So it doesn't "know" internally about correct uv1?

(I could have a look at the code but I can't promise anything - because the author seems to be knowledgeable. There might be reasons why he used the lightmap as uv 1.)
Yes, ohana is displaying currently uv1 as lightmap uv, while uv2 would be diffuse(even if it should be the other way around). You see, with the other program i sent (spica) it disaplays correctly, but at the export it exports just like ohana. So both programs read only one of the uvs2, and yet export only one being the ligthmap uv
[https://github.com/KillzXGaming/Switch-Toolbox/releases](https://github.com/KillzXGaming/Switch-Toolbox/releases) this is another tool, kinda wonky imo, a collection of script and such from other programs just o make it an all in one. In all this mess it opens these stages, displays correctly, and you can cycle between different uvs to check which is which if it helps. No point in looking at that code instead of ohana, considering toolbox just took ohana's code and put it along other codes, but it could help you understanding better the uv problem since maybe with my poor english it wasn't very clear...thanks once again for looking into it!
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-01T21:53:01+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

well, easier than expected, so not sure if I hit the spot  
.



snowman_uvs_different.png (210.41 KiB) Viewed 106 times
## Post #7
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-03-01T22:01:01+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

> Reply from shakotay2 ↑Tue Mar 02, 2021 5:53 am at Tue Mar 02, 2021 5:53 am
>
> 
well, easier than expected, so not sure if I hit the spot  
.
snowman_uvs_different.png

it could be just looking like that! can you try other meshes like the house walls please?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-01T22:36:41+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

When I select building_01 in blender's outliner list there's 8 houses highlighted in the 3D view. Thus the uv map is overlapped as hell.
When I try "border selecting" it doesn't select a whole house. No idea, atm.
(Btw, you know the house's meshes are missing their backsides?)

Here's the snowman's texture again:
.



snowman_uvs_different_.jpg (229.64 KiB) Viewed 100 times
## Post #9
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-03-01T22:49:06+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

> Reply from shakotay2 ↑Tue Mar 02, 2021 6:36 am at Tue Mar 02, 2021 6:36 am
>
> 
When I select building_01 in blender's outliner list there's 8 houses highlighted in the 3D view. Thus the uv map is overlapped as hell.
When I try "border selecting" it doesn't select a whole house. No idea, atm.
(Btw, you know the house's meshes are missing their backsides?)

Here's the snowman's texture again:
.
snowman_uvs_different_.jpg

Nope, doesn't seem to fit, but you should notice the snowman has 2 textures, try the other one maybe?
[https://imgur.com/a/GOwinWf](https://imgur.com/a/GOwinWf)
yes, i am aware they are missing their backsides, in game u never see them from behind after all
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-01T23:12:16+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

snowman's ok now (didn't see the tex you uploaded in Ohana, btw).

Building's uv map  is kinda weird, though:
.



isolatedBuilding.jpg (169.48 KiB) Viewed 92 times



Is it possible that there's objects where uv1/uv2 need to be swapped (snowman) and others (houses) where not? (see pic in next post)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-01T23:24:03+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

buildings_uvs_unswapped.png (192.05 KiB) Viewed 87 times
## Post #12
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-03-01T23:26:00+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

> Reply from shakotay2 ↑Tue Mar 02, 2021 7:12 am at Tue Mar 02, 2021 7:12 am
>
> 
snowman's ok now (didn't see the tex you uploaded in Ohana, btw).

Building's uv map  is kinda weird, though:
.
isolatedBuilding.jpg

Is it possible that there's objects where uv1/uv2 need to be swapped (snowman) and others (houses) where not?

if that is the case, it would be really hard on every stage(there are a lot in the game) to know which mesh uses uv1 and which one uv2...
as for the textures, maybe you simply didn't export all textures
I also saw the unswapped one, and can confirm that uv is just the lightmap uv still
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-02T08:08:57+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

Ok, then the best thing would be that you try it out for yourself, imho.

These are the changes to the code I made (very simple, so dunno, whether it's a correct patch),
see CGFX.cs, public static RenderBase.OModelGroup load(Stream data):

```
                                        // swapped 0 to 1!
                                        vertex.texture1 = new RenderBase.OVector2(vector.x * format.scale, vector.y * format.scale);
                                        break;
                                    case PICACommand.vshAttribute.textureCoordinate1:
                                        // swapped 1 to 0!
                                        vertex.texture0 = new RenderBase.OVector2(vector.x * format.scale, vector.y * format.scale);
                                        break;

```

Can't tell the exact line because of adding log lines etc., so search for this loop (2nd occurrence!):
for (int attribute = 0; attribute < vshAttributeFormats.Count; attribute++)

Also I checked the obj export only because exported .dae file seemed to miss uvs completely (I maybe wrong, though).
## Post #14
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-03-02T08:32:31+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

> Reply from shakotay2 ↑Tue Mar 02, 2021 4:08 pm at Tue Mar 02, 2021 4:08 pm
>
> 
Ok, then the best thing would be that you try it out for yourself, imho.

These are the changes to the code I made (very simple, so dunno, whether it's a correct patch),
see CGFX.cs, public static RenderBase.OModelGroup load(Stream data):
Code: Select all                                    case PICACommand.vshAttribute.textureCoordinate0:
                                        // swapped 0 to 1!
                                        vertex.texture1 = new RenderBase.OVector2(vector.x * format.scale, vector.y * format.scale);
                                        break;
                                    case PICACommand.vshAttribute.textureCoordinate1:
                                        // swapped 1 to 0!
                                        vertex.texture0 = new RenderBase.OVector2(vector.x * format.scale, vector.y * format.scale);
                                        break;

Can't tell the exact line because of adding log lines etc., so search for this loop (2nd occurrence!):
for (int attribute = 0; attribute < vshAttributeFormats.Count; attribute++)

Also I checked the obj export only because exported .dae file seemed to miss uvs completely (I maybe wrong, though).

Thank you so much! Sure, i would try myself, but I don't any experience to coding really, only in model porting...those things i need to change that you pointed out, how would i change them? Do i open the exe in notepa++ or something?
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-02T09:09:03+00:00
- Post Title: [HELP] Ohana3ds for nintendo 3ds models does not export correctly

> Reply from Makoto ↑Tue Mar 02, 2021 4:32 pm at Tue Mar 02, 2021 4:32 pm
>
> those things i need to change that you pointed out, how would i change them? Do i open the exe in notepa++ or something?well, no, you can't change the exe in a text editor. In a hex editor, maybe, because it's a small change only, but you usually change the cs file in Visual Studio and compile the project to an exe (pmed you).

edit:
made an unloadable stage loadable with Ohana but seems on the cost of (at least one) spoiled texture (or this stage doesn't need uvs' swap?):
(the texture in question is pv061_lightMap_01_sa, well, "lightmap")
.



loadable.jpg (208.08 KiB) Viewed 49 times


edit2: yeah, no swap for this model of the stage!

So you'll have to work with 2 versions of the Ohana exe because I have no idea, how to detect this automatically. And no time, of course.
