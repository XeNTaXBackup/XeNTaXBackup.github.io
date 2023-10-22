## Post #1
- Username: sprintstar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 10, 2007 4:42 am
- Post datetime: 2007-12-10T13:22:11+00:00
- Post Title: How to unpack the file pictures of the PFF? X-Files The Game

There is a game X-Files The Game published by Hyperbole Studio, in 1998.
Unable to find the correct program to unpack / packaging graphics. [http://xfiles.cwx.ru/tmp/10.12.07/X7.PFF](http://xfiles.cwx.ru/tmp/10.12.07/X7.PFF) (700kb~)
One program (Dragon UnPACKer) unpack graphics, but after editing images (Photoshop), it will need to somehow pack again in the format of PFF.
How can I find out which program to use?
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-12-17T08:17:39+00:00
- Post Title: How to unpack the file pictures of the PFF? X-Files The Game

This may be a longshot.....

but i notice that the PFF file there is actually an JPEG file with a small extended header.

so, what happens if you take the PFF header and attach it ontop of the resaved images? (using an hexeditor, just copy paste it)

[http://ihateui.com/pffheader.zip](http://ihateui.com/pffheader.zip)

it MIGHT work! , i have no idea, but its worth a try [/url]
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-17T08:46:34+00:00
- Post Title: How to unpack the file pictures of the PFF? X-Files The Game

> Reply from Strobe
>
> This may be a longshot.....

but i notice that the PFF file there is actually an JPEG file with a small extended header.

so, what happens if you take the PFF header and attach it ontop of the resaved images? (using an hexeditor, just copy paste it)

http://ihateui.com/pffheader.zip

it MIGHT work! , i have no idea, but its worth a try [/url]

it's STROBE  !
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-12-17T09:20:46+00:00
- Post Title: How to unpack the file pictures of the PFF? X-Files The Game

its me  atleast a little bit! until i run away and hide again!
## Post #5
- Username: sprintstar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 10, 2007 4:42 am
- Post datetime: 2007-12-17T19:34:11+00:00
- Post Title: How to unpack the file pictures of the PFF? X-Files The Game

Altogether, received a reply from a man involved in the development of the game!  
But as far as I understood, the programs for packing / unpacking no ..   


PFF stands for "PICT Flick File." It's a custom format HyperBole Studios developed for storing animations, somewhat similar to GIF files. PICTs are Apple-format images (see [http://en.wikipedia.org/wiki/PICT](http://en.wikipedia.org/wiki/PICT)). Here's some documentation that describes the format of PFF files.

|______________________________________________________________________________|
| 32-bit value: Number of PICTs in the structure                                     |
|______________________________________________________________________________|
| Array of 32-bit values, size (number of PICTs + 1): The absolute offsets of each PICT from the   |
|                                 beginning of the file. The last offset value is used to determine the size of the last PICT in the structure.
|______________________________________________________________________________|
| Array of 32-bit values, size (number of PICTs): The duration (in milliseconds) associated with   |
|                             each PICT (for animations)                       |
|______________________________________________________________________________|
| variable length PICT data                                                    |
|______________________________________________________________________________|
