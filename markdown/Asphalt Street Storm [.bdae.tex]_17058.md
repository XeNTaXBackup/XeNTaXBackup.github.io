## Post #1
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2017-09-24T13:18:57+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

I found .bdae and .tex files in zip files of Asphalt Street Storm game.
.bdae files : 3D model files but new format unsupported to BDAE importer script.
.tex files : texture files.

Sample (Mercedes-AMG S65)
[http://www.mediafire.com/file/ry8lm77mzqo9cck/s65.zip](http://www.mediafire.com/file/ry8lm77mzqo9cck/s65.zip)
## Post #2
- Username: khiro
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 23, 2017 8:18 am
- Post datetime: 2017-09-24T16:13:03+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

Hello.
I created a tool that can convert .bdae to .dae (Collada format) only for Asphalt Street Storm Racing.
Here is the sample you posted (in Blender):


And for textures, I created also a simple tool to make them all .dds and there is a small problem I had faced in your sample which is that the textures are not 32 bit-per-pixel. I am working on this issue.
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-09-26T21:46:22+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

> Reply from khiro
>
> Hello.
I created a tool that can convert .bdae to .dae (Collada format) only for Asphalt Street Storm Racing.
Here is the sample you posted (in Blender):


And for textures, I created also a simple tool to make them all .dds and there is a small problem I had faced in your sample which is that the textures are not 32 bit-per-pixel. I am working on this issue.great job! where can I download your tool?
## Post #4
- Username: khiro
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 23, 2017 8:18 am
- Post datetime: 2017-09-27T21:36:01+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

The development of the tool still in progress but I will finish it soon. Just be patient
## Post #5
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2017-11-04T22:22:36+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

Hi. Any Progress? A month has passed.
## Post #6
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-11-04T23:40:43+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

Textures seems to have some Variable Block Compression, my tip was on ASTC but I was unable to sucessfully wrap data.
Textures from Gamel0ft can be real pain sometimes.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-05T02:18:42+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

> Reply from nosfornos
>
> .tex files : texture files.
http://www.mediafire.com/file/ry8lm77mzqo9cck/s65.zip
all of the textures samples but one are pvr, and all those but two are lz4 compressed, use this script to decompress  

```

comtype lz4
idstring "\x23\x4c\x5a\x34"
get NAME basename
string NAME + .pvr
get ZSIZE asize
math ZSIZE - 0x8
get SIZE long
clog NAME 0x8 ZSIZE SIZE

```

use pvrtextool to open the pvr textures
## Post #8
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-11-05T11:21:57+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

> Reply from AceWell
>
> nosfornos wrote:.tex files : texture files.
http://www.mediafire.com/file/ry8lm77mzqo9cck/s65.zip
all of the textures samples but one are pvr, and all those but two are lz4 compressed, use this script to decompress  
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

comtype lz4
idstring "\x23\x4c\x5a\x34"
get NAME basename
string NAME + .pvr
get ZSIZE asize
math ZSIZE - 0x8
get SIZE long
clog NAME 0x8 ZSIZE SIZE

use pvrtextool to open the pvr textures
If can't open some textures, rename pvr to ktx and open using PvrTexTool
## Post #9
- Username: khiro
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 23, 2017 8:18 am
- Post datetime: 2017-11-09T15:03:26+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

Hi, I am sorry because I did not give any information about the progress.
The problem, as I said previously, is textures. There are 2 types of textures for this game: DDS and PVR.
I am still stuck on PVR textures which are using PVRTC2bpp with mode 1. Actually the results are close to the original textures but still need some work.
I have already managed to convert PVR with PVRTC4bpp to DDS.
Any help about PVRTC2bpp (mode = 1) is appreciated.
## Post #10
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-11-11T19:08:22+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

Just browsed yesterday: [https://github.com/powervr-graphics/Nat ... mpress.cpp](https://github.com/powervr-graphics/Native_SDK/blob/5.0/Framework/PVRCore/Texture/PVRTDecompress.cpp)
PowerVR is really interesting format indeed.
## Post #11
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-11-25T14:56:58+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

Any news about importer?
## Post #12
- Username: khiro
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 23, 2017 8:18 am
- Post datetime: 2017-11-30T17:25:25+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

I'm so sorry because I made you wait and it looks like the issue of textures will be solved soon (thanks to PredatorCZ for the source code which will help me to finish the tool).
And to not let you wait more I uploaded the tools for you (not completed yet but may do the work   ).
Sorry again.
Khiro.
[ASSR_Exporters.rar](https://xentaxbackup.github.io/file/13620_ASSR_Exporters.rar)
## Post #13
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-11-30T23:42:46+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

Thank you so much for this!
## Post #14
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-12-27T10:28:15+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

Anybody can opening textures from Alpine?? When I have .ktx files, PVR seeing message: "Please check that astcenc.exe is in path"
[http://www.mediafire.com/file/9c339635m58mxz7/tex.rar](http://www.mediafire.com/file/9c339635m58mxz7/tex.rar)
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-08T08:59:36+00:00
- Post Title: Asphalt Street Storm [.bdae/.tex]

> Reply from zimex25
>
> When I have .ktx files, PVR seeing message: "Please check that astcenc.exe is in path"
Check it [here](http://forum.xentax.com/viewtopic.php?f=16&t=17591) the second note in the first post.
## Post #16
- Username: silkroad820420
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 22, 2019 7:52 pm
- Post datetime: 2019-01-26T15:16:19+00:00
- Post Title: Re: Asphalt Street Storm [.bdae/.tex]

> Reply from Bigchillghost
>
> zimex25 wrote:When I have .ktx files, PVR seeing message: "Please check that astcenc.exe is in path"
Check it here the second note in the first post.

hi,I already put the astcenc.exe in PVRTexToolGUI folder (C:\Imagination\PowerVR_Graphics\PowerVR_Tools\PVRTexTool\GUI\Windows_x86_64 )

and set astcenc.exe to environment PATH.(;C:\Imagination\PowerVR_Graphics\PowerVR_Tools\PVRTexTool\GUI\Windows_x86_64\astcenc.exe) 
but it still not working ,I don't know why. can you help me?
[1111.JPG](https://xentaxbackup.github.io/file/15584_1111.JPG)
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-01-26T15:32:34+00:00
- Post Title: Re: Asphalt Street Storm [.bdae/.tex]

> Reply from silkroad820420
>
> and set astcenc.exe to environment PATH.(;C:\Imagination\PowerVR_Graphics\PowerVR_Tools\PVRTexTool\GUI\Windows_x86_64\astcenc.exe)
It's the location of the executable that needs to be placed in PATH, so remove "astcenc.exe" from your string.
## Post #18
- Username: silkroad820420
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 22, 2019 7:52 pm
- Post datetime: 2019-01-27T03:22:41+00:00
- Post Title: Re: Asphalt Street Storm [.bdae/.tex]

> Reply from Bigchillghost
>
> silkroad820420 wrote:and set astcenc.exe to environment PATH.(;C:\Imagination\PowerVR_Graphics\PowerVR_Tools\PVRTexTool\GUI\Windows_x86_64\astcenc.exe) 

It's the location of the executable that needs to be placed in PATH, so remove "astcenc.exe" from your string.

thank you so much!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
