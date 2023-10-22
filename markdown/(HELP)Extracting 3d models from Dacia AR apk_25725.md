## Post #1
- Username: olixvameshu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 22, 2022 12:02 am
- Post datetime: 2022-08-21T16:48:03+00:00
- Post Title: (HELP)Extracting 3d models from Dacia AR apk

Hi there, I'm new here.
Can anyone help me to extract 3d files and textures from apk named [Dacia AR](https://play.google.com/store/apps/details?id=com.renault.daciaar&hl=ro&gl=US) ?

They dont have any extention. Tried to ripp them with Ninja Ripper in emulators like NOX or Bluestacks, but incomplete(no interiors and incomplet textures), the emulators can't instal  Google Service for AR.

The files are looking like [that](https://disk.yandex.com/d/kr-OPBoKaamDuw).



Screenshot 2022-08-21 182505.png (56.75 KiB) Viewed 228 times
## Post #2
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-09-02T10:45:08+00:00
- Post Title: (HELP)Extracting 3d models from Dacia AR apk

well i found it interesting so i gave it a shot and downloaded the apk with the models and inspecting them on hxd seems to show some light, first of all the files are not raw, im not sure if its an encryption or just a compression method, one thing for sure is that all of them seem to have the same header which is:

15 4D 4D 51 5D 19 00 63 61 6C 65 36 65 41 0A 5A 19 6C 6D 13 16 15 6E 10 0A 16 14 39 62 63 61 6C 65 31
MMQ]�cale6eAZlmn9bcale1

i wonder if there is here any clue to a decompression method into it
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-02T11:19:40+00:00
- Post Title: (HELP)Extracting 3d models from Dacia AR apk

> Reply from olixvameshu ↑Mon Aug 22, 2022 12:48 am at Mon Aug 22, 2022 12:48 am
>
> 
Hi there, I'm new here.
Can anyone help me to extract 3d files and textures from apk named Dacia AR ?

They dont have any extention.Dunno which files you tried to extract exactly. When giving the Android version of that apk a zip extension I can see it containing a unity apk which again contains a datapack.unity3d. Loaded with AssetStudio from Perfare:
.


AssetStudio-datapack-unity3d.jpg (106.15 KiB) Viewed 187 times


(Use Asset List tab to display Texture2D, sprites etc.)
## Post #4
- Username: olixvameshu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 22, 2022 12:02 am
- Post datetime: 2022-09-22T21:49:14+00:00
- Post Title: (HELP)Extracting 3d models from Dacia AR apk

I've tried this before i asked for help here. The files that i request are as android bundle, once you instal the apk on a phone that support ar, and run it, you will need to download the bundle separately, after that the model will load. The models from my shared image does not come with the instaled apk, they appear after you start download the bundles separately.

The models are made in unity but there is no file extencion on them, the folder is simply named bundles and the file are without extencion.
## Post #5
- Username: gumbii
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 23, 2022 10:10 pm
- Post datetime: 2022-10-23T14:16:19+00:00
- Post Title: (HELP)Extracting 3d models from Dacia AR apk

> Reply from olixvameshu ↑Fri Sep 23, 2022 5:49 am at Fri Sep 23, 2022 5:49 am
>
> 
I've tried this before i asked for help here. The files that i request are as android bundle, once you instal the apk on a phone that support ar, and run it, you will need to download the bundle separately, after that the model will load. The models from my shared image does not come with the instaled apk, they appear after you start download the bundles separately.

The models are made in unity but there is no file extencion on them, the folder is simply named bundles and the file are without extencion.

Have you found a way?
## Post #6
- Username: olixvameshu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 22, 2022 12:02 am
- Post datetime: 2022-10-26T06:11:39+00:00
- Post Title: (HELP)Extracting 3d models from Dacia AR apk

Yes and i will make some tutorial at the end of the weekend for everybody.
## Post #7
- Username: gumbii
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 23, 2022 10:10 pm
- Post datetime: 2022-10-27T15:14:33+00:00
- Post Title: (HELP)Extracting 3d models from Dacia AR apk

> Reply from olixvameshu ↑Wed Oct 26, 2022 2:11 pm at Wed Oct 26, 2022 2:11 pm
>
> 
Yes and i will make some tutorial at the end of the weekend for everybody.

Nice!
## Post #8
- Username: gumbii
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 23, 2022 10:10 pm
- Post datetime: 2023-06-27T00:58:08+00:00
- Post Title: (HELP)Extracting 3d models from Dacia AR apk

> Reply from olixvameshu ↑Wed Oct 26, 2022 2:11 pm at Wed Oct 26, 2022 2:11 pm
>
> 
Yes and i will make some tutorial at the end of the weekend for everybody.

are you still working on it lmao?
