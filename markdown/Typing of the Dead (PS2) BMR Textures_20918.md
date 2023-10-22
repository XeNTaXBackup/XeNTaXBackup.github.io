## Post #1
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2019-08-06T08:48:46+00:00
- Post Title: Typing of the Dead (PS2) BMR Textures

Hi everyone,

So I came across a copy of the PS2 version of Typing of the Dead and started looking at the file structure which to my surprise was a bit different than the usual HotD2 and TotD PC versions.  Files in the root directory are stored in .HAB containers (which was easy to extract) but two new folders appeared which I've never seen before, polmdb and texbmr.  Files are then stored in .HAB containers again and extracting these yielded separate part names in .mdb format and textures in .bmr format (something the normal HotD2 decrypted files didn't do).  I figured I'd tackle the bmr textures first but didn't get very far.  I see offsets in the file header for the data and file size and maybe a color palette prior to it but couldn't come up with anything solid. I've attached the hab files for Rogan's HotD1 model and texture data.  Hopefully someone with  more expertise can shed some light as this might be the way to finally extract the HotD2 models.

QuickBMS script for HAB
[viewtopic.php?f=10&t=9521](https://forum.xentax.com/viewtopic.php?f=10&t=9521)

Regards,
[totdzp.zip](https://xentaxbackup.github.io/file/16574_totdzp.zip)
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-08T12:25:39+00:00
- Post Title: Typing of the Dead (PS2) BMR Textures

well. the palette is easy to deshuffle, but the bitplane is compressed. do i wanna figure that out?
## Post #3
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2019-08-09T17:07:35+00:00
- Post Title: Typing of the Dead (PS2) BMR Textures

I kind of figured it was compressed, was hoping it wasn't.  My feeling tells me that the data for the mdb files are also compressed.
