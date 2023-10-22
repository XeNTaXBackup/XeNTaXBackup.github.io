## Post #1
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-12T23:31:56+00:00
- Post Title: Granado Espada models and animations - .lma files

Hello,

GE char models and animation are stored in a format I never seen before: .lma
I was wondering if anyone would like to help figure how to open them and extract the meshes and animation.
I attached 2 small archives with some file examples.

Character: [http://rapidshare.com/files/172838370/character.rar](http://rapidshare.com/files/172838370/character.rar) The archive contains the folder structure that was inside the .ipf files
Animation: [http://rapidshare.com/files/172838415/animation.rar](http://rapidshare.com/files/172838415/animation.rar)

Thanks
## Post #2
- Username: MrSpoon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 02, 2009 2:09 pm
- Post datetime: 2009-04-02T06:24:18+00:00
- Post Title: Granado Espada models and animations - .lma files

I figured I'd drag this thread back from the dead instead of opening a new one. I'm also looking into Granado Espada's file formats, well rather, the North American localized version - Sword of the New World. While I have little to no experience related to 3D file formats, I'm very stubborn. I'll post what information I am able to dig up on my own here. If anyone here is able to take a look at my findings and help point me in the right direction, that would be excellent.

Edit:
Okay this is what I have come up with so far. As I stated earlier, I'm not entirely familiar with 3D file formats. As such, some of my terms might be off. Sorry about that, if you need clarification, let me know and I'll do my best to make myself understood.

All of the resources are stored in .ipf files according to type. animations.ipf, char_textures.ipf, char_hi.ipf, and et cetera. These are password protected pkzip files. I wanted to start on manipulation of textures and the user interface, so I'll start there. I extracted every ipf file and retained the folder structure inherent in the .ipf files. Within the .ipf archives that seemed to be relevant to the characters, the directory trees are laid out like so with an exception. 

char_hi.ipf / char_low.ipf / char_mid.ipf

```
   body\ .lma
   bone\ .lma
   material\ .xml
npc\
   body\ .lma
   bone\ .lma
   material\ (empty)
pc\
   armor\ (empty)
   body\ .lma and .dds
   bone\ .lma
   costume\ .lma
   material\ .xml

```

These three main directories are for the varying levels of detail in the game. The amount of files and their names are identical with slight alterations to the contents. The exception mentioned earlier is that char_textures.ipf has a varied structure, as well as contents. 

char_textures.ipf

```
npc\ .dds
pc\
   armor\ .dds
   body\ .dds
```


There are even a few xml files in the char_mid/hi/low directories, but after browsing through about 15 of them, they seem to be related to action sounds for animations. I couldn't get the nVidia DDS plugin working for me in Photoshop CS4, and it seems that it's not only me judging from the nvidia forums, so I tried my hands at freeware to accomplish viewing of these .dds files. At any rate, I figure the .dds problem is easily solved with a trial install of an older version of Photoshop and nVidia's plugin.

.LMA File. What is it?
I have found no information on the internet for this file type, so I decided to try to determine on my own what the files are. I decided to try my hand at examining the file contents with a hex editor to see what I could find out about this elusive, and most likely proprietary (or at least renamed!) file format. Here is what I have (and have not) deduced. I'll be using example file 'pc_set_fgt_head_f.lma' from char_hi.ipf/pc/body/ 

Offsets 0x0 to 0xB are 4C 4D 41 20 01 01 01 06 00 00 00 6C. Header, yeah? It says it's LMA(space) with a 1 in decimal at offset 0xB. Offset 0x15+ says in decimal 'Extra Material' and at offset 0x7D it lists PC_SET_FGT_BODY_F_NONE_L1.  This file is a texture file located in char_textures.ipf/pc/body. Well, not quite, the _L1 isn't attached, and it is specifying a layer from the .DDS. This is speculation, but looking at other .lma files, the ones in char_hi.ipf all have _L1 extensions, char_mid.ipf have _L2 extensions, and char_low.ipf have _L3 extensions. This tells me that the .DDS files are layered for different qualities. 

Everything readable (in English) looks to reference texture files. There are other sections where I have no idea what they're referencing. Such examples are 

0x49-0x5E: (present in every .lma)
40 3F 00 00 40 3F 00 00 40 3F 00 00 80 3F 00 00 80 3F 00 00 80 3F
(translates to @?..@?..@?...?...?...?)

Scattered around the files are things like "Bip01 Pelvis" "Bip01 Spine" "Bip01 Spine2". I gather these are the names of the 'objects' to be rendered. 

I'm sure it's not much, but I hope that this information would be a bit of help in determining what the .lma files are. An example .lma is attached.

On another note, while the files inside the ipf's (which is what should be discussed as it is the game archive file) can be extracted through RPGViewer - I haven't found any method to reinserting them. PKZip has the files encrypted, and it looks like there's some sort of compression as the files fail to show their correct names. An example .ipf is attached.
[ipf and lma.rar](https://xentaxbackup.github.io/file/1948_ipf and lma.rar)
