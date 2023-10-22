## Post #1
- Username: RampantLeaf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Apr 17, 2017 6:50 am
- Post datetime: 2017-06-28T22:57:51+00:00
- Post Title: Epic Mickey nif_wii and hkx_wii files

I've been extensively trying to find unused content and extract models from Epic Mickey. I know there is a lot of scrapped, test and debug content in this game from its development history and the filenames I've seen.

My biggest issue right now is nif_wii and hkx_wii files. I've extracted nif files from Epic Mickey 2 for PC and viewed them in Noesis, but renaming nif_wii files from the first game to nif doesn't seem to work. As for hkx_wii files, I have no way to view these files, but I have good reason to believe they're the meshes. 

If it helps, the NIF version is "Gamebryo File Format, Version 20.6.5.0"
Here's some file example files if anyone is interested in taking a look: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/0BzvBP9zuLJaCMjJhYTF5WmNCNEk?usp=sharing)
## Post #2
- Username: RampantLeaf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Apr 17, 2017 6:50 am
- Post datetime: 2017-08-10T15:02:58+00:00
- Post Title: Epic Mickey nif_wii and hkx_wii files

I have some evidence that hkx_wii files may also contain animations.
## Post #3
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-08-29T12:59:28+00:00
- Post Title: Epic Mickey nif_wii and hkx_wii files

Box_Dynamic.hkx_wii may be game engine file that represents it's build and rendering settings. It contains majority of strings data, example: "D:\\JunctionPoint\\Mickey\\Game\\Content\\Raw\\Environments\\HauntedMansion\\Props\\Temp\\Box_Default.ma" which is import path, casual for game engines to control versions in-development

Box_Dynamic.nif_wii is another setting format that has info about scenes and relative path to \environments\thepark\neworleanssquare\hauntedmansion\props\textures\HM_FloorER1_Toon_tex.nif <-- this cube uses this texture

Box_Static.nif_wii as above

None of the files you provided contain texture/graphics

> Reply from RampantLeaf
>
> I have some evidence that hkx_wii files may also contain animations.
I doubt it
## Post #4
- Username: RampantLeaf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Apr 17, 2017 6:50 am
- Post datetime: 2017-09-01T11:34:51+00:00
- Post Title: Epic Mickey nif_wii and hkx_wii files

> Reply from MaKiPL
>
> Box_Dynamic.hkx_wii may be game engine file that represents it's build and rendering settings. It contains majority of strings data, example: "D:\\JunctionPoint\\Mickey\\Game\\Content\\Raw\\Environments\\HauntedMansion\\Props\\Temp\\Box_Default.ma" which is import path, casual for game engines to control versions in-development

Box_Dynamic.nif_wii is another setting format that has info about scenes and relative path to \environments\thepark\neworleanssquare\hauntedmansion\props\textures\HM_FloorER1_Toon_tex.nif <-- this cube uses this texture

Box_Static.nif_wii as above

None of the files you provided contain texture/graphics
RampantLeaf wrote:I have some evidence that hkx_wii files may also contain animations.
I doubt it
Hm, so from what I understand, nif_wii files aren't textures at all? I originally assumed they were a variation of nif files. Looks like nif files may be the real textures, although I haven't found many of them. Thanks for the information!
