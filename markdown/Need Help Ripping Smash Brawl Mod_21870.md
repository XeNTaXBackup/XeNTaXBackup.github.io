## Post #1
- Username: Mechanist'sVise
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 13, 2020 3:40 am
- Post datetime: 2020-03-12T19:54:25+00:00
- Post Title: Need Help Ripping Smash Brawl Mod

Recently, I have discovered a mod for Super Smash Brothers Brawl, that being the Robo-Lucario model swap mod ([http://forums.kc-mm.com/Gallery/BrawlVi ... ber=210289](http://forums.kc-mm.com/Gallery/BrawlView.php?Number=210289)). I decided that I wanted the model to use in renders and such, so I downloaded the mod, unpacked the files, and opened the model's .pac in BRRES Viewer. This is where the problem comes in. You see, the model loaded in just fine, but the textures were incorrect. This is what it should look like: ([https://m.imgur.com/XkF2JS5](https://m.imgur.com/XkF2JS5)), meanwhile, this is what it looked like in the program: ([https://cdn.discordapp.com/attachments/ ... nknown.png](https://cdn.discordapp.com/attachments/625655294193827840/687675677809442829/unknown.png)). Could you give me some advice on how to properly port the model and/or its textures to C4D or Blender?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-12T22:28:46+00:00
- Post Title: Need Help Ripping Smash Brawl Mod

> Reply from Mechanist'sVise ↑Fri Mar 13, 2020 3:54 am at Fri Mar 13, 2020 3:54 am
>
> Could you give me some advice on how to properly port the model and/or its textures to C4D or Blender?Don't have much experience with textures but I assume your problem is how to add the ambient occlusion map to the texture (exported "Texture" and "AO" from "Textures" in BRRESviewer):
.



Lucario_tex.png (191.29 KiB) Viewed 30 times


.
blender tutorial how to bake an ambient occlusion map
Look here [https://www.youtube.com/watch?v=UbhiZGCAo0Q](https://www.youtube.com/watch?v=UbhiZGCAo0Q) at 3:30 how to do it (but URtuts uses Photoshop).

(He uses a color map, so I'm not sure if this is exactly what you need.)
