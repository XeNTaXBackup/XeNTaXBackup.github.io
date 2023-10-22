## Post #1
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-10-08T18:37:54+00:00
- Post Title: Nippon Ichi game (PS2)

The contents of this post was deleted because of possible forum rules violation.
[mk_ 24809569_xxxx.rar](https://xentaxbackup.github.io/file/896_mk_ 24809569_xxxx.rar)
## Post #2
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-10-11T18:26:16+00:00
- Post Title: Nippon Ichi game (PS2)

I hope anyone can help me
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-12T19:15:54+00:00
- Post Title: Nippon Ichi game (PS2)

Well, I've looked at it, but perhaps this is more a question for people like Xela. What I can gather from the data file, is that all graphics seem saved one after the other, but I haven't found an index part.
## Post #4
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-10-15T18:44:33+00:00
- Post Title: Nippon Ichi game (PS2)

Not really understand about index and Xela part, is that hard to do it?
I really hope you can help me Mr.Mouse
## Post #5
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-15T19:54:48+00:00
- Post Title: Nippon Ichi game (PS2)

I have this game, and  there is separeted file "sector.h" that has filenames and perhaps offsets.

I don't know what to look for in the file, but do know that the game is made from 3d tilemaps, they are probably just a 2d map that the game uses to create the 3d conterpart.

It does have 3d models but it mainly uses animated sprites

ps: What is Xela?
2: the two first offsets overlap so I guess they are relative from the last offset
[SECTOR.RAR](https://xentaxbackup.github.io/file/923_SECTOR.RAR)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-15T20:02:46+00:00
- Post Title: Nippon Ichi game (PS2)

> Reply from alera
>
> I have this game, and  there is separeted file "sector.h" that has filenames and perhaps offsets.

I don't know what to look for in the file, but do know that the game is made from 3d tilemaps, they are probably just a 2d map that the game uses to create the 3d conterpart.

It does have 3d models but it mainly uses animated sprites

ps: What is Xela?
2: the two first offsets overlap so I guess they are relative from the last offset

Thanks, will take a peek. 

Xela is a forum regular and part of the team here, so a person!
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-15T20:37:25+00:00
- Post Title: Nippon Ichi game (PS2)

After taking the peek in the sector.h file this is clear:

```
// For each entry (0x28 bytes in lenght)

byte {0x20} - Filename (null-terminated)
uint32 - Offset block (blocks are 0x800 in size)
uint32 - Actual size in bytes


```


The file lists 822 files. However, at first sight they do not seem to refer to the files in the data2.dat file. The last entry in the sector.h file refers to a block beyond the total size of data2.dat, inferring that it must be a table of another file.
## Post #8
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-15T20:59:00+00:00
- Post Title: Nippon Ichi game (PS2)

hmm there is only one more visible file in the dvd and that is sndpak.pak.

How exacly do these blocks work? is the data 2048 byte aligned?
The data file is 143mbs long which seems plenty for low resolution textures
and models.
Is this the data2.dat you are talking about? The only other option I can think of is a hidden track on the dvd.

> Xela is a forum regular and part of the team here, so a person!

Oh! i see :)
## Post #9
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-10-16T05:38:42+00:00
- Post Title: Nippon Ichi game (PS2)

Forgive me Mr.Mouse the reson why sector.h file dont match maybe because the one i upload is not Makai data.dat (maybe disgaea 1)
I uploaded new data.dat this time from makai kingdom

[http://rapidshare.de/files/36922696/DATA.7z.html](http://rapidshare.de/files/36922696/DATA.7z.html)

Alera data2.dat in first post is data.dat i change the name and that the one cause confusion.

and i also attach sector.h file from makai, disgaea, disgaea 2

btw because each sector is different so then must you check all data.dat from each game to?
[sector.zip](https://xentaxbackup.github.io/file/925_sector.zip)
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-16T06:17:59+00:00
- Post Title: Nippon Ichi game (PS2)

Excellent! Now we have a match. The Disgaea sector matches the first data2.dat perfectly. Now I can write a script!
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-16T07:58:36+00:00
- Post Title: Nippon Ichi game (PS2)

```
# By Mr.Mouse
# Note that this needs the right SECTOR.H file in the same
# folder as the DAT file! 
# --------
# Open the file sector.h in the same folder as the archive (FileDir) as file 1
Open FileDir sector.h 1 ;
# Calculate the size of the sector.h file
SavePos ST 1 ;
GoTo EOF 1 ;
SavePos ED 1 ;
# The last entry is extra, we don't need it, so set the max size 
Math ED -= 40 ;
# Go to start in sector.h
GoTo ST 1 ;
# Start the loop
Do ;
# Save the current offset and then get a null-terminated string
SavePos PE 1 ;
Get FileName String 1 ;
# There are 32 bytes reserved for a filename, so jump to the position after that
Math PE += 32 ;
GoTo PE 1 ;
# Get the block offset (blocks are 2048 in size) and size
Get BlockOff Long 1 ;
Get Size Long 1 ;
# Calculate the actual offset in the DAT file
Math BlockOff *= 2048 ;
Log FileName BlockOff Size 0 0 ;
# What position are we now at in the sector.h?
SavePos PE 1 ;
# Is this still less than the end (ED) of our sector.h? If no, quit. 
While PE < ED ;

```


You can run this one on the dat file, follow the guidelines in the script. 
It's a MexScript, not compiled to BMS. So use the correct tool in MexCom (Run MexScript On...).
[dat.zip](https://xentaxbackup.github.io/file/926_dat.zip)
## Post #12
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-10-16T09:37:01+00:00
- Post Title: Nippon Ichi game (PS2)

Thank you Mr.Mouse the script can open Disgaea, Disgaea 2 and Makai data.dat

But i kind a confuse with file inside this, i dont know how see the pic
Can you help me with this Mr.Mouse?

The file inside is  .chr  .dat  .mda  .pos  .tx2
[file.rar](https://xentaxbackup.github.io/file/927_file.rar)
## Post #13
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-10-16T14:00:54+00:00
- Post Title: Nippon Ichi game (PS2)

the main purpose of scripts are usually to unpack files,when its done you may have custom formats whose not about unpacking method...my 2cents..
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-16T16:52:15+00:00
- Post Title: Nippon Ichi game (PS2)

> Reply from LustD
>
> Thank you Mr.Mouse the script can open Disgaea, Disgaea 2 and Makai data.dat

But i kind a confuse with file inside this, i dont know how see the pic
Can you help me with this Mr.Mouse?

The file inside is  .chr  .dat  .mda  .pos  .tx2

Questions about specific file formats such as graphics and sounds go in the other forums (graphics, sounds etc).
## Post #15
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-16T19:28:06+00:00
- Post Title: Nippon Ichi game (PS2)

I have only loaded one image so I still don't fully understand the format

short Width(has to be divided by 2) 
short Height
short was 16 so it could be palette size
short was 2058... no idea
short offset to palette, it was 16 so it could also be the palette size
short was 1 :P
padding to 16
and the next 64 bytes is the actual palette (R, G, B + 0x80)
then the picture data
[bg002.png](https://xentaxbackup.github.io/file/930_bg002.png)
## Post #16
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-10-16T20:37:53+00:00
- Post Title: 

I see Mr.Mouse thanks.

Alera what program did you use to open the file?
And this is file that i upload i hope you can help me with this
[http://rapidshare.de/files/37008514/aw.rar.html](http://rapidshare.de/files/37008514/aw.rar.html)
## Post #17
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-16T22:49:09+00:00
- Post Title: 

The program was one I made but it only opens that one specific image so it will be useless to you as it is :)

I do not have a registrated version of mexcom and can't run the scrip mr mouse provided, I will try to see if I can understand it can code my own

if successful, I will create a program to view the images that actualy works(well hopefuly)
