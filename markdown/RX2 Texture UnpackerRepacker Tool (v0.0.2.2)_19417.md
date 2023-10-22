## Post #1
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-30T03:53:35+00:00
- Post Title: RX2 Texture Unpacker/Repacker Tool (v0.0.2.2)

So I am making an RX2 [RW4xb2] file exporter with easy access to information about the files for modding and it supports 100% of Skate 2 and 3 Textures at the moment.

Thought it'd share it here for those that might need it for easier modding without having to check all the info in the Hex Editor.

I will add support for all other EA Games RX2 files over time as I work on it, and also add reimport options with different mipmap levels and settings for easy modding of files. 
If you have any request for options and information that might be needed from the files, post about it below and I will add it when I have time.

How to use: [https://youtu.be/cSLv-oyI6Qg](https://youtu.be/cSLv-oyI6Qg)
Download: [https://mega.nz/#F!L05SEArB!Tay7tyVKps27RK5whClf9A](https://mega.nz/#F!L05SEArB!Tay7tyVKps27RK5whClf9A)

Update v0.0.2.2

1. Updated logic for Skate 2 and 3 files to get the DataOffset from the header instead of a set value of 0x238.
This allows you to convert rx2 textures stored inside Skate 3 savefiles to TGA.


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Update v0.0.2.1

1. Tool now repacks to RX2 as well as XPR.


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Update v0.0.1.6

1. Added ability to compress rx2 files with the RefPack algorithm.
2. Added highly experimental option to repack the xpr without mipmaps/levels. Only works if the exported XPR has less than 10 levels right now!


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.5

1. Added RePacking to XPR from loaded TGA.
2. Stability updates and release build instead of debug.
3. Checks TGA width and height and compares it to the RX2 so they absolutely match. If they don't match, it won't load the TGA file.
4. Each file is put in it's own folder with time and date on it, both for repacked and TGA files.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.4

Update the Tool to Support Skate 1.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.3

Added okay support for Some of the NHL games and some support for Def Jam: Icon.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.0

Added support for Skate 2/3.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Edit: I just saw there was a general tools section. Move this over there if you want to 

Much love,
GHFear
## Post #2
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-02-09T08:58:03+00:00
- Post Title: RX2 Texture Unpacker/Repacker Tool (v0.0.2.2)

> Reply from GHFear
>
> So I am making an RX2 [RW4xb2] file exporter with easy access to information about the files for modding and it supports 100% of Skate 2 and 3 Textures at the moment.

Thought it'd share it here for those that might need it for easier modding without having to check all the info in the Hex Editor.

I will add support for all other EA Games RX2 files over time as I work on it, and also add reimport options with different mipmap levels and settings for easy modding of files. 
If you have any request for options and information that might be needed from the files, post about it below and I will add it when I have time.

How to use: https://youtu.be/cSLv-oyI6Qg
Download: https://mega.nz/#F!L05SEArB!Tay7tyVKps27RK5whClf9A

Update v0.0.2.1

1. Tool now repacks to RX2 as well as XPR.


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Update v0.0.1.6

1. Added ability to compress rx2 files with the RefPack algorithm.
2. Added highly experimental option to repack the xpr without mipmaps/levels. Only works if the exported XPR has less than 10 levels right now!


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.5

1. Added RePacking to XPR from loaded TGA.
2. Stability updates and release build instead of debug.
3. Checks TGA width and height and compares it to the RX2 so they absolutely match. If they don't match, it won't load the TGA file.
4. Each file is put in it's own folder with time and date on it, both for repacked and TGA files.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.4

Update the Tool to Support Skate 1.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.3

Added okay support for Some of the NHL games and some support for Def Jam: Icon.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.0

Added support for Skate 2/3.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Edit: I just saw there was a general tools section. Move this over there if you want to 

Much love,
GHFear

I can't open obj file with noesis?
## Post #3
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-02-09T19:26:46+00:00
- Post Title: RX2 Texture Unpacker/Repacker Tool (v0.0.2.2)

> Reply from mita996
>
> GHFear wrote:So I am making an RX2 [RW4xb2] file exporter with easy access to information about the files for modding and it supports 100% of Skate 2 and 3 Textures at the moment.

Thought it'd share it here for those that might need it for easier modding without having to check all the info in the Hex Editor.

I will add support for all other EA Games RX2 files over time as I work on it, and also add reimport options with different mipmap levels and settings for easy modding of files. 
If you have any request for options and information that might be needed from the files, post about it below and I will add it when I have time.

How to use: https://youtu.be/cSLv-oyI6Qg
Download: https://mega.nz/#F!L05SEArB!Tay7tyVKps27RK5whClf9A

Update v0.0.2.1

1. Tool now repacks to RX2 as well as XPR.


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Update v0.0.1.6

1. Added ability to compress rx2 files with the RefPack algorithm.
2. Added highly experimental option to repack the xpr without mipmaps/levels. Only works if the exported XPR has less than 10 levels right now!


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.5

1. Added RePacking to XPR from loaded TGA.
2. Stability updates and release build instead of debug.
3. Checks TGA width and height and compares it to the RX2 so they absolutely match. If they don't match, it won't load the TGA file.
4. Each file is put in it's own folder with time and date on it, both for repacked and TGA files.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.4

Update the Tool to Support Skate 1.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.3

Added okay support for Some of the NHL games and some support for Def Jam: Icon.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.0

Added support for Skate 2/3.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Edit: I just saw there was a general tools section. Move this over there if you want to 

Much love,
GHFear

I can't open obj file with noesis?

Not yet. No. I will work on that once I have a new apartment and things are steady.
## Post #4
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-02-13T18:55:07+00:00
- Post Title: RX2 Texture Unpacker/Repacker Tool (v0.0.2.2)

> Reply from GHFear
>
> So I am making an RX2 [RW4xb2] file exporter with easy access to information about the files for modding and it supports 100% of Skate 2 and 3 Textures at the moment.

Thought it'd share it here for those that might need it for easier modding without having to check all the info in the Hex Editor.

I will add support for all other EA Games RX2 files over time as I work on it, and also add reimport options with different mipmap levels and settings for easy modding of files. 
If you have any request for options and information that might be needed from the files, post about it below and I will add it when I have time.

How to use: https://youtu.be/cSLv-oyI6Qg
Download: https://mega.nz/#F!L05SEArB!Tay7tyVKps27RK5whClf9A

Update v0.0.2.1

1. Tool now repacks to RX2 as well as XPR.


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Update v0.0.1.6

1. Added ability to compress rx2 files with the RefPack algorithm.
2. Added highly experimental option to repack the xpr without mipmaps/levels. Only works if the exported XPR has less than 10 levels right now!


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.5

1. Added RePacking to XPR from loaded TGA.
2. Stability updates and release build instead of debug.
3. Checks TGA width and height and compares it to the RX2 so they absolutely match. If they don't match, it won't load the TGA file.
4. Each file is put in it's own folder with time and date on it, both for repacked and TGA files.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.4

Update the Tool to Support Skate 1.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.3

Added okay support for Some of the NHL games and some support for Def Jam: Icon.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Update v0.0.1.0

Added support for Skate 2/3.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Edit: I just saw there was a general tools section. Move this over there if you want to 

Much love,
GHFear
Great tool mate, I've download all the scripts, noesis, but I can't open it with noesis. I realize that the files are compressed ''rw4xb2''. I want to extract textures from old fifa. Please help me. Here is a sample: [https://www.mediafire.com/file/tdt0d72r ... s.rx2/file](https://www.mediafire.com/file/tdt0d72rag61ct3/face_3_0_0_0_0_3_textures.rx2/file)
## Post #5
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-05-06T09:53:08+00:00
- Post Title: RX2 Texture Unpacker/Repacker Tool (v0.0.2.2)

Updated to 0.0.2.2.

Can now open RX2 files ripped from Skate 3 savefiles.
