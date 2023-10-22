## Post #1
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2018-10-26T19:02:46+00:00
- Post Title: GUN .img.xbx

Hi
Can someone help me with specifying this graphic format? 

GUN on PC uses same formats as in Tony Hawk's Underground 1-2 on Xbox platform. But except extensions, .img.xbx files doesn't seems very similar.

That's my draft specification:

```
int16 subversion? 	# 0x28

int32 unknown	# crc? might be 0x0
int16 width
int16 height
int16 widthAdjusted
int16 heightAdjusted

# Pixelformat

byte unknown	# always 1
byte bitCount	# 32, 8..
byte depth??	# 0 32..
byte unknown 	# mipmaps??

int32 unknown	# always 1 ?
int32 unknown	# always 0x28 ?
int32 unknown	# 0x3C for 8 bit or 0xFFFFFFFF for 32 bit
int32 unknown	# 0xFFFFFFFF

int32 unknown	# 0x01
int16 unknown	# 0x01
int16 unknown	# 0x04
int32 unknown	# 0x00
int32 unknown	# 0x00

int32 unknown	# 0x00
int32 unknown	# 0x00
int16 unknown	# 0x01 for 8 bit
unt16 unknown	# 0xC003 for 8 bit
int32 unknown	# 0x2000 for 8 bit

#Palette size for 8 bit - 256 ???
#Offset 0x80: Image data start

```


In attach I provide a logo texture from main menu screen. Tex_0134.dds it's ripped texture, which show how should looks like.

Thanks in advance.
[Logo_gun_white_128.zip](https://xentaxbackup.github.io/file/15094_Logo_gun_white_128.zip)
