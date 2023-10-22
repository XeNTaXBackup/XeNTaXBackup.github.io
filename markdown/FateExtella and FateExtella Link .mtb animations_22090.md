## Post #1
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2020-04-30T21:47:24+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

I figured out a way to extract Fate/Extella and Fate/Extella Link animations from .mtb files. The process is a bit complicated but basically it uses the game itself to decode frames. This was simpler to do than figuring out the format details.

Requirements:
- PC version of Fate/Extella or Fate/Extella Link
- Steamless: [https://github.com/atom0s/Steamless](https://github.com/atom0s/Steamless)
- Latest fate-tools: [https://github.com/kotcrab/fate-tools/releases](https://github.com/kotcrab/fate-tools/releases)

Setup:
- Start Steamless and select game exe (either game.exe or fateextellalink.exe) then press Unpack
- This will create ...exe.unpacked.exe file
- Rename it to fate.exe
- From fate-tools copy animserv.exe and animserv.dll next to the fate.exe
- Run animserv.exe, if you see "server started" you're good to go

Note: this starts fate.exe and injects animserv.dll into it, you probably don't want to have Steam running during this

Using the Blender script:
- Export the model from Noesis and import it into Blender
- Save the Blender file somewhere
- Copy source model .mdl file next to the Blender file
- Copy .mtb files for the model next to the Blender file
- Open the import_mtb.py script in Blender and edit the config at the top
- You should change at least mdlPath and mtbPath
- Run the script

[https://imgur.com/a/0UdgSOC](https://imgur.com/a/0UdgSOC)

I'm sure this animation format is used in other games (header 80AE), animserv should be universal but the Blender script will need adjustments for different model types.
## Post #2
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-09-22T15:59:02+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

could you make a easier way to import mtb like other blender script? im retarded to use this
## Post #3
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-10-09T04:49:49+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

I'm with wansf, I've followed the steps properly, but I'm having no luck with it in Blender 2.81
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-10-09T11:38:42+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

> Reply from Kotcrab ↑Fri May 01, 2020 5:47 am at Fri May 01, 2020 5:47 am
>
> 
I figured out a way to extract Fate/Extella and Fate/Extella Link animations from .mtb files. The process is a bit complicated but basically it uses the game itself to decode frames. This was simpler to do than figuring out the format details.Very cool idea!
## Post #5
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2020-10-09T14:40:38+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

> Reply from demonslayerx8 ↑Fri Oct 09, 2020 12:49 pm at Fri Oct 09, 2020 12:49 pm
>
> 
I'm with wansf, I've followed the steps properly, but I'm having no luck with it in Blender 2.81

This is as simple as its gets. Feel free to post more details if you have a specific problem.

> Reply from shakotay2 ↑Fri Oct 09, 2020 7:38 pm at Fri Oct 09, 2020 7:38 pm
>
> 
Very cool idea!

Thanks!
## Post #6
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2020-10-12T00:54:49+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

I failed thousand time trying to run script
i already open animserv as background here the command inside
animserv starting 
found animation decoder at 0xc626c0
server started using port 54217
when i run the script and this come out 
*accepted connection
i changed the script path and run , and it gimme this
Python script failed, check the message in the system console
Traceback (most recent call last):
  File "C:\Users\Flyers\Desktop\source model\untitled.blend\import_mtb.py", line 212, in <module>
    importMtb()
  File "C:\Users\Flyers\Desktop\source model\untitled.blend\import_mtb.py", line 48, in importMtb
    bpy.data.objects[blenderSkeletonTarget].animation_data_clear()
KeyError: 'bpy_prop_collection[key]: key "Armature" not found'
And another one
 File "C:\Users\Flyers\Desktop\source model\untitled.blend\import_mtb.py", line 212, in <module>
    importMtb()
  File "C:\Users\Flyers\Desktop\source model\untitled.blend\import_mtb.py", line 48, in importMtb
and yes i create a folder called motion and put mtb in
## Post #7
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2020-10-12T17:03:26+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

Here is the problem: 
```
key "Armature" not found'
```

Your Blender scene doesn't have "Armature" object so either edit script config to use correct object or rename it in Blender to be "Armature". Maybe your exported model is missing skeleton, in that case re-export it from Noesis. I recommend using .dae format for export.
## Post #8
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2020-10-12T20:27:34+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

> Reply from Kotcrab ↑Tue Oct 13, 2020 1:03 am at Tue Oct 13, 2020 1:03 am
>
> 
Here is the problem: Code: Select allkey "Armature" not found'
Your Blender scene doesn't have "Armature" object so either edit script config to use correct object or rename it in Blender to be "Armature". Maybe your exported model is missing skeleton, in that case re-export it from Noesis. I recommend using .dae format for export.
Thank you i export as fbx i didnt realise the armature name has changed to N_ALL
and it's work now
## Post #9
- Username: yourreason
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 16, 2020 4:15 pm
- Post datetime: 2021-11-12T12:08:32+00:00
- Post Title: Fate/Extella and Fate/Extella Link .mtb animations

Good work, but there one problem (may be only mine).
Isn't it supposed to be that the model is fixed in the Z axis and moves only along Y, X
Here an example: [https://imgur.com/a/bPLqU9V](https://imgur.com/a/bPLqU9V)
Is there any way to fix this? Or is it the way it should be?
