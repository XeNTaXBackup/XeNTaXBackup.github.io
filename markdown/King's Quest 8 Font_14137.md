## Post #1
- Username: wiaparker
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 20, 2014 11:31 pm
- Post datetime: 2016-03-24T20:20:04+00:00
- Post Title: King's Quest 8 Font

Hello, 

I'm currently working on polish translation of the computer game King's Quest VIII. I ask you for help, because I have a problem with opening and editing fonts that I put below. I would be grateful for help. 
[KQ8_font.zip](https://xentaxbackup.github.io/file/10628_KQ8_font.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-02T18:08:24+00:00
- Post Title: King's Quest 8 Font

i spent a bit of time on this.


do you want to make your own fonts? or add new glyphs? there is a fixed table of 256 ascii mappings which you could use for patch new glyphs.

(const32 is just an int) 

```

struct Unk
{
  ubyte Index;
  ubyte unknown;
  ubyte flags; // 0x2e?
  ubyte unknown_2;

  Const32 e(EQ, 0x2e);
};

struct Font(int max)
{
  local int pos = FTell();
  Const32 a(EQ, 2);
  Const32 b(EQ, 65);
  Const32 c(EQ, 0);

  uint MappedItemCount;

  uint aa, bb; // aa>=bb

  Const32 another(EQ, 255);
  Const32 z(EQ, 0);

  uint cc;

  Const32 d(EQ, 65536);
  Const32 e(EQ, 65536);
  Const32 f(EQ, 0);
  
  uint MapSize;

  short map[MapSize]; // -1 is unmapped


  Unk mapped[MappedItemCount] <optimize=false>;

  struct CH
  {
    char Name[4]; uint unknown; // not size!
  };

  CH test;
  
while((FTell()-pos) < max)
{
  Chunk blah;
}

  ubyte Data[max - (FTell()-pos)];
};

struct Chunk
{
  char Name[4]; // can be none

  if( Name[0] == 0 ) Exit(0);
  uint Size;

  if(Name == "PFON")
  {
     Font Data(Size);
  }
  else if(Name == "PBMA")
  {
     // head/data
     ubyte Data[Size];
  }
  else if(Name == "DETL")
  {
    // ??
ubyte Data[Size];
  }
  else if(Name == "PBMP")
  {
    // nothing this size is incorrect
  }
  else 
  { 
    ubyte Data[Size];
  }
};

while(!FEof())
{
  Chunk chunk;
}

```
## Post #3
- Username: wiaparker
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 20, 2014 11:31 pm
- Post datetime: 2017-02-12T19:57:52+00:00
- Post Title: King's Quest 8 Font

I would like to patch existing glyphs. Can anyone help?
