## Post #1
- Username: Peter Parker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 03, 2018 4:13 am
- Post datetime: 2018-12-02T20:56:29+00:00
- Post Title: Skyrim Switch Hyrule Exclusives Textures Won't Open

The Hyrule.esm can be viewed with Xedit just fine. Exclusive nifs can be opened with nifskope; practically any 3D model software with NIF support installed. 

However, the Switch textures cannot be opened with DDS Viewer nor Photoshop with both Nvidia's and Intel's DDS plugins on, even though I can open PC regular Skyrim and SSE textures without issue. Possibly due to some unknown compression format for the Switch? I tried Daemon's Raw Texture Cooker without success. Willing to donate 5 bucks through Paypal to whoever solves the issue for their time. Thanks for reading

[https://drive.google.com/file/d/1UI8M6r ... hb5mt/view](https://drive.google.com/file/d/1UI8M6rw7vRTB5teNo08xQw22kychb5mt/view)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-12T03:43:39+00:00
- Post Title: Skyrim Switch Hyrule Exclusives Textures Won't Open

you can open these with RawTex tool, you just have to enter correct 
settings and change extension from dds to something else.   

this is some specs i see in your sample files :
width is stored at 0x40 as int
height is stored at 0x44 as int
format ID is stored at 0x50 as int
number of mipmaps is stored at 0x54 as int
total datasize is stored at 0x58 as int
the relative offset table for each mip begins at 0x5c
image data starts at 0xd0 
if format ID is 0x42 the format is dxt1 (BC1)
if format ID is 0x44 the format is dxt5 (BC3)

if RawTex tool allowed to set swizzle type on commandline i 
would hook it with Noesis to automate this whole process.
