## Post #1
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2018-02-11T18:06:28+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

Need some help converting these phyre.dds files

Here's some samples
[tex.zip](https://xentaxbackup.github.io/file/13901_tex.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-12T01:34:44+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

here is a Noesis python script to open your 3 samples  
*script updated Feb 28, 2018*


 tex_FinalFantasyXIIZA_PC_phyre.zip
(992 Bytes) Downloaded 247 times


supports argb8, bc5, a8, dxt5
## Post #3
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2018-02-12T04:23:28+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from AceWell
>
> here is a Noesis python script to open your 3 samples  
tex_FinalFantasyXIIZA_PC_phyre.zip
supports argb8 and bc5
Thank you very much agaian it works, but it conflicts with the ffx hd plugin i need to disable it to use this one.
## Post #4
- Username: onelight
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 01, 2017 12:05 am
- Post datetime: 2018-02-12T15:19:30+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from AceWell
>
> here is a Noesis python script to open your 3 samples  
The attachment tex_FinalFantasyXIIZA_PC_phyre.zip is no longer available
supports argb8 and bc5

Hello. 
I have some .phyre from PS4 games, it look very like that 3 samples. Unfortunately not support by tex_FinalFantasyXIIZA_PC_phyre.py
It's there a Noesis python script or bms script support .phyre from PS4?
Here is my samples
[dds.GNM.phyre-PS4.7z](https://xentaxbackup.github.io/file/13905_dds.GNM.phyre-PS4.7z)
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-18T00:52:26+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from onelight
>
> 
Hello. 
I have some .phyre from PS4 games, it look very like that 3 samples. Unfortunately not support by tex_FinalFantasyXIIZA_PC_phyre.py

Just the file structures are similar, since they are both phyre engine files. The texture data in your samples isn't just raw pixels or block compression like FFX. I guess there is some additional compression because of the GNM format.
## Post #6
- Username: EmptyMan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2016 2:22 am
- Post datetime: 2018-02-28T12:04:40+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from AceWell
>
> supports argb8 and bc5
Hello, AceWell.
Can you add support more textures?
Samples:
[tex.rar](https://xentaxbackup.github.io/file/13968_tex.rar)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-01T00:33:56+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

okay i updated the script here to support dxt5 and a8 also
[viewtopic.php?p=137846#p137846](http://forum.xentax.com/viewtopic.php?p=137846#p137846)
the only one i could not get was the cubemap, still not sure how to read and display those properly.  
i guess if you need that one bad enough you can just use TextureFinder.
## Post #8
- Username: notmyfavorite
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 21, 2018 1:59 pm
- Post datetime: 2018-03-01T07:35:32+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

Ace, you're fantastic...

Anychance you could shed some light on some *.cm files?
Texturefinder for sure reveals some obvious images.. not sure what to make of them..

here are some samples..
[maybetextures.zip](https://xentaxbackup.github.io/file/13974_maybetextures.zip)
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-02T19:40:54+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

are those samples from this same game? they sure don't look like phyre files to me.   
not much i can do with them, i can only help break down the chunks to better see what is happening.   
this bms script will split the chunks into individual files from cm samples (i wish we had spoiler tags here   )

```

get EXT extension
if EXT == cm
    get FOLDER basename
    idstring "\x40FRP"
    get ZERO long
    get DATA_SIZE long
    get FILES long
    goto 0x30
    for i = 1 to FILES
        get OFFSET long
        math OFFSET + 0x30
        savepos TMP
        goto OFFSET
        get SKIP byte
        getdstring EXT 3 
        get SKIP long
        get SIZE long
        string NAME p "%s\%s_%d.%s" FOLDER FOLDER i EXT 
        log NAME OFFSET SIZE
        goto TMP
    next i
elif EXT == FTE
    get FOLDER basename
    idstring "\x40FTE"
    get ZERO long
    get DATA_SIZE long
    get FILES long
    goto 0x40
    for i = 1 to FILES
        get UNK long
        get WIDTH short
        get HEIGHT short
        get UNK long
        get UNK2 long
        get ZERO long
        get SIZE long
        get OFFSET long
        get UNK4 long
        string NAME p "%s_%s\%02d_%03d_%03d.texd" FOLDER EXT i WIDTH HEIGHT
        log NAME OFFSET SIZE
    next i
elif EXT == FCT
    get FOLDER basename
    idstring "\x40FCT"
    get ZERO long
    get DATA_SIZE long
    get FILES long
    goto 0x30
    for i = 1 to FILES
        get UNK long
        get UNK2 long
        get UNK3 long
        get OFFSET long
        savepos TMP
        if i == FILES
            xmath SIZE "DATA_SIZE - OFFSET" 
        else
            goto 0xc 0 seek_cur
            get NEXT_OFFSET long
            xmath SIZE "NEXT_OFFSET - OFFSET"
        endif
        string NAME p "%s_%s\%02d.pald" FOLDER EXT i
        log NAME OFFSET SIZE
        goto TMP
    next i
endif

```

the FCT and FTE chunks can be broken down further with this script into the number of files they contain,
i believe the FTE files contain series of image data while the FCT files contain series of palette data,
but i'm not sure, this is too chaotic for me and i've only dabbled with paletted images previously.
## Post #10
- Username: notmyfavorite
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 21, 2018 1:59 pm
- Post datetime: 2018-03-03T03:51:18+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

Awesome, trying it out right now! This is really interesting! Thanks for taking the time to help out!

I've actually found something kind of interesting with the `.phyre` files recently..
Texture Finder actually finds the mipmaps in the .dds while Noesis does not seem to be doing so..

I have been editing the exported dds version from Noesis but have found that it clearly does not include the entire texture.
See the screenshot below.. Any ideas?

Noesis (left) -- Texturefinder (right)
[comparison.PNG](https://xentaxbackup.github.io/file/13991_comparison.PNG)
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-03T04:45:38+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from notmyfavorite
>
> Texture Finder actually finds the mipmaps in the .dds while Noesis does not seem to be doing so..
I have been editing the exported dds version from Noesis but have found that it clearly does not include the entire texture.
no, the entire image is there, just no mipmaps. none of my scripts are set for mipmaps, 
i don't care for them, you can easily resave the images to restore mipmaps.  
if you edit the image then you will have to save out new mipmaps anyway which is easy enough.
## Post #12
- Username: notmyfavorite
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 21, 2018 1:59 pm
- Post datetime: 2018-03-03T05:04:43+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

Yeah they are, found in the the ps2data folder... 
`ps2data\obj_finish\in\*`


I have been using gimp to save the .dds files after editing them.. they don't seem to be creating mipmaps properly.. is there an application you would suggest?

is it hypothetically possible to extract the dds with mipmaps? I ask becuase editing these dds files and then reinserting them into a phyre file via hex editing is a lot of work.. it seems like it would just be easier to extract the mipmaps as well?
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-03T05:34:34+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from notmyfavorite
>
>  found in the the ps2data folder...
so those are from PS2 platform and not PC, that explains the paletted image data and why i asked.   

i use Photoshop with Nvidia tools to save out dds and anything is possible given enough time and interest invested.
it sounds like you want a phyre file exporter which is a modding thing and not my area.  


edit
now it all makes sense knowing your samples are taken from PS2  
if you combine the first palette with the first image data and open it in ConsoleTextureExplorer you get this



Untitled-1.png (119.75 KiB) Viewed 735 times
## Post #14
- Username: kidling
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 15, 2015 11:34 am
- Post datetime: 2018-03-10T00:39:28+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

AceWell is possible to do a plugin for noesis to import the colada file inside the phyre container(FFXII)?
[c1004.dae.rar](https://xentaxbackup.github.io/file/14010_c1004.dae.rar)
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-11T01:58:48+00:00
- Post Title: Final Fantasy XII ZA PC Phyre.dds Textures

i can't do much with the model in the phyre containers, maybe Hex2obj but that is about it.   
the phyre files are already chaotic in my eyes, daemon1 seems to have it figured out though, give his phyre tools a try.   
[viewtopic.php?f=16&t=16930](http://forum.xentax.com/viewtopic.php?f=16&t=16930)
## Post #16
- Username: kidling
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 15, 2015 11:34 am
- Post datetime: 2018-03-12T08:35:18+00:00
- Post Title: Re: Final Fantasy XII ZA PC Phyre.dds Textures

Thank you Acewell, i will talk with him
## Post #17
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-14T02:07:29+00:00
- Post Title: Re: Final Fantasy XII ZA PC Phyre.dds Textures

I was able to make my SAO tool load the meshes by making some slight changes. 


I will take a look at the skeleton when I have the time. Also the model seems to be really low poly, like ps2 stuff. I was expecting something better for the pc release, kinda disappointed.
## Post #18
- Username: kidling
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 15, 2015 11:34 am
- Post datetime: 2018-03-14T12:54:18+00:00
- Post Title: Re: Final Fantasy XII ZA PC Phyre.dds Textures

wow, that would be gamechanging if we got a tool to edit that models.
## Post #19
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-03-15T02:06:35+00:00
- Post Title: Re: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from akderebur
>
> I was able to make my SAO tool load the meshes by making some slight changes. 


I will take a look at the skeleton when I have the time. Also the model seems to be really low poly, like ps2 stuff. I was expecting something better for the pc release, kinda disappointed.

Is it possible to edit the tool to load the environments in the game?
The characters aren't my forte, but retexturing those environments will be a loooot easier if we can view them outside of the game.
## Post #20
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-15T02:43:47+00:00
- Post Title: Re: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from lionheartuk
>
> 
Is it possible to edit the tool to load the environments in the game?
The characters aren't my forte, but retexturing those environments will be a loooot easier if we can view them outside of the game.

Can you send me some sample files? I will take a look and see if I can get them to work.
## Post #21
- Username: kidling
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 15, 2015 11:34 am
- Post datetime: 2018-03-18T01:48:56+00:00
- Post Title: Re: Final Fantasy XII ZA PC Phyre.dds Textures

> Reply from akderebur
>
> I was able to make my SAO tool load the meshes by making some slight changes. 


I will take a look at the skeleton when I have the time. Also the model seems to be really low poly, like ps2 stuff. I was expecting something better for the pc release, kinda disappointed.

just did a unpacker/packer with all texture formats: ARGB8, DXT5, BC5

now time to get the 3d model of phyre

akderebur please may you help me finding the offsets for 3d model? i Think we don´t need the squeleton/bones, only the 3d model for modding
[phyreffxii.rar](https://xentaxbackup.github.io/file/14060_phyreffxii.rar)
## Post #22
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-18T10:19:52+00:00
- Post Title: Re: Final Fantasy XII ZA PC Phyre.dds Textures

A tool that imports modified meshes would have some limitations. Like the new mesh needs to have same vertex and index count as the original mesh. Otherwise it would cause problems with the offsets inside the file.

So with those limitations I think only thing you can do is to move the vertices of the mesh. I mean it is still something, but it won't be proper modding.
## Post #23
- Username: kidling
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 15, 2015 11:34 am
- Post datetime: 2018-03-18T13:19:23+00:00
- Post Title: Re: Final Fantasy XII ZA PC Phyre.dds Textures

holy shit, I had not thought about that. So if we want to mod a 3d model we need to find a way to redo the phyre file from scratch?

That's sad
