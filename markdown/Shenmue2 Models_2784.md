## Post #1
- Username: jwrayth
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 13, 2007 1:15 am
- Post datetime: 2007-09-13T09:22:20+00:00
- Post Title: Shenmue/2 Models

Sorry, realised I posted this in the wrong forum >_<

Basically, I was wondering if anyone has any interest in ripping hte models from the game Shenmue, for the Sega Dreamcast.

I've done some examination of the format (MT5 for Shenmue 1, MT7 for Shenmue 2). 

The Texture Data is stored at the end of the file, and is relativly easy to rip (as has been done before). Otherwise, I'm a bit lost as to analysing the files.

I've hosted two MT7 files on my website, for you guys to take a look 

[http://www.ninja-penguin.com/RYO_B.MT7](http://www.ninja-penguin.com/RYO_B.MT7)
[http://www.ninja-penguin.com/RYO_M.MT7](http://www.ninja-penguin.com/RYO_M.MT7)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-13T22:31:39+00:00
- Post Title: Shenmue/2 Models

I am always looking for someone interested in console game who would like to share, so let me start my findings first:

The format looks like a tag/section based. the first tag/section is:

```
dword       sizeMDC7       //size of this section
dword       ofs_1             //offset of ??
dword       nTex

struct TextureData {
 word        nTexW
 word        nTexH
 word        ??
 word        ?? 
 dword      ofsSize
 dword      nIdx
} TextureData[nTex]

struct UknTexData {
 dword      ??
 dword      ??
} UknTexData[nTex]

dword       nData
struct UknData {
 dword      ofsData          //No sure if they are offset
} UknData[nData]

* Now should be in the location where ofs_1 pointing at!
0x40 bytes unknown
```


Then inside the section, there are many "MDC7"(sub section?)
"WVTX" should be the vertices data
"WEVL" looks like skin weight
## Post #3
- Username: jwrayth
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 13, 2007 1:15 am
- Post datetime: 2007-09-14T08:35:02+00:00
- Post Title: Shenmue/2 Models

Thats really nice work  I wasn't expecting a response so fast! I'll have to get some time over the weekend to follow up with this some more.
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-14T22:08:08+00:00
- Post Title: Shenmue/2 Models

Yet more findings for the following "MDC7" section:

```
float X16     matrix4X4     //typical transformation data

* dword      uknCount1      //if this one is zero, an extra 0x00000000 follow
struct uknData1 {
  dword      ??
  dword      ??
} uknData1[uknCount1]

* Sometime another sub-section start here, like WVTX etc
or:
dword        uknCount2
struct uknData2 {
  dword       ??
  float X 7   ??                 //This 7 float look like posXYZ and quatXYZW
} uknData2[uknCount2]

* Sometime another sub-section start here as well
or:
dword         ??

float X 3     ??                 // \ 
float X 3     ??                 //  This 3 sets of float look like colorRGB data? 
float X 3     ??                 // / 
dword X 6     ??

```


So I guess each MDC7 section is actually an object, maybe a dummy object for hit point, special effects etc
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-09-15T02:51:49+00:00
- Post Title: Shenmue/2 Models

wow, fatduck, your really good at this stuff.    have you taken a look into any xbox360 model files, they primarily use triangle strips.
