## Post #1
- Username: ali1560
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 11, 2020 8:20 am
- Post datetime: 2020-11-11T00:28:43+00:00
- Post Title: A plague of tale : innocence localization

Hi there... GT
I wanted to translate this game into my language  (arabic or persian)...I found the subtitle files ( it was easily editable by notepad) I rewrite it in persian
but in the game it looks like this picture

What should I do right now?
I think it has something to do with the file in the font folder (ENGLISH.DPC) and maybe I must replace a persian font instead of that btw
is there any body here who can help me to extract this file and change the font too?
[photo_2020-11-11_02-43-37.jpg](https://xentaxbackup.github.io/file/19011_photo_2020-11-11_02-43-37.jpg)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-11T10:41:06+00:00
- Post Title: A plague of tale : innocence localization

You need to edit font to translate the game. You should edit file FONT.DPC
and  when there is no such archive, then you should edit ENGLISH.DPC or any archive with font.

DPC archives have been researched by me lately and you can find all info here
[http://wiki.xentax.com/index.php/Asobo_Studio_DPC_DPS](http://wiki.xentax.com/index.php/Asobo_Studio_DPC_DPS)

But sadly, for now there are no many tools supporting these archives
You can see my tool here 
[https://github.com/bartlomiejduda/Tools ... PS_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Asobo%20Studio%20DPC%20DPS%20Research/Asobo_DPC_DPS_Tool.py)
but I think that my tool tool won't work, because in A Plague Tale: Innocence compression seems to be different.
Also file format could be slightly different in version 2.128.92.19.
## Post #3
- Username: ali1560
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 11, 2020 8:20 am
- Post datetime: 2020-11-11T12:36:23+00:00
- Post Title: A plague of tale : innocence localization

Aha....I'll check it out
and thanks for your help
## Post #4
- Username: gameside
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 07, 2020 6:21 am
- Post datetime: 2020-11-14T15:16:07+00:00
- Post Title: A plague of tale : innocence localization

Can You upload FONT.DPC or ENGLISH.DPC?
i want to check them
## Post #5
- Username: mrmemmo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 25, 2019 5:44 pm
- Post datetime: 2020-11-18T04:23:00+00:00
- Post Title: A plague of tale : innocence localization

//------------------------------------------------
//--- 010 Editor v10.0.2 Binary Template
//
//      File: 
//   Authors: 
//   Version: 
//   Purpose: 
//  Category: 
// File Mask: 
//  ID Bytes: 
//   History: 
//------------------------------------------------
FSeek(260);
int none1;
int64 none2;
FSkip(16);
int64 none3;
FSkip(8);
int64 lengthz;
int64 lengthu;
FSkip(8);
int num;
FSkip(3764);
typedef struct{
    byte Magic[8];
    uint64 ID;
    int unk;
    int ck;
    if(Magic[0] == 0 && Magic[1] == 0)
    {
        BreakStream( FTell() - 24);
    }
    else if (Magic[4] == 0 && Magic[5] == 0)
    {
        FSkip(2048 - 24);
    }
    else if (ck == 0)
    {
        FSkip(1496 - 24);
        int none4;
        FSkip(none4 * 36);
        BreakStream(FTell() - 24);
    }
    else
    {
        local char texture[8] = {
        0x6D, 0x32, 0xF3, 0xC3, 0xD1, 0x9C, 0x65, 0xE9 
        };
        int blockleng;
        int h_blockleng;
        int unleng;
        int l4;
        int64 l5;
        uint64 hash2;

        if(Magic == texture)
        {
            byte array[blockleng];
            BreakStream(FTell() - 8 );
            //Printf("ok");
        }
        else
        {
            byte array[blockleng];
            FSkip(-8);
        }
    }
    /**/
    //local int c = FTell() - 8;
    //Printf("%d",Magic[1]);
} DPCSTRUCT;
DPCSTRUCT dcpstruct[num + 2] <optimize=false>;

void BreakStream (int f)
{
    local int por = f % 2048;
    local int go = 2048 - por + f;
    FSeek(go);
}
## Post #6
- Username: mrmemmo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 25, 2019 5:44 pm
- Post datetime: 2020-11-18T04:40:33+00:00
- Post Title: A plague of tale : innocence localization

just help me repack dpc. i can unpack it, edit bottom( mapping font) but can't inject texture to middle, game can't show text because something wrong. there are some places in the file that I do not know how to function but i have no time find it.
## Post #7
- Username: LazyCat2k3
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 26, 2020 1:03 am
- Post datetime: 2020-11-20T16:01:01+00:00
- Post Title: A plague of tale : innocence localization

It's LZ4.
Try compressing the unpacked file with a smaller size, fill the padding with null and edit some size references.
