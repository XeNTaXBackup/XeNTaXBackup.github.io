## Post #1
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2022-03-03T09:23:02+00:00
- Post Title: Grimm Echoes (Repage)

Alright, there are two games but i should talk about them together.
I want to get 2D, 3D and sounds from them. Both of them are closed and have offline version with OBB.
But first, you can get nothing by rar software, extracting the OBBs. Hope someone can have a look at it.

"Repage"  dont have 3d but the 2d is great. Get these two games here.
[https://play.google.com/store/apps/deta ... n_US&gl=US](https://play.google.com/store/apps/details?id=com.square_enix.android_googleplay.grimmsechoes&hl=en_US&gl=US)
[https://play.google.com/store/apps/deta ... msnotesjpn](https://play.google.com/store/apps/details?id=com.square_enix.grimmsnotesjpn)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-03T22:16:42+00:00
- Post Title: Grimm Echoes (Repage)

> Reply from z22901206 ↑Thu Mar 03, 2022 5:23 pm at Thu Mar 03, 2022 5:23 pm
>
> 
OBB
the game is 4gb, 
at least you should have written a header or post a screenshot from the HEX Editor.
use 7zp or ImDisk.
after unpacking you will get .zip files inside which are .prefab(mesh) and others...
example unpacking files : [Grimm Echoes.zip](https://drive.google.com/file/d/10UNILpupm4RJ0aUoKI1YuAq-BugP0bKS/view?usp=sharing)
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-14T00:03:04+00:00
- Post Title: Grimm Echoes (Repage)

> Reply from z22901206 ↑Thu Mar 03, 2022 5:23 pm at Thu Mar 03, 2022 5:23 pm
>
> 
I want to get 2D
i create import/export plugin for *.texture and replaced a couple of textures in the game. 
(they have different types)
so I have a question: how to check the transparency of an image in order to automatically select the type for export?  

sample replaced texture(translated label):



test.png (223.19 KiB) Viewed 108 times


(also I can't find where the text is. the problem seems to be in Japanese hieroglyphs)
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-14T18:55:51+00:00
- Post Title: Grimm Echoes (Repage)

> Reply from Durik256 ↑Mon Mar 14, 2022 8:03 am at Mon Mar 14, 2022 8:03 am
>
> 
how to check the transparency
now I check the alpha like this. maybe there is a better way or built-in noesis?

```
for x in range(0,len(data),4):
	if data[x+3] != 255:
		alpha = 1
		break

```
## Post #5
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2022-03-15T00:49:06+00:00
- Post Title: Grimm Echoes (Repage)

> Reply from Durik256 ↑Fri Mar 04, 2022 6:16 am at Fri Mar 04, 2022 6:16 am
>
> 
at least you should have written a header or post a screenshot from the HEX Editor.
use 7zp or ImDisk
I dont know how to repair the header, but 7z still works.
My main task is getting the audio and finally i do it.
Thanks you.

> 2D 3D
Unfortunately i can give no help because i am a noob.
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-15T00:52:01+00:00
- Post Title: Grimm Echoes (Repage)

> Reply from z22901206 ↑Tue Mar 15, 2022 8:49 am at Tue Mar 15, 2022 8:49 am
>
> 
I dont know how to repair the header
file header. 

> Reply from z22901206 ↑Tue Mar 15, 2022 8:49 am at Tue Mar 15, 2022 8:49 am
>
> 
My main task is getting the audio
just rename name.audio >> name.ogg
## Post #7
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2022-03-15T01:44:44+00:00
- Post Title: Grimm Echoes (Repage)

> Reply from Durik256 ↑Tue Mar 15, 2022 8:52 am at Tue Mar 15, 2022 8:52 am
>
> 
z22901206 wrote: ↑Tue Mar 15, 2022 8:49 am
I dont know how to repair the header

file header. 
z22901206 wrote: ↑Tue Mar 15, 2022 8:49 am
My main task is getting the audio

just rename name.audio >> name.ogg
Yes, i did it like this and i get the ogg.
The header is not obviously, so i didn't notice that 7z can open it.
