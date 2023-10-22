## Post #1
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-11-01T11:24:58+00:00
- Post Title: Hellgate London Model format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-11-18T16:13:34+00:00
- Post Title: Hellgate London Model format

I should post these long time ago, since my computer crashed sometime ago and I have never finish the format yet. That is! The format below had not finished! But should be able to rip the model manually!

```
dword        header      //always 0xCAFE1515
dword        ver         //??
dword        ??          //always 1
dword        nTableCount    
struct geoTable {
  dword      nType     //2=faces section, 5=vertices, 6=??
  dword      ofsStar    //*not so correction in type 5 and 6??
  dword      ofsSize
} geoTable[nTableCount]
dword      
dword      
dword      
dword      
dword      
dword
```


```
dword        ??          //always -1
dword        ofsFaces    //size of face data
byte X 12    ??          //always 0 (pad)
struct Face {
  word X 3   FaceIndex
} Face[ofsFaces/6]
dword
dword
word         
dword
dword
dword
dword        tLen1       //Length of texture name 1
char[tLen1]  TexName1
dword        tLen2       //Length of texture name 2
char[tLen2]  TexName2
dword
dword
dword
dword
dword        tLen3       //Length of texture name 3
char[tLen3]  TexName3
word
float X 3    col1
float X 3    col2
float X 3    col3
dword X 6
```


```
dword        ??           //-1
dword        ofsUkn1      //size of Unknown data in bytes
struct UknData1 {
  float 
} UknData1[ofsUkn1/4]
dword        ofsUkn2      //size of Unknown data in bytes
struct UknData2 {
  byte       ?? 
} UknData1[ofsUkn2]
*dword                    //only when ofsUkn2 > 0
dword        nVerts       //vert count
dword
dword
dword
dword
dword        ofsVerts     //Size of Vertices in bytes
struct Vert {
  float X 3  poxXYZ 
} Vert[nVerts]
```
## Post #3
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-11-20T13:05:33+00:00
- Post Title: Hellgate London Model format

Nice thx. Now it is possible to write an converter.
## Post #4
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2010-04-11T21:34:52+00:00
- Post Title: Hellgate London Model format

sorry for such a massive necro. I'm just curious, did anyone have any success of getting the files into something normal with the information contained here?
## Post #5
- Username: YourPackage
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 09, 2008 6:35 am
- Post datetime: 2010-09-05T04:46:39+00:00
- Post Title: Hellgate London Model format

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: greywaste
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 30, 2010 5:10 am
- Post datetime: 2010-09-05T22:25:21+00:00
- Post Title: Hellgate London Model format

*begs for someone to take a look at these*
