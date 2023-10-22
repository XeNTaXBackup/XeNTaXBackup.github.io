## Post #1
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-04-11T12:11:27+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

hello all does anyone know of a plugin or script or software that can convert swg msh files with the correct uvmaps so the textures show up correctly? i have tried 3d object converter but it does not work, and unwrap 3d works but have to pay 59.99 us dollars to save any advice would be great!
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-04-11T14:05:36+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

Someone started on a python plugin for Blender but it doesn't support UVs
[https://github.com/apathyboy/SWGANHBlenderAddons](https://github.com/apathyboy/SWGANHBlenderAddons)

I found another import plugin for Blender that looks like it might have support for UVs
[http://home.earthlink.net/~xunil/swg_msh_import.py](http://home.earthlink.net/~xunil/swg_msh_import.py)
[http://home.earthlink.net/~xunil/](http://home.earthlink.net/~xunil/)

Theres also an import plugin for 3ds Max
[viewtopic.php?p=20914#p20914](http://forum.xentax.com/viewtopic.php?p=20914#p20914)

A Noesis plugin would be nice to have though.
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-04-11T16:13:08+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

> Reply from luke9511
>
> i have tried 3d object converter but it does not work

Can you tell me what is your problem with my program?

It converts the geometry, UV datas and the materials automatically, if the .sht/msh files are in the same folder, so it works fine.

[http://3dconverter.clanteam.com/convert ... to_obj.zip](http://3dconverter.clanteam.com/converted/SWG_msh_to_obj.zip)
## Post #4
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-04-11T16:37:28+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

> Reply from Karpati
>
> luke9511 wrote:i have tried 3d object converter but it does not work

Can you tell me what is your problem with my program?

It converts the geometry, UV datas and the materials automatically, if the .sht/msh files are in the same folder, so it works fine.

http://3dconverter.clanteam.com/convert ... to_obj.zip
a few of the models the uv's were messed up where the textures were not showing up correctly, i did try the 3ds max plugin and that works but i love 3d object converter and would love to use that as my main go to program
## Post #5
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-04-12T01:18:38+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

> Reply from Karpati
>
> luke9511 wrote:i have tried 3d object converter but it does not work

Can you tell me what is your problem with my program?

It converts the geometry, UV datas and the materials automatically, if the .sht/msh files are in the same folder, so it works fine.

http://3dconverter.clanteam.com/convert ... to_obj.zip
here is a screenshot of the issue i am having with everything in the same folder
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-04-12T06:56:58+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

Can you send me this .msh file with its texture files to [3dconverter@gmail.com](mailto:3dconverter@gmail.com) ?
## Post #7
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-04-12T14:52:23+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

> Reply from Karpati
>
> Can you send me this .msh file with its texture files to 3dconverter@gmail.com ?
sent!
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-04-12T16:40:19+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

Thank you for your sample file and bug report.

I tracked down what was the problem and I rewrote the vertex loader module to handle the 11 (!) different vertex sizes.

I uploaded the latest version of my program (unpublished yet officially) to my web page:
[http://3dconverter.clanteam.com/develop ... 130412.zip](http://3dconverter.clanteam.com/develop_x86/3doc_5002_20130412.zip)
## Post #9
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-04-12T17:53:31+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

Works perfectly Thank you!
## Post #10
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-05-09T02:03:14+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

im using 3d object converter to see where the textures go and then applying them in 3ds max, but would rather be able to import into 3ds max with the textures, is there anyone who is able to update the 3ds max plugin to work?
## Post #11
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-05-09T18:07:10+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

As I wrote to you, if you use the correct .sht file (see the Tools/Quick Material information/Material name) in the folder where is the .msh file you will get the texture file names automatically.
## Post #12
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-05-19T18:57:51+00:00
- Post Title: [Request] Star Wars Galaxies .msh converter

> Reply from Karpati
>
> As I wrote to you, if you use the correct .sht file (see the Tools/Quick Material information/Material name) in the folder where is the .msh file you will get the texture file names automatically.
thank you very much for your help! thought i would also update and say there is a new version of the 3ds max scripts for these models which can be downloaded here [http://www.rosuto.com/swg/SWG_3ds_tools.zip](http://www.rosuto.com/swg/SWG_3ds_tools.zip) or search on the mode the galaxy forums, the scripts do not import textures but each part of the model is named after the texture it needs so you can just apply it that way!
