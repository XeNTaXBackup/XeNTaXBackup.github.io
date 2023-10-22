## Post #1
- Username: oyunceviri
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-05-19T15:25:45+00:00
- Post Title: Resident Evil Revelation

Hi wo is interested here is completed template script for RER in 010  XBOX 360 Version of course 

Currently doing Repacker for GMD files.....


```
//--- 010 Editor v4.0.3 Binary Template[X360]
//
// File: Texts_GMD.bt []
// Author: michalss
// Revision: 1.0
// Purpose: Revers Texts
//--------------------------------------

BigEndian();

local int CEntry,CTexts;
local int x,pos,base,base2,zal,posss,rec,cnt;
local int Entry,Texts;
local string text,text2;

char dmg[4];
uint version;
uint langID;
PrintLang(langID);
uint zero; 
uint GUID;
uint count1;
cnt=count1;
uint count2;

uint SizeOfIDSEntry;
Entry=SizeOfIDSEntry;
uint SizeOfTEXTSEntry;
Texts=SizeOfTEXTSEntry;

uint FileNameSize;
char FileName[FileNameSize+1];

base=36+FileNameSize+5+count1*8;
base2=36+FileNameSize+5+count1*8;

if (version == 66049) {

for (x=0;x<count1;x++) {
    
    struct String {
        uint CountID <bgcolor=0x0000FF>; 
        uint Offset <bgcolor=cPurple>;
        zal=FTell();
        FSeek(base);
        text=ReadString(FTell());
        char textID[Strlen(text)+1] <bgcolor=cYellow>;  
        base+=Strlen(text)+1;
        CEntry+=Strlen(text)+1;
      
               FSeek(base2+Entry);
               text2=ReadString(base2+Entry);
               base2+=Strlen(text2)+1;
               CTexts+=Strlen(text2)+1;
               char textString[Strlen(text2)+1] <bgcolor=cGreen>;  
     
        rec+=1;        
        FSeek(zal);
    } DATA;
}

Printf("Should be record : %i\nReal is : %i \n\n",cnt,rec);

Printf("Size of Enty IDS : %i\nSize of Texts : %i \n\n",CEntry,CTexts);

if (cnt == rec) Printf("File is pharsed Correctly!!\n");
if (CEntry == Entry) Printf("Size of entry is Correct!!\n");
if (CTexts == Texts) Printf("Size of Text is Correct!!\n\n");

} else {
    Printf("Unknow version, cannot continue!!");
}


void PrintLang(int ID) {

    switch(ID) {
    
        case 0: Printf("Lang Mutation is : JAP\n"); break;
        case 1: Printf("Lang Mutation is : ENG\n"); break;
        case 12: Printf("Lang Mutation is : HOL\n"); break;
        case 2: Printf("Lang Mutation is : FRE\n"); break;
        case 4: Printf("Lang Mutation is : GER\n"); break;
        case 5: Printf("Lang Mutation is : ITA\n"); break;
        case 11: Printf("Lang Mutation is : POL\n"); break;
        case 9: Printf("Lang Mutation is : POR\n"); break;
        case 10: Printf("Lang Mutation is : RUS\n"); break;
        case 3: Printf("Lang Mutation is : SPA\n"); break;
        case 21: Printf("Lang Mutation is : PTB\n"); break;
    }

}



```
## Post #2
- Username: Scofield
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jul 13, 2014 5:27 am
- Post datetime: 2014-12-17T10:43:10+00:00
- Post Title: Resident Evil Revelation

Hi michalss,

I sent you a private message.

You please read.

Thanks.
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-17T18:41:55+00:00
- Post Title: Resident Evil Revelation

Tools here : 
```
https://dl.dropboxusercontent.com/u/38234344/X360_Tools.rar
```


You dont not need to keep same size of strings
## Post #4
- Username: Scofield
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jul 13, 2014 5:27 am
- Post datetime: 2014-12-17T19:00:17+00:00
- Post Title: Resident Evil Revelation

> Reply from michalss
>
> Tools here : Code: Select allhttps://dl.dropboxusercontent.com/u/38234344/X360_Tools.rar

You dont not need to keep same size of strings

Thanks. Michalss

How to do back packing ?
## Post #5
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-01-22T13:00:57+00:00
- Post Title: Resident Evil Revelation

I sent pm message for you! Thanks!
