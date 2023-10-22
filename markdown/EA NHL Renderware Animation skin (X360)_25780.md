## Post #1
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2022-09-07T12:41:55+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

Hi,
I have been trying to figure out how to read bones in Noesis but I can't understand the logic. The file is skeleton bind pose animation skin which consists of pose translation values in 3x4 matrix. I found source for spore RWAnimationSkin which seems same but different endianness but is there anyone here who can help further?
[https://github.com/emd4600/SporeModder- ... nSkin.java](https://github.com/emd4600/SporeModder-FX/blob/master/src/sporemodder/file/rw4/RWAnimationSkin.java)

offsets:
0x140 = boneCount?
0x150 = translation values in float


 skeleton_bindpose_player.rx2.zip
(4.67 KiB) Downloaded 14 times



Rx2 3d model files have bind bone indices and bind bone weights values for each vertex block but Noesis can't assign it if the model doesn't contain any skeleton.
## Post #2
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2022-09-07T20:41:46+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

You can try this:
1. Decomposite bind pose matrices to position, scale, rotation.
2. Create model, make bones by hierarchy ids from model file and transforms of bones getted on step one.
3. Attach model to scel and applying weights.
## Post #3
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2022-09-08T07:30:59+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

> Reply from grandshot ↑Thu Sep 08, 2022 4:41 am at Thu Sep 08, 2022 4:41 am
>
> 
You can try this:
1. Decomposite bind pose matrices to position, scale, rotation.
2. Create model, make bones by hierarchy ids from model file and transforms of bones getted on step one.
3. Attach model to scel and applying weights.

Thank you!
Do you have any Noesis examples for this?
Here is simple model+animation skin file and Noesis script to load the model.

Edit: BW and BI enums changed. BW = UBYTE4N and BI = UBYTE4


 female_0_4.zip
(28.58 KiB) Downloaded 11 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-08T09:59:15+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

@Beedy:

> rx2t: #modified test file female_0_4 not real rx2 fileWhat did you modify?
## Post #5
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2022-09-08T10:10:31+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

> Reply from shakotay2 ↑Thu Sep 08, 2022 5:59 pm at Thu Sep 08, 2022 5:59 pm
>
> 
@Beedy:
rx2t: #modified test file female_0_4 not real rx2 fileWhat did you modify?

I removed some header data before but nothing for the data buffers. I thought the data is easier to read this way.
I edited datatypes in the script before:
Indices are UBYTE4
Weights are UBYTE4n (D3DDECLTYPE_UBYTE4N   =  8,  // Each of 4 bytes is normalized by dividing to 255.0)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-08T10:25:39+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

So then all we know about the skeleton is in the data before offset 0x670 in that female_0_4.rx2t?

That would mean there's 82 assumed bones (or 99?). With 16 bytes each containing transform data, I guess (3 big endian floats + DWORD 0).
But no bone names, no hierarchy. Strange.

Last year JimmyJ wrote here 
> Reply from JimmyJ ↑Tue Jun 08, 2021 1:11 pm at Tue Jun 08, 2021 1:11 pm
>
> 
"but all characters have a same model, but ingame it was other geometry,"

Maybe there's only one basic skeleton for all, or something like this.
So you'll need to find that skeleton file (whit names and hierarchy).
## Post #7
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2022-09-08T10:44:57+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

Here's the original one:


 female_0_4.zip
(28.87 KiB) Downloaded 16 times



There are only render ware filetypes listed in 0x50 to 0x150 
Vertex descriptor in 0x150 to 0x1A0
Vertex data header 0x1A0 to 0x1D4
Face data header 0x1A0 to 0x200
Animation skin 0x200 ->
File list table 0x8dC to 0x9A0

I have explored all the file paths but none of skeleton files hasn't been found in the game.
## Post #8
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2022-09-08T10:54:34+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

I found that crowd_fxo (female 0_4 is in crowd) files from fxo shaders folder which may be contains some interesting data:


 shaders.zip
(19.17 KiB) Downloaded 12 times
## Post #9
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2022-09-08T11:12:44+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

There are also cba animation files in the game:
Could the bones be there:
[https://imgur.com/T6OvuHk](https://imgur.com/T6OvuHk)
[https://app.box.com/s/6lh3ebqysnoo3qqdxd9k27tle6bwhc1w](https://app.box.com/s/6lh3ebqysnoo3qqdxd9k27tle6bwhc1w)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-08T15:57:50+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

At least bone names! And a maybe hierarchy table. The rest is hard to track. I'd suggest giving it a structure searching for 05620E03 (or "GD.DATAl", less findings):
.



crowd_cba_3.png (40.14 KiB) Viewed 75 times



```
57961  8151 26840  6476 38244 39486  5200 33375 rotation/translation?
47292   985 11953 40514 44372 42318 62232 60143 ???

address 0xcb9a4:
13303  7107 24379 13126 39384  4786 19317 37673 rotation/translation?
47292   985 11953 40514 44372 42318 62232 60143 ??? 

address 0xcba24:
53986 13536 40206 22851 43642 19751 63222 53108 rotation/translation?
47292   985 11953 40514 44372 42318 62232 60143 ???
```
## Post #11
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2022-09-08T23:46:50+00:00
- Post Title: EA NHL Renderware Animation skin (X360)

The crowd.cba file definitely is chunk package with some meta data. I started to write the template for 010 editor for easy parsing. 
[graf_renderware4_cba.zip](https://drive.google.com/file/d/116JqPd4zoEtS5dUWAC1r2Vq7O48Azyqb/view?usp=sharing) 
Easy, right  
Structure of GD.DATAl chunks is nasty. Sort out of that would be not easy.
[Снимок экрана (26).png](https://xentaxbackup.github.io/file/22787_Снимок экрана (26).png)
