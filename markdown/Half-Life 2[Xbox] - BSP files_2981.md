## Post #1
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-03-23T21:06:14+00:00
- Post Title: Half-Life 2[Xbox] - BSP files

Well I have been looking at these BSP files from half-life 2 for xbox. Heres what I got:

The files are composed of blocks. Each block has its offset and size in the header, and are spaced 8 bytes per block.

```
{
     public const string VBSP; //0
     public const int EngineVersion; //4 - 19
     public int EntityTableOffset; //8
     public int EntityTableSize; //12
     public long Null; //16
     public int UnknownBlockOffset; //24
     public int UnknownBlockSize; //28
     public long Null; //32
     public int CoordinateBlockOffset; //40
     public int CoordinateBlockSize; //44
     public long Null; //48
     public int UnknownIndexOffset; //56
     public int UnknownIndexSize; //60
     public long Null; // 64
     public int UnknownIndexOffset; //72
     public int UnknownIndexSize; //76
     public long Null; //80
     public int UnknownTableOffset; //88
     public int UnknownTableSize; //92
     public long Null; //96
     public int UnknownMetaTableOffset; //104
     public int UnknownMetaTableSize; //108
     public long Null; //112
     public int PointerBlockOffset; //120
     public int PointerBlockSize; //124
     public long Null; //128
     //Blocks I havent mapped yet
     public int PhysicsBlockOffset; //424
     public int PhysicsBlockSize; //428
     public long Null; //432
     //More Blocks I havent mapped
     public int MaterialTableOffset; //696
     public int MaterialTableSize; //700
     public long Null; //704
     public int MaterialTableIndexOffset; //712
     public int MaterialTableIndexSize; //716
     public long Null; //720
     //A cuple more Blocks I havent Mapped
}
```


```
{
     public float X;
     public float Y;
     public float Z;
     public int Ident; 
}
```


```
{
     public int Unknown1;
     public int Unknown2;
     public int Unknown3;
}
```


```
{
     public int Unknown;
}
```


```
{
     public int Unknown1;
     public int Unknown2;
     public int Unknown3;
}

public class PointerBlock
{
     public int Ident1;
     public int Unknown1;
     public int Ident2;
     public int Unknown2; //Size of something?
     public int Unknown3; //Count of something
     public int Ident3;
     public int Identifier; //Increasment by 1
     public long Unused; //Null
     public int Identifier; //Increasment by 9
     public int Unknown5;
}
```


Im gunna take a break for an hour and go skate, but when I come back I'll map more blocks.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-03-27T15:02:43+00:00
- Post Title: Half-Life 2[Xbox] - BSP files

[Why are you researching a documented format?](http://www.geocities.com/cofrdrbob/bspformat.html)
## Post #3
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-03-27T19:18:54+00:00
- Post Title: Half-Life 2[Xbox] - BSP files

Dident know that. You ruined my fun lol
