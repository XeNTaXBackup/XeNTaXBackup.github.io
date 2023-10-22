## Post #1
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-05-03T17:12:53+00:00
- Post Title: Help with Dog's Life (PS2) bones and animations

Hi, I'm trying to figure out how to parse the bones in Dog's Life OVL file, but I can't seem to figure it out. I've provided some information on what has been figured out so far as for anyone who wants to help. The archive attached contains the 5.ovl along with 2 scripts. The 5.ovl contains two sets of bone names, one at offset 3D3D6 to 3D6BF (hex) and another at offset F0AE6 to F0E35 (hex). I'm not 100% sure which each set is used for, but I know both are important.
offset 250014 (dec) may be the start of the indices, as loomy suggested. offset 353638 (dec) appears to have plain floats which could be positions of bones. hex 0000803f (float 1.0) may be scale. These are all guesses, feel free to take a look and see if you can figure anything else out. thanks in advance!
[dogslifestuff.7z](https://xentaxbackup.github.io/file/20034_dogslifestuff.7z)
## Post #2
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-05-03T17:16:19+00:00
- Post Title: Help with Dog's Life (PS2) bones and animations

Image 1
[Screenshot_3.png](https://xentaxbackup.github.io/file/20039_Screenshot_3.png)
## Post #3
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-05-03T17:16:36+00:00
- Post Title: Help with Dog's Life (PS2) bones and animations

Image 2
[Screenshot_1.png](https://xentaxbackup.github.io/file/20038_Screenshot_1.png)
## Post #4
- Username: Dogmander
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Feb 02, 2021 9:03 am
- Post datetime: 2021-05-03T17:57:27+00:00
- Post Title: Help with Dog's Life (PS2) bones and animations

Also, Gibbed's script gibbed.FGDK3 can also rip models, but not animations or bones properly yet. This script is much more complete than the noesis script from Dave, as it can do textures and automatic ripping of all models. [https://github.com/gibbed/Gibbed.FGDK3](https://github.com/gibbed/Gibbed.FGDK3)
