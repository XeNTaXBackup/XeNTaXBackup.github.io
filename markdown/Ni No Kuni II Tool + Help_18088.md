## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-11T22:58:46+00:00
- Post Title: Ni No Kuni II Tool + Help

Update
- UVs are working now

Hello,

I recently started working on the pc version of Ni No Kuni 2. I was able to load the vertex positions and indices, but I need some help with the uvs.

Here is a model of a bird : [http://www.mediafire.com/file/7o76s0c6a ... 01000.g4mg](http://www.mediafire.com/file/7o76s0c6a8cn5bc/a30001000.g4mg)

And here is the first mesh using hex2obj. Other ones are just LODs.



The file starts immediately with the vertex blocks, and every block is 60 bytes. First 3 floats are vertex positions. UVs should also be somewhere in the block, but I couldn't see them. Any help would be appreciated.

-- Tool --

I also started to make a tool. Not really useful atm without the uvs, but I will update it as I discover new stuff. Skeleton data also doesn't look that complicated, but I want to have proper uvs first.

Overview



How to use
- Extract the cpk archives using CriPakTools (or something else) first
- File -> Open to select a file
- Either select the .g4mg or the .g4pkm file. Both files need to in the same folder.

Download :  [http://www.mediafire.com/file/zh7xa2i8q ... wer_UV.rar](http://www.mediafire.com/file/zh7xa2i8qzyozp3/NNKViewer_UV.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-05-12T00:58:54+00:00
- Post Title: Ni No Kuni II Tool + Help

> Reply from akderebur
>
> I need some help with the uvs.
wordUV at position 56 looks good to me 



a30001000_g4mg.png (42.78 KiB) Viewed 416 times
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-12T05:21:02+00:00
- Post Title: Ni No Kuni II Tool + Help

> Reply from AceWell
>
> 
wordUV at position 56 looks good to me
Great, thanks. I need to find a way to convert WORD to float in my code. I think I will check the Make_obj source
## Post #4
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2021-01-16T03:17:33+00:00
- Post Title: Ni No Kuni II Tool + Help

> Reply from akderebur ↑Sat May 12, 2018 1:21 pm at Sat May 12, 2018 1:21 pm
>
> 
AceWell wrote:
wordUV at position 56 looks good to me 
Great, thanks. I need to find a way to convert WORD to float in my code. I think I will check the Make_obj source

I was attempting to use this to convert g4pkm files from Yo-kai Watch 4
This tool can open them and save them as obj but the meshes are exploded, so the vert cords are not correct(not sure how best to put it)
[https://drive.google.com/file/d/1L1xqRM ... sp=sharing](https://drive.google.com/file/d/1L1xqRMwJmIenlv2TRxY1Y5uorhVOgVHj/view?usp=sharing)
here is a sample files

Any chance you could take a look, took me a few hours to figure out how to extract the xci the cpk now im suck :/
