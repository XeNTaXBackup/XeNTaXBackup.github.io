## Post #1
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-12T03:25:25+00:00
- Post Title: Megaman Legends 2

Before anyone comments about the Megaman 64 ROM, I will just say this:
It does not apply here. I'm talking about the sequel to that game, of which there is no N64 version.

There are 3 versions of this game that I'm aware of.

The PSX version, the PSP rerelease(which is likely the same as the PSX game), and the rare PC port... which no one owns and is not for sale anywhere on the planet, nor can it be found on the intertubes...

Simply put, I want the models in a format I can use.

I've attached a file which I am almost certain at 96% is Roll's model. It is the file directly before the similarly named file that contains her texture. (PL01T::PL01P000)

I'm seeing a lot of familiar patterns in the file, but without knowing what to do with them, I can't say I know what they are...

I'm seeing things that occur in 3's with a trailer of 00, this could be some sort of key or index to something, it could be a vertex lighting chart or I could be way off... All I really care about are verts and UVs...


There are files I seem to be missing/files that are encrypted somehow on the disc, since I know there are more than this number of models... I'm thinking perhaps enemies and NPCs are packed with area map data, as with many PSX era games.

Also, while some textures are easily obtainable others seem to be in packages and/or encrypted as they do not display correctly in GGD, which can view the unencrypted ones with no problem.

I see places in this file that seem to be Bone/Weight tables, or possibly vertex/linkage tables, as they seem to contain large amounts of data in one chunk, immediately followed by a series of 4 byte patterns... This is similar to structures I've seen in other games, but like I said, I don't know what to do with any of this, so I need the help of someone slightly more experienced.


Try your eyes friends, I hope for the best and expect the worst.
[PL01P000.rar](https://xentaxbackup.github.io/file/3034_PL01P000.rar)
## Post #2
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-19T00:17:47+00:00
- Post Title: Megaman Legends 2

Ok, it seems that the PL01P000 file, at the offset of 0x0978, is the vertex color/lighting information for one of the LoD models, likely the largest one... or the smallest one... Hard to tell just yet.

It lasts to 0x0E18. 

0x0080 seems to be a header of some sort. 

I'd really love some help with this, I can't really find a good place to start looking for the vertex info...
## Post #3
- Username: FallenAngelRiku
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 30, 2011 1:28 pm
- Post datetime: 2011-12-09T00:38:18+00:00
- Post Title: Megaman Legends 2

Sorry for posting on an outdate topic, but I recently downloaded Megaman Legends 2 PC version, the rare japanese one, (NO emulators) I always wanted to have the models/maps from ML2, not the first one, those models are soo blocky, anyone willing to help me? I could not rip any 3d models with 3dripperDX, 3D via printscreen & gameassasin, anyone wants to help me? If so, I can upload maps/models files from the DAT folder.
all the 3d models are stored on separate *.dat files
maps & models
It uses Open GL
you could help by writing a model/map converter/viewer, or giving me some tips on ripping 3d models.
## Post #4
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2012-03-15T18:11:39+00:00
- Post Title: Megaman Legends 2

> Reply from FallenAngelRiku
>
> Sorry for posting on an outdate topic, but I recently downloaded Megaman Legends 2 PC version, the rare japanese one, (NO emulators) I always wanted to have the models/maps from ML2, not the first one, those models are soo blocky, anyone willing to help me? I could not rip any 3d models with 3dripperDX, 3D via printscreen & gameassasin, anyone wants to help me? If so, I can upload maps/models files from the DAT folder.
all the 3d models are stored on separate *.dat files
maps & models
It uses Open GL
you could help by writing a model/map converter/viewer, or giving me some tips on ripping 3d models.

I'm afraid you've got it wrong.
It doesn't use OpenGL. If you view its dependency you'll see it loads DDRAW.dll but OpenGL32.dll, which indicates that it's rendering in DirectX7.
In other words, ripping models from MML2 PC version is definitely impossible for now.
## Post #5
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2012-03-15T18:14:56+00:00
- Post Title: Megaman Legends 2

I wonder if the PSP rerelease is emulatable or not. If it's ok with JPCSP, then we can rip models with OGLE.

Anyone got the MML2 PSP rom?

**EDIT**
PSP rom seems not working with the latest Jpcsp
Plus PSX emulators will resolve 3d scenes into flat mesh

So the only options left is either to wish that 3DXripper would support DX7,
or to look into the fileformat.
**EDIT**
