## Post #1
- Username: snv
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 17, 2011 12:04 am
- Post datetime: 2011-11-29T10:10:40+00:00
- Post Title: How does PSP palette and tile packing works?

I ripped a tileset, but palette has more than 256 colors and tiles are packed as 16x16 pixel chunks in a 256x256 textures.
## Post #2
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-29T22:00:27+00:00
- Post Title: How does PSP palette and tile packing works?

Please supply the following information:

Which game?
How did you get the files? (were they compressed or just somewhere in the file system)
Provide samples! (upload them somewhere)
Tell us what you know about the file format.



The PSP is pretty much a portable PS1/PS2, treat it as such and look for common file formats from those consoles
like TIM, TIM2, GIM. Some of them contain palette data.

Look out for eventual swizzled textures, they are saved that way to be optimized for the GPU.
## Post #3
- Username: snv
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 17, 2011 12:04 am
- Post datetime: 2011-11-30T07:26:07+00:00
- Post Title: How does PSP palette and tile packing works?

> Reply from 0xFAIL
>
> Please supply the following information:

Which game?
How did you get the files? (were they compressed or just somewhere in the file system)
Provide samples! (upload them somewhere)
Tell us what you know about the file format.
Popolocrois archives (p00/p10/p99 files). They contain map, packed together with tiles and NPC sprites. The palette itself stored as a 32-bit image, even with height and width. Pixels are 4-bit 512x512 array (16x16 tiles, each somehow selects it's own row inside palette). I believe, PSP selects palette during blitting. There is no standalone tiles, you will see in a PC or Amiga isometric games. Shame we cant rip this tileset, it's one of the best isometric tilesets you can find, beside Lunar Dragon Song tileset.

> Reply from 0xFAIL
>
> 
The PSP is pretty much a portable PS1/PS2, treat it as such and look for common file formats from those consoles
like TIM, TIM2, GIM. Some of them contain palette data.
I know about TIM, but it requires decompiling whole game engine to make a tileset extractor and still you'll have to assembly tiles into sprites by hand.

[](http://imageshack.us/photo/my-images/823/16474637.png/)
## Post #4
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-30T23:28:42+00:00
- Post Title: How does PSP palette and tile packing works?

So, what do you actually need? The palette data for the picture?
An image splitter to have each tile as an individual file?

Can you upload some of those archives or the pictures (and if they have a palette the palette too) to a filehost (like mediafire/megaupload/...)?


> I know about TIM, but it requires decompiling whole game engine to make a tileset extractor and still you'll have to assembly tiles into sprites by hand.
TIM is a file format, why decomile the entire game when the data is inside archive files?
## Post #5
- Username: snv
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 17, 2011 12:04 am
- Post datetime: 2011-12-02T06:22:13+00:00
- Post Title: How does PSP palette and tile packing works?

> Reply from 0xFAIL
>
> An image splitter to have each tile as an individual file?
Preferably with correct palette. That would be ideal for using them with RPGMaker-like package.

> Reply from 0xFAIL
>
> Can you upload some of those archives or the pictures (and if they have a palette the palette too) to a filehost (like mediafire/megaupload/...)?
Just search "popolocrois psp cso".

> TIM is a file format
Does TIM have info how to combine tiles into sprites or how to select palette?

> why decomile the entire game when the data is inside archive files?
How do you interpret them? Especially without a working emulator/debugger? With debugger researcher can damage interesting field and see what happen (yeah! evil experiments on living things).
