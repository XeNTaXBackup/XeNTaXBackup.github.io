## Post #1
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2015-05-17T22:16:25+00:00
- Post Title: Doom 3: BFG Edition

Hi, I need help with this file, which comes from Doom 3: BFG Edition /id Tech 5. I'd like to open this file in Ps, but don't know the settings of RAW.

[https://docs.google.com/file/d/0B4krCHc ... pxTHM/edit](https://docs.google.com/file/d/0B4krCHcJalIcS3YzbjhJSWpxTHM/edit)

Thanks
## Post #2
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2015-05-19T23:36:38+00:00
- Post Title: Doom 3: BFG Edition

Solved! But i want to say everyone how to do. It's simple for now. File header is 56 bytes and everything is in BE.

SignedInt[1]=zeroes;
SignedInt[2]=magic;
SignedInt[3]=magic;
SignedInt[4]=hell knows; maybe layer count;
SignedInt[5]=hell knows;
SignedInt[6]=hell knows; maybe chanels;
SignedInt[7]=y offset;
SignedInt[8]=x offset;
SignedInt[9]=hell knows;
SignedInt64=bunch of zeroes;
SignedInt[10]=hell knows; looks like again y offset;
SignedInt[11]=hell knows; looks like again x offset;
SignedInt[12]=hell knows; maybe comp size;

How to convert this BIMAGE files into the DDS. 
First create DDS with same size as BIMAGE "check from header" and save it with DXT1 compression. 
Then open created DDS in HEX editor and copy 128 bytes of DDS header into the BIMAGE and replace 56 bytes of BIMAGE header and save as DDS.

That's all and I hope it helps. This tutorial is pointed on fonts files.

Result:
## Post #3
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2015-05-24T10:33:00+00:00
- Post Title: Doom 3: BFG Edition

Ok, so far I got the fonts from the BIMAGE file, but don't know the exact number of mipmaps used by the file. Does anyone know how to find out?

Thanks alot
