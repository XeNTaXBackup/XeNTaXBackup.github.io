## Post #1
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-03-27T13:18:57+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

Hello everyone...
Half-Life: Alyx recently released.  I want to be able to export the models of the game.  But I could not find much information and resources on this subject. Models with bones would actually be beautiful.

[viewtopic.php?f=16&t=15400&p#p123736](https://forum.xentax.com/viewtopic.php?f=16&t=15400&p#p123736)
[https://github.com/Penguinwizzard/Sourc ... Decompiler](https://github.com/Penguinwizzard/Source2ResourceDecompiler)
[https://github.com/SteamDatabase/ValveResourceFormat](https://github.com/SteamDatabase/ValveResourceFormat)

VRF / Source 2 Resource Viewer
[https://opensource.steamdb.info/ValveResourceFormat/](https://opensource.steamdb.info/ValveResourceFormat/)
At least he can open the archive perfectly. (Opening in previous apps.) But there are still problems in exporting textures.

But it cannot export models. Does anyone have any ideas or help on this matter?

I will share 3 different character files.
--> Alyx, G-man, Gordon

File types...
gman.vmdl_c
gman_vmorf.vtex_c
gman_attache.vmat_c
gman_attache_ao_tga_3c7cd30a.vtex_c

All the files of the characters -->  [http://www.mediafire.com/file/2r2s4j4p1 ... yx.7z/file](http://www.mediafire.com/file/2r2s4j4p1yhrz22/HF_Alyx.7z/file)
Less data (little) --> [http://www.mediafire.com/file/92642nrji ... le.7z/file](http://www.mediafire.com/file/92642nrjiwqr3ee/HF_Alyx_little.7z/file)
## Post #2
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-01T12:30:45+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

I did use Model Researcher Pro to find the mesh, It seems uv are inside compressed 3VK blocks
## Post #3
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-04-01T20:45:01+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

> Reply from EPYCSPYDER ↑Wed Apr 01, 2020 8:30 pm at Wed Apr 01, 2020 8:30 pm
>
> 
 It seems uv are inside compressed 3VK blocks

It looks really good.
The export of textures is easy. I have no idea about UV map. 
SteamVR doesn't work on me.
  damn it
## Post #4
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-01T22:26:41+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

I found this online to run without a headset, It's not worth it though.
[https://www.youtube.com/watch?v=5HUGaJj ... e=youtu.be](https://www.youtube.com/watch?v=5HUGaJjP9AI&feature=youtu.be)

[http://www.mediafire.com/file/mc8x5scqo ... n.rar/file](http://www.mediafire.com/file/mc8x5scqora8uvk/hlvr-fakevr-bin.rar/file)
add -novr -console to the end of hlvr.exe desktop shortcut

NinjaRipper worked okay I ripped gman, these scripts are useful if anybody uses 3ds max and NinjaRipper

Duplicate Geometry Select
[http://www.scriptspot.com/3ds-max/scrip ... try-select](http://www.scriptspot.com/3ds-max/scripts/duplicate-geometry-select)

Select by Bitmap

```
theObjs = #()
for i in (getclassinstances bitmaptexture) where (filenamefrompath i.filename) == theMap do (join theObjs (refs.dependentNodes i))
select theObjs
```
## Post #5
- Username: cuone
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 04, 2020 3:53 am
- Post datetime: 2020-04-03T20:00:15+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

when you export the models the uv is broken, TSelman61X you miss a lot of alyx materials in your link can you reupload those materials?
## Post #6
- Username: cuone
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 04, 2020 3:53 am
- Post datetime: 2020-04-03T20:25:09+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]


## Post #7
- Username: exhaleme
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 10, 2017 10:59 am
- Post datetime: 2020-04-04T02:55:07+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

You can actually already use Pragma Engine to fully export Source 2 assets: [https://knockout.chat/thread/11218/1](https://knockout.chat/thread/11218/1).
It's basically a better source engine anyways.
## Post #8
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-04-04T22:06:26+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

> Reply from EPYCSPYDER ↑Thu Apr 02, 2020 6:26 am at Thu Apr 02, 2020 6:26 am
>
> 
I found this online to run without a headset, It's not worth it though.
https://www.youtube.com/watch?v=5HUGaJj ... e=youtu.be

Playing  without a headset  is really interesting.   

I tried a ninja ripper but I can't say it was very successful. I do not know why the problem occurred. It does not create any files.
## Post #9
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-04-04T22:33:58+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

> Reply from cuone ↑Sat Apr 04, 2020 4:00 am at Sat Apr 04, 2020 4:00 am
>
> 
when you export the models the uv is broken, TSelman61X you miss a lot of alyx materials in your link can you reupload those materials?

Maybe you are right. I will export again with GUI v0.1.3.1140 version.
I send it again for guarantee.
[http://www.mediafire.com/file/tx7hl4bbb ... an.7z/file](http://www.mediafire.com/file/tx7hl4bbb09s0et/gman.7z/file)
## Post #10
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2020-04-04T23:52:31+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

> Reply from exhaleme ↑Sat Apr 04, 2020 10:55 am at Sat Apr 04, 2020 10:55 am
>
> 
You can actually already use Pragma Engine to fully export Source 2 assets: https://knockout.chat/thread/11218/1.
It's basically a better source engine anyways.

I still don't know how it works. But it works. I guess.
There is no material. All in one material. 
may be due to my stupidity.
## Post #11
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-05T00:57:40+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

I used this on alyx it took ages to build the ao

util_export_model -model "characters/alyx/alyx" -export_animations 1 -export_skinned_mesh_data 1 -export_morph_targets 1 -export_images 1 -image_format dds -enable_extended_dds 1 -generate_ao 1 -ao_samples 512 -ao_resolution 4096

Here is the textures tga

[http://www.mediafire.com/file/8hfakd38a ... x.rar/file](http://www.mediafire.com/file/8hfakd38a6wjk5f/alyx.rar/file)

Has anybody been able to load a map with pragma?
## Post #12
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2020-04-06T13:06:28+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

pragma isnt working for me. can somebody help ? i dont know how to use it properly.
## Post #13
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-06T16:50:30+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

Try this blender importer, It can open .vmdl_c
[https://github.com/REDxEYE/SourceIO](https://github.com/REDxEYE/SourceIO)
## Post #14
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2020-04-07T04:03:18+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

> Reply from EPYCSPYDER ↑Tue Apr 07, 2020 12:50 am at Tue Apr 07, 2020 12:50 am
>
> 
Try this blender importer, It can open .vmdl_c
https://github.com/REDxEYE/SourceIO

not working either (on blender v2.79 and v2.82). is this for blender v2.8 or problem is something else?
[234.png](https://xentaxbackup.github.io/file/17896_234.png)
## Post #15
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-04-07T04:20:56+00:00
- Post Title: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

It works okay in 2.82 I'm using blender zip instead of the installer. try rename the folder to just SourceIO, that should be the root for the plugin files/folders. C:\Users\EPYCSPYDER\Documents\blender-2.82a-windows64\2.82\scripts\addons\SourceIO\
## Post #16
- Username: RedMiller
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 10, 2017 12:19 am
- Post datetime: 2020-04-07T05:52:11+00:00
- Post Title: Re: Half-Life: Alyx [*.vtex_c and *.vmdl_c]

You can use this for static models:
[viewtopic.php?f=33&t=21379](https://forum.xentax.com/viewtopic.php?f=33&t=21379)
