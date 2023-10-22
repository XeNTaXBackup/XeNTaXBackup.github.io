## Post #1
- Username: nmdpkvs
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 29, 2017 2:09 pm
- Post datetime: 2017-11-09T12:20:10+00:00
- Post Title: 010 Editor Binary Template Need help

I do not know how to write the following change. Request help to complete
Length 36
Loop 109

//------------------------------------------------
//--- 010 Editor v8.0.1 Binary Template
//
//      File: fnt
//   Authors: 
//   Version: 
//   Purpose: 
//  Category: 
// File Mask: 
//  ID Bytes: 
//   History: 
//------------------------------------------------
LittleEndian();
typedef struct
{
   int ucode;
   SetBackColor(cLtRed);
   float x;
   SetBackColor(cLtBlue);
   float y;
   SetBackColor(0xA020F0);
   float w;
   SetBackColor(0x9BCD9B);
   float h;
   SetBackColor(0xEEEE00);
   float u1;
   float u2;
   float u3;
   float u4;
}block;
SetBackColor(0x112266);
char uni(0xA8);
int empty;
SetBackColor(0x0000ff);
int num;
block b[num];
char uni2[320];
SetBackColor(0xFF0066);
int ??;
block ;
char ??;
SetBackColor(0xFF33CC);
int ??;
block ??;
char ??;
[20171109202138.jpg](https://xentaxbackup.github.io/file/13536_20171109202138.jpg)
## Post #2
- Username: nmdpkvs
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 29, 2017 2:09 pm
- Post datetime: 2017-11-10T05:45:46+00:00
- Post Title: 010 Editor Binary Template Need help

Although didn't get help but I still finished own template, well, I made a little mistake, did not understand the grammar
//------------------------------------------------
//--- 010 Editor v7.0 Binary Template
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
LittleEndian();
typedef struct{
SetBackColor(cLtRed);
int ucode;
SetBackColor(cLtBlue);
float x;
SetBackColor(cLtGreen);
float y;
SetBackColor(0xA020F0);
float w;
SetBackColor(0x9BCD9B);
float h;
SetBackColor(0xEEEE00);
float page;
float xoffset;
float yoffset;
float chnl;
}block;

SetBackColor(0x112266);
char uni[0xA8];
int empty;
SetBackColor(0x0000ff);
int num;
block b[num];
char uni2[320];
[20171110134501.jpg](https://xentaxbackup.github.io/file/13539_20171110134501.jpg)
