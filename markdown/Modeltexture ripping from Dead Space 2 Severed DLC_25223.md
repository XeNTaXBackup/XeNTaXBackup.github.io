## Post #1
- Username: Kilroy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 04, 2022 12:10 am
- Post datetime: 2022-04-06T13:07:58+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

So I've been trying to get my hand on Gabe Weller's Patrol suit from the Severed DLC for Dead Space 2 for quite some time now and I have been struggling quite a lot and am very close to giving up.

Where my progress stops is at the .str files from the severed dlc which for some reason the str unpacker that comes with Visceral Viewer wont unpack properly, basically I get nothing from a 8,62 MB file... 

All of this works perfectly fine for the ds2 base game and all the dlc suits for that because they're already in the files before you buy those dlc unlike severed.

I am getting desperate.
Any help would be appriciated.
## Post #2
- Username: Kilroy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 04, 2022 12:10 am
- Post datetime: 2022-04-15T09:24:09+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

Ok so update on this
I managed to unpack the proper .str file and I've got the textures extraced
the only issue now is that the script that is supposed to import the .geo files into 3dsmax just isn't working at all for me.

If anyone who has extracted ds2 files before could convert the files to fbx or obj for me it would mean the world to me.
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-21T22:26:25+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

need samples. otherwise no one will help you.  
i saw your theme on [zenhax](https://zenhax.com/viewtopic.php?f=5&t=16801&hilit=.geo+ds2#p71216) and downloaded the models there.
ps3 and xbox models use bigendian.
in this [topic](https://forum.xentax.com/viewtopic.php?p=123701#p123701) is a plugin for noesis. by modifying it a bit you can add support for your models...
here is the helmet in hex2obj
[helmet.png](https://xentaxbackup.github.io/file/22108_helmet.png)
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-22T00:02:47+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

> Reply from Durik256 ↑Fri Apr 22, 2022 6:26 am at Fri Apr 22, 2022 6:26 am
>
> 
by modifying it a bit you can add support for your models...
ok i did it. only "0271_face_puked.geo" does not open. 
because it has 2 submesh. the plugin only supports 1. 
(it's easy to edit)


[fmt_DS2_PS3_geo.zip](https://xentaxbackup.github.io/file/22113_fmt_DS2_PS3_geo.zip)
## Post #5
- Username: Kilroy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 04, 2022 12:10 am
- Post datetime: 2022-04-22T17:18:23+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

> Reply from Durik256 ↑Fri Apr 22, 2022 8:02 am at Fri Apr 22, 2022 8:02 am
>
> 
Durik256 wrote: ↑Fri Apr 22, 2022 6:26 am
by modifying it a bit you can add support for your models...

ok i did it. only "0271_face_puked.geo" does not open. 
because it has 2 submesh. the plugin only supports 1. 
(it's easy to edit)

thank you so incredibly much I managed to get the model into blender now, but there is just one issue, the model has no UVs did I do something wrong? or could you not get any UVs?
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-22T17:55:07+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

> Reply from Kilroy ↑Sat Apr 23, 2022 1:18 am at Sat Apr 23, 2022 1:18 am
>
> 
any UVs?
offset uvs points to the end of the file. Therefore, I ignore them in the plugin.
as they wrote here, uv in a separate file.:

> Reply from Acewell ↑Sat Oct 22, 2016 8:38 am at Sat Oct 22, 2016 8:38 am
>
> 
looks like the difference between DS1 and DS2/3 models is DS1 stores the UV data 
with the model where DS2/3 store it in a separate file in the "MeshVolatile" folder.
(don't quote the whole post)
## Post #7
- Username: Kilroy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 04, 2022 12:10 am
- Post datetime: 2022-04-22T18:06:28+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

> Reply from Durik256 ↑Sat Apr 23, 2022 1:55 am at Sat Apr 23, 2022 1:55 am
>
> 
Kilroy wrote: ↑Sat Apr 23, 2022 1:18 am
any UVs?

offset uvs points to the end of the file. Therefore, I ignore them in the plugin.
as they wrote here, uv in a separate file.:
Acewell wrote: ↑Sat Oct 22, 2016 8:38 am
looks like the difference between DS1 and DS2/3 models is DS1 stores the UV data 
with the model where DS2/3 store it in a separate file in the "MeshVolatile" folder.

(don't quote the whole post)

do you know how to fix it with thos files included?
[MeshVolatile.rar](https://xentaxbackup.github.io/file/22122_MeshVolatile.rar)
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-22T18:42:22+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

> Reply from Kilroy ↑Sat Apr 23, 2022 2:06 am at Sat Apr 23, 2022 2:06 am
>
> 
do you know how to fix it with thos files included?
I don't know the folder structure of the game to find the UVs file. so I added a file select dialog.

(don't quote the whole post, edit previous posts)  
[fmt_DS2_PS3_geo.zip](https://xentaxbackup.github.io/file/22124_fmt_DS2_PS3_geo.zip)
## Post #9
- Username: Kilroy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 04, 2022 12:10 am
- Post datetime: 2022-04-22T18:59:23+00:00
- Post Title: Model/texture ripping from Dead Space 2 Severed DLC

> Reply from Durik256 ↑Sat Apr 23, 2022 2:42 am at Sat Apr 23, 2022 2:42 am
>
> 
I don't know the folder structure of the game to find the UVs file. so I added a file select dialog.

I love you,
thank you so incredibly much you have no idea how incredibly happy I am to have finally gotten my hands on this.

also sorry about the whole quote thing, I'm very new to posting on forums and that
