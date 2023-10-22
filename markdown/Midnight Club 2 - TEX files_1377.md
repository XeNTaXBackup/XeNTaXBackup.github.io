## Post #1
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2005-07-06T13:17:32+00:00
- Post Title: Midnight Club 2 - TEX files

Hi all...
I would like to know if it is possible to have a pluggin to suport this format  .TEX files from the game Midnight club this .tex files are the texture format they use... Will be cool if you can make a pluggin to convert them to bmp or other... If you can plz take a look in the fill i attached sorry my bad english

  Peter
[t_roads_rainly_crosswalk04.rar](https://xentaxbackup.github.io/file/329_t_roads_rainly_crosswalk04.rar)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-06T13:49:52+00:00
- Post Title: Midnight Club 2 - TEX files

Use iRipper 1.8 

[http://toca.game-editing.net/](http://toca.game-editing.net/)
## Post #3
- Username: barti
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-06T15:14:05+00:00
- Post Title: Midnight Club 2 - TEX files

These .tex files are actually DDS files. (DXT5), without the DDS header. iRipper just saves a template header, appends to it the .text file data, and fills in the blanks in the template header.  

format of .tex:

uint{16} - width of image
uint{16} - heigth of image
uint{16} - type (26 = DXT5, 22 = DXT1, 14 = DXT3)
uint{16} - unknown (iRipper says number of mips, but doesn't save them in the new dds file) 

DDS file data (inserted at 128 (right after the template header)).
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-06T18:53:53+00:00
- Post Title: Midnight Club 2 - TEX files

Even so  I all time thought that the schedule in this game has the format... What I blind however
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-21T20:27:37+00:00
- Post Title: Midnight Club 2 - TEX files

It's worth to mention that there is a tools suite which supports converting TEX files to DDS or TGA:

> mcTex.zip - .tex to .tga or .dds texture converting tool.
>
> iripper.rar - iRipper, a tool that allows you to open the assets_p.dat file, extract it, view .tex textures, etc.

Here is the topic with download link [https://officialmc2.boards.net/thread/2 ... ools-suite](https://officialmc2.boards.net/thread/24/modding-tools-suite)
## Post #6
- Username: tempaccount555
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-07T12:25:04+00:00
- Post Title: Midnight Club 2 - TEX files

I think that I have found a good solution for converting TEX to TGA and TGA to TEX.
Here is the instruction:

1. Download Noesis [https://richwhitehouse.com/index.php?co ... project=91](https://richwhitehouse.com/index.php?content=inc_projects.php&showproject=91)
2. Go to this post [https://zenhax.com/viewtopic.php?p=53920#p53920](https://zenhax.com/viewtopic.php?p=53920#p53920)
3. Download the script and save it as "tex_angelstudios_tex.py".
4. Copy script to "\noesisv4459\plugins\python" directory.
5. Run Noesis. Load TEX file to the program.
6. Right click on TEX file and choose "Export" option. Save it as TGA.
7. Edit TGA file in GIMP or any other similar program.
8. Open TGA file in Noesis.
9. Right click on TGA file and choose "Export" option. Save it as TEX file.
10. Replace TEX file in game and test your results.


Here is also article about TEX file for reference
[http://wiki.xentax.com/index.php/Midnight_Club_TEX](http://wiki.xentax.com/index.php/Midnight_Club_TEX)
