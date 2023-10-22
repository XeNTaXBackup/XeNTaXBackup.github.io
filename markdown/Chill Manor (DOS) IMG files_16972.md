## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2017-09-06T08:25:22+00:00
- Post Title: Chill Manor (DOS) IMG files

Ages ago on here a program was made that converted sprites from the .IMG files of I.M.Meen into BMP. Chill Manor uses a very VERY similar setup, even many of the same formats, given it was by the same (long defunct) company, Animation Magic, and the game using a significantly updated version of the engine. Among the things that were updated, was the IMG container, now featuring mipmaps and textures and sprites that were greater than 64x64 giving the graphics a higher level of detail than was previously shown in I.M.Meen.

Long story short, it broke the program... significantly. There are now extra bits of data per graphic entry that defines height (and possibly width) as well as, as it seems, sub-textures (for mipmaps). Even 64x64 tiles, used in ceiling and floor textures are broken due to the extra data. Aside from these changes, however, the format is the same. Minor changes make the difference, eh? Kinda sucks to have this one sitting for so long and being close but never finished.

[Provided here in this link are examples of IMGs from both I.M.Meen and Chill Manor, as well as a BMS script for extracting files from both. Also, provided is IMG2BMP as well as edited source code of IMG2BMP that has the Chill Manor palette programmed in. Never got far with the format. The program was written in Delphi.](https://file.io/0wYkZt)

Maybe someone can kindly put this old beast to rest, heh.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2017-09-16T08:04:26+00:00
- Post Title: Chill Manor (DOS) IMG files

For reference, this is how the first texture looks in the sample Chill Manor IMG after being processed ingame. Used TiledGGD to grab it. Typical wall textures are 64x128. This was easy to grab given it is without masking. If needed, can attach the raw palette to this thread.
[ChillIMAGES1.png](https://xentaxbackup.github.io/file/13318_ChillIMAGES1.png)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2017-11-26T21:14:51+00:00
- Post Title: Chill Manor (DOS) IMG files

Still no progress elsewhere on this, any help appreciated.
