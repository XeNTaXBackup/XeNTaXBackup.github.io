## Post #1
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2020-11-26T17:54:48+00:00
- Post Title: Extracting audio files from Halo 2 Anniversary

Hello, i'm trying to rip sounds/musics and voicelines from Halo 2 Classic and Anniversary from Halo the Master Chief collection released on Steam.
I've already tried different softwares, as well as QuickBMS with the Halo: tmcc's script with no success at all, could someone please help me on that?
Here a sample of the sound file container i need to unpack:
[https://drive.google.com/file/d/14M-FCa ... sp=sharing](https://drive.google.com/file/d/14M-FCa-CtwCxAmzmk7gOu1SFl9l0qRz4/view?usp=sharing)
Thank you all!
## Post #2
- Username: fellowstarstuff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 03, 2021 9:08 am
- Post datetime: 2021-01-03T01:11:49+00:00
- Post Title: Extracting audio files from Halo 2 Anniversary

Hi Simone, were you able to figure it out? I'm in the same boat as well. I can't seem to find a way to extract audio/music files from H2A on PC. I'm hoping Assembly might be updated in the future to allow for extraction. If I find a way to extract H2A audio, I'll definitely let everyone know here. Please let us know if you find a way, as well.
## Post #3
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2021-04-05T12:21:19+00:00
- Post Title: Extracting audio files from Halo 2 Anniversary

Has anyone found a solution yet?
## Post #4
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2021-04-23T22:34:42+00:00
- Post Title: Extracting audio files from Halo 2 Anniversary

H2 anniversary file structure is a based upon the structure they used in Halo Online, which came after saber's work on H2A. 

Campaign assets are located in the sounds_remastered.dat for audio, the compression used is an updated zlib compression that was used in Halo: CE Anniversary. The zlib compress they used in H:CE was very hard to figure out, and the same is going on with H2. I've kept my eyes open on the modding scene for any breakthroughs but there hasn't been any. 

I posted here back when the game first came out on PC but no one was interested. All I can do is repost the same info and samples. Unless someone with more experience wants a challenge i've attached sample and first bytes. 

```
44 00 EC 7F FC 9C D5 F2 CE 66 11 E3 03 F3 8B E6 99 AB 1A F8 8F 05 14 2B 44 31 37 6A 72 78 DB 94 93 37 A4 4B C3 F0 A7 72 11 52 61 FA ED CA CC 9E 52 6E 63 16 6A 50 3A 2A 99 F4 BE 7D 6B B7 2B 45 A8 26 17 29 90 0A 44 00 EC 7F F9 48 29 5C D7 77 CA AE 9D 8E FE 8E 51 98 D6 82 E4 24 67 6B 52 DD 25 9C 9F 08 11 CF 9A D4 5E 95 6A 9B 28 5F 3D 61 CF 8D 9B 62 53 06 83 39 07 4B 1D 43 83 0E 63 A6 36 B6 BA 50 B2 91 9C 94 42 DA 31 4C 69 00 EC 7D F5 CF 90 6F AB 19 37 95 62 04 D3 32 C4 FB C8 DF A8 90 D6 6A 7E E3 63 35 BD 5A 64 72 B5 C0 72 02 23 7A 48 E4 73 0D 3D 6E 7A 81 A7 96 9B AC 2B C1 8D A6 61 DF 3C 90 22 F7 B1 A7 6B 70 CF FA 04 E2 4E CE 84 E7 9A F1 0B 69 2F 3F 44 C4 C7 CF 34 3D 76 91 84 91 67 01 DE E9 13 D5 44 1A 68 C1 AC 24 6A 3C 5A DF F0 A0 A5 39 00 EC 47 56 A2 C1 0B 90 E4 A2 79 D1 63 19 D3 6C 41 78 59 0D 2C F6 C3 EA 68 C8 37 91 A8 1A 13 55 E0 52 9C B7 8D 87 4D C9 56 99 4B 0E 44 22 F2 FB F0 74 34 15 B9 47 5C 07 CC 00 41 00 EC 27 A8 50 9A F7 2C E8 C2 13 0F 5D D9 78 FB 5A 95 2D 22 CC 49 A1 6E 9F 04 9B 35 2D 77 BB 8C C2 AA 56 45 50 DE FA 30 74 57 2D D8 7D
```


Mod tools might also open up the option to export audio, but i'd love to get the compression cracked.
[sounds_remastered.zip](https://xentaxbackup.github.io/file/19945_sounds_remastered.zip)
## Post #5
- Username: fellowstarstuff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 03, 2021 9:08 am
- Post datetime: 2021-10-20T19:20:07+00:00
- Post Title: Extracting audio files from Halo 2 Anniversary

> Reply from durandal217 ↑Sat Apr 24, 2021 6:34 am at Sat Apr 24, 2021 6:34 am
>
> 
Mod tools might also open up the option to export audio, but i'd love to get the compression cracked.

Now that 343 released Guerilla for H1-3 on Steam, they also released the .sound tags/files. Unfortunately they are .sound files encoded with xbox adpcm codec, so I can only play the files within Guerilla and can't figure out a way to export them to a more usable format like .wav. 

Is there anyway to export/convert the xbox adpcm-encoded .sound files to .wav?
## Post #6
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2021-11-03T20:34:43+00:00
- Post Title: Extracting audio files from Halo 2 Anniversary

I've got the same problem!
I'll leave here a sample of the files i'm trying open/convert:

[https://drive.google.com/file/d/1A64ee4 ... WfKtx/view](https://drive.google.com/file/d/1A64ee4QGoKURwZM-GQbEdfZCAGwWfKtx/view)

Thanks a lot!
## Post #7
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2021-11-05T17:57:46+00:00
- Post Title: Extracting audio files from Halo 2 Anniversary

> Reply from fellowstarstuff ↑Thu Oct 21, 2021 3:20 am at Thu Oct 21, 2021 3:20 am
>
> so I can only play the files within Guerilla and can't figure out a way to export them to a more usable format like .wav.

How do you play sounds in Guerilla? I tried to play but it keeps asking for a target machine, search results from google come up with H2 guerilla not supporting sound playback.
