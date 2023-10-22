## Post #1
- Username: S1OTI
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 15, 2021 11:25 pm
- Post datetime: 2022-08-21T19:18:58+00:00
- Post Title: Swizzling textures for Unreal Engine 4 PS4

I'm trying to mod Sackboy: A Big Adventure on the PlayStation 4 but I need a way to swizzle the textures for them to look right. I've heard of a tool for swizzling textures for Unreal Engine 4 games on the Nintendo Switch, but I need to swizzle the textures for PS4. If anyone knows of a tool that can swizzle textures for UE4 PS4, I would appreciate it. (Sackboy's skin is a custom texture here that unswizzles despite already being unswizzled)
## Post #2
- Username: S1OTI
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 15, 2021 11:25 pm
- Post datetime: 2022-08-23T01:07:39+00:00
- Post Title: Swizzling textures for Unreal Engine 4 PS4

Also, if anyone's wondering, this is what the texture should look like

But this is how it ends up looking, at least according to UModel


Not too sure, but I think UE4 PS4 swizzling might be a bit different compared to the GNF swizzling. If anyone wants to make a swizzle script, you could probably use the PS4 texture untiling code from UModel as a reference (SUPPORT_PS4 from UEViewer/Unreal/UnrealMaterial/UnTexture.cpp) But again, any help is appreciated.
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-08-23T13:08:49+00:00
- Post Title: Swizzling textures for Unreal Engine 4 PS4

Swizzling is platform dependent, not engine dependent, so there shouldn't be any differences for raw data. Also, some latest UE games on switch doesn't even use swizzling, I suppose it's now supported on the engine side for different platforms.

I suppose you can convert dds to gnf with PS4 swizzling with something like [Texture Converter](https://github.com/Backporter/SSE-Fallout-4-Texture-Converter) and then copy raw data from gnf to UE asset (DXT raw data has fixed size, based on compression and image dimensions, swizzling only reorganize it). If you can provide original assets (uasset/uexp/ubulk) for texture and dds you want to put back (of the same DXT format and dimensions), I can make a converted sample for reference.
## Post #4
- Username: S1OTI
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 15, 2021 11:25 pm
- Post datetime: 2022-08-24T22:29:54+00:00
- Post Title: Swizzling textures for Unreal Engine 4 PS4

Thanks!    That worked, but I'm not sure why BC1 gnf textures have darker colors than BC3 it seems, I had to brighten up the textures so they weren't darkened. I'm using different items in this screenshot, but they all use custom textures.
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-08-25T09:30:18+00:00
- Post Title: Swizzling textures for Unreal Engine 4 PS4

@S1OTI: BC compressions doesn't change palette or something, they're just optimized for different texture contents. In case of modding it's always recommended to use the same compression for the same texture types, otherwise you may have issues like that due to different blend options and post-processing at the engine side. Also, it may be converter specifics (which I doubt though) - you can convert the same texture to different formats and then check raw data with rawtex (it has support for PS4 unswizzling), if results will be the same, it's related to the game then.
