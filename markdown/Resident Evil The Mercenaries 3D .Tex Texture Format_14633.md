## Post #1
- Username: scottie304
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 08, 2016 4:29 am
- Post datetime: 2016-07-13T01:19:46+00:00
- Post Title: Resident Evil: The Mercenaries 3D .Tex Texture Format

Hello! I've been trying to crack open these texture files for a while but to no avail.

I was wondering if anyone has figured out how to convert these .tex texture files yet to a different format.

The game uses MT framework Mobile and so far I've been able to import the models using the Monster Hunter 4 Importer script but have found nothing that works for the textures.

If anyone wants a go at figuring this out here are some .tex file examples and the monster hunter 4 import script:
.tex examples - [https://www.dropbox.com/s/bpeqil9pxihhw ... s.rar?dl=0](https://www.dropbox.com/s/bpeqil9pxihhwr6/.TEX%20Examples.rar?dl=0)
Monster hunter 4 Import Script - [viewtopic.php?f=16&t=11910](http://forum.xentax.com/viewtopic.php?f=16&t=11910)

Any help is appreciated
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-13T12:21:55+00:00
- Post Title: Resident Evil: The Mercenaries 3D .Tex Texture Format

The problem is the texture data does not look like standard DDS data. The pixel data must have been customised for the 3DS, perhaps something from the 3DS SDK is required or some compression is applied (unlikely).
