## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-05-30T20:48:15+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

Hello, everyone! It's always been a little mystery how Oddworld: Stranger's Wrath's models could possibly be ripped. I have been looking on the internet for a way to extract them for quite a while, ever since the HD version of Stranger first appeared on PC. The only thing I managed to get, were the sounds, which were from the PS3 version.. From what I can see, there are multiple directories and I am not sure in which the models are stored: the two possible folders are "global" and "bundles".

The global folder contains numerous files of different extensions: .sbl, .smh, but mostly .smb. For example: "global_effects.smb", "global_stranger.smb", "global_steefanims.smb" and so on.

The bundles folder is full of subfolders named "region_" where multiple files are located. They are the resources used for each level, the most interesting fact about these is that there are file names such as "npc_0.smb", "npc_1.smb", etc.

I have uploaded .zip containing a couple files from the last level (all the npc_.smb files I could find in that region) and also a couple global files, like "global_stranger.smb" [here](https://www.dropbox.com/s/4ioy5u6ja93o625/Stranger%27s%20Wrath%20assets.zip?dl=0) on Dropbox if anyone wishes to give them a try, I'd really appreciate it.

Thank you and have a nice day!
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-06-01T14:32:03+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

Can someone please help? I've always wanted the models and animations from my favorite game, does anyone have an idea? All I know is that it runs on Granny3D
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-06-01T18:56:07+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

> Reply from Pepsee
>
> All I know is that it runs on Granny3Dthat's not too much -
I found some funny point clouds - maybe it's animation data. But I don't have time to investigate further.



npc_11-smb.jpg (77.85 KiB) Viewed 419 times



If you own the PC version of the game try out some 3D ripper.
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-06-01T19:32:33+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

> Reply from shakotay2
>
> Pepsee wrote:All I know is that it runs on Granny3Dthat's not too much -
I found some funny point clouds - maybe it's animation data. But I don't have time to investigate further.
npc_11-smb.jpg

If you own the PC version of the game try out some 3D ripper.

Well, I do own the game, and I've tried using a 3D ripper before. Sadly, I couldn't get anything.. 
I'd really like to have these models, I'm just not good at ripping models or textures, I only managed to get the sounds.
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-06-04T19:00:06+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

Hi
Here is a blend file to import models and animations from smb files.
How use:
1. install Blender version 249b(32bits) and Python version 26(32bits).
2. unpack 7z archive and doubleclick file "Blender249.blend"
3. in Blender Text Window press alt+p and select:
- smb file - it creates new folder *_files
4. from new folder select file:
- skeleton - we get all textured meshes and bones
- meshinfo - to import geometry if there is any skeleton file
- imageinfo - to convert images
- gr2 - to import animation
5. if you want import only skeleton, without meshes change line 6 from getAll=1 to getAll=0

I tested script on files from this topic.
Not all is fine.
[Blender249[Oddworld Stranger's Wrath][PC][SMD][2016-06-04].7z](https://xentaxbackup.github.io/file/11012_Blender249[Oddworld Stranger's Wrath][PC][SMD][2016-06-04].7z)
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-06-04T20:21:55+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

> Reply from Szkaradek123
>
> Hi
Here is a blend file to import models and animations from smb files.
How use:
1. install Blender version 249b(32bits) and Python version 26(32bits).
2. unpack 7z archive and doubleclick file "Blender249.blend"
3. in Blender Text Window press alt+p and select:
- smb file - it creates new folder *_files
4. from new folder select file:
- skeleton - we get all textured meshes and bones
- meshinfo - to import geometry if there is any skeleton file
- imageinfo - to convert images
- gr2 - to import animation
5. if you want import only skeleton, without meshes change line 6 from getAll=1 to getAll=0

I tested script on files from this topic.
Not all is fine.

Hello! Thank you for your help. I downloaded both Blender and Python with the exact build you mentioned, but I get an error:
[error.png](https://xentaxbackup.github.io/file/11013_error.png)
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-06-04T20:47:28+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

Your blend files are open with Blender 272.
Please change to Blender 249 , use right click on blend file .
## Post #8
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-06-04T21:26:57+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

> Reply from Szkaradek123
>
> Your blend files are open with Blender 272.
Please change to Blender 249 , use right click on blend file .

But I downloaded v249b from here: [https://download.blender.org/release/Blender2.49b/](https://download.blender.org/release/Blender2.49b/) and Python v26 from here [https://www.python.org/download/releases/2.6.2/](https://www.python.org/download/releases/2.6.2/)
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-06-05T05:34:05+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

Uninstall all  blenders , clear system registry with program like ccleaner , one more time install Blender 249b
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-06-05T10:29:08+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

> Reply from Szkaradek123
>
> Uninstall all  blenders , clear system registry with program like ccleaner , one more time install Blender 249b

Thank you very much! Everything is working perfectly now!
## Post #11
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-06-06T08:35:27+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

Sorry for the double post, but is there a way to rip the animations as well? And also, how do I export a model with it's skeleton? What format should I use?
## Post #12
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-06-16T18:29:16+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

I feel horrible for bumping this once more, but I really want those animations and a way to export the skeletons as well, can anyone help, please?..
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-06-16T19:05:00+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

Did you get a skeleton/animation loaded?
If 'no', read what Mariusz wrote:  

Load a skeleton file then a gr2 file - as simple as that.



npc_11_11-skeleton.jpg (20.7 KiB) Viewed 314 times


export as fbx or dae
## Post #14
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-07-15T21:17:28+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

Sorry to be bothering once more, but I have tried to import certain models such as props and they just do not get fully imported, I don't know what to do. I get a python error, I will upload a few samples [here](https://www.dropbox.com/s/qm5ugzinuzzjdzx/Help.zip?dl=0). There aren't only certain .meshinfo's, but also entire .smd's that just give me an error halfway after being imported in Blender.
[errors.png](https://xentaxbackup.github.io/file/11290_errors.png)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-17T18:51:50+00:00
- Post Title: Oddworld Stranger's Wrath: looking for a way to rip models

> Reply from Pepsee
>
> I don't know what to do. I get a python errorsurprise  

Comment out the following like shown and you're done (for now):

```
			dataPath=dirPath+os.sep+os.path.basename(node[1])
			new=open(dataPath,'wb')
			g.seek(A[0]+A[2]+node[0][4])
			if i<len(nodeList)-1:
				new.write(g.read(nodeList[i+1][0][4]-nodeList[i][0][4]))
			new.close()"""
```
results in 403 files to be extracted from lm_level_05_tgl.smb
## Post #16
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-07-17T22:55:06+00:00
- Post Title: Re: Oddworld Stranger's Wrath: looking for a way to rip mode

> Reply from shakotay2
>
> Pepsee wrote:I don't know what to do. I get a python errorsurprise  

Comment out the following like shown and you're done (for now):
Code: Select all		"""if node[0][1] in [6]:
			dataPath=dirPath+os.sep+os.path.basename(node[1])
			new=open(dataPath,'wb')
			g.seek(A[0]+A[2]+node[0][4])
			if i<len(nodeList)-1:
				new.write(g.read(nodeList[i+1][0][4]-nodeList[i][0][4]))
			new.close()"""results in 403 files to be extracted from lm_level_05_tgl.smb

Thank you!! I managed to finally load all the files, even though some models from other packs give errors.



erross.png (42.56 KiB) Viewed 108 times


 I have really wanted to get the Dropship models. It seems all props give the same error (at least in region_05). I've added a [dropbox link](https://www.dropbox.com/s/xrcvfyqsji39y34/Dropship%20files.zip?dl=0) for the dropships if you can help.
## Post #17
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2016-08-01T14:22:02+00:00
- Post Title: Re: Oddworld Stranger's Wrath: looking for a way to rip mode

Any ideas?
## Post #18
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2019-01-28T04:40:50+00:00
- Post Title: Re: Oddworld Stranger's Wrath: looking for a way to rip mode

BUMP!   - Any idea if this will work on 'New & Tasty' ?.. If not is there a blender script for this other great Oddworld Inhabitants release??...
## Post #19
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-02-03T00:07:58+00:00
- Post Title: Re: Oddworld Stranger's Wrath: looking for a way to rip mode

> Reply from wubbaworwee
>
> BUMP!   - Any idea if this will work on 'New & Tasty' ?.. If not is there a blender script for this other great Oddworld Inhabitants release??...

For New & Tasty use Unity Studio [https://www.unity-studios.com/](https://www.unity-studios.com/)

It allows you to export meshes and textures but animations are in an intricate format I can't quite remember...
