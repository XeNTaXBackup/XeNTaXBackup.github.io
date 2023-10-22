## Post #1
- Username: xanadu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 18, 2020 2:46 am
- Post datetime: 2020-06-17T18:47:46+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

--Solved--

Hello everyone, I've got a strange question in my mind. I play a game that have all the audio in a file called music.grp. Is there a way to extract them? 

Game: Code Lyoko - Quest For Infinity. (PS2 - WII - PSP)

Here's the single .grp file: [https://mega.nz/file/WXRliYZQ#-S-TiOlqz ... K4HKeWJGTI](https://mega.nz/file/WXRliYZQ#-S-TiOlqzKnu1FrdougRFwYrnzfBX3ZhSK4HKeWJGTI)

I was able to open the Iso of the ps2 and wii disk and they have the same music.grp file.

Thanks to all of you.
## Post #2
- Username: xanadu
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-17T20:15:38+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

Hello. I was able to extract data from your sample.
Here are tool and documentation --> [https://github.com/bartlomiejduda/Tools ... 20Infinity](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Code%20Lyoko%20-%20Quest%20For%20Infinity)

After you extract files from archive, just open them in MFAudio and play
## Post #3
- Username: xanadu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 18, 2020 2:46 am
- Post datetime: 2020-06-17T22:07:11+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

Ok I got several .bin files. The first 500 are 1kb. is that normal?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-17T22:43:11+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

Yeah, those are probably some dummy files.

If you compare MUSIC.GRP file size with output folder size 
as on screenshot below, you see that sizes are similar, so everything was extracted fine
## Post #5
- Username: xanadu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 18, 2020 2:46 am
- Post datetime: 2020-06-17T23:05:56+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

Yeah, now.. I listened to all files. It's seems like there aren't sfx. Which is funny because there's a file called sounds.cfg and it set all the volumes. There are also three other folders: Data - IRX - Video. 
Video contains just the cutscenes in pss which I can open in vlc without problems.
Online I found that the IRX files are something which every ps2 needs so that doesn't contain the sfx.
The last folder is Data. It has some subfolders like: Boss, common, level, loading ecc.. (more in the screenshot)
Inside every folder there are folders called "Lxxx" (xxx are three numers).
Inside them there are: name_of_the_folder.CP2 and  name_of_the_folder.PC
I don't know if they are models or sound..

Screenshot of the folders: [https://imgur.com/a/qTTYFwD](https://imgur.com/a/qTTYFwD)
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-06-17T23:25:29+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

There shouldn't be any dummy files in MUSIC.GRP.  There are 587 files in total.  If you want an alternative extracting method, try my QuickBMS script attached, which will play in Foobar with the vgmstream plugin.
[Code Lyoko.zip](https://xentaxbackup.github.io/file/18346_Code Lyoko.zip)
## Post #7
- Username: xanadu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 18, 2020 2:46 am
- Post datetime: 2020-06-17T23:37:39+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

Yeah, I tried also PSound and it worked. But also the method with MFAudio works. Now I just need to know where are the sound effects.. I thought they were also in music.grp but they aren't in there..
## Post #8
- Username: xanadu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 18, 2020 2:46 am
- Post datetime: 2020-06-18T13:48:59+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

By the way, I opened the Wii game and the same files is 1Gb instead of 300mb of the ps2. Maybe this contains also the sound effects? The python script on github don't work on this.. It just makes a loud noise
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-18T16:50:21+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

Upload this file to some hosting server and I'll check it.
## Post #10
- Username: xanadu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 18, 2020 2:46 am
- Post datetime: 2020-06-18T18:51:02+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

Here's the file: [https://mega.nz/file/WPIQxYZT#VBLx5kJ-l ... su8ucfDj1Q](https://mega.nz/file/WPIQxYZT#VBLx5kJ-luNeucTr8IyYqR5ABmZSvwcM0su8ucfDj1Q)
## Post #11
- Username: xanadu
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-24T22:22:04+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

I have answered by PM. Extracted files are 16-bit PCM.


Edit:
Ok, so I have checked your game files. 
All sound effects are in samples.MSC file.
You can rip them by PSound Tool --> [http://snailrush.online.fr/](http://snailrush.online.fr/)
## Post #12
- Username: KrupierX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 10, 2021 6:26 am
- Post datetime: 2021-04-10T11:28:48+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

I send link to all files I recognize they would contain sound effects. Grp file is under the "music" name and it couldn't possibly contain any sound effect, so I didn't include it. Unfortunately I have only the Wii version of the game, I can't download the PS2 one cuz I'm having internet connection crisis and I'm using cellular connection.   

Link to files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/194HO6x6KbioNCaquYrQFnobDOwYvQhAN?usp=sharing)
## Post #13
- Username: KrupierX
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-10T14:19:56+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

@KrupierX, well, first of all, we are speaking only english on this forum... so please edit your message to contain only english text.
Please read also the rules [viewtopic.php?f=28&t=1270&p=8545#p8545](https://forum.xentax.com/viewtopic.php?f=28&t=1270&p=8545#p8545)


As for your files, all sounds are stored in SAMPLES.SPD file.
It is Nintendo DSP 4-bit ADPCM format and it can be easily played in Foobar with vgmstream plugin.
Just drag and drop SPD file to Foobar to play it [https://i.imgur.com/FFyf8M1.png](https://i.imgur.com/FFyf8M1.png)
## Post #14
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2021-09-15T19:45:53+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

Have you guys tried extracting the .gcn, .cp2 and .pc files in Code Lyoko Quest for Infinity?
## Post #15
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-16T08:55:48+00:00
- Post Title: Code Lyoko Quest For Infinity - Extraction of .grp file

No, I haven't. If those are the archives, you can ask about them in the separate topic in the archives section.
## Post #16
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2021-09-16T09:59:23+00:00
- Post Title: Re: Code Lyoko Quest For Infinity - Extraction of .grp file

> Reply from ikskoks ↑Thu Sep 16, 2021 4:55 pm at Thu Sep 16, 2021 4:55 pm
>
> 
No, I haven't. If those are the archives, you can ask about them in the separate topic in the archives section.

I kinda did that but I didn’t get much results from it.
