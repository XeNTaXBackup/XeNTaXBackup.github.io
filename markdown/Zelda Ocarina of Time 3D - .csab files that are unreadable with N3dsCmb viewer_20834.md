## Post #1
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-07-19T21:30:45+00:00
- Post Title: Zelda Ocarina of Time 3D - .csab files that are unreadable with N3dsCmb viewer

[https://anonymousfiles.io/bvKVBn9W/](https://anonymousfiles.io/bvKVBn9W/)
[https://anonymousfiles.io/42Bt3Ap5/](https://anonymousfiles.io/42Bt3Ap5/)
These .csab files cannot be loaded with any version of N3dsCmb viewer.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-02T21:30:43+00:00
- Post Title: Zelda Ocarina of Time 3D - .csab files that are unreadable with N3dsCmb viewer

can't serve with .csab - using hex2obj (view link in my sig) for getting a mesh:
.



zelda_horse.zar-SM_01.png (50.35 KiB) Viewed 108 times
## Post #3
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-08-18T13:56:20+00:00
- Post Title: Zelda Ocarina of Time 3D - .csab files that are unreadable with N3dsCmb viewer

bump
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-18T19:43:34+00:00
- Post Title: Zelda Ocarina of Time 3D - .csab files that are unreadable with N3dsCmb viewer

> Reply from andree ↑Sat Jul 20, 2019 5:30 am at Sat Jul 20, 2019 5:30 am
>
> 
These .csab files cannot be loaded with any version of N3dsCmb viewer.Is there any .zar file with .csab included which CAN be loaded by N3dsCmb viewer with anim played?

btw: I got rid of the exception occuring on selecting a .csab anim but the horse still doesn't move.
(Playing doesn't seem to be implemented nor the building of frame list data.)

You might read xdaniels post here (from 4 years ago):
[https://gbatemp.net/threads/n3dscmbview ... st-5667609](https://gbatemp.net/threads/n3dscmbviewer.397275/#post-5667609)

horse skeleton data, logged by viewer (shortened):

```

-- CmbChunk --
Filesize: 0x11780
Number of chunks: 0x6, Unknown: 0x0
Cmb name: epona
Number of indices: 0xC24
Indices offset: 0x6B0C, Texture offset: 0x8380

-- SklChunk --
Number of bones: 0x19, Unknown: 0x0

-- Bone 0, Par -1 Scale XYZ: 1, 1, 1 rot XYZ: 0, 0, 0 trans XYZ: 0, 5789, -2411.384
-- Bone 1, Par 0 Scale XYZ: 1, 1, 1 rot XYZ: -1.5708, -1.53979, -1.5708 trans XYZ: 0, -158.6708, 984.148
-- Bone 2, Par 1 Scale XYZ: 1, 1, 1 rot XYZ: 0, 0, -0.250276 trans XYZ: 1726.692, 146.1416, 0
-- Bone 3, Par 2  Scale XYZ: 1, 1, 1 rot XYZ: 0, 0.0319913, 2.23911 trans XYZ: 2006.52, 1170.472, 835.2
-- Bone 4, Par 3  Scale XYZ: 1, 1, 1 rot XYZ: 0.0127438, -0.0105506, -0.409707 trans XYZ: 1200.532, 4.64456E-05, 0
-- Bone 5, Par 4  Scale XYZ: 1, 1, 1 rot XYZ: -0.00108238, -0.0162147, 0.0576295 trans XYZ: 1417.916, 0, 0
-- Bone 6, Par 5  Scale XYZ: 1, 1, 1 rot XYZ: 0.00188848, -0.00170928, -0.835167 trans XYZ: 1726.86, 0, 0
-- Bone 7, Par 2  Scale XYZ: 1, 1, 1 rot XYZ: 0, 0, -0.724362 trans XYZ: 2200.924, -230.0648, 0
-- Bone 8, Par 7  Scale XYZ: 1, 1, 1 rot XYZ: 0, 0, 0.328187 trans XYZ: 1205.488, 70.2504, 0
-- Bone 9, Par 8  Scale XYZ: 1, 1, 1 rot XYZ: 0, 0, 1.3901 trans XYZ: 1448.02, -101.322, 0
-- Bone 10, Par 2  Scale XYZ: 1, 1, 1 rot XYZ: 0, -0.0319915, 2.23911 trans XYZ: 2006.52, 1170.492, -835.2
-- Bone 11, Par 10  Scale XYZ: 1, 1, 1 rot XYZ: -0.012744, 0.0105509, -0.409708 trans XYZ: 1200.524, 7.59712E-05, 0
-- Bone 12, Par 11  Scale XYZ: 1, 1, 1 rot XYZ: 0.00108233, 0.0162146, 0.0576273 trans XYZ: 1417.928, 0, 0
-- Bone 13, Par 12  Scale XYZ: 1, 1, 1 rot XYZ: -0.00188848, 0.00170928, -0.835164 trans XYZ: 1726.88, 0, 0
-- Bone 14, Par 1  Scale XYZ: 1, 1, 1 rot XYZ: 0, 0, 3.09995E-06 trans XYZ: 1268.024, -1763.744, 0
-- Bone 15, Par 0  Scale XYZ: 1, 1, 1 rot XYZ: -1.5708, -0.414462, -1.5708 trans XYZ: 690.868, -498.416, -525.828
-- Bone 16, Par 15  Scale XYZ: 1, 1, 1 rot XYZ: 0, 0.0424371, 1.04715 trans XYZ: 1535.376, 0, 0
-- Bone 17, Par 16  Scale XYZ: 1, 1, 1 rot XYZ: 0.022342, -0.0540031, -0.554481 trans XYZ: 1607.232, -7.16944E-05, 0
-- Bone 18, Par 17  Scale XYZ: 1, 1, 1 rot XYZ: -0.0131906, 0.0121209, -0.827676 trans XYZ: 1993.904, 0, 0
-- Bone 19, Par 0  Scale XYZ: 1, 1, 1 rot XYZ: -1.5708, -0.41446, -1.5708 trans XYZ: -690.944, -498.416, -525.828
-- Bone 20, Par 19  Scale XYZ: 1, 1, 1 rot XYZ: 0, -0.0424372, 1.04714 trans XYZ: 1535.376, 0, 0
-- Bone 21, Par 20  Scale XYZ: 1, 1, 1 rot XYZ: -0.022342, 0.0540032, -0.55448 trans XYZ: 1607.228, 0, 0
-- Bone 22, Par 21  Scale XYZ: 1, 1, 1 rot XYZ: 0.0131907, -0.0121209, -0.827681 trans XYZ: 1993.904, 0, 0
-- Bone 23, Par 0  Scale XYZ: 1, 1, 1 rot XYZ: 0, 1.5708, 0 trans XYZ: 0, 387.2696, -1308.824
-- Bone 24, Par 23  Scale XYZ: 1, 1, 1 rot XYZ: 0, 0.0113405, 0 trans XYZ: 2346.832, 0, 0

```
The animation data looks straight forward afaics, but you need frame interpolation (deja vue)
.



horse-hl_anim_stop2.png (6.76 KiB) Viewed 72 times

(difference of offsets= count x 16)
------------------------------------
(well, I totally forgot about the skinning. I've to check whether the exported mesh includes the weightings at least.)

Seems to be handled (but I didn't find the weights in the .dae export):

```
            Vector2[] weights = new Vector2[(int)(Root.VatrChunk.BoneWeights.Length - sepd.BoneWeightArrayOffset) / 
```
## Post #5
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-08-26T15:25:46+00:00
- Post Title: Zelda Ocarina of Time 3D - .csab files that are unreadable with N3dsCmb viewer

A bump
