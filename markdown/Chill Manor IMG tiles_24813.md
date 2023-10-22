## Post #1
- Username: MartinVole
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 15, 2016 11:15 am
- Post datetime: 2021-12-07T06:15:25+00:00
- Post Title: Chill Manor IMG tiles

Hello, this is an old Doom-style DOS game, sequel to the edutainment game I. M. Meen by the internet infamous (and long defunct) company Animation Magic (You know, CDI Zelda and all that jazz). A tool was made ages ago on here for I.M. Meen that handled the RLE compression used for the sprites and masked textures and much of the framework of Chill Manor is the same... except Chill Manor has variable height textures greater than 64x64, and has MIP maps, both of which throws off the tools meant for I.M.Meen. The original tool was written in Delphi by WRS.

What is known: Much like I.M.Meen, textures and sprites stored in the IMG files is rotated 90 degrees, RLE compression is used for transparency on wall textures/sprites. Chill Manor still uses 64x64 textures for floor and ceilings, but with MIP maps that throws off the IMG2BMP tool for those as well.

Attaching examples of SKY and IMAGES from Level 1 and slightly altered source code for the I.M.Meen tool that includes the Chill Manor palette. Currently it crashes at the first instance of transparent textures and graphic output gets messy from the MIP maps. Also, 

Any help would be appreciated!

[https://drive.google.com/file/d/1FUPnOR ... sp=sharing](https://drive.google.com/file/d/1FUPnOR4iocosDKtNFgK1Z8V8wFq_OzWA/view?usp=sharing)

Considerable progress was made here by arcnor: [http://www.classicdosgames.com/forum/vi ... php?t=1634](http://www.classicdosgames.com/forum/viewtopic.php?t=1634)
Unfortunately the source may have been lost.
## Post #2
- Username: MartinVole
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 15, 2016 11:15 am
- Post datetime: 2022-02-01T19:00:19+00:00
- Post Title: Chill Manor IMG tiles

Seems the source was lost on arcnor's method, sadly.
