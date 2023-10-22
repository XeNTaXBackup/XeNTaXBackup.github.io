## Post #1
- Username: CarLoiD
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 10, 2020 7:10 am
- Post datetime: 2020-05-19T13:32:35+00:00
- Post Title: God Hand Animations

Hello everybody, I would like to ask some help on figuring out how the animations or bone data are organized in these files from God Hand (PS2), I've already figured it out how the .MD models works, and it appears that bone data always come before the actual vertex data. After the model meshes, there's some .MOT and .SEQ files, that's very likely to be the animation data. I'm trying with the Gene Chihuahua model, so, the bone structure should be a little dog as well. I'll send the samples.

[https://www.mediafire.com/file/990ktxmi ... t.zip/file](https://www.mediafire.com/file/990ktxmiyoar8fy/pl03_GeneChihuaha.dat.zip/file)
## Post #2
- Username: mrx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 26, 2022 10:22 pm
- Post datetime: 2022-09-26T14:29:07+00:00
- Post Title: God Hand Animations

vc ainda tem modelos ? pode passar estou tentando extrair mas da erro
## Post #3
- Username: mrx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 26, 2022 10:22 pm
- Post datetime: 2022-09-26T14:30:47+00:00
- Post Title: God Hand Animations

Modelos e textura se possivel
## Post #4
- Username: akiot
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 15, 2022 8:16 am
- Post datetime: 2022-10-15T22:05:56+00:00
- Post Title: God Hand Animations

Hi there.

i HIGHLY especulate that the MOT files are "where" the animations are localized.

tested on gene's .dat file and i repared that all the SEQ files are 1kb lenghtened, 
and since 409 SEQ files got extracted during the .dat extraction, i'm pretty sure that they're not what you're looking for. Since gene in-game have +100 movements, and having 400 animation clips don't makes sense. Even more when all of them are 1kb lenghtened.

but in the other hand(insert internal god hand joke here), the MOT files seems to be pretty variated at it's lenght. And most important, it actually seems to have some pretty important vector values over there, which seems to be the positions and rotations itself.

some kind of other indices that MOT files is actually what ur looking for is that i found this pattern in some of my researches.

sample MOT file: [https://drive.google.com/file/d/1HqL26v ... sp=sharing](https://drive.google.com/file/d/1HqL26vVDtaHju1jw6z4FDIqBgn3EFqNI/view?usp=sharing)
(i used the lightiest MOT file available since it's easier to research for)
*03* 5F 46 41 *03* 54 3C 31 *04* 4C 4D 49 *03* 49 36 2F (after 3 numbers it repeats the same pattern)

they kindly repeat "03" and "04" which means should be the sepparator for the positions and rotations.
e.g.: posfromframe1:   10(refered to the X axis).30(refered to the Y axis).50(refered to the Z axis)


so you can deduce 03 and 04 is the main sepparator for the axis frames, there's sometimes a "05","02","00" sepparator but it don't appear so ofter as 03 and 04. Remember to take some attention to the 3 number pattern (x,y,z)   

i deduce god hand animationClip(MOT files) FPS is 30 since the game itself have a 30 FPS limiter. It would not make sense if the animationClips Wasn't 30 FPS.


i also speculate that the SEQ files are the models skeleton partitures. Which needs to be assembled. Not confirmed byt the way.


so we have the current knowledge about god hand's files(as far as i discovered):
MD/is the files used to synthetize the model in-game(MODEL IN GENERAL).
MOT/is the files used to synthetize the model movement in-game(ANIMATION IN GENERAL).
SEQ/ it's unknown.but i kindly especulate that they're used to create the model bones. A bone sequence?(if i'm correct, BONES IN GENERAL.)
TM3/is the files used to synthetize the model textures(TEXTURES IN GENERAL).


hope i helped you someway.

i will try to research the chihuaha files so i will reply back as soon as i find something.
## Post #5
- Username: akiot
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 15, 2022 8:16 am
- Post datetime: 2022-10-15T22:22:07+00:00
- Post Title: God Hand Animations

Yes, as i especulated i was kindly right, the MOT files are animation data files. The same 3 number pattern repeats after "00,01,02,03,04,05" numbers.

about how to identify which bones the frame refers to, i have absolutely NO clue really. But i deduce the different 00,01,02,03,04 and 05 numbers before the pattern should be a clue, maybe the different numbers refers to the specific bone that they're going to position/rotate since they can repeat and vary, but again, no clue really.


(edit, i discovered that the sepparator can go from 0 to 20+).


tip: use 16 bytes per line. This makes the pattern easier to identify
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-15T22:24:29+00:00
- Post Title: God Hand Animations

Thanks for your investigation but without having the skeleton bones it's not worth bothering, imho.
This is the mesh (auto created faces; too tired to search for face indices; might be burried in the block at 0x76B0)
-



1-MD.jpg (115.17 KiB) Viewed 77 times
## Post #7
- Username: akiot
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 15, 2022 8:16 am
- Post datetime: 2022-10-15T22:31:08+00:00
- Post Title: God Hand Animations

i see   well i will try investigating further so i can see where can i go with it.
## Post #8
- Username: akiot
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 15, 2022 8:16 am
- Post datetime: 2022-10-15T23:02:18+00:00
- Post Title: God Hand Animations

i tried to find bone indices in the MD model file thing.
maybe the bones are stored in the MD model actually. But still no clue... The "1.MD" model have some weird
pattern in 0xAA0, which consists in a 3 number pattern also.... No clue really.
