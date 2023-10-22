## Post #1
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-07-02T19:39:33+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

Hello I would like to request a noesis script to extract One Piece Burning Blood models, the game comes in an unencrypted .cpk archive, which contains compressed .scz files, after using aluigi’s cmp_scz script, we get 3 types of files for the models, .npk, .npki, .npkv.
The game uses Spike Chunsoft own model structure SRD [https://wiki.spiralframework.info/wiki/SRD](https://wiki.spiralframework.info/wiki/SRD) with a different extension, I tried to use the Spiral tool for Danganronpa V3 extraction, but the UVs are messed up, the textures come out fine though.
.srd -------> .npk (pointer/reference file for the model and texture data)
.srdi ------> .npki (raw model data)
.srdv ------> .npkv (raw texture data)

I’ve been skimming through the first 2 files to understand the model structure with the help of hex2obj, and I think I got it, but don’t have the knowledge to put it into a script. I’ll try to explain myself using Luffy (Marineford) model with the character id “character_000” and the interface from h2o, please bear with me if I say some gibberish. [character_000.7z sample](https://www.mediafire.com/file/wycjgl9rrjqa7ol/character_000.7z/file)

In the character_000.npk file there are $VTX entries that points to the submeshes data in the character_000.npki, each with a $RSI sub-entry, and this last one ends with $CT0.



This is the first $VTX entry in character_000.npk, it points to the straw hat submesh in character_000.npki 
20 bytes after $VTX we have the submesh vertices count 75 04, in reverse byte ordering 0x475 = 1141 decimal.
28 bytes after $RSI we have the vertices start address 00 00 00, and right below it, after 13 bytes, the face indices start address E0 AB 01, 0x1abe0, 1 byte after it we have the face indices block length 80 2B, 0x2b80 when divided by 2 we get the FI count 0x15c0 = 5568 decimal.

To get the UV start address we must add the bytes in blue to the vertices start address, they’re not always in the same position in the $VTX section, but they are preceded by 00 00 20 00 00 00 after the vertices block length, which is always after the 30 00 00 00 bytes in the $VTX section: 0x0 + 0x16490 UV start address.

For the FVFsize we divide the vertices block length by the vertices count: 
0xd5f0 / 0x475 = 0x30 = 48 decimal (haven’t found models with other value).
To get size UVB we need to subtract the values in blue from the values in purple 1 byte after the vertices address and divide the difference by the vertices count: (0x1abe0 – 0x16490) / 0x475 = 0x10 = 16 decimal (some are 8 and some 16).

And if I understood the hex2obj tutorial correctly the values between the vertices block and the UVs block should be the submesh’s normals, we can get their start address if we add the vertices block length to the vertices start address: 0x0 + 0xd5f0 = 0xd5f0.
Before the $CT0 we have the name of the submesh, in this case C_HUT.
Open the character_000.npki in hex2obj and input the calculated values from character_000.npk



After this cumbersome explanation here is an example with the next submesh, the left eye. See that the vertices block length and values in blue aren’t in the same position as the previous $VTX.


```
Face indices start address: 0x1fce0			FI count: 0x438/2 = 0x21c = 540 decimal
FVFsize: 0x1470 / 0x6d = 0x30 = 48 decimal
UV start address: 0x1d760 + 0x2210 = 0x1f970		Size UVB: 0x2578 – 0x2210 / 0x6d = 8
Normals? start address: 0x1d760 + 0x1470 = 0x1ebd0
```



I know it is lazy of me to just request a noesis script but after reading the tutorials here I really don't get it, I hope this information would be useful to anyone wanting to help with the coding part.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-03T08:15:57+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

Nice. Seems you've found the "magic table" containing the counts.
I assume it's marked by the pattern 0605040200000000 which is to be found 108 times in the npk file.

Atm I'm too busy with RL concerns but I think I can add npki to my Make_H2O project sooner or later.

(It would be possible with Noesis, too. But I'm quicker with "standalone" C, I guess.  )

As a reference (didn't check it):
[viewtopic.php?f=16&t=17510&p=136909#p136909](https://forum.xentax.com/viewtopic.php?f=16&t=17510&p=136909#p136909)

edit: some progress,



character_000.npk.png (58.61 KiB) Viewed 775 times
## Post #3
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-07-03T08:55:50+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

Thanks, I did check that post, my introduction is kind of a summary of it. Really any tool would be cool, because getting 107 meshes manually is just oof, I'm just glad this info could help in some way.
As for the "06 05 04 02 00 00 00 00" pattern I think you might be right, but the first instance of that is found in a $TXR entry and not $VTX, the other 107 instances are indeed in all of the $VTX entries.


EDIT: I checked another .npk and yeah the pattern was there in one $TXR entry and all of the $VTX entries.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-10T15:24:18+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

> Reply from JosouKitsune ↑Wed Jul 03, 2019 4:55 pm at Wed Jul 03, 2019 4:55 pm
>
> Really any tool would be cool, because getting 107 meshes manually is just oof,Tool is cool, yes, but tested with one model only:
.


 Make_obj-OnePBB.zip
(49.03 KiB) Downloaded 36 times



Btw, "Make_obj" is misleading here, because H2O files are being created which can be used (together with the npki) to create obj files using hex2obj.

(Splitting the task up onto two tools was easier for me because the parameters are in the *.npk files and the model is in the suiting *.npki.)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-11T06:40:55+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

I've updated the tool for various uvb sizes (tested one model only!):
.


 Make_obj-OnePBB.zip
(49.05 KiB) Downloaded 31 times
## Post #6
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-07-12T22:19:58+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

Sorry I didn't check earlier   here are other 6 models [https://www.mediafire.com/file/1ukqnkd5 ... ls.7z/file](https://www.mediafire.com/file/1ukqnkd595qf5yt/BB_models.7z/file)
But for the most part is working great. Don't mind the flat square parts in the pants or skin, that's how they're supposed to be.
## Post #7
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-07-12T23:19:27+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

I checked back on the "06 05 04 02 00 00 00 00" pattern and some files don't have the first instance of it in a $TXR entry. For example character_002 only has it on the $VTX entries, and character_003 has it in one of the $TXR entries, but these are after the $VTX ones. Both characters were provided in the previous post.

Also character_003 has 2 groups of $VTX entries one at the start of the file and one at the end.
Last $VTX entry in the first group.


First $VTX entry in the second group.


See in this last $VTX the vertices address go back 00 00 00, that's because *.npk, *.npki, *.npkv are containers of multiple *.srd, *.srdi, *.srdv respectively, character_003.npki has 2 models, the first one being human Marco and the second one phoenix Marco.
What I did was to go to the last mesh of human Marco and see where the phoenix model started and it was at address 0x1AEF80 of the npki so I added that value to the addresses that were extracted by Make_obj-OnePBB since the first phoenix mesh, it was "character_003.npk_43.h2o".



So after that I went and see if character_003.npk had any reference to 0x1AEF80 and found this "80 EF 1A" at offset 0x410 and this information below. Although this may only be relevant to characters with multiple model blocks.
## Post #8
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-07-13T04:39:11+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

Also something weird happen with character_001 from the h2o the tool generated, character_001.npk_27.h2o had the wrong FI count 26104 I multiplied it by 2 and then converted it to hex that being 0xCBF0. This is my fault because in my first post I only highlighted the first 2 bytes of the vertex count, FI block length, values in blue and values in purple instead of the 4 bytes that were needed.


What it obtained


What it should be


Please refer to this table instead, also updated in the first post.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-13T12:38:49+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

I've updated FI and vertex count to DWords in the zip of my previous post (can't care for the other issues atm).
## Post #10
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-07-13T13:27:32+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

Thanks the counts were the main issue, for the other problems I can get around them adding dummy data.
## Post #11
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2019-07-14T03:19:51+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

what about bones and rigging
## Post #12
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-07-14T03:51:40+00:00
- Post Title: Help with Noesis script for One Piece Burning Blood models .npk | .npki

> Reply from ChaoticFusion40 ↑Sun Jul 14, 2019 11:19 am at Sun Jul 14, 2019 11:19 am
>
> 
what about bones and rigging
Each npk file has a $SKL entry where the skeleton is stored, and each $VTX entry has its corresponded weight, but a whole new tool would be needed for that since from what I understood hex2obj only gets the meshes.
