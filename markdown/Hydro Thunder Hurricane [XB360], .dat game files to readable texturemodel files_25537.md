## Post #1
- Username: nghthwkk
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 14, 2022 12:12 pm
- Post datetime: 2022-06-16T08:48:12+00:00
- Post Title: Hydro Thunder Hurricane [XB360], .dat game files to readable texture/model files?

I need help from anybody who knows how to extract the model/texture data from any of these files. These are all extracted from the base.apf file.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1f58-03CZM3sT5HAPOxpWCbb6TrSB771Y?usp=sharing)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-16T10:17:24+00:00
- Post Title: Hydro Thunder Hurricane [XB360], .dat game files to readable texture/model files?

> Reply from nghthwkk ↑Thu Jun 16, 2022 4:48 pm at Thu Jun 16, 2022 4:48 pm
>
> 
I need help extract the model
using hex2obj



Vector_dest00.dat.png (85.33 KiB) Viewed 62 times
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-16T11:15:42+00:00
- Post Title: Hydro Thunder Hurricane [XB360], .dat game files to readable texture/model files?

> Reply from nghthwkk ↑Thu Jun 16, 2022 4:48 pm at Thu Jun 16, 2022 4:48 pm
>
> 
I need help from anybody who knows how to extract the model
i made a plugin. opens all model from folder 'AkStaticModelAsset'

(in order to avoid conflicts with other plugins (*.dat) it is better to change the resolution of all files. e.g. [*.dat] >> [*.myStaticMesh])
(also replace inside plugin line 5)
[fmt_dat.zip](https://xentaxbackup.github.io/file/22377_fmt_dat.zip)
## Post #4
- Username: nghthwkk
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 14, 2022 12:12 pm
- Post datetime: 2022-06-16T11:29:16+00:00
- Post Title: Hydro Thunder Hurricane [XB360], .dat game files to readable texture/model files?

> Reply from Durik256 ↑Thu Jun 16, 2022 7:15 pm at Thu Jun 16, 2022 7:15 pm
>
> 
nghthwkk wrote: ↑Thu Jun 16, 2022 4:48 pm
I need help from anybody who knows how to extract the model

i made a plugin. opens all model from folder 'AkStaticModelAsset'

Traceback (most recent call last):
  File "F:\lil apps\noesis4\plugins\python\fmt_dat.py", line 20, in LoadModel
    name = searchString(bs)
  File "F:\lil apps\noesis4\plugins\python\fmt_dat.py", line 52, in searchString
    return noeAsciiFromBytes(bytes)
NameError: global name 'noeAsciiFromBytes' is not defined


When exporting/previewing any of them.
## Post #5
- Username: nghthwkk
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 14, 2022 12:12 pm
- Post datetime: 2022-06-16T11:33:38+00:00
- Post Title: Hydro Thunder Hurricane [XB360], .dat game files to readable texture/model files?

> Reply from Durik256 ↑Thu Jun 16, 2022 7:15 pm at Thu Jun 16, 2022 7:15 pm
>
> 
nghthwkk wrote: ↑Thu Jun 16, 2022 4:48 pm
I need help from anybody who knows how to extract the model

i made a plugin. opens all model from folder 'AkStaticModelAsset'
(in order to avoid conflicts with other plugins (*.dat) it is better to change the resolution of all files. e.g. [*.dat] >> [*.myStaticMesh])
(also replace inside plugin line 5)
Can it extract textures? I included everything the game has in the drive.
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-16T11:34:23+00:00
- Post Title: Hydro Thunder Hurricane [XB360], .dat game files to readable texture/model files?

> Reply from nghthwkk ↑Thu Jun 16, 2022 7:29 pm at Thu Jun 16, 2022 7:29 pm
>
> 
NameError: global name 'noeAsciiFromBytes' is not defined
strange, 'noeAsciiFromBytes' its standart method in 'inc_noesis.py'
i update plugin, .actually there is no need for this method.
don't quote all post. (edit your msg) 

> Reply from nghthwkk ↑Thu Jun 16, 2022 7:33 pm at Thu Jun 16, 2022 7:33 pm
>
> 
Can it extract textures?
No, its load only mesh and uv. I just looked at the static mesh
## Post #7
- Username: nghthwkk
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 14, 2022 12:12 pm
- Post datetime: 2022-06-16T11:41:46+00:00
- Post Title: Hydro Thunder Hurricane [XB360], .dat game files to readable texture/model files?

> Reply from Durik256 ↑Thu Jun 16, 2022 7:34 pm at Thu Jun 16, 2022 7:34 pm
>
> 
nghthwkk wrote: ↑Thu Jun 16, 2022 7:33 pm
Can it extract textures?

No, its load only mesh and uv. I just looked at the static mesh

Any way to extract textures from AkTextureAsset?
