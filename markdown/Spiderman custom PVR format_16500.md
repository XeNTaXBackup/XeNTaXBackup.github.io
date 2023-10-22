## Post #1
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-05T15:50:52+00:00
- Post Title: Spiderman custom PVR format

Hello so i've been reversing the [Spiderman 2000](https://en.wikipedia.org/wiki/Spider-Man_%282000_video_game%29)PC version of the game. The game stores all its content in a custom file format called pkr also used in tony hawks pro skater.

The models and its textures of each character are in a file with the extension PSX. PSX files may contain a lot of stuff, some are bitmaps and others models and textures in PSXPVR format which make it really hard. The textures are not a single archive, they're split through the file.

I can preview the textures using tile molester and setting view mode to 16bpp ARGB and 2-dimensional.
But the header of the structure is what i'm struggling with.

The first 0x10 bytes i dont't understand their purpose but modifying them doesn't have much impact in the game.
The following 2 words are width and height and the dword is palette related. Then until 0x18 i have no clue, it's there where the actual texture starts.


If you download the zip, each texture offset is:
1: 0005956C
2: 0005DD90
3: 000625B4
4: 00066DD8
5: 000685FC
6: 00069E20
7: 0006E644
8: 0006FE68

I got them using a tool i've coded, here's the source in case you want to check what it's done:
[https://github.com/krystalgamer/spidey- ... /psx/psx.c](https://github.com/krystalgamer/spidey-tools/blob/master/psx/psx.c)

The reason i know the file name is PSXPVR is due to references in the code. Also there was also something related to VQ which i see might be PVR related but i'm a newbie in graphic file format so i'm seeking help.
[spidey.7z](https://xentaxbackup.github.io/file/13077_spidey.7z)
## Post #2
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-06T11:56:57+00:00
- Post Title: Spiderman custom PVR format

I made some progress. The textures are compressed, i was able to decompressed them.
Open with tile molester and set codec to 16bpp RGB565.
Any ideia on the format??
It's not a zip, i just added it to upload.
[spidey.zip](https://xentaxbackup.github.io/file/13080_spidey.zip)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-07T04:08:47+00:00
- Post Title: Spiderman custom PVR format

> Reply from krystalgamer
>
> The textures are compressed, i was able to decompressed them.
how?   

the 0x1c length header looks like this to me
4bytes - unk
4bytes - unk2
4bytes - zero
4bytes - zero2
2bytes - image width
2bytes - image height
1byte - flag   //?
1byte - flag2  //?
1byte - flag3  //?
1byte - flag4  //?
4bytes - size of data until next file
## Post #4
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-07T14:29:56+00:00
- Post Title: Spiderman custom PVR format

> Reply from AceWell
>
> 
4bytes - size of data until next file

Thanks, didn't notice this 


I'm not totally sure if it's compression but there's something weird going on.
Here's the interesting part of what i've reversed: [https://github.com/krystalgamer/spidey- ... #L212-L215](https://github.com/krystalgamer/spidey-tools/blob/master/psx/psx.c#L212-L215)

I'll explain a bit of what's going on. 
Right next to the header there's 0x800 bytes of RGA565 colors(lets call colorList). After that there's a big chunk of offsets(lets call them offsetList) that point each one point to a position inside the colorList.

The entry of offsetList to be used is calculated using the current location of the pixel being drawn(x,y coordinates that i called them curHeight and curWidth) and the width and the height of the uncompressed image(the v20 and v32 thing that i dont understand). The colors array i have no ideia of what it is, i called it that since i thought it was the palette.

After that it reads 8 consecutive bytes(4 colors) from the colorList and puts them on the the uncompressed texture but here's the interesting part, considering it's currently drawing the pixel at (x,y), it puts the first color at (x,y), the third at (x+1, y), the second at (x,y+1) and the fourth at (x+1,y+1). Also each loop related to the curWidth draws (uncompressed width)*4 bytes into the uncompressed texture.

My current problem is now compressing it again, i'll try and post something if i can.

By the way here's the the decompressed textures. They're raw RGB565.
[psx.7z](https://xentaxbackup.github.io/file/13085_psx.7z)
## Post #5
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-08T15:55:21+00:00
- Post Title: Spiderman custom PVR format

The colorList that i've reference in the latest post is actually the [Moser de Bruijn sequence](http://oeis.org/A000695) which is used for data interleaving, so i'm now sure the textures are really compressed.
## Post #6
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-09T16:16:31+00:00
- Post Title: Spiderman custom PVR format

Texture extraction is completly done!
Here's a demonstration video: [https://www.youtube.com/watch?v=N4WuFQAFnns](https://www.youtube.com/watch?v=N4WuFQAFnns)
The code is here: [https://github.com/krystalgamer/spidey- ... _extractor](https://github.com/krystalgamer/spidey-tools/tree/master/psx_extractor)

I have to thank NoFate for telling me about the sequence, without him i'd still be poking around.
Also need to thank AceWell for noticing that important detail about the PSX files
## Post #7
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-07-09T17:45:46+00:00
- Post Title: Spiderman custom PVR format

Amazing! can't believe what someone made this.
Can you also made tool for a models? (if this is a possible of course)
Thanks!
## Post #8
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-09T18:10:17+00:00
- Post Title: Spiderman custom PVR format

> Reply from Rutabaga
>
> Amazing! can't believe what someone made this.
Can you also made tool for a models? (if this is a possible of course)
Thanks!
After working on the texture repacker, for sure.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-10T00:08:04+00:00
- Post Title: Spiderman custom PVR format

hmm i can't seem to open the extracted bmp files with anything   
i compiled the source with MinGW and everything else seems to work, 
i can open the bmps with TextureFinder and the image data looks ok with the RGB565 setting,
i guess the issue is something with the header.

spidey.psx
0.bmp header

```
6C 00 00 00 00 01 00 00 00 FF FF FF 01 00 10 00
03 00 00 00 00 00 02 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 F8 00 00 E0 07 00 00 
1F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00
```
## Post #10
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-10T12:02:46+00:00
- Post Title: Spiderman custom PVR format

> Reply from AceWell
>
> hmm i can't seem to open the extracted bmp files with anything   
i compiled the source with MinGW and everything else seems to work, 
i can open the bmps with TextureFinder and the image data looks ok with the RGB565 setting,
i guess the issue is something with the header.

spidey.psx
0.bmp header
Code: Select all42 4D 00 00 7C 00 02 00 00 00 00 00 7C 00 00 00 
6C 00 00 00 00 01 00 00 00 FF FF FF 01 00 10 00
03 00 00 00 00 00 02 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 F8 00 00 E0 07 00 00 
1F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00

Could you please post the bmp? The header seems indeed wrong. According to that header your bmp has the size of 7mb which is just wrong and the bit offset is 0x7C0000 which is also wrong. How did you compile the code and what's the system you compiled in?
Did you run make or simply gcc? Looks like your BmpHeader structures are 4 bytes padded which is causing the issue.

I'll post my psx.exe here.
[psx.7z](https://xentaxbackup.github.io/file/13092_psx.7z)
## Post #11
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-07-10T13:56:17+00:00
- Post Title: Spiderman custom PVR format

Thanks a lot for the compiled exe,because i'm noob at this stuff.
Btw will your tool work with psx files from Enter Electro and First game for PS1?
And how i can use your load_from_disk tool?
Thanks.
## Post #12
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-10T15:55:26+00:00
- Post Title: Spiderman custom PVR format

> Reply from Rutabaga
>
> Thanks a lot for the compiled exe,because i'm noob at this stuff.
Btw will your tool work with psx files from Enter Electro and First game for PS1?
And how i can use your load_from_disk tool?
Thanks.

Most likely not. Since the ps1 version uses a different format called rgb.
Rename your original binkw32 to binkw32_ and my binkw32_proxy to binkw32. It's a dll proxy.
## Post #13
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-07-10T16:42:53+00:00
- Post Title: Spiderman custom PVR format

> Reply from krystalgamer
>
> 
Most likely not. Since the ps1 version uses a different format called rgb.
Rename your original binkw32 to binkw32_ and my binkw32_proxy to binkw32. It's a dll proxy.
Thanks,i renamed dll's,and tried to start the game.
When i running the game executable it pop ups me the VCRUMTIME140D dll error message,despite the fact what i have Microsoft Visual C++ 2015 Redistributable installed..
is this a fixable?
thanks!
## Post #14
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-10T17:38:00+00:00
- Post Title: Spiderman custom PVR format

> Reply from Rutabaga
>
> krystalgamer wrote:
Most likely not. Since the ps1 version uses a different format called rgb.
Rename your original binkw32 to binkw32_ and my binkw32_proxy to binkw32. It's a dll proxy.
Thanks,i renamed dll's,and tried to start the game.
When i running the game executable it pop ups me the VCRUMTIME140D dll error message,despite the fact what i have Microsoft Visual C++ 2015 Redistributable installed..
is this a fixable?
thanks!

I compiled it in debug mode. If i were you i'd try to compile it myself, earlier was talking to a person with the same error and compiling in release mode didn't help him. Sorry.
Or you could wait for a newer version.
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-11T02:34:15+00:00
- Post Title: Spiderman custom PVR format

> Reply from krystalgamer
>
> How did you compile the code and what's the system you compiled in?
Did you run make or simply gcc?
i don't know how to use the "Makefile", i'm fairly new to compiling sources and i'm not a programmer  

```
gcc -std=c99 -o psx.exe psx.c psx.h bmp.c
```


edit
nevermind i got it working, i used the "CFLAGS" you had in the "Makefile" instead (although i've no idea what they mean) 

```
gcc -std=c11 -g -mno-ms-bitfields -o psx.exe psx.c psx.h bmp.c
```

my psx.exe is 70.2kb
## Post #16
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-11T11:39:24+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from AceWell
>
> krystalgamer wrote:How did you compile the code and what's the system you compiled in?
Did you run make or simply gcc?
i don't know how to use the "Makefile", i'm fairly new to compiling sources and i'm not a programmer  
Code: Select allgcc -std=c99 -o psx.exe psx.c psx.h bmp.c

edit
nevermind i got it working, i used the "CFLAGS" you had in the "Makefile" instead (although i've no idea what they mean) 
Code: Select allgcc -std=c11 -g -mno-ms-bitfields -o psx.exe psx.c psx.h bmp.c
my psx.exe is 70.2kb

You're compiling it manually. When there's a Makefile just type "make". It'll do everything for you.

-std=c11 defines the newer standard of C, the C11, which i use for the anonymous structures
-g is for debug symbols
-mno-ms-bitfields is used because newer versions of gcc have trouble packing the structures, even expliciting telling it (__attribute__((packed))) is not enough.
## Post #17
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-11T14:44:19+00:00
- Post Title: Re: Spiderman custom PVR format

Update!!! 

My texture repacker is finally done  Check the code here: [https://github.com/krystalgamer/spidey-tools](https://github.com/krystalgamer/spidey-tools)
For real, it's a huge pain in the ass to create custom textures. You're limited to 256 patterns of 4 colors. Unless someone develops a plugin or a image editor that allows to keep count of them custom textures won't happen this way.

If you intend to create custom textures make sure to save them as BMP 16Bit RGB565! The only image editor i know that allows to do so is photoshop :/ sorry, hope everyone interested can find its ways.

Btw here's a little demo of the tool: [https://www.youtube.com/watch?v=bLyL9-Jk5ks](https://www.youtube.com/watch?v=bLyL9-Jk5ks)

This + the custom file loader allows me to live edit the textures which is amazing for testing 

I'll be writting a custom texture loader that allows to load them from the disk
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-12T04:08:15+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from krystalgamer
>
> You're compiling it manually. When there's a Makefile just type "make". It'll do everything for you.

-std=c11 defines the newer standard of C, the C11, which i use for the anonymous structures
-g is for debug symbols
-mno-ms-bitfields is used because newer versions of gcc have trouble packing the structures, even expliciting telling it (__attribute__((packed))) is not enough.
thanks! but whenever i type "make" i just get this error:

> 'make' is not recognized as an internal or external command, operable program or batch file.
i launch MinGW command prompt and change directory to where the makefile is and type "make" but get that error always.  

edit
ok i got it working by typing "mingw32-make" instead
## Post #19
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-07-12T06:19:04+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from krystalgamer
>
> Update!!! 

My texture repacker is finally done  Check the code here: https://github.com/krystalgamer/spidey-tools
For real, it's a huge pain in the ass to create custom textures. You're limited to 256 patterns of 4 colors. Unless someone develops a plugin or a image editor that allows to keep count of them custom textures won't happen this way.

If you intend to create custom textures make sure to save them as BMP 16Bit RGB565! The only image editor i know that allows to do so is photoshop :/ sorry, hope everyone interested can find its ways.

Btw here's a little demo of the tool: https://www.youtube.com/watch?v=bLyL9-Jk5ks

This + the custom file loader allows me to live edit the textures which is amazing for testing 

I'll be writting a custom texture loader that allows to load them from the disk
Thanks for such amazing tool,can't wait for release (i know,i can download tool now,but i'm noob in compiling and etc. stuff) 
Btw,what means "you're limited to 256 patterns of 4 colors" if i wanna create skin from PS4 game or CW/Homecoming i can't then?
Thanks.

Edit: I made a homecoming SM chest,it has no webs (working on it)
can you test it plz?
[https://mega.nz/#!b851wJ7R!opjK7o5qn-bf ... F7cY55VFj8](https://mega.nz/#!b851wJ7R!opjK7o5qn-bfTqaT4b0K0Wsl5lEHb5bOxF7cY55VFj8)
## Post #20
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-12T11:18:04+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from AceWell
>
> krystalgamer wrote:You're compiling it manually. When there's a Makefile just type "make". It'll do everything for you.

-std=c11 defines the newer standard of C, the C11, which i use for the anonymous structures
-g is for debug symbols
-mno-ms-bitfields is used because newer versions of gcc have trouble packing the structures, even expliciting telling it (__attribute__((packed))) is not enough.
thanks! but whenever i type "make" i just get this error:
'make' is not recognized as an internal or external command, operable program or batch file.
i launch MinGW command prompt and change directory to where the makefile is and type "make" but get that error always.  

edit
ok i got it working by typing "mingw32-make" instead

Nice, if you want you can rename the mingw32-make.exe to make.exe or if you're using MSYS2 you can run pacman -S make to install it. (Also mingw32-make is just as fine as make )

> Reply from Rutabaga
>
> krystalgamer wrote:Update!!! 

My texture repacker is finally done  Check the code here: https://github.com/krystalgamer/spidey-tools
For real, it's a huge pain in the ass to create custom textures. You're limited to 256 patterns of 4 colors. Unless someone develops a plugin or a image editor that allows to keep count of them custom textures won't happen this way.

If you intend to create custom textures make sure to save them as BMP 16Bit RGB565! The only image editor i know that allows to do so is photoshop :/ sorry, hope everyone interested can find its ways.

Btw here's a little demo of the tool: https://www.youtube.com/watch?v=bLyL9-Jk5ks

This + the custom file loader allows me to live edit the textures which is amazing for testing 

I'll be writting a custom texture loader that allows to load them from the disk 
Thanks for such amazing tool,can't wait for release (i know,i can download tool now,but i'm noob in compiling and etc. stuff) 
Btw,what means "you're limited to 256 patterns of 4 colors" if i wanna create skin from PS4 game or CW/Homecoming i can't then?
Thanks.

Edit: I made a homecoming SM chest,it has no webs (working on it)
can you test it plz?
https://mega.nz/#!b851wJ7R!opjK7o5qn-bf ... F7cY55VFj8

There's a a space of 0x800 bytes for the colors on the PSXPVR file. Since it is 16bpp then there's a max of 0x400 colors there but the colors are being read 4 at once, that's what i call i pattern. Because of that the max number of patterns is 0x100 aka 256. If you want an ideia of what's a pattern in the actual image, set your pencil brush to a square brush of 2 px wide, this way you'll be using a pattern when paiting, BUT paint only odd and even rows and columns, or else you could be end up creating 4 new patterns.

With this i mean considering the pixel count start from 0, a pattern is ((1,1);(1,2);(2,1);(2,2)) if you paint this you'll be adding a pattern(if it already is not used) but if you paint ((1,2);(1,3);(2,2);(2,3)) you'll be creating 4 new patterns. 

Doesn't work way too many patterns. Yours uses 4746. Also i had to save again your texture.
Make sure to save it has a 16bit bitmap RGB565 and FLIP ROW ORDER as I showed in the video.
## Post #21
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-13T23:22:47+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from Rutabaga
>
> krystalgamer wrote:Update!!! 

My texture repacker is finally done  Check the code here: https://github.com/krystalgamer/spidey-tools
For real, it's a huge pain in the ass to create custom textures. You're limited to 256 patterns of 4 colors. Unless someone develops a plugin or a image editor that allows to keep count of them custom textures won't happen this way.

If you intend to create custom textures make sure to save them as BMP 16Bit RGB565! The only image editor i know that allows to do so is photoshop :/ sorry, hope everyone interested can find its ways.

Btw here's a little demo of the tool: https://www.youtube.com/watch?v=bLyL9-Jk5ks

This + the custom file loader allows me to live edit the textures which is amazing for testing 

I'll be writting a custom texture loader that allows to load them from the disk 
Thanks for such amazing tool,can't wait for release (i know,i can download tool now,but i'm noob in compiling and etc. stuff) 
Btw,what means "you're limited to 256 patterns of 4 colors" if i wanna create skin from PS4 game or CW/Homecoming i can't then?
Thanks.

Edit: I made a homecoming SM chest,it has no webs (working on it)
can you test it plz?
https://mega.nz/#!b851wJ7R!opjK7o5qn-bf ... F7cY55VFj8

First version of my texture loader is done 
Your skin appears on the video: [https://www.youtube.com/watch?v=VDDz1mZ8vSI](https://www.youtube.com/watch?v=VDDz1mZ8vSI)
I won't release now since there's a weird bug where the costume gets reseted, after i fix it, everyone will be able to use it
## Post #22
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-07-14T05:21:30+00:00
- Post Title: Re: Spiderman custom PVR format

Amazing,thanks for all your hard work. 
My texture looks strange btw (looks like i should make a total revamp)
And is there any chance for export/import models or maybe mod the hud head (spidey's head)?
Thanks.
## Post #23
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-07-31T14:27:05+00:00
- Post Title: Re: Spiderman custom PVR format

Custom texture loader is finally released!
[https://www.youtube.com/watch?v=fZ5rSIQ6ZuA](https://www.youtube.com/watch?v=fZ5rSIQ6ZuA)

Everything is explained in the video. Thanks everyone for the help!
## Post #24
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-01T16:27:20+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from krystalgamer
>
> Custom texture loader is finally released!
https://www.youtube.com/watch?v=fZ5rSIQ6ZuA

Everything is explained in the video. Thanks everyone for the help!
Amazing,btw,do you still have plans about Model Extractor?
## Post #25
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-08-01T17:29:02+00:00
- Post Title: Re: Spiderman custom PVR format

If you have some free time now, maybe try to work on font replacer and text replacer :p
## Post #26
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-08-07T11:13:12+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from ikskoks
>
> If you have some free time now, maybe try to work on font replacer and text replacer :p

From what i've seen the font is actually a bitmap which contains the letters in sequential order since it's loaded through the same function as the other bitmaps. Now the text replacer is actually easy to do, sadly the strings are in the exe(except the map notes). In fact i was able to do even more, i can now render more strings in the game 

[https://www.youtube.com/edit?o=U&video_id=V-HVpzkJAHg](https://www.youtube.com/edit?o=U&video_id=V-HVpzkJAHg)
## Post #27
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-08-07T22:29:21+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from krystalgamer
>
> https://www.youtube.com/edit?o=U&video_id=V-HVpzkJAHg

Cool.  But the link is broken. Is it possible to replace strings which are longer than original?
## Post #28
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2017-08-24T12:18:57+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from ikskoks
>
> krystalgamer wrote:https://www.youtube.com/edit?o=U&video_id=V-HVpzkJAHg

Cool.  But the link is broken. Is it possible to replace strings which are longer than original?
Sorry, completly forgot about this: [https://www.youtube.com/watch?v=V-HVpzkJAHg](https://www.youtube.com/watch?v=V-HVpzkJAHg)
Yes you can.
## Post #29
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-09-16T20:20:37+00:00
- Post Title: Re: Spiderman custom PVR format

@krystalgamer, do you plan to create some tools to support export/import text from TRG/EXE files or edit FNT font files?
## Post #30
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2018-11-11T10:24:29+00:00
- Post Title: Re: Spiderman custom PVR format

> Reply from ikskoks
>
> @krystalgamer, do you plan to create some tools to support export/import text from TRG/EXE files or edit FNT font files?

I can already edit the text but not yet the fonts. Currently I'm busy with exams and other stuff but you can contact me so we can work it out.
krystalgamer#5397 on discord.
## Post #31
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2019-07-21T10:17:28+00:00
- Post Title: Re: Spiderman custom PVR format

New version of the custom texture loader is out!
Now much simpler and way efficient!

[https://www.youtube.com/watch?v=ykF8PP_FMd8](https://www.youtube.com/watch?v=ykF8PP_FMd8)
