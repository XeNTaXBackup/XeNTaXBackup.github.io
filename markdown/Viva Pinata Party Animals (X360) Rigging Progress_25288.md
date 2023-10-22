## Post #1
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-23T20:25:30+00:00
- Post Title: Viva Pinata Party Animals (X360) Rigging Progress

I and 2 other people I've gotten help from in the Return To Paradise Discord Server have been getting some progress on this, though we need stuff like the skeleton hierarchy and the rotation and scale for bones. Anybody wanna give some advice on this, especially from those who're more familiar with model ripping from Krome Studios games? 


2022-04-17_10_04_49-Blender__C__Users_sunst_Desktop_A301_Bug_Common.blend.png (225 KiB) Viewed 44 times

 
Sample files of things like Character models and etc: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1Pk9UGLJisbzo6-pO7IbAMRevcCQr8pxQ?usp=sharing)
Miscellaneous:
[viewtopic.php?f=16&t=14903](https://forum.xentax.com/viewtopic.php?f=16&t=14903)
[viewtopic.php?f=18&t=19059](https://forum.xentax.com/viewtopic.php?f=18&t=19059)
## Post #2
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-04-23T20:45:24+00:00
- Post Title: Viva Pinata Party Animals (X360) Rigging Progress

> Reply from ShadowLuigi ↑Sun Apr 24, 2022 4:25 am at Sun Apr 24, 2022 4:25 am
>
> 
I and 2 other people I've gotten help from in the Return To Paradise Discord Server have been getting some progress on this, though we need stuff like the skeleton hierarchy and the rotation and scale for bones. Anybody wanna give some advice on this, especially from those who're more familiar with model ripping from Krome Studios games? 2022-04-17_10_04_49-Blender__C__Users_sunst_Desktop_A301_Bug_Common.blend.png 
Sample files of things like Character models and etc: https://drive.google.com/drive/folders/ ... sp=sharing
Miscellaneous:
viewtopic.php?f=16&t=14903
viewtopic.php?f=18&t=19059
Forgot to mention, this is what one of the buddies I'm collaborating on this with said to me.

"Ive only been able to get the location of the bones, the hierarchy and rotation/ scale isnt converted
C1 D9 6A 1E 42 74 02 DE 41 87 D4 DB 02 49 35 74
00 00 17 AC 00 10 00 1E 00 02 00 00 00 00 15 68
First 12 bytes are 3 floats for xyz, 2 shorts at 20 (dec) I believe are parent bone indexes.

Which means the rotational data is either calculated with 8 bytes, or for some ungodly reason it's split into 2 sets of 8 either side of the indexes.

To me that's not enough data, but I don't know what to look for so I might be overlooking something"
