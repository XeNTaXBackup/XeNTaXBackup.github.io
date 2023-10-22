## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-08-07T10:30:32+00:00
- Post Title: Far Cry 6 model tool

Far Cry 6 model tool will be posted here after some testing

Currently supports all skeletal & static models.






[FC6Model.7z](https://xentaxbackup.github.io/file/22625_FC6Model.7z)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-08-11T17:27:50+00:00
- Post Title: Far Cry 6 model tool

Tool posted.

Usage: drop .XBG file onto the tool, use command line, or create batch.

Special option for universal heads which need facial bones applied from separate files:

First, XBG file as usual. It will have positions/rotations for all bones of a mesh.
Then .item.Bwsk files. You can convert them to readable format as usual FCB file. They have a full description of model parts (.XBG meshes), all skeletons combined, all their bones, materials override, etc, and also in the end there will be a link to .dpdx (facial pose definition). These .dpdx files have final facial bones positions/rotations.

To convert such universal head, provide 2 or more parameters: XBG, and then all BWSK & DPDX files you want to apply.
This will create a "face-fixing" .SMD file with data from all files, in the order you place them in command line.
Bone pos/rot from each next file will OVERWRITE previous values.

Usually, faces need 3 files: XBG, BWSK, DPDX.
For example for Vaas:

```
FC6Model.exe fct_hed_shr_average_01_m.xbg dlc_char501_01_m.item.bwsk fct_fac_dlc_char501_01_m.dpdx 
```
## Post #3
- Username: Banner2020
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 23, 2020 6:54 pm
- Post datetime: 2022-08-12T05:23:26+00:00
- Post Title: Far Cry 6 model tool

Excellent as usual~
## Post #4
- Username: CQuence
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 13, 2017 12:20 am
- Post datetime: 2022-08-13T07:52:20+00:00
- Post Title: Far Cry 6 model tool

Hello.
In the PC version of the game there is only .dat and .fat files. 
How do I unpack them? How to get to .XBG files? 
Thanks.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-08-13T08:15:43+00:00
- Post Title: Far Cry 6 model tool

> Reply from CQuence ↑Sat Aug 13, 2022 3:52 pm at Sat Aug 13, 2022 3:52 pm
>
> 
Hello.
In the PC version of the game there is only .dat and .fat files. 
How do I unpack them? How to get to .XBG files? 
Thanks.
you can use FCBConverter
## Post #6
- Username: Alexxxxxxx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 02, 2017 6:44 am
- Post datetime: 2022-08-22T13:59:15+00:00
- Post Title: Far Cry 6 model tool

Hey! Please tell me how to import .xbg into blender?
## Post #7
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2022-12-27T05:55:07+00:00
- Post Title: Far Cry 6 model tool

> Reply from daemon1 ↑Sun Aug 07, 2022 6:30 pm at Sun Aug 07, 2022 6:30 pm
>
> 
Far Cry 6 model tool will be posted here after some testing

Currently supports all skeletal & static models.

It's cool that at least some tool has appeared to convert the xbg ​​format to another more understandable 3D editor, but unfortunately there are no vertex groups for transport, this could divide the parts of the model into even parts. 
By the way, air transport has no problems with the presence of group vertices, except for the cars themselves.
P.S. How to specify a parameter?
## Post #8
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2022-12-27T05:59:43+00:00
- Post Title: Far Cry 6 model tool

> Reply from Alexxxxxxx ↑Mon Aug 22, 2022 9:59 pm at Mon Aug 22, 2022 9:59 pm
>
> 
Hey! Please tell me how to import .xbg into blender?

ascii can be exported via Noesis, for example, to fbx.
## Post #9
- Username: Bebranuh2004
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 26, 2023 8:09 pm
- Post datetime: 2023-01-26T12:14:01+00:00
- Post Title: Far Cry 6 model tool

> Reply from daemon1 ↑Sun Aug 07, 2022 6:30 pm at Sun Aug 07, 2022 6:30 pm
>
> 
Far Cry 6 model tool will be posted here after some testing

Currently supports all skeletal & static models.

This tool convert .xbg to .ascii format. How i can open .ascii? Noesis support only doesnt support this format, or i just dont have plugin for this
## Post #10
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-26T20:35:19+00:00
- Post Title: Far Cry 6 model tool

> Reply from Bebranuh2004 ↑Thu Jan 26, 2023 8:14 pm at Thu Jan 26, 2023 8:14 pm
>
> This tool convert .xbg to .ascii format. How i can open .ascii? Noesis support only doesnt support this format, or i just dont have plugin for this
[viewtopic.php?p=187182#p187182](https://forum.xentax.com/viewtopic.php?p=187182#p187182)

Also, edit the post, you quoted the whole thing, very messy.
