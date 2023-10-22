## Post #1
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-05-16T18:40:33+00:00
- Post Title: Lara Croft and the Temple of Osiris Compressed DRM (CDRM)

Hi all
I want to open a file and edit it to Then again Repack.
I am sure compressed with zlib
Please help
thanks
## Post #2
- Username: A20Group
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-16T20:03:42+00:00
- Post Title: Lara Croft and the Temple of Osiris Compressed DRM (CDRM)

Compression shouldn't be the problem. CDRM files can be read uncompressed by altering the flag. The problem is that repacking TIGER files is easier said than done. I don't think it's worth the time since most of the TIGER file may have to be rebuilt due to dynamic sharing of sections across DRM files (at least that's how I figured it worked from TR2013).
## Post #3
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-05-18T13:35:23+00:00
- Post Title: Lara Croft and the Temple of Osiris Compressed DRM (CDRM)

plz give me zlib comperesor.My zlib dont work properly.
i think that the CDRM Files in the tiger file is the same PCD9 file but in copmersot form.
thanks
## Post #4
- Username: A20Group
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-18T14:08:41+00:00
- Post Title: Lara Croft and the Temple of Osiris Compressed DRM (CDRM)

> Reply from A20Group
>
> plz give me zlib comperesor.My zlib dont work properly.
i think that the CDRM Files in the tiger file is the same PCD9 file but in copmersot form.
thanks
You don't need to compress the DRM files. I don't know what tools you are using but... The current tools ONLY extract the DRM headers with an additional tool which extracts the data. CDRM format is nothing like PCD9 files. CDRM files are simply DRM files in compressed blocks.

Again... Packing DRM files may be a tedious task thus nobody ever wrote any repackers but I wrote an injector that does not support DRM files due to the nature of them sharing sections.
## Post #5
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-05-18T14:27:10+00:00
- Post Title: Lara Croft and the Temple of Osiris Compressed DRM (CDRM)

> Reply from Gh0stBlade
>
> A20Group wrote:plz give me zlib comperesor.My zlib dont work properly.
i think that the CDRM Files in the tiger file is the same PCD9 file but in copmersot form.
thanks
You don't need to compress the DRM files. I don't know what tools you are using but... The current tools ONLY extract the DRM headers with an additional tool which extracts the data. CDRM format is nothing like PCD9 files. CDRM files are simply DRM files in compressed blocks.

Again... Packing DRM files may be a tedious task thus nobody ever wrote any repackers but I wrote an injector that does not support DRM files due to the nature of them sharing sections.

i want to edit some texture in lara?
in your openion what shoud i do?
## Post #6
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-22T10:57:52+00:00
- Post Title: Lara Croft and the Temple of Osiris Compressed DRM (CDRM)

To my knowledge there is no direct way of manipulating the textures. In previous games, fans used a program called TexMod which is some form of hook that allows replacing certain textures. That said, it is not compatible with DX11 which Lara Croft and the Temple of Osiris utilises. I believe that someone might have made a DX11 hook and a member found it and posted in the Noesis thread on tombraiderforums. I recall a website modifying Lara's top to pink but I cannot confirm if it's real or not.

The 3 Options would be:

1. Wait until a DX11 compatible Texmod is created.
2. There is a possibility that modified textures can be re-injected back into the DRM safely if the size is less than or equal to the original texture.
3. Creating a patch bigfile is most likely the most effective solution since only the patch bigfiles are modified thus those patch files are easier to download and revert any changes or corruptions which may occur.

Those are the only way around replacing any textures that i can think of. PCD files are simple DDS files with a custom header so there are already plenty of tools to modify DDS files. However, the header may need to be rebuilt but since it's so known already it's not much of a problem.

Because there are no propper Bigfile tools written for the new engine it just makes things more difficult.

Regards
