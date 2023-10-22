## Post #1
- Username: Henderson
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 10, 2011 8:01 pm
- Post datetime: 2013-12-15T10:08:06+00:00
- Post Title: Silent Hill 4 .BIN Files PS2 Version

Hello, I'm trying to visualize this file but no program opens.
Could anyone help?

[http://www.mediafire.com/download/9z59t ... _title.bin](http://www.mediafire.com/download/9z59tv63756r79i/snap_title.bin)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-15T11:23:09+00:00
- Post Title: Silent Hill 4 .BIN Files PS2 Version

[](http://www.pic-upload.de/view-21631349/SilentHill.jpg.html)
## Post #3
- Username: Henderson
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 10, 2011 8:01 pm
- Post datetime: 2013-12-15T12:27:18+00:00
- Post Title: Silent Hill 4 .BIN Files PS2 Version

Thanks

I want to edit the image, you know how I can repack the edited file in the original image?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-15T13:37:59+00:00
- Post Title: Silent Hill 4 .BIN Files PS2 Version

nope.

edit: you could google for SH Texture Explorer.

But the version I got crashes on your .bin sample.

Maybe it needs as an input the games texture path (but I don't owe the game).
## Post #5
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-07-15T17:57:10+00:00
- Post Title: Silent Hill 4 .BIN Files PS2 Version

You can extract and replace textures in this file with: Console Texture Explorer
 Open CTE, open snap_title.bin file, click on "load ini" button and create this file:
Code: Select all[items_count]
count=1
[item_0]
name=logo
platform=PS2
offset=229648
width=512
height=512
BPP=8
mipmaps=-1
palette_offset=525584
swizzling=Enabled

 click on "logo" on right side, click "settings - alpha" - you will see texture, click "export - tm2"
 open and edit this texture with "OPTPiX iMageStudio for PS2" (same tutorial: http://youtu.be/fJCtNjcGALo?t=30s)
 open CTE again, click "import", select your new texture (saved as 8bpp with alpha channel, not bigger than original TIM2 texture) and press "save" button.
 done, you can replace file in ISO with HEX or with any other method - new texture will work on original console and anywhere else too. There is more textures in this file, you need to search offsets by your own/by your own tools. PC tools like "SH Texture Explorer" will not help you with anything, but maybe will help with xbox original version hah.
[sh4logops2.png](https://xentaxbackup.github.io/file/7586_sh4logops2.png)
