## Post #1
- Username: udkultimate
- Rank: beginner
- Number of posts: 29
- Joined date: Thu May 25, 2017 6:11 am
- Post datetime: 2019-09-21T22:56:22+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

Hello guys!!!

I am porting Fortnite to PS3 and Xbox360, I am using my modified version of UDK Engine ([viewtopic.php?f=33&t=21071](https://forum.xentax.com/viewtopic.php?f=33&t=21071)) for this project.

I know UE Viewer ([https://www.gildor.org/projects/umodel/compat](https://www.gildor.org/projects/umodel/compat)) can extract models and animations from Fortnite game, as I already extracted man of them.

However I would like to know if there is a tool, or some method to extract the entire map (level) from the game fortnite to a readable 3d format like OBJ, or import direct into 3dsmax.

I know I could use NinjaRipper to rip the map, however whenever there is a specific tool, is better.

For example, for Source Engine games (Half Life 2, Counter Strike Source, Let for Dead, Team Fortress), there is a tool called Crafty Object Viewer ([http://nemesis.thewavelength.net/index.php?p=45](http://nemesis.thewavelength.net/index.php?p=45)) which exports the maps entirely as an OBJ file with textures and UVW coordinates, which I can import flawlessly into 3dsmax.

Is there a way to do this for Unreal Engine 4 games?

Thanks!!!
## Post #2
- Username: udkultimate
- Rank: beginner
- Number of posts: 29
- Joined date: Thu May 25, 2017 6:11 am
- Post datetime: 2019-09-21T23:04:58+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

I just found this tool for kingdom hearts 3: [viewtopic.php?f=16&t=21066&start=45](https://forum.xentax.com/viewtopic.php?f=16&t=21066&start=45)

Will this extract the map for any Unreal Engine 4 Game? Does the map meshes come textured and UVW mapped?

Thanks!
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-09-22T04:25:57+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

> Reply from udkultimate ↑Sun Sep 22, 2019 7:04 am at Sun Sep 22, 2019 7:04 am
>
> 
I just found this tool for kingdom hearts 3: viewtopic.php?f=16&t=21066&start=45

Will this extract the map for any Unreal Engine 4 Game? Does the map meshes come textured and UVW mapped?

Thanks!

No, its a tool for KHIII, it will only work on KHIII. Each unreal game has slightly different data, and each unreal version has very different data, a tool for one will almost never work on another, unless both are using default UE4 vanilla files and formats with no customization.

Also even for KH, it doesn't come with textures, but things do come UVmapped, you'll have to extract textures and apply them seperatly.
## Post #4
- Username: udkultimate
- Rank: beginner
- Number of posts: 29
- Joined date: Thu May 25, 2017 6:11 am
- Post datetime: 2019-09-22T12:35:05+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

Thanks for the answer my friend!!!

So Ninja Ripper is still the best option for this, right?
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-09-22T12:41:28+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

> Reply from udkultimate ↑Sun Sep 22, 2019 8:35 pm at Sun Sep 22, 2019 8:35 pm
>
> 
Thanks for the answer my friend!!!

So Ninja Ripper is still the best option for this, right?

Ninja Ripper might be abe to dump the game yes, I haven't tried sorry.
But Ninja Ripper won't rip everything in its position, it will move all objects to the 0,0,0 axis.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-09-22T12:59:36+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

> Reply from udkultimate ↑Sun Sep 22, 2019 6:56 am at Sun Sep 22, 2019 6:56 am
>
> 
I know I could use NinjaRipper to rip the map
you really think so?
i'd be very surprised if its even remotely possible
## Post #7
- Username: udkultimate
- Rank: beginner
- Number of posts: 29
- Joined date: Thu May 25, 2017 6:11 am
- Post datetime: 2019-09-22T15:24:42+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

Hello friends. Thanks for the answers. In resume, there is no way to get an Unreal Engine 4 Game Map flawlessly like for Source Engine Maps? Anyone can recommend another method? 

And the old 3D Ripper DX from Deep Shadows, would work?

Thanks.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-09-22T16:19:39+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

> Reply from udkultimate ↑Sun Sep 22, 2019 11:24 pm at Sun Sep 22, 2019 11:24 pm
>
> 
Hello friends. Thanks for the answers. In resume, there is no way to get an Unreal Engine 4 Game Map flawlessly like for Source Engine Maps?
i can only mention that comparing engines made in 2005 with modern age is not good idea
i may be wrong, but in my opinion, words "flawlessly get" and "UE4 Game Map" are from different galaxies
## Post #9
- Username: udkultimate
- Rank: beginner
- Number of posts: 29
- Joined date: Thu May 25, 2017 6:11 am
- Post datetime: 2019-09-22T22:28:52+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

Ok my friends, thanks for the replies. I will try to see what I can do with ninja ripper, and if I found something interesting, I will for sure share with people here.
## Post #10
- Username: cobaltbluebengal
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 04, 2016 12:15 am
- Post datetime: 2021-07-23T21:37:32+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

Were you able to rip the landscape? I can use Umodel for the characters, but it always crashes with any static meshes. I don't know if it is cause the latest updates or not? Does Ninjaripper work? Whenever I used it in the past the game crashes to desktop (tried it on Sunset Overdrive, Anthem and Mirror's Edge)

Wanted to do some renders with authentic sceneries like the load screens but alas, I cant seem to get it to work
## Post #11
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2021-09-13T07:41:33+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

May not be directly useful, but I added some features to Gildor's UEViewer maps and landscape related
Here is my fork: [https://github.com/dhk-room101/UEViewer](https://github.com/dhk-room101/UEViewer)

Landscape related:
if a cooked map in UEViewer has textures it means it has a landscape, so I added a simple stitching method and exporting the landscape textures to TGA. Simply select the map in UEViewer, right-click on it, and choose export landscape textures. It exports heightmap/s and weightmap/s if found.
It doesn't work with all UE4 projects, so trial and error  May also not be 100% accurate, depending if my stitching method was scientifically correct   

Maps related:
it parses the cooked map/s, and checks for transforms for static/skeletal meshes, lights, and some other minor stuff (no postprocessing or proper materials, the end result will not be identical visually/aesthetically). It exports the results in plain text, which can be parsed and reimported in Unreal Engine 4/5 (the reimport parser is not included in the above repository, but it's all plain text, should be easy to write one). It assumes that the static/skeletal meshes assets are already in the correct Content folder location, meaning the original UEViewer was used to export the meshes to psk/x, 3DS Max was used to convert them to fbx, and fbx meshes where already imported in the unreal engine 4/5 version of your choice

Here is an example result (comparison between original UE4 cooked map and automatically reconstructed one in UE5)
[https://www.youtube.com/watch?v=qa-lkNyiBjo](https://www.youtube.com/watch?v=qa-lkNyiBjo)

PS: I don't remember if I mentioned the above already on this forum, if I'm tooting my own horn again, my apologies...

========================
Credits:
Thanks to gildor and daemon1 for inspiration and smarts
## Post #12
- Username: xaiin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 10, 2020 6:47 am
- Post datetime: 2022-02-05T22:13:47+00:00
- Post Title: Extracting Unreal Engine 4 Game Maps

Did you remove your repo buddy, this sounded interesting.
