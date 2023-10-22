## Post #1
- Username: miky69vandoorne
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 05, 2017 8:36 pm
- Post datetime: 2019-06-30T08:38:51+00:00
- Post Title: What DDS Format is the right one to save it? (Shadow of the Tomb Raider)

Hey, i made a texture i want to save back in .DDS format for SOTR Armor, 
Now i don't know witch program i should use (PS - Gimp) i have both,
but most important is idk what DDS Format i need ... 
Can someone point me in the right direction?
i already tried a bunch of them and they all appear black in game.

here is a bit of info i could gather about the texture with DDS Checker:

magic				: 0x20534444 - DDS 
dwSize			: 0x0000007C - 124
dwFlags			: 0x000A1007 - [DDSD_CAPS] [DDSD_HEIGHT] [DDSD_WIDTH] [DDSD_PIXELFORMAT] [DDSD_MIPMAPCOUNT] [DDSD_LINEARSIZE] 
dwHeight			: 0x00000400 - 1024
dwWidth			: 0x00000400 - 1024
dwPitchOrLinearSize	: 0x00080000 - 524288
dwDepth			: 0x00000001 - 1
dwMipMapCount		: 0x0000000B - 11
dwReserved1
					00 = 0x00000000 - 00000000	
					01 = 0x00000000 - 00000000	
					02 = 0x00000000 - 00000000	
					03 = 0x00000000 - 00000000	
					04 = 0x00000000 - 00000000	
					05 = 0x00000000 - 00000000	
					06 = 0x00000000 - 00000000	
					07 = 0x00000000 - 00000000	
					08 = 0x00000000 - 00000000	
					09 = 0x00000000 - 00000000	
					10 = 0x00000000 - 00000000	
ddspf.dwSize		: 0x00000020 - 32
ddspf.dwFlags		: 0x00000004 - [DDPF_FOURCC] 
ddspf.dwFourCC		: 0x30315844 - DX10
ddspf.dwRGBBitCount	: 0x00000000 - 0
ddspf.dwRBitMask		: 0x00000000 - 0
ddspf.dwGBitMask		: 0x00000000 - 0
ddspf.dwBBitMask		: 0x00000000 - 0
ddspf.dwABitMask		: 0x00000000 - 0
dwCaps			: 0x00401008 - [DDSCAPS_COMPLEX] [DDSCAPS_TEXTURE] [DDSCAPS_MIPMAP] 
dwCaps2			: 0x00000000 - 
dwCaps3			: 0x00000000 - 0
dwCaps4			: 0x00000000 - 0
dwReserved2			: 0x00000000 - 0
[DX10 Extension]
Format			: DXGI_FORMAT_BC1_UNORM_SRGB 
Ressource Dimension	: D3D10_RESOURCE_DIMENSION_TEXTURE2D 
Misc Flags			: 0x00000000 
Array Size			: 0x00000001
Misc Flags 2		: 0x00000000 DDS_ALPHA_MODE_UNKNOWN

To be honest i still don't know witch format i should pick and with or without mipmaps and any other settings on/off.
Could you maybe post a screenshot?

Thx for your time.
## Post #2
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2020-05-21T14:30:38+00:00
- Post Title: What DDS Format is the right one to save it? (Shadow of the Tomb Raider)

dwMipMapCount : 0x0000000B - 11
Format : DXGI_FORMAT_BC1_UNORM_SRGB

Game uses DX10 dds. Use gimp it has support for DX10 dds or photoshop with intel plugin.
Anyway you want to tell me that game use textures with DDS headers?
