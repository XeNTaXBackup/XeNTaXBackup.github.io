## Post #1
- Username: Radu13
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 02, 2018 7:01 pm
- Post datetime: 2019-01-09T21:11:01+00:00
- Post Title: Slave Zero texture files .tex

I am trying to open and edit the texture files from a 1999 game: slave zero
Tried several programs without luck, any suggestions?

Example below:
[https://drive.google.com/file/d/1Px9Smv ... 2Y0Lb/view](https://drive.google.com/file/d/1Px9Smv38I6_2p_8T5QqbLwHNKMg2Y0Lb/view)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-09T22:34:55+00:00
- Post Title: Slave Zero texture files .tex

with TextureFinder 128x128 rgba5551 looks good, image data starts at 0x10.  



a_Slave0_live_Torso.png (27.08 KiB) Viewed 149 times


need more and variety of samples to make a script.
## Post #3
- Username: Radu13
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 02, 2018 7:01 pm
- Post datetime: 2019-01-10T09:43:51+00:00
- Post Title: Slave Zero texture files .tex

> Reply from Acewell
>
> with TextureFinder 128x128 rgba5551 looks good, image data starts at 0x10.  
a_Slave0_live_Torso.png
need more and variety of samples to make a script.
Thank you, i uploaded the entire texture folder for more examples.

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1O1q8UCrDdHZfcEPhk4bGCV2nC86vRYbl?usp=sharing)

Hopefully you shoud be able to create a working script!
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-12T02:12:46+00:00
- Post Title: Slave Zero texture files .tex

okay here is Noesis python script to open all tex samples of this game.  


 tex_SLaveZero_tex.zip
(738 Bytes) Downloaded 51 times


supports 8bit alpha(?), rgba8888 and rgba5551

this script will conflict with other scripts that also open tex files that don't have proper
type checking, you will have to move those out of the plugins folder while using this one.
## Post #5
- Username: Radu13
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 02, 2018 7:01 pm
- Post datetime: 2019-01-12T10:00:06+00:00
- Post Title: Slave Zero texture files .tex

> Reply from Acewell
>
> okay here is Noesis python script to open all tex samples of this game.  
tex_SLaveZero_tex.zip
supports 8bit alpha(?), rgba8888 and rgba5551

this script will conflict with other scripts that also open tex files that don't have proper
type checking, you will have to move those out of the plugins folder while using this one.
Good job, so this script works with a program called Noesis?
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-12T23:24:39+00:00
- Post Title: Slave Zero texture files .tex

> Reply from Radu13
>
>  so this script works with a program called Noesis?
yes, the link to Noesis is in my signature.
## Post #7
- Username: Strangways
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 28, 2020 7:59 am
- Post datetime: 2020-06-28T07:54:41+00:00
- Post Title: Slave Zero texture files .tex

I played the demo version of Slave Zero back in the day, and one of the things I enjoyed was the anime/Evangelion billboard images. When I finally got the full version, I was quite surprised to find that those textures had been replaced!
Thanks to this forum post, I went digging through the demo and full version .tex files. There are a number of minor changes: Some scaffold textures are darker or have an added light. The Klieg, Otto, and Vitriol billboards where either made brighter or dirtied up. s_sign_dragon_B is the "Tristan" sign and has the words "Amber Ale" at the bottom. s_sky_mission15.tex has a red clouds on the bottom, rather than being all black. The loading screen is different, showing Slave Zero standing still rather than shooting. The menu font is different, being textured and harder to read. s_signage_girl has a vignette added. There were 50 textures that were slightly, changed, but they were not all that interesting.

The completely swapped textures are the most interesting ones, and they are in the attached image. Clearly there were some copyright and adult content issues in a few!



SZtextures.jpg (191.36 KiB) Viewed 90 times
## Post #8
- Username: Strangways
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 28, 2020 7:59 am
- Post datetime: 2020-06-28T07:57:57+00:00
- Post Title: Slave Zero texture files .tex

If anyone would like to add these textures from the demo back into their full game, they are in the attached zip file. Simply unzip all the .tex files from the game's textures.zip file, replace any of the .tex files where you'd prefer to have the ones from the demo, and create a new textures.zip file with all of the .tex files together.
[SZDEMOtextures.zip](https://xentaxbackup.github.io/file/18392_SZDEMOtextures.zip)
## Post #9
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2020-06-28T19:40:18+00:00
- Post Title: Slave Zero texture files .tex

If you're interested at all in wiki editing, [The Cutting Room Floor](https://tcrf.net/The_Cutting_Room_Floor) would welcome this information.
