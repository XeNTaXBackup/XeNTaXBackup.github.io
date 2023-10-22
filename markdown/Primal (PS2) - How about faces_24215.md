## Post #1
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-07-09T17:40:55+00:00
- Post Title: Primal (PS2) - How about faces?

HI, another day. Im trying to get models from topic name game, and i can't beat faces.

I  read on this forum PS2 games auto-generate faces, trying do that with @shakotay2 [code](https://forum.xentax.com/viewtopic.php?p=116369#p116369), and don't look right. Game data sometime have faces but it look strange for me like that:

```
           1 2 3
           ...etc
           10 12 13
           ...etc
           120 121 1022
          1221 1223 1224
           121 120 122
           123 124 125
           ...etc
```


Now try explain some, here is what i've using:
PRIMAL (PS2) NTSC USA (SCUS 97142)
CRC from PCSX2 FCD89DC3
for ISO
CRC32 5D7D80D0
SHA1  812E5DE188E91AC0D03CF51567BA88CE26F26BAC

ISO can be readed by HEX don't need unzip or something like scan for hide data.

Here a screenshot how looks vertices: [https://imgur.com/a/vDVUSsP](https://imgur.com/a/vDVUSsP)

Screnshot parameters:

```
      Ofs:     0x517974
      Count:   838
      Padding: 4
      Type:    Float

UVs            :
      Ofs:     0x5262a4
      Count:   986
      Padding: 0
      Type:    Float

Normals        :
      Ofs:     0x51ade4
      Count:   854
      Padding: 4
      Type:    Float

```


In help you here what if found:

VRT1 <56 52 54 31> Vertex indices - Float padding 4
  -> Uint32 + Current offset(after read Uint32) are End of VRT1 data, or Uint32 + 8 + Offset VRT1 position 
  -> Current offset(after read Uint32) +12 bytes Start of VRT1 data

NRM1 <4E 52 4D 31> Normals        - Float padding 4
  -> Uint32 + Current offset(after read Uint32) are End of NRM1 data, or Uint32 + 8 + Offset NRM1 position
  -> Current offset(after read Uint32) +8 bytes Start of NRM1 data 

PWT1 <50 57 54 31> are UNK?

WGT0 <57 47 54 30> Maybe Weights And Faces?
  -> Uint32 + Current offset(after read Uint32) are End of WGT0 data
  -> 4 bytes are UNK?

RGN0 <52 47 4E 30> are UNK?

UVS1 <55 56 53 31> UVs            - Float
  -> Uint32 + Current offset(after read Uint32) are End of UVS1 data
  -> Current offset(after read Uint32) are Start of UVS1 data

TXI1 <54 58 49 31> are UNK? 
 Sometime -> + 16 Bytes have FF FF FF FF FF FF 00 00 maybe end flag, I think it false not END flag.
  -> 4 bytes UNK?
  -> 2 bytes UNK?
  -> 2 bytes 255 are Alpha or Color 
  TEX0 <54 45 58 30> Texture name
   -> +7 bytes Texture name(s)
PSM0 <50 53 4D 30> Pallete or texture. 
  -> 4 Bytes UNK?
  -> 2 couple of 2 bytes are pixel resolution, 40 00, 40 00 are 64 and 64

SKE0 <53 4B 45 30> and SKL0 <53 4B 4C 30> UNK? Maybe skeleton
JNA0 <4A 4E 41 30> Joints for skeleton or names of joints?
 DYS0 <44 59 53 30> and CLD2 <43 4C 44 32> going a bit above JNA0 and i don't know what is it.

And some random chunks, for example, [https://dropmefiles.com/yUdtJ](https://dropmefiles.com/yUdtJ)
Contain textures for few models, for better UV compare, and YES maybe this is bad example and good to look a whole ISO file, maybe i cut chunk don't accurate or some NEED info was at start or end of ISO, sorry me for that. This is for hobby right - Don't spend too much time! IF you can't see much or this format are ridiculous.
