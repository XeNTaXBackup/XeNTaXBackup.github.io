## Post #1
- Username: maddjakkal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 23, 2011 5:12 am
- Post datetime: 2017-02-05T20:54:34+00:00
- Post Title: PTX Pump it Up DCT Based Format - an odd one

A couple of colleagues and myself have been banging our head off of this format for years - there exists an old dos program that can convert TGAs to this format, accepts two types (24bpp and 32bpp), and somehow it uses DCT and some super weird compression to come up with the final file.

This is for the first 3 pump it up games in the series that used 3DFX cards and some defunct game engine that no longer exists.

I've dug into DCT a bit, but haven't made a whole lot of progress past that.

Odd - an 8x8 24bpp all white image compresses data down to about 5 bytes, if it's 32bpp, the final data is about 8 bytes. It sort of looks like jpg but it's gotta be different somehow.

From what I've figured out:
Header[16]
char magic[4] = {'P','T','X','\0'}
int16 somevalue = 256 (always 256)
int16 width >> 3
int16 height >> 3
int16 type (0x81 = 24bpp, 0x82 = 32bpp)
int16 somevalue2 = 0x12C (seems to always be 300)
int16 padding = null

The rest of the file is the pixel data in some form.

I've attached the tga->ptx utility (PTX.exe), an 8x8 white rgb tga, and its equivalent ptx file.

Maybe this will interest someone at some point - it's literally the last file format that we never quite figured out. The goal is to eventually load this into a library while rebuilding the dos game to run on linux/win32 which is pretty much working at the moment, but the ptx unpacking functions in the game error out and it would be easier to replace them if we knew what it was doing.

Cheers!
[ptx.zip](https://xentaxbackup.github.io/file/12405_ptx.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-05T21:39:51+00:00
- Post Title: PTX Pump it Up DCT Based Format - an odd one

> Reply from maddjakkal
>
> int16 somevalue2 = 0x12C (seems to always be 300)
at first glance i would say that is uncompressed size but i can't get 
the ptx.exe to work so i can convert various sizes to check.
## Post #3
- Username: maddjakkal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 23, 2011 5:12 am
- Post datetime: 2017-02-05T22:02:33+00:00
- Post Title: PTX Pump it Up DCT Based Format - an odd one

> Reply from AceWell
>
> maddjakkal wrote:int16 somevalue2 = 0x12C (seems to always be 300)
at first glance i would say that is uncompressed size but i can't get 
the ptx.exe to work so i can convert various sizes to check.

It's a dos executable - best bet is to use like dosbox daum svn or something, that's how I did it.
