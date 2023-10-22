## Post #1
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-05-20T08:27:33+00:00
- Post Title: Animation files .BNM Star Wars: Ep III - RotS (2005) [XBOX]

Hello, so I have the .bnm files, I really need help to extarct animation  
I put in a .rar files, in "animation" samples of .bnm. I also put a folder named "gameinfo" (there is this kind folder on every level of the game) which could maybe help you about "bones group" and characters, but i dont know.   

.Rar file: [https://www.mediafire.com/file/ynskgdh6 ... s.rar/file](https://www.mediafire.com/file/ynskgdh66s1h0ga/.BNM_Animation_Files.rar/file)

I also assume a lot that the .bnm animation files before being imported into the game engine have been converted with the Slayer Engine properties.   
__________________________________________________________________________________________________________________________
PS: "Star Wars: Ep III - RotS" have MAYBE the same kind of animation file as "Indiana jones and the emperor's tomb"
Indiana Jones have .boneanmi files:
[https://www.computerhilfen.de/hilfen-11-342367-0.html](https://www.computerhilfen.de/hilfen-11-342367-0.html)
I know that "Indiana jones and the emperor's tomb" and "Reveneg of the sith" were Published by LucasArt and Developped by The Collective, and we find the same name in .pak file which contains all game assets.
And about Indiana jones animation files, i have just these words: BoneAnim -----> AnimationAEIP
__________________________________________________________________________________________________________________________

I also give 3d models/bones skeleton from "Star Wars: Ep III - RotS" same level of the .bnm animation samples, with 2 extensions: original .msh and .fbx (converted .fbx by Bigchillghost script, with Noesis, thanks to him)

.Rar file: [http://www.mediafire.com/file/hgx6nbrrg ... X.rar/file](http://www.mediafire.com/file/hgx6nbrrgiv0cxf/3D+Models+-+MSH+-+FBX.rar/file)

Thank you! 

edited topic december
## Post #2
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-12-06T18:40:55+00:00
- Post Title: Animation files .BNM Star Wars: Ep III - RotS (2005) [XBOX]

If anyone's curious, here are my (very rudimentary) notes on the format:

```

Data ends at "77 BC"

Value "80" is *always* at offset 2C, regardless of skeleton or specific animation.

"41" always at offset 23

"C1" *usually* at offset 22 - again this is only *usually* true, and is not related to skeleton or file size. First discovered inconsistencies on Anakin.

Offset 21 is similar to above - seems to be *mostly* consistent, but only in the same skeleton. First discovered inconsistencies on Anakin.

Dooku's animations consistently have value "21" at offset 21. R2D2's have "F0" at the same location, Anakin's seem to be inconsistent.

Dooku's animations consistently have value "2E" at offset 28. R2D2's have "10" at the same location, and Anakin "30".

Possible frame count at offset A5. Scales consistently (but not linearly) with file size.

R2D2 Bones: ~6 - counted manually and quickly.

"Human" bones: ~28 - seems to be a simple skeleton with three finger bones per hand. Counted manually and quickly.

Multiple files with the same skeleton and frame count do not always have the same length. Presumably, unused bones are not stored by animations.
```


I wish as much as you do that my notes were more useful (I'd just write the converter myself if I could find where each keyframe begins and ends), but it should be a start.
## Post #3
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2021-02-22T07:20:02+00:00
- Post Title: Animation files .BNM Star Wars: Ep III - RotS (2005) [XBOX]

Just revisited the format - my notes are now considerably less useless, and have been moved into a .bt (binary template) file for 010 Editor.

Here are the contents of the .bt (ASCII):

```
{
    //EXPECTED DATA:
    //Frame number (1 value) (2-4 bytes, unsigned)
    //Rotation (3 values) (float32)

    //POTENTIAL DATA:
    //Location (3 values)

    //More information on skeleton setup here: https://forum.xentax.com/viewtopic.php?p=163558#p163558

    //Correlates very closely to per-bone data size, is not frame count.
    //Frequently identical to length between two unknown1s (including self), but often off by 1-2 bytes.
    int unknownint <bgcolor=cGreen>;

    //Does not have any correlation with per-bone data size. Can have non-0/1 values.
    short unknownshort <bgcolor=cDkBlue>;
    short unknownshort <bgcolor=cBlue>;
    
    //The only difference between the PS2 and Xbox versions of the .bnm format are the values in this space,
    //which appears only once per bone. Everything else is identical.
    //This first value varies from bone-to-bone
    byte consolespecifica <bgcolor=cRed>;
    //This second value varies only from file-to-file.
    byte consolespecificb[3] <bgcolor=cRed>;



    //Shortest possible per-bone data (including first "unknownint") is 32 bytes. This can be assumed to be a single frame.
    //Second smallest observed is 36 bytes, four bytes larger than the smallest. This is not large enough to contain an entire frame of data.

    //NEITHER rotations NOR frame numbers are stored as single bytes.
    //A byte caps out at 255 which is less than 360 degrees, making them unsuitable for rotations
    //and not enough for longer anims.
};

//Read the header and declare the bonedata.
typedef struct bnmFile
{
    struct bnmHeader
    {
        //Name of the file. Sort of redundant, but it's there.
        char filename[32]<bgcolor=cBlue>;

        FSkip(8);
        int bonecount<bgcolor=cDkBlue>;
        
        FSkip(80);
        int boneoffsets[bonecount]<bgcolor=cYellow>;
    } header;

    struct bnmData
    {
        local int i;
        for (i=0; i < header.bonecount; i++)
        {
            //The following will be added to each offset described in boneoffsets
            //Goes back four before the offset due to "unknownint"
            FSeek(header.boneoffsets[i] - 4);
            bnmBonedata bonedata;
        };
    } data;
};

bnmFile file;
```
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-02-26T14:34:17+00:00
- Post Title: Animation files .BNM Star Wars: Ep III - RotS (2005) [XBOX]

Oh man i cant wait!!!!
Marc Eckos Getting Up is using the same animation file Formats (Slayer Engine).
So the info should be the same....unless they Made some minor Updates to the Format.
## Post #5
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2021-02-26T22:40:55+00:00
- Post Title: Animation files .BNM Star Wars: Ep III - RotS (2005) [XBOX]

i'm still learning reverse engineering and I'm still excited
## Post #6
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2021-02-26T22:43:49+00:00
- Post Title: Animation files .BNM Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from Henchman800 ↑Fri Feb 26, 2021 10:34 pm at Fri Feb 26, 2021 10:34 pm
>
> 
Oh man i cant wait!!!!
Marc Eckos Getting Up is using the same animation file Formats (Slayer Engine).
So the info should be the same....unless they Made some minor Updates to the Format.

From what little I looked into it, the format changes are more than minor - at the very least, I couldn't find the bone offset table for Getting Up while it was fairly easy to find in ROTS.
## Post #7
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-02-28T06:17:49+00:00
- Post Title: Animation files .BNM Star Wars: Ep III - RotS (2005) [XBOX]

Oh shoot :-/
I was hoping the house kept the same method for the early slayer games. Thanks for taking a look though
