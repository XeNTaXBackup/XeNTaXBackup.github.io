## Post #1
- Username: PaK
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue May 29, 2007 7:43 pm
- Post datetime: 2007-06-23T14:32:22+00:00
- Post Title: Are these files RLE compressed?

QRS header is 128bytes, textures are raw 32bit RGBA swizzled. After unswizzled it will become 4 or 8 bit indexed with 32bit RGBA palette. Many textures match with it data size, but others not and are bad unswizzled.

texture1: sizeX=64, sizeY=32, and totalsize=0x8200 & 0x7FFF *0x10 = 64*32*4 = 8192, but it really has 8196bytes

texture2: sizeX=100, sizeY=20, totalsize= 0x8800 & 0x7FFF * 0x10 = 32768, but it only has 20547bytes

Texture1 is partial well unswizzled, texture2 cant view anything.. this examples are with a default grey palette.

texture1 
[samples.zip](https://xentaxbackup.github.io/file/1233_samples.zip)
