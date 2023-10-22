## Post #1
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2021-04-26T16:57:50+00:00
- Post Title: Initial D Arcade Stage (5 to Zero) Noesis Script

[ Updated here ](https://forum.xentax.com/viewtopic.php?f=16&t=14024&p=178325#p178325)

> I know I've made a thread for this, but since I think a lot of people are following this one, I'm posting this here.
>
> 
>
> I wrote a Blender Addons 2.8+ (tested in Blender 2.92.0) to import the models. More details here.
>
> 
>
> 
>
> 
>
> The characters are all skinned now, except one which is Miki (since he has 4 bone weights, and the bone indices isn't in the right order in the vertex buffer).
>
> 
>
> Miki sample (one vertex buffer at offset 0xC64A8, stride 40, last 8 bytes being the bone indices and bone weights) 
>
> 
>
> In order to import the trees, you will need the folder path with the extension .pa8. Also I don't think the trees in the game have random rotations, but there is some informations in the .pa8 that I skipped (It might not be important though). The file format is like this :
>
> Code: Select allchar	Header[4]
>
> int 	Unknown
>
> uint	FileSize
>
> uint	TransformationCount
>
> bytes	zeros[16]
>
> 
>
> for i = 0 < TransformationCount
>
> 	float	Translation[3]
>
> 	float	MeshIndex  // the float is always a int, except in Gunsai sometimes
>
> 	byte	Unknown[28] // Maybe rotations ?
>
> 	float 	Scale
>
> 
>
> 
>
> I'm posting pa8 samples just in case : https://drive.google.com/file/d/1bhCx-O ... sp=sharing
>
> 
>
> Also, I admit I'm lazy to set up everything to play the Zero version, but I will be glad if someone could picture a high quality picture of this corner in Gunsai  since the index for one of the tree isn't precise, so I don't know if I'm importing the right one.
>
> 
>
> 
>
> 
>
> (Unrelated, but I can't believe I've been interested in this format for since 2018)
## Post #2
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-04-28T20:58:58+00:00
- Post Title: Initial D Arcade Stage (5 to Zero) Noesis Script

Hello
I tried opening just a random file, "title.efo" int he ADVERTISE folder
Edit: lot of efo files from folders like PRIMITIVE, RENDERER and SPRITEBG also don't open. I'm not having a lot of luck...I tried to open some 3d meshes such as "balloon.efo" and it just throws an errorr saying bad size or bad read
Edit2: Sayuki from CHARACTER folder crashes
[9oH0c2gvpF.png](https://xentaxbackup.github.io/file/19978_9oH0c2gvpF.png)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-28T22:18:40+00:00
- Post Title: Initial D Arcade Stage (5 to Zero) Noesis Script

> Reply from Makoto ↑Thu Apr 29, 2021 4:58 am at Thu Apr 29, 2021 4:58 am
>
> 
Hello
I tried opening just a random file, "title.efo" int he ADVERTISE folder
Edit: lot of efo files from folders like PRIMITIVE, RENDERER and SPRITEBG also don't open. I'm not having a lot of luck...I tried to open some 3d meshes such as "balloon.efo" and it just throws an errorr saying bad size or bad read

You may have to continue some basic research which had been started here:

> Reply from blackracer ↑Thu Nov 09, 2017 5:19 pm at Thu Nov 09, 2017 5:19 pm
>
> 

or here:

> Reply from Neitancrost ↑Wed Jun 05, 2019 7:54 am at Wed Jun 05, 2019 7:54 am
>
> 

helper tool (unfinished) for getting params

> Reply from shakotay2 ↑Wed Jan 08, 2020 11:24 pm at Wed Jan 08, 2020 11:24 pm
>
> 

----------------------------

When using the script on JZA80C_Body_genuine_00.efo I had to export as .dae from Noesis (while .obj contained QNANS).
.



JZA80C_Body_genuine_00-efo.png (109.03 KiB) Viewed 125 times


(dae import, uvs missing or lost, whatever)
## Post #4
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2021-04-29T17:41:43+00:00
- Post Title: Initial D Arcade Stage (5 to Zero) Noesis Script

[ Updated here ](https://forum.xentax.com/viewtopic.php?f=16&t=14024&p=178325#p178325)

> I know I've made a thread for this, but since I think a lot of people are following this one, I'm posting this here.
>
> 
>
> I wrote a Blender Addons 2.8+ (tested in Blender 2.92.0) to import the models. More details here.
>
> 
>
> 
>
> 
>
> The characters are all skinned now, except one which is Miki (since he has 4 bone weights, and the bone indices isn't in the right order in the vertex buffer).
>
> 
>
> Miki sample (one vertex buffer at offset 0xC64A8, stride 40, last 8 bytes being the bone indices and bone weights) 
>
> 
>
> In order to import the trees, you will need the folder path with the extension .pa8. Also I don't think the trees in the game have random rotations, but there is some informations in the .pa8 that I skipped (It might not be important though). The file format is like this :
>
> Code: Select allchar	Header[4]
>
> int 	Unknown
>
> uint	FileSize
>
> uint	TransformationCount
>
> bytes	zeros[16]
>
> 
>
> for i = 0 < TransformationCount
>
> 	float	Translation[3]
>
> 	float	MeshIndex  // the float is always a int, except in Gunsai sometimes
>
> 	byte	Unknown[28] // Maybe rotations ?
>
> 	float 	Scale
>
> 
>
> 
>
> I'm posting pa8 samples just in case : https://drive.google.com/file/d/1bhCx-O ... sp=sharing
>
> 
>
> Also, I admit I'm lazy to set up everything to play the Zero version, but I will be glad if someone could picture a high quality picture of this corner in Gunsai  since the index for one of the tree isn't precise, so I don't know if I'm importing the right one.
>
> 
>
> 
>
> 
>
> (Unrelated, but I can't believe I've been interested in this format for since 2018)
