## Post #1
- Username: JediKnightChan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 09, 2018 3:29 pm
- Post datetime: 2018-08-23T16:41:20+00:00
- Post Title: Eternal Crusade

WH40K: Eternal Crusade is based on Unreal Engine. UE Version: 4.12. Many interesting Warhammer models, eg Space Marines, Eldar are stored in its depths. It would be nice to extract them.
## Post #2
- Username: JediKnightChan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 09, 2018 3:29 pm
- Post datetime: 2018-08-23T16:57:08+00:00
- Post Title: Eternal Crusade

Some interface pictures and movies are stored in the game folder without any encryption. Most game resources, such as models and textures, are placed into .pak file in {Game}/EternalCrusade/Content/Paks/ directory. You can easily unpack it with UnrealPak.exe (comes with UE) or use Umodel for fast extracting models and textures (not all of them). [Here](https://github.com/panzi/u4pak) are file specs and Python script.

After unpacking .pak you get a .uproject with a lot of content. I managed to extract some models with Umodel (but it couldn't extract all models one time and it doesn't support all .uasset files) and open .uasset files with UE. 



It's neccessary to find supervisor files with links to all these .psk, .tga and .mat files, I would like to get links to standard Blood Angel Jump Assault.
