## Post #1
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2017-11-09T20:36:27+00:00
- Post Title: Game Engines Filetypes Reverse Engineering

Since a while I am keen on trying to use game files somewhere outside of the game. While most of the formats are unique per game engine, for less popular or new games there is a necessity to write your own format parser. This can be very exhausting when working alone, especially for those who are not very familiar with format subject. It would be great if several people could collaborate on parsing particular file type. For this purpose I've create GitHub repository to gather information about different file format used by different games. There is not much info there yet, but I really do hope people will contribute.

Repository: [https://github.com/lOlbas/Game-Engines- ... ngineering](https://github.com/lOlbas/Game-Engines-Filetypes-Reverse-Engineering)

Please, refer to the README file for more information.
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-11-10T11:15:28+00:00
- Post Title: Game Engines Filetypes Reverse Engineering

Uh-oh, I don't think storing samples aswell is a great idea, they are copyrighted material.
IF your github gets bigger overtime, then having all those sample files from different games can be dangerous.
If you have script then why do you have samples?
When end user needs, then he will download only template/script, he don't need sample files since he already have extracted files, he needs.
## Post #3
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2017-11-10T11:34:11+00:00
- Post Title: Game Engines Filetypes Reverse Engineering

> Reply from PredatorCZ
>
> they are copyrighted material
Good point, haven't thought of that.

> Reply from PredatorCZ
>
> If you have script then why do you have samples?
Well... For templates and scripts development it might be good to be able to store samples somewhere just like scripts itself. Also, for those who are just curious to RE, they might not be aware of where to get those files. Another good point is to add a list of games which contain this or that file.
## Post #4
- Username: voidapex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 20, 2017 12:58 am
- Post datetime: 2017-11-20T13:56:22+00:00
- Post Title: Game Engines Filetypes Reverse Engineering

Hello,

i'm new to reversing game engine models.
i've tried to reverse the ".smd" data file of the game Path of Exile, but it cannot get it to extract all information properly.
I've also tried to export it through noesis plugin "fmt_PoE_sm.py", but it fails to encode the meshdata bytearray.

i would really appreciate it if any of the xentax community professionals could take a look on these files.



I have zipped the files and uploaded it to my webspace.

[PoEMonsterVoll.zip](https://tinyurl.com/poemodel-monster-voll)


here is the 010 template for the .smd data structure (not created by me, not final and does not fully work)

```
    wchar_t data[size/2];
} STRING_BLOCK <read=ReadBlockBytes>;

string ReadBlockBytes(STRING_BLOCK &block) {
    local string s;
    SPrintf(s, "%s",  block.data);
    return s;
};

struct FILE {
    struct HEADER{
        byte version <format=hex>;
        uint numIdx;
        uint numVert;
        byte prop_0;
        byte numMeshes;
        byte prop_2;
        uint totalStringLength;
        float boundingBox[6];
        struct MESH {
            uint meshNameLen;
            uint meshUnkProp;
        } mesh[numMeshes];
    } header;

    struct STRINGS {
        local int i <hidden=true>;
        for ( i = 0 ; i < header.numMeshes; i++ )
        {
            STRING_BLOCK data(header.mesh[i].meshNameLen) <open=suppress>;
        }
    } strings;
    
    ushort indexBuffer[header.numIdx * 3];  

    struct VERTEX{
        float x <bgcolor=0xC0F0C0>, y <bgcolor=0xC0F0C0>, z <bgcolor=0xC0F0C0>;
        byte unk0[8];
        hfloat u <bgcolor=0xA0D0A0>,v <bgcolor=0xA0D0A0>; 
        byte boneIndex[4] <bgcolor=0xF0D0A0>;
        byte unk1[4] <bgcolor=0xA0D0F0>; 
    } vertex[header.numVert];

} file;
```


Regards
