## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-10-28T22:29:40+00:00
- Post Title: Mercenaries 3D image data format

I'm having difficulty figuring out the format for a texture format used in Mercenaries 3D (and other 3DS Capcom titles). This is the image data for a 64x64 texture (I'm not sure, but I think it's supposed to have an alpha channel).
[CAPDEMO_BM_NOMIP_00.rar](https://xentaxbackup.github.io/file/7996_CAPDEMO_BM_NOMIP_00.rar)
## Post #2
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-10-29T15:47:36+00:00
- Post Title: Mercenaries 3D image data format

This should be a better example as I have a hunch how it's supposed to look like. I think it's a low res version of this logo : [http://nintendoartwork.com/gallery/resi ... sc-usa.jpg](http://nintendoartwork.com/gallery/resident-evil-mercenaries-3d/resident-evil-mercenaries-3d-logo-ntsc-usa.jpg)

Resolution is 512x256. If you read it as RGBA (one byte per channel), you get something which is somewhat similar, but the pixel order is really weird.
[title_e_ID_HQ.rar](https://xentaxbackup.github.io/file/7997_title_e_ID_HQ.rar)
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-10-30T02:28:29+00:00
- Post Title: Mercenaries 3D image data format

I ran into these in RE6 and RE:Revelations on the PS3 version of the games. When the textures for this ID type are square and power of two, they are Morten Z-order swizzled. However, when not square, they are still some kind of Z-order swizzle but I was never able to figure out a good algorithm for it. I even used a non-recursive subdivision algorithm to generate Z-order mappings (it's easy, start with a box, continuously divide box size by two putting them in a queue until you get 2 x 2 or smaller, then you generate mapping), but it didn't work.

In fact, if you divide your image into 2 256x256 images, and run Morten on them, you definitely see portions of text.



Fortunately, these texture types were only used for interface textures so screw them lol.
## Post #4
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-10-30T13:03:16+00:00
- Post Title: Mercenaries 3D image data format

Thanks for the info. Unfortunately, all textures for MT Framework Mobile games seems to be using this texture format. Maybe I should move onto another project instead. I've tried to deal with swizzled textures in the past and they're a bit of a pain.
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-10-30T21:06:23+00:00
- Post Title: Mercenaries 3D image data format

I worked on getting the meshes early last month. I decided to put it aside since I didn't get round to figuring out what was wrong with the textures. The files you uploaded do look like raw argb of some kind. They also lack the TEX header for some strange reason which the files I have did have those. The ones with TEX headers look like some form of DDS file, possibly 4bit? Not sure.

Mesh format is simple, pretty much the same as RE6. Some small alterations that's all.



Regards.
