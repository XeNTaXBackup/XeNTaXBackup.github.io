## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-11-13T04:32:09+00:00
- Post Title: Soul Calibur 1-6 .mot animation file

It appears as though every soul calibur game has shared the same animation file format (ios, ps2, pc...)

I have been able to extract individual entries from the .mot archive
But i havent been able to make sense of the entries


.mot

```
int idType[2]<hidden=true>;
if(idType[1] == 0) //SC6
{
    FSeek(0);
    int64 count;
}
else //==2 SC3
{
    FSeek(0);
    int count;
    int unkn;
}


int offset[count]<bgcolor=cLtGreen>;
typedef struct(int size)
{
    byte data[size];
}Data<optimize=false>;

local int i = 0;
local int size = 0;
local int id = 0;
local int minID = 0;
local int maxID = 0;
local int minSize = 9999999;
local int maxSize = -9999999;
for(i = 0; i < count; i++)
{
    FSeek(offset[i]);
    if(i == count-1)
        size = FileSize() - offset[i];
    else
        size = offset[i+1] - offset[i];

    if( i%2)
        SetBackColor(cLtRed);
    else
        SetBackColor(cLtBlue);

    if(size == 0)
        continue;

    if(size < minSize)
    {
        minSize = size;
        minID = id;
    }
    
    if(size > maxSize)
    {
        maxSize = size;
        maxID = id;
    }


    Data data(size)<optimize=false>;
    id++;
}

SetBackColor(cNone);
Printf("Min: [%d] %d Max: [%d] %d  -> Count: %d\n", minID, minSize, maxID, maxSize, id);


```

MOTION Entry

```
short size; //mostly varies with size
short flagA, flagB; //flag a is not a size

byte pad0[3]; //fffff

short count0;
short count1;
short count2;
short count3;

byte pad1[8];
byte pad2;

if(flagA == 0)
{

}
else
{
    int count;

}

```

[Mitsu-Moveset.zip](https://xentaxbackup.github.io/file/15169_Mitsu-Moveset.zip)
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-02-20T06:27:05+00:00
- Post Title: Soul Calibur 1-6 .mot animation file

Kinda sad. No progress
## Post #3
- Username: zsjcoral
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Dec 13, 2021 6:15 pm
- Post datetime: 2023-05-05T08:35:41+00:00
- Post Title: Soul Calibur 1-6 .mot animation file

Can no one conquer this difficult problem??
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-05-05T12:19:38+00:00
- Post Title: Soul Calibur 1-6 .mot animation file

> Reply from zsjcoral ↑Fri May 05, 2023 4:35 pm at Fri May 05, 2023 4:35 pm
>
> 
Can no one conquer this difficult problem??It simply doesn't work this way: jumping into a format trying to get animations.
It should start with the skeleton. If you don't nothing will happen. In my experience, at least.

I don't have any overview of the different Soul Calibur versions.

SC3 format seems to be a little bit complex so I dunno whether it's a good idea to start with:

> Reply from zaramot ↑Tue Sep 16, 2014 10:46 pm at Tue Sep 16, 2014 10:46 pm
>
> 
(Leap in time, 5 and a half years later  )

> Reply from mariokart64n ↑Sat Apr 18, 2020 12:04 am at Sat Apr 18, 2020 12:04 am
>
> 

At least you find "skeleton" in the block diagram and, more important, a skeleton section in the appended maxscript:
(see		-- Construct Skeleton)
## Post #5
- Username: zsjcoral
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Dec 13, 2021 6:15 pm
- Post datetime: 2023-05-11T14:15:22+00:00
- Post Title: Soul Calibur 1-6 .mot animation file

I really hope someone can conquer their MOT animation format, I really like their actions
## Post #6
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2023-05-11T22:03:08+00:00
- Post Title: Soul Calibur 1-6 .mot animation file

Probably not. More than Tekken, SC, especially SC2, has been modded for years, but no one has been able to analyze the mot about it.
This is despite the fact that there are modders who can port data from other models to other models and do complete endian flips.
In short, while some people have a complete understanding of the file structure itself, no one understands how it is actually parsed as animation data and assigned to bones.

The most practical way is to get the coordinates and angles from the actual 3D data being drawn to get the animation frame data, 
as I and sadamitsu from Tekken modder do. It is primitive and forceful, but reliable.
## Post #7
- Username: zsjcoral
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Dec 13, 2021 6:15 pm
- Post datetime: 2023-05-12T15:06:44+00:00
- Post Title: Soul Calibur 1-6 .mot animation file

Unfortunately, the MOT animation files of tekken cannot be obtained or modified either
