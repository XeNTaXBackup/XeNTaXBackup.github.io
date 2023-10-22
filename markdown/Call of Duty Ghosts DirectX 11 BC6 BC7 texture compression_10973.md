## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-20T09:21:13+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

I'm reversing call of duty ghosts, they seem to use some DX11 textures for storing normal maps

 -BC1_UNORM (DXT1)
 -BC2_UNORM (DXT3)
 -BC3_UNORM (DXT5)
 -BC5_SNORM (16Bytes per 4x4 pixel block)(ATI2)
 -BC7
 -r8g8b8a8_UNORM
 -r16g16b16a16_float

I can't seem to figure out this one anyone mind taking a look. I'm sure it's one of the dx11 compression methods but so far no tool has worked to even view it.

Here is as close as I have gotten it under BC5


rawfile
[https://dl.dropboxusercontent.com/u/107 ... ure.rawIWI](https://dl.dropboxusercontent.com/u/10798900/DUMPBOX/texture.rawIWI)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-21T09:58:36+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

which tool did you use to display it? 

This is a R16G16B16A16 (uint16) to R8G8B8A8 "conversion" by me 
[](http://www.pic-upload.de/view-21397126/raw.png.html)
so your pic is looking much better.  
What is the problem? The "noise" or the number of palette entries?
[](http://www.pic-upload.de/view-21397069/RAW_versa_normal.png.html)

Guess you're searching for a calculation formula for BC7 (similar to the one for BC5_SNORM [http://msdn.microsoft.com/en-us/library ... 85%29.aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/bb694531%28v=vs.85%29.aspx))?

What about this: [http://msdn.microsoft.com/de-de/library ... 85%29.aspx](http://msdn.microsoft.com/de-de/library/windows/desktop/hh308953%28v=vs.85%29.aspx) (Decoding the BC7 Format)

Seems to make sense to use the D3DX11CreateTextureFromFile function (D3D 11 SDK).

edit: ok, if you tried BC7 it seems to be a little bit harder...
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-21T10:20:33+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

> Reply from shakotay2
>
> which tool did you use to display it? 

This is a R16G16B16A16 (uint16) to R8G8B8A8 "conversion" by me 

so your pic is looking much better.  
What is the problem? The "noise" or the number of palette entries?


Guess you're searching for a calculation formula for BC7 (similar to the one for BC5_SNORM http://msdn.microsoft.com/en-us/library ... 85%29.aspx)?

What about this: http://msdn.microsoft.com/de-de/library ... 85%29.aspx (Decoding the BC7 Format)

Photoshop I used the nvidea texture tools set to make a bc5 file and they wacked on the header and opened the dds in photoshop.

It's weird I've tried everything even bc7 compression and that didn't work either
## Post #4
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-11T17:45:14+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

I'm posting here instead of making a new topic because i think i have some similar textures and i am also guessing that they are compressed with one of the newest compression methods.

[https://www.dropbox.com/s/d7dnxzkd0t5cf ... m.dds?dl=0](https://www.dropbox.com/s/d7dnxzkd0t5cfk6/ball_nm.dds?dl=0)


I've added a dxt5 (bc5) header on this one but it is a mess. The container in which it is contained states that its name is ball_nm.dds, its from FIFA 15 Demo for PC which was released a couple of days ago and its 99,999% a normal map as well.




Any help is highly appreciated
## Post #5
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-12T14:18:42+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

I solved my issue.

Its a BC5 compressed image and it needs the "new" DDS_HEADER_DXT10 structure as an additional 20 bytes to the main dds header which needs the dwFourCC code to be set to "DX10"

In this additional header the mode the form contains the surcace picture format which can be 1-115  
More info here: [http://msdn.microsoft.com/en-us/library ... 85%29.aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/bb943983%28v=vs.85%29.aspx)

Anyway i extracted mine using texgenpack tool (after an enless google searching) [http://sourceforge.net/projects/texgenpack/](http://sourceforge.net/projects/texgenpack/)

and then i needed to invert the color channels

Here is what came out
## Post #6
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-12T15:11:04+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

Managed to get it working with nvidia texture tools 2 as well. To be honest i have no idea what kind of garbage the nvidia tool wrote in the dds header, but this seems to work with the basic dds header (without the dx10 extension), with dwFourCC code equal to ATI2 and some other text added by the tool in it.

Anyway with this way, i managed to get it working with photoshop right away and i tested the dds with blender and they work there as well.
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-13T03:01:57+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

> Reply from gregkwaste
>
> Managed to get it working with nvidia texture tools 2 as well. To be honest i have no idea what kind of garbage the nvidia tool wrote in the dds header, but this seems to work with the basic dds header (without the dx10 extension), with dwFourCC code equal to ATI2 and some other text added by the tool in it.

Anyway with this way, i managed to get it working with photoshop right away and i tested the dds with blender and they work there as well.
Good to hear could you post the sample dds
## Post #8
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-13T12:14:39+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

> Reply from cra0
>
> gregkwaste wrote:Managed to get it working with nvidia texture tools 2 as well. To be honest i have no idea what kind of garbage the nvidia tool wrote in the dds header, but this seems to work with the basic dds header (without the dx10 extension), with dwFourCC code equal to ATI2 and some other text added by the tool in it.

Anyway with this way, i managed to get it working with photoshop right away and i tested the dds with blender and they work there as well.
Good to hear could you post the sample dds
[https://www.dropbox.com/s/pf7c27nzkyv1a ... d.dds?dl=0](https://www.dropbox.com/s/pf7c27nzkyv1ach/ball_nm_fixed.dds?dl=0)

This is the final
## Post #9
- Username: zohaa3492
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 23, 2014 1:23 pm
- Post datetime: 2014-10-23T05:24:34+00:00
- Post Title: Call of Duty Ghosts DirectX 11 BC6 BC7 texture compression

Gildor replied with:
