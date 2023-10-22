## Post #1
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2009-09-22T14:20:14+00:00
- Post Title: The Elder Scrolls: Arena .RCI Animation File

Does anyone know how to open the .RCI files from The Elder Scrolls: Arena?
What i do know is that they are 5 frame animation files 320x100
image data, uncompressed, without any header information.
As far as i know there is no program that will open them.

There is a sample file attached.
[WATERANI.rar](https://xentaxbackup.github.io/file/2364_WATERANI.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-09-27T21:53:38+00:00
- Post Title: The Elder Scrolls: Arena .RCI Animation File

I'll take a look. Have you got some more ? You've choosen Water, which is not very specific in terms of pixeling.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-09-27T22:34:32+00:00
- Post Title: The Elder Scrolls: Arena .RCI Animation File

Okay, never mind.

I believe these to be 5 frames of 160x100 saved after one another, 16 bit colour depth. 

See my animation. The palette is an approximation, as I don't know the original one.
[Untitled-2.gif](https://xentaxbackup.github.io/file/2388_Untitled-2.gif)
## Post #4
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2009-09-28T02:05:33+00:00
- Post Title: The Elder Scrolls: Arena .RCI Animation File

The water actually has a lighter color to it, here is the link for a screenshot:
[http://www.thehouseofgames.net/files/e/ ... rena-7.jpg](http://www.thehouseofgames.net/files/e/elder_scrolls_arena/elder_scrolls_arena-7.jpg)

BTW, how did you get the images to display?
## Post #5
- Username: StarQuake
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-09-28T05:43:25+00:00
- Post Title: The Elder Scrolls: Arena .RCI Animation File

Simple, I opened it with a hex editor ans saw it was a continuous graphics file. I then loaded it up as a raw file in Adobe Photoshop, first as 8 bit. As 8 bit it could have a size of 400x400. It looked already something like water. But I noticed a repeating pattern every 80 bytes in a row, and set the width to 80. Still not good, then to 160 - close but not quite. I then realized it had to be 16-bit (so two bytes per colour). This looked good and showed frames of 160x100, 5 of them beneath eachother. I simple copied and pasted each of them in a animation GIF to animate. 

Perhaps the game has a palette file stored somewhere for you to use?
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-09-28T20:52:37+00:00
- Post Title: The Elder Scrolls: Arena .RCI Animation File

Okay, got it. I have the game myself, so I could check for a palette file. 

There are a number of files that end with .COL. This is what you need.  
These are 256 colour palettes, preceded with an 8 byte header for us to ignore. 

Also, the images we have are actually 8-bit bitmapped 256-colour of 320x100 in size. 

We need the PAL.COL files for the .RCI files

Using a good Hex editor: remove the first 8 bytes of PAL.COL and save it as PAL.COL.ACT

Using Photoshop:

1. Open a .RCI file as RAW, and specify 320x500 (the whole image of 5 frames), channels: 1 of 8-bit, headersize 0. 
2. Go to Image->Mode and select Indexed colours
3. Go to Image->Mode and Color Table. There select Load Table and point to PAL.COL.ACT. Done you now have the correct colours. 

This leaves you with all frames. You can cut out each frame of 320x100 yourself and store them for use. 

Here's the result for WATERANI.RCI and LAVAANI.RCI



WATERANI.RCI.jpg (176.98 KiB) Viewed 153 times





LAVAANI.RCI.jpg (196.6 KiB) Viewed 152 times



Here's my animation of WATERANI.RCI:



WATERANI.RCI.gif (30.94 KiB) Viewed 151 times



Note how the colours match your screenshot:



WATERANI.RCI.MATCH.jpg (199.76 KiB) Viewed 150 times
## Post #7
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2009-09-29T00:19:27+00:00
- Post Title: The Elder Scrolls: Arena .RCI Animation File

Awesome work and a great explanation.
Thank you very much for your help!
