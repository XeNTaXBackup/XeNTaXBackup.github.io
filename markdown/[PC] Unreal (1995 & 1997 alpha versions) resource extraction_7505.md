## Post #1
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-10-14T16:52:12+00:00
- Post Title: [PC] Unreal (1995 & 1997 alpha versions) resource extraction

Greetings. The second of my requests is something I simply forgot to place on the main list of my introduction topic, but nonetheless, the matter IS important for fans of Unreal.

```
http://www.multiupload.com/24ZIJGDE49
```


These two alphas contain textures, models and code not used in the final game. Some of the textures from the 97 demo were extracted, but the main code and models have not. Some of them seem to be embedded in either .unr or .dll files, or both. Known formats that may be encrypted in there include:

.u or .uc -- classes (UnrealScript code)
_a.3d and _d.3d -- models
.pcx -- textures.

I'd like to politely request help in extracting (either by QuickBMS or in any other way possible) the resources we still are missing. Any help will be met with immense amounts of gratitude from Unreal communities.

Thanks in advance.

EDIT: There may be some wav files stashed somewhere as well, but it's doubtful -- both demos are almost completely mute.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-10-18T12:50:16+00:00
- Post Title: [PC] Unreal (1995 & 1997 alpha versions) resource extraction

I'm in support of this, these are the demos containing the dragon, beta blob that looks a bit like a Visceroid, gargoyle-like Warlord, and so forth? I certainly hope the model format hasn't changed much between the versions. As my experience goes with the beta I'm working with (recreating mainly just the beta material like Nitrogen and Fire Sliths, not much else to do since most has been put into OldUnreal) the scripts may be in plain view through any text editor. I shall check to see if that is the case.

Very different it is. Didn't think the earlier versions would be this different. I suppose the 1995 version wouldn't really have much going in the way of uscript, though, as it really has no coded actors as far as I see. Does have models though. Maybe they are uncompressed _a.3d and _d.3d? But in the 1997 alpha, they are definitely there. Already see something interesting, originally was going to be a flamethrower? Well, I'm seeing the scripts for most stuff in Fred.unr of the 1997 demo, it contains, as it seems, the majority of scripts, textures, and models used. Odd method they were going here of storing scripts in maps.

Huh, Dragon script in the EXEC calls something called Dragon.mac. Odd. I guess they didn't want people knowing the EXEC functions so they put them as an external call? Seems ridiculous though. Though, perhaps it is because the model was unfinished as only a fly animation was completed. Regardless, I am intrigued. Somebody on OldUnreal is recreating the models, though, and may put in the missing animations with his own for this.
## Post #3
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-10-18T18:09:00+00:00
- Post Title: [PC] Unreal (1995 & 1997 alpha versions) resource extraction

I know of this initiative, I know Master_Unreal personally from online interactions -- still, I believe that grabbing the original model files and any hidden away textures is a must as well, hence me asking here. Maybe a QuickBMS script would do the trick? I don't know how to make these.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-10-21T09:08:40+00:00
- Post Title: [PC] Unreal (1995 & 1997 alpha versions) resource extraction

Biggest problem that I know of is that models are usually compiled and must be decompiled back into _a and _d though I AM curious if this is quite the case here. Now, from I seem to be able to tell is that in the Unreal 97 Alpha, is that imports, models (_a + _d), and textures, are listed underneath the script code. I recognize animation data and vertexmesh data. Though perhaps is a different version? The big thing is though, is that new Unreal encodes and compresses stuff while the alphas did not... I'm using vertex meshes from other Unreal 1 engine games as reference in any case.

Under Dragon's script, there is the definite model data followed by the animation. With Blob, there's the model data under it, then a very short animation file because it doesn't really have any animations.

Honestly, I have no idea why this would be hard to decompile back into _a and _d data. Follows a very similar routine.

Textures are easy as well, as they don't have any encryption. The palettes used by the textures are not stored far away. I think I'll test my theory and run through here, post what I snag.

Edit: Haven't figured out the exact palette format but it doesn't seem like GGD supports it anyways. But I/you can use UnrealEd to extract textures from 97 alpha it seems, I'll check 95 alpha now.

Edit 2: Same case with 95 alpha. Difference is that 95 alpha didn't have a naming system yet.
[Unreal97Palette.png](https://xentaxbackup.github.io/file/4796_Unreal97Palette.png)
## Post #5
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-10-21T14:46:48+00:00
- Post Title: [PC] Unreal (1995 & 1997 alpha versions) resource extraction

The Unreal95 alpha has no editor to speak of... OK, it has the camera views, but no real commands work.

The Unreal97 alpha editor has no working command to extract meshes.

Bottom line: I need this dissected
