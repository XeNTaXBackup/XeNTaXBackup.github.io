## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-10-14T06:28:46+00:00
- Post Title: Fairy Fencer F TID Texture

They got the same format for neptunia mk2 texture but howfie batch didn't work for most of it.
can anyone make a batch or a noesis script?because i don't know how to make one.  

here is sample
[http://www.mediafire.com/download/f3dur ... 31/001.zip](http://www.mediafire.com/download/f3durctfbb6x631/001.zip)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-15T07:09:14+00:00
- Post Title: Fairy Fencer F TID Texture

Ok here is the structure

```


struct tidHeader {

int24 HeaderMAGIC = TID
int8  IdentifierA = 145
int16 FlagA
int16 FlagB
int16 Padding
int16 IdentifierB = 32768
int32 Unknown1 = 1
int32 Unknown2 = 1
int32 Unknown3 
int32 Unknown4 
int32 Unknown5
asciiz textureName
int32 Unknown6 = 96
int32 Width 
int32 Height

0x100 = TextureMagicType (DX1/DX3/DX5)
}

```


Ill write you a quick tool soon
## Post #3
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-10-15T09:18:01+00:00
- Post Title: Fairy Fencer F TID Texture

thank you so much
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-15T09:25:00+00:00
- Post Title: Fairy Fencer F TID Texture

Your tool

(attached)
[Fairy Fencer F TID Texture Tool.zip](https://xentaxbackup.github.io/file/6700_Fairy Fencer F TID Texture Tool.zip)
## Post #5
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-10-15T09:28:03+00:00
- Post Title: Fairy Fencer F TID Texture

Thank you so much!
