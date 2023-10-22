## Post #1
- Username: sinkillerj
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 17, 2008 11:13 pm
- Post datetime: 2020-01-03T04:06:44+00:00
- Post Title: Classic Entropia Universe Models (Gamebryo NIF)

I've been exploring the files of the old Entropia Universe (Before the drastic redesign and switch to CryEngine) after finding the archive here: [https://archive.org/details/EntropiaUniverse180208](https://archive.org/details/EntropiaUniverse180208)

Ultimately my goal is to decode the game enough to recreate the old world. Dragon Unpacker has no problem with the BNT archives, and the textures are easy as they are simply a mix of TGA and DDS disguised as DAT, but the model and terrain formats have been giving me some trouble and thus I come to the experts here.

Random example model: [https://drive.google.com/open?id=12pezK ... NrDbiAZqiJ](https://drive.google.com/open?id=12pezKzLHHuHiHfzkr8gv78NrDbiAZqiJ)

These are in NIF format which is a pretty widely used Gamebryo format, but NifSkope refuses to open them due to the unknown block type NiArkAnimationExtraData. 

As for the terrain I've no idea where to begin, it appears to be in chunks of TDF files, but this may be proprietary as I can find no info online.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-03T05:54:09+00:00
- Post Title: Classic Entropia Universe Models (Gamebryo NIF)

mesh.png (151.07 KiB) Viewed 199 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-03T08:35:14+00:00
- Post Title: Classic Entropia Universe Models (Gamebryo NIF)

> Reply from sinkillerj ↑Fri Jan 03, 2020 12:06 pm at Fri Jan 03, 2020 12:06 pm
>
> These are in NIF format which is a pretty widely used Gamebryo format, but NifSkope refuses to open them due to the unknown block type NiArkAnimationExtraData.There's a handful of NifSkope versions. This one is from 2010 iirc:
.



CEU-nif.png (58.54 KiB) Viewed 191 times

(There's unknown ints in the NiArkAnimationExtraData node, yes.)
## Post #4
- Username: sinkillerj
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 17, 2008 11:13 pm
- Post datetime: 2020-01-04T01:29:26+00:00
- Post Title: Classic Entropia Universe Models (Gamebryo NIF)

Thanks for the help guys, this community never ceases to impress me. I tried the version of NifSkope from your screenshot and sure enough it can handle the files fine, who woulda thought that ancient versions would be the solution...

Edit: For those jumping down this rabbit hole any version of NifSkope 1 appears to work, including the seemingly latest 1.2.0 Alpha 2, some files stil have issues that will need to be resolved but for the most part it works quite well: [https://github.com/niftools/nifskope/re ... 0140710.7z](https://github.com/niftools/nifskope/releases/download/v1.2.0-alpha.2/NifSkope-nightly-20140710.7z)

Now I just need to look more into how the terrain works. If anyone wants to take a stab at it here is one of the TDF files: [https://drive.google.com/open?id=17LmGr ... dgvt6sAr8t](https://drive.google.com/open?id=17LmGr1AbyAXY5rwYeJPn5Sdgvt6sAr8t)

As well as one of the TEZ files from TerrainEditZones, though this seams minor as there are not many of them compared to the terrain chunks, and I'm not quite sure how they correlate yet: [https://drive.google.com/open?id=1pEk75 ... Q6eHrxKhfg](https://drive.google.com/open?id=1pEk75vUpFvh5aqU5P3zYIuQ6eHrxKhfg)
