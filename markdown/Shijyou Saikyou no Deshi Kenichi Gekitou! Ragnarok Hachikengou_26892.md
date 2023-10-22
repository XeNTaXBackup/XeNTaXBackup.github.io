## Post #1
- Username: sangrento55
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 24, 2022 9:38 am
- Post datetime: 2023-06-23T02:53:39+00:00
- Post Title: Shijyou Saikyou no Deshi Kenichi Gekitou! Ragnarok Hachikengou

I'm trying to extract 3d models from Shijyou Saikyou no Deshi Kenichi Gekitou! Ragnarok Hachikengou ps2 game

I took a look at the files and come to this:

# Audio

- Folder `snd`

- Sony's PS2 sequence and instrument formats .BD and .HD

- HD files contain header chunks while BD files contain audio data.

Ref: [http://wiki.xentax.com/index.php/PlaySt ... D_HD_Audio](http://wiki.xentax.com/index.php/PlayStation_2_BD_HD_Audio)

# Video

- Folder `str`

- Standard PlayStation 2 movie file format. It contains MPEG2 video data and PCM/ADPCM audio data.

- PSS extension stands for "PlayStation Stream"

# Executable

- Folder `modules`

- Sony's PS2 executable format .IRX

- It is executable file format used mostly in some Unix based operating systems like Ubuntu, OpenBSD etc. and on some consoles like PlayStation Portable, PlayStation Vita etc.
  Android uses ELF \*.SO libraries (shared object files) for the Java Native Interface.

Ref: [https://wiki.xentax.com/index.php/ELF_Executable](https://wiki.xentax.com/index.php/ELF_Executable)
Ref: [https://www.retroreversing.com/irx-ps2](https://www.retroreversing.com/irx-ps2)

# Dummy

- Folder `dummy`

- Dummy files are used to fill up the remaining space on a disc. They are not used by the game.

# Files AFS

- `bgm` - Background music - format `adx`
- `data` - Data files
- `voice` - Voice Acting - format `adx`

### Data files

* All files are compressed as `FSB` format. inside the `FSB` file there are `DFF` files. `TEX` files are renderware files. 

Ref: [https://wiki.xentax.com/index.php/ADX_Audio](https://wiki.xentax.com/index.php/ADX_Audio)
Ref: [https://wiki.xentax.com/index.php/Silen ... mories_TXD](https://wiki.xentax.com/index.php/Silent_Hill:_Shattered_Memories_TXD)

I need to get the models in data folder but it seems to be encrypted.

Here are the files extracted from data.afs: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1_O3gMLclBkqdJUy6cVgC8dzBUhqFfPiK?usp=sharing)
## Post #2
- Username: sangrento55
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 24, 2022 9:38 am
- Post datetime: 2023-06-23T02:56:38+00:00
- Post Title: Shijyou Saikyou no Deshi Kenichi Gekitou! Ragnarok Hachikengou

oh i tried fsbext as well
## Post #3
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2023-06-23T17:45:47+00:00
- Post Title: Shijyou Saikyou no Deshi Kenichi Gekitou! Ragnarok Hachikengou

Put the .fpk extension on the files and extract with noesis
## Post #4
- Username: sangrento55
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 24, 2022 9:38 am
- Post datetime: 2023-06-23T18:56:39+00:00
- Post Title: Shijyou Saikyou no Deshi Kenichi Gekitou! Ragnarok Hachikengou

Thanks for reply.

I had to extract again thouse files that I upload are not correct extracted, but yes fpk works fine.

 I will continue digging, thanks again.
## Post #5
- Username: sangrento55
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 24, 2022 9:38 am
- Post datetime: 2023-06-24T07:09:37+00:00
- Post Title: Shijyou Saikyou no Deshi Kenichi Gekitou! Ragnarok Hachikengou

I manage to extract EVERYTHING hahahah



but there is one last thing.

The maps I have then separly but would be nice to have the BSP loader to import in blender. Can you help ?

Here are the files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1qG4IWmZv5gYmmuucG61J1VygvBEhxEix?usp=sharing)
## Post #6
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2023-06-24T07:46:47+00:00
- Post Title: Shijyou Saikyou no Deshi Kenichi Gekitou! Ragnarok Hachikengou

This game uses Renderware, but unlike regular dff, it is customized by 8ing. How did you load the dff?
## Post #7
- Username: sangrento55
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 24, 2022 9:38 am
- Post datetime: 2023-06-25T00:50:55+00:00
- Post Title: Shijyou Saikyou no Deshi Kenichi Gekitou! Ragnarok Hachikengou

I use noesis with a custom pugin [https://github.com/leeao/Noesis-Plugins](https://github.com/leeao/Noesis-Plugins) I was having a hardtime converting this script to work with this dff model. But the plugin creator answer me and fixed for me.
