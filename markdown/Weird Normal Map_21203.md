## Post #1
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-10-03T23:55:06+00:00
- Post Title: Weird Normal Map

Hi,

Not exactly a format question, more like something going on with my dumps. I hope it is ok to be here since it's graphic related.

These are the normal maps I'm getting from NinjaRipper. If you switch the image channels you can definitely see there is normal information going on there, but it's not the usual switch/invert channels to get them right.



It is also dumping this:



Does anyone know what is going on there?
I could not figure this one out.

Thanks
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-10-04T01:44:27+00:00
- Post Title: Weird Normal Map

> These are the normal maps I'm getting from NinjaRipper. If you switch the image channels you can definitely see there is normal information going on there, but it's not the usual switch/invert channels to get them right.

This normal map is only the R and G channels, known as the normal maps X and Y.
Normal maps usually ahve 3 channels, RGB right, but the B channel is usually useless information and so can be discarded and rebuild in a shader in the engine itself.
That frees up space to use the B channel for something else, such as a height map, or a roughness map.
Looking at this particular texture, the B channel is entirely diffrent to the previous 2, and its a lot lower detail,it could be a roughness map, I can't really tell sorry.

> It is also dumping this:
>
> Does anyone know what is going on there?
>
> I could not figure this one out.

Thats an LUT texture, LookupTexture.
Typically thats applied to the camera as a post process.
These files handle things like color tinting, you take a screenshot of your scene, with no color tinting applied, take it into photoshop, along with a clean version of an LUT texture, and then in photoshop you start applying effects to the above layers, such as darkening, color tints and so on.
Theres a more detailed explanation of them and what they do here [https://docs.unrealengine.com/en-US/Eng ... index.html](https://docs.unrealengine.com/en-US/Engine/Rendering/PostProcessEffects/UsingLUTs/index.html)

I don't know what engine the files you've exported are from, as a few engines use LUT textures.
## Post #3
- Username: purupeo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 11, 2010 2:55 am
- Post datetime: 2019-10-05T12:05:42+00:00
- Post Title: Weird Normal Map

Try normalcompleter v1.0.
## Post #4
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-10-05T23:24:22+00:00
- Post Title: Weird Normal Map

> Reply from lionheartuk ↑Fri Oct 04, 2019 9:44 am at Fri Oct 04, 2019 9:44 am
>
> 
These are the normal maps I'm getting from NinjaRipper. If you switch the image channels you can definitely see there is normal information going on there, but it's not the usual switch/invert channels to get them right.

This normal map is only the R and G channels, known as the normal maps X and Y.
Normal maps usually ahve 3 channels, RGB right, but the B channel is usually useless information and so can be discarded and rebuild in a shader in the engine itself.
That frees up space to use the B channel for something else, such as a height map, or a roughness map.
Looking at this particular texture, the B channel is entirely diffrent to the previous 2, and its a lot lower detail,it could be a roughness map, I can't really tell sorry.

Ha, yes! I understand about the normal maps, I think I didn't explain my issue very well. Sorry about this.

The problem I have is mostly the channels.
I can tell the Green and Red channels are inverted. They are "GRB". Switching them fixes this problem.
I had to invert the Blue channel so it's white (usually they are mostly white anyway)

BUT now, obviously, the color of this normal map is completely wrong.
The channels are very dark, I tried to play with levels here and there, trying to fix them, but I can never get why it's like that or how to restore it.

What is up with that? Could you figure this out?

> Reply from lionheartuk ↑Fri Oct 04, 2019 9:44 am at Fri Oct 04, 2019 9:44 am
>
> 
Thats an LUT texture, LookupTexture

Oh, I completely missed this one. Thanks 
I thought it had something to do with the Normal mapping (look at the colors hehe)

> Reply from purupeo ↑Sat Oct 05, 2019 8:05 pm at Sat Oct 05, 2019 8:05 pm
>
> 
Try normalcompleter v1.0.

Thanks, this will fix my blue channel, but have a look on the above! hehe
## Post #5
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2019-12-14T12:27:32+00:00
- Post Title: Weird Normal Map

Does NinjaRipper rip everything to 24-bit jpg files?

Because if this is a 32-bit file, then you're missing the alpha channel (RGBA), which could hold some important information.
NinjaRipper could be discarding it.
## Post #6
- Username: Hoogkamp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 02, 2020 12:09 pm
- Post datetime: 2020-03-02T04:14:40+00:00
- Post Title: Weird Normal Map

It’s hard to see what’s going on in your screenshots. The first one is very bright and the second one seems to have a color texture which makes it more confusing. If it’s a normal map problem, all the other material channels are unnecessary to show [liteblue login](https://liteblue.me)
## Post #7
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-03-02T06:38:22+00:00
- Post Title: Weird Normal Map

> Reply from Hoogkamp ↑Mon Mar 02, 2020 12:14 pm at Mon Mar 02, 2020 12:14 pm
>
> 
It’s hard to see what’s going on in your screenshots. The first one is very bright and the second one seems to have a color texture which makes it more confusing. If it’s a normal map problem, all the other material channels are unnecessary to show.

The second one isn't a normal map, its a LUT texture, which is used in various game engines to tint scenes during post processing.
