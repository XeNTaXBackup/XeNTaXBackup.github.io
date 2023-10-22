## Post #1
- Username: nobanek
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 03, 2014 3:04 am
- Post datetime: 2015-01-03T09:06:06+00:00
- Post Title: Metal Gear Solid V: Ground Zeroes

Thanks to Sergeanur, who made tools to unpack/repack game files, it is no problem to get to game files.

Currently, I am translating this game. But here starts the problem. I can edit those files, but I have to keep same size of those files and same lenghts of sentences or words. That means, that I have to shorten words, that are longer in Czech than in English and put spaces after words that are shorter in Czech than in English. It is mostly no problem when translating a longer sentence, but some really short English words or sentences do not have Czech translation of the same lenght and shortening is really not a good thing for understanding the text.

If I would not keep the size of text (e.g. add 1 byte in one string and delete 1 byte in another), some texts would not show properly. 

Is there any way to solve this problem so I would not have to keep sizes?

I uploaded files with texts for menu and English subtitles.

```
https://www.dropbox.com/s/2qr0g3dz7amh73l/MGS%20xentax.rar?dl=0
```

Thanks for your help!
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-03T10:19:46+00:00
- Post Title: Metal Gear Solid V: Ground Zeroes

Use search : there is a repacker for .fpk already  But u still need repacker for *.subp files. I will have a look, but not sure when ...
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-03T10:52:51+00:00
- Post Title: Metal Gear Solid V: Ground Zeroes

```
//--- 010 Editor v5.0.2 Binary Template
//
// File:*.subp
// Author: michalss
// Revision: 2
// Purpose: 
//--------------------------------------

LittleEndian();

local uint x,pos,nextOff,done;

ushort sign;
ushort count;

struct IDs {
for (x=0;x<count;x++) {

  struct Data {
    uint id;      
    uint offset;

    if (count==x+1) {
        nextOff=FileSize();
        
    } else {
        nextOff=ReadUInt(FTell()+4);
    }    

    pos=FTell();
    FSeek(offset);

    struct Text { 
        uint stringID;
        ushort stringLenght1;
        ushort stringLenght2;
        done=nextOff-stringLenght1;

        FSeek(done);
        string text;

     } Block;
    FSeek(pos);
   
 }ID;

}

} Record;


```


WIP never had a tim to do complete investigation yet!!!
