## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-02-14T10:34:48+00:00
- Post Title: Backyard Wrestling 2 - There Goes The Neighborhood (3D-Models and Textures)

Hey guys,
I hope this one goes rather quick, since the formats seem to be similar to the first game and, they have been figured out already.
All of the games data is again stored in a "GAMEDATA.WAD" (265 MB). Dowload it here: [https://we.tl/t-W9m0S8fzSt](https://we.tl/t-W9m0S8fzSt) (Link is active for 7 days only!)
You can open this archive with the quickbms script "BackyardWrestlingDTTAHwad.bms" and will end with 5.224 files that are either DATA or MESH.


3D-Models:
The first games static models could be converted to 3ds with the quickbms script "BackyardWrestlingMeshto3dsUVbeta.bms". However when I try to use it on all of the second games .MESH files, I receive this error:


Character models form the first game could be extracted thanks to Szkaradek123's Blender 2.49 import-script:

> Reply from Szkaradek123 ↑Sat Mar 09, 2019 11:40 pm at Sat Mar 09, 2019 11:40 pm
>
> 
Blend file to import mesh files with uvs ,bones and weights.

http://www.mediafire.com/file/q3416gvoa ... 3-09%5D.7z

You need:
http://download.blender.org/release/Ble ... indows.exe
and
https://www.python.org/ftp/python/2.6.6 ... -2.6.6.msi

Unpack archive, doubleclick on file "Blender249.blend" , press alt+p in Blender Text Window and import .mesh.

Meshes are split by the same texture (uv mapping).
sadly it doesn't work on the second games characters.

Here are 2 sample files, from what i believe are a character and some random object:
Character - [https://cdn.discordapp.com/attachments/ ... /4742.mesh](https://cdn.discordapp.com/attachments/553220665692651542/810446729572253736/4742.mesh)
Object - [https://cdn.discordapp.com/attachments/ ... 4/385.mesh](https://cdn.discordapp.com/attachments/553220665692651542/810446724597940284/385.mesh)


Textures:
There are actually 2 scripts for textures...(both have to be used on the .WAD file)
"BackyardWrestlingDTTAwadTexture.bms" is the original by albinoleopard and doesnt cover all of the texture files.
"BackyardWrestling_TEX-Files.bms" has been made by Acewell and got much more if not all of the textures.

....Acewells noesis script [download/file.php?id=17121](https://forum.xentax.com/download/file.php?id=17121) then reads/converts the TEX-files.

albinoleopards script actually worked on the second games .WAD! The resulting files cant be read by the ps2txdviewer or Acewells noesis-script. Afriend was able to help me a little though:

He gave me the following info on the games textures:

```

struct{
    char header[84];
    int width;
    int height;
    int bbp;
    char header2[100 - 4 - 32];

    struct{
        int header[5];
        int16 zero;
        int16 type; //0 => dxt5 or 64 => swizzle pallete
        int header3[2];
        int width;
        int height;
        char unk[40 - 16 + 7];
        char headerSize;
        char header2[headerSize];

        if (type == 64){ //palette
            char data[width*height];
        
        }else{ //real image
            char data[width*height*4];
        }


    }data[2]<optimize=false>;

}entry;
```


first block is the image, second one is the palette.
palette uses "regular" ps2 swizzeling and the images are stored as DXT5.

Here are 3 sample files, already extracted from the .WAD:
[https://cdn.discordapp.com/attachments/ ... .162.0.TXD](https://cdn.discordapp.com/attachments/550649773363822672/796445026904702996/texture.162.0.TXD)
[https://cdn.discordapp.com/attachments/ ... .216.0.TXD](https://cdn.discordapp.com/attachments/550649773363822672/796445062811877386/texture.216.0.TXD)
[https://cdn.discordapp.com/attachments/ ... 2983.0.TXD](https://cdn.discordapp.com/attachments/550649773363822672/795102435349233674/texture.2983.0.TXD)



Link to my thread about the first game and all bms scripts:
[viewtopic.php?t=19370](https://forum.xentax.com/viewtopic.php?t=19370)



I hope I could provide enough info and sample files in order for you guys to work your magic again. Anybody helping or actually just creating scripts and helpers is super welcome. thank you for your time and we hopefully have some byw2 models and textures soon   

PEACE
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-02-26T14:39:03+00:00
- Post Title: Backyard Wrestling 2 - There Goes The Neighborhood (3D-Models and Textures)

*friendly bump*
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-04-16T08:43:13+00:00
- Post Title: Backyard Wrestling 2 - There Goes The Neighborhood (3D-Models and Textures)

Just figured out, that the old texture script DOES work on most of byw2s textures! Only rectangle ones seem to have conversion problems.
## Post #4
- Username: JuggaloJesus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 26, 2021 4:13 pm
- Post datetime: 2021-05-26T08:21:08+00:00
- Post Title: Backyard Wrestling 2 - There Goes The Neighborhood (3D-Models and Textures)

For textures you can use TexMod. I was only kind of skimming and saw that this wasn't too terribly old so figured I would reply because I'm also trying to get my hands on the Backyard Wrestling models. I've been making games geared towards Juggalos you can check out over at [https://www.juggalogames.com](https://www.juggalogames.com) and long story short I'm in need of the models for at least some placeholder stuff for prototyping until I can get newer up to date models to use for 3D stuff.

I was wondering if you had ever figured anything out with this? I can get the textures for Backyard Wrestling 2 but they're discolored at the moment. There is supposed to be a way to fix them in Gimp which I will be trying to do later but for now I'm stuck trying to rip the models to use them on so it's sort of pointless for me to recolor the texture if I don't have a model to use it with.

Let me know asap if you see this if you ever figured out anything with this.

-MMFWCL
## Post #5
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-06-03T05:46:03+00:00
- Post Title: Backyard Wrestling 2 - There Goes The Neighborhood (3D-Models and Textures)

> Reply from JuggaloJesus ↑Wed May 26, 2021 4:21 pm at Wed May 26, 2021 4:21 pm
>
> 
For textures you can use TexMod. I was only kind of skimming and saw that this wasn't too terribly old so figured I would reply because I'm also trying to get my hands on the Backyard Wrestling models. I've been making games geared towards Juggalos you can check out over at https://www.juggalogames.com and long story short I'm in need of the models for at least some placeholder stuff for prototyping until I can get newer up to date models to use for 3D stuff.

I was wondering if you had ever figured anything out with this? I can get the textures for Backyard Wrestling 2 but they're discolored at the moment. There is supposed to be a way to fix them in Gimp which I will be trying to do later but for now I'm stuck trying to rip the models to use them on so it's sort of pointless for me to recolor the texture if I don't have a model to use it with.

Let me know asap if you see this if you ever figured out anything with this.

-MMFWCL

Hey fam!
I know texmod, and all you gotta do in the end is  Switch the RED and BLUE channel in the end to get the real texture color....this is a long process though and will take forever since byw2 uses more textures per character than byw1.
Still no success with the byw2 models :-/
I Got all characters of byw1 if i can help you with that...just PM me.
Whoop whoop!
