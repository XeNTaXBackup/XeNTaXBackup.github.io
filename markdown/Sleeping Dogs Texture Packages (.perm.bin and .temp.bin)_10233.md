## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-19T09:21:31+00:00
- Post Title: Sleeping Dogs Texture Packages (*.perm.bin and *.temp.bin)

I found: Width, Height, Offset, Size but dunno where type, mipmaps and ect.

.perm.bin - Info: Width, Height, Offset, Size
.temp.bin - Textures

Count Files = PermBinSize / 304 (Entry Size)

```
{
  dword h01; // Magic
  char h02[24]; // Unknown
  dword h03; // Hash for Texture name without extension
  char h04[12]; // Nulls
  char h05[48]; // Texture name without extension
  word h06; // Width
  word h07; // Heigth
  word h08; // Unknown
  word h09; // Unknown
  char h10[28]; // Unknown
  dword h11; // Offset
  dword h12; // Size
  char h13[168]; // Unknown
};
```


Anyone can help? (Top [Secret](http://www.sendspace.com/file/oex7aa) Files)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-20T08:05:38+00:00
- Post Title: Sleeping Dogs Texture Packages (*.perm.bin and *.temp.bin)

h08 is number of mipmaps. 

0x200 x 0x200 = 0 0x20000 DXT1 size 
0x100 x 0x100 = 1 0x8000 DXT1 size
0x080 x 0x080 = 2 0x2000 DXT1 size
0x040 x 0x040 = 3 0x800 DXT1 size
0x020 x 0x020 = 4 0x200 DXT1 size
0x010 x 0x010 = 5 0x080 DXT1 size
0x008 x 0x008 = 6 0x020 DXT1 size
0x004 x 0x004 = 7 0x08 DXT1 size
0x002 x 0x002 = 8 0x08 DXT1 size (anything less than 0x4 x 0x4 always clamp to 4x4)
---------------------------------
total size = 0x2AAB0

what does data in perm.bin file say...
01000000 ... 0002 0002 0800 0100 ... B0AA0200 ...

for another 0x200 by 0x200 image it has 
03000000 ... 0002 0002 0800 0100 ...50550500 ...
notice file size is twice as large... probably means DXT5.

so my guess is your h03 is probably type (not file extension has) with 0x0001 being DXT1 and 0x0003 being DXT5.

you have my code ekey... lookup my CreateDXT1Header and CreateDXT5Header in x_dds.h/x_dds.cpp and it will create dds header for you. save to file. paste data from bin file to end of test.dds file. hopefully you see image he he he.

```
 CreateDXT1Header(0x200, 0x200, 8, FALSE, &ddsh);
 ofstream ofile("test.dds", ios::binary);
 ofile.write("DDS ", 4);
 ofile.write((char*)&ddsh, sizeof(ddsh));

```
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-20T08:22:48+00:00
- Post Title: Sleeping Dogs Texture Packages (*.perm.bin and *.temp.bin)

h03 - it's 100% texture name hash (string without extension)



You can check it with BIGUnpacker
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-20T08:36:06+00:00
- Post Title: Sleeping Dogs Texture Packages (*.perm.bin and *.temp.bin)

oh i see, i was starting the entry from the filename lol
lemme see, texture type would be part of your h05. i would make h05 only 32 bytes, rather than 48.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-20T14:12:55+00:00
- Post Title: Sleeping Dogs Texture Packages (*.perm.bin and *.temp.bin)

Okay thanks for help.
