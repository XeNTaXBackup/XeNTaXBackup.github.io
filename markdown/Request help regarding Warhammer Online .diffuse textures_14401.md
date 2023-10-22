## Post #1
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2016-05-27T22:54:21+00:00
- Post Title: Request help regarding Warhammer Online .diffuse textures

Hi,
the game's static meshes and textures were accessible for quite some time thanks to nif tools, now recently Machinima Studio made it possible to convert the .geom character models too.
Now i'm asking, has anyone had any success opening the character textures? They're .diffuse, .specular, .mask and so on, i suppose owing to their use.
I've provided an example if anyone would give it a look.
[WHO diffuse.rar](https://xentaxbackup.github.io/file/10979_WHO diffuse.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-28T01:59:25+00:00
- Post Title: Request help regarding Warhammer Online .diffuse textures

your sample is dxt1 in TextureFinder annd it looks good except for the strange bit shifting near the bottom, i have never seen anything like that.
## Post #3
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2016-05-28T03:17:56+00:00
- Post Title: Request help regarding Warhammer Online .diffuse textures

Indeed you're right, makes me feel ashamed that i didn't even try it myself before asking for help. I just didn't think it could be so easy, when all those years noone ever wrote a converter or something. Well, not exactly easy, texture finder usually requires still some tinkering. Thank you very much for your time.

Edit: Hmm you're right about that strange distortion though. I've tried a few that worked flawlessly, at first i thought it was only those with an alpha channel but now i think there's something else to it. I'm unable to fix it via offset values.
Shouldn't the alpha channel be visible in Texture Finder when i select DXT1+a? I'm sure there has to be one, as i have a ninjaripped version to compare it to.
[diffuse2.rar](https://xentaxbackup.github.io/file/10981_diffuse2.rar)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-28T04:43:48+00:00
- Post Title: Request help regarding Warhammer Online .diffuse textures

transparency isn't shown in TextureFinder, but the alpha is preserved when you save out the image to bmp.

your second .diffuse sample looks worse than the first one   

looks like some research was done already on these textures
[viewtopic.php?p=26825#p26825](http://forum.xentax.com/viewtopic.php?p=26825#p26825)
[viewtopic.php?p=26838#p26838](http://forum.xentax.com/viewtopic.php?p=26838#p26838)

> Reply from Wobble
>
> The mipmap data decodes fine with DXT1, but the image is shifted for me.   I'm guessing you might have to use those mipmap padding amounts to 'unshift' the image correctly?
## Post #5
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2016-05-28T11:14:01+00:00
- Post Title: Request help regarding Warhammer Online .diffuse textures

There goes my optimism i had when the first two files i opened in texture finder were completely restorable. I've had a look the Sundering mod for Medieval2, which uses WAR models, and the way it looks to me they used Ninja-ripped textures too.

I'll try to find a pattern so that some might at least be restored in "post-production".

EDIT:
Strange coincidence. The saved bmp doesn't have an alpha channel or transparency, but the "corruption" starts pretty much where the transparent part of the texture should begin. Here's a comparison, ninja-ripped and edited texture on the right, alpha channel visible in red:



At the beginning, where the alpha channel is still white, everything is fine. Only at the bottom, where the hairs around the hooves should be transparent, does the shifting begin. That would explain why some pictures are more corrupted than others, with transparent parts further at the top. What it doesn't explain is why it affects specular textures as well, as they shouldn't have transparent parts.
[example.rar](https://xentaxbackup.github.io/file/10982_example.rar)
## Post #6
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2016-05-28T22:32:29+00:00
- Post Title: Request help regarding Warhammer Online .diffuse textures

Ok i managed to get Intel GPA running with WAR, so at least i can get those textures of the models i meet in the game. 
Strangely, it sometimes gives me two almost identical textures, one in DXT1 and one in DXT3.
Does that help in any way?
## Post #7
- Username: OllyOrc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 17, 2017 4:12 am
- Post datetime: 2017-06-16T20:20:50+00:00
- Post Title: Request help regarding Warhammer Online .diffuse textures

We found the same issues but only with rectangular diffuse textures. Fortunately square diffuse textures extracted fine, with our diffuse converter tool.

[http://forum.dark-omen.org/3d-scenery-m ... 7#msg13777](http://forum.dark-omen.org/3d-scenery-models/warhammer-age-of-reckoning-modding-t1361.0.html;msg13777#msg13777)

Currently investigating if .mask files can be edited and resaved and also if .obj can be edited and converted back to .geom, if anyone would like to help please. (or we have loads of other  Dark Omen mod stuff to do but thankfully we now have enough tools to create Dark Omen 2 and we are even remaking the game engine in the Unreal Editor - Dark Omen Reborn!)

ps. I've only just discovered the TextureFinder tool due to this thread and it's a very cool tool but sadly also struggles with rectangular diffuse textures.
