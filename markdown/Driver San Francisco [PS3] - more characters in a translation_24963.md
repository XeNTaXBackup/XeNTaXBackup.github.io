## Post #1
- Username: SpeedVash
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat May 15, 2021 9:14 am
- Post datetime: 2022-01-18T22:11:17+00:00
- Post Title: Driver San Francisco [PS3] - more characters in a translation

Hi guys, I'm doing a translation where I'm having problems with the size of the sentences, I would like someone to help me add more space.

EX: 
Original:           (HOLD THEN RELEASE TO RAM)
Translation:      (SEGURE E SOLTE PARA SE LANÇAR)

If anyone is willing to help me, I'd appreciate it.
## Post #2
- Username: SpeedVash
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-18T22:33:09+00:00
- Post Title: Driver San Francisco [PS3] - more characters in a translation

If you want help, you need to specify more details like:
1. What is the name of the game you are translating?
2. Do you know what engine this game use?
3. What type of files contain language files? What are the extensions and in which directory they are stored?
3b. (please also upload some samples)
4. What tools do you use to translate?
## Post #3
- Username: SpeedVash
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat May 15, 2021 9:14 am
- Post datetime: 2022-01-18T22:55:10+00:00
- Post Title: Driver San Francisco [PS3] - more characters in a translation

> Reply from ikskoks ↑Wed Jan 19, 2022 6:33 am at Wed Jan 19, 2022 6:33 am
>
> 
If you want help, you need to specify more details like:
1. What is the name of the game you are translating?
2. Do you know what engine this game use?
3. What type of files contain language files? What are the extensions and in which directory they are stored?
3b. (please also upload some samples)
4. What tools do you use to translate?

I'm translating the Driver San Francisco PS3 

The game's subtitles are in the subtitles.astd.sdat file, I decrypted it with JjkkYu's TrueAncestor_EDAT_Rebuilder_v1.65, and I'm using an hxd editor to do the translation.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-18T22:59:12+00:00
- Post Title: Driver San Francisco [PS3] - more characters in a translation

Can you upload this "subtitles.astd.sdat" file to some hosting site like mega.nz or google drive?
## Post #5
- Username: SpeedVash
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat May 15, 2021 9:14 am
- Post datetime: 2022-01-18T23:08:37+00:00
- Post Title: Driver San Francisco [PS3] - more characters in a translation

> Reply from ikskoks ↑Wed Jan 19, 2022 6:59 am at Wed Jan 19, 2022 6:59 am
>
> 
Can you upload this "subtitles.astd.sdat" file to some hosting site like mega.nz or google drive?

Follow the file.
[https://www.mediafire.com/file/jwlngczs ... p.rar/file](https://www.mediafire.com/file/jwlngczshsa3y29/DSF_english_backup.rar/file)
## Post #6
- Username: SpeedVash
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-19T18:21:56+00:00
- Post Title: Driver San Francisco [PS3] - more characters in a translation

Try to use npdtool - edat/sdat tool.
Download here --> [https://www.sendspace.com/file/w5mtcm](https://www.sendspace.com/file/w5mtcm)
or here --> [https://drive.google.com/file/d/1cMp3n9 ... sp=sharing](https://drive.google.com/file/d/1cMp3n96YsjVOp5V5K1IB-8lQ6_9b3gMC/view?usp=sharing)

Then unpack data with this command:

```
npdtool.exe ds subtitles.astd.sdat subtitles.astd.out
```


Then open OUT file with hex editor and you will be able to see decrypted text.

Edit: You already know that, but let's leave this instruction for others.


But the file format seems to be too complicated to handle packing with longer sentences.

Edit2: I have created this article for future reference [http://wiki.xentax.com/index.php/PlayStation_EDAT_SDAT](http://wiki.xentax.com/index.php/PlayStation_EDAT_SDAT)
## Post #7
- Username: SpeedVash
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat May 15, 2021 9:14 am
- Post datetime: 2022-01-20T00:18:08+00:00
- Post Title: Driver San Francisco [PS3] - more characters in a translation

> Reply from ikskoks ↑Thu Jan 20, 2022 2:21 am at Thu Jan 20, 2022 2:21 am
>
> 
Try to use npdtool - edat/sdat tool.
Download here --> https://www.sendspace.com/file/w5mtcm
or here --> https://drive.google.com/file/d/1cMp3n9 ... sp=sharing

Then unpack data with this command:
Code: Select allnpdtool.exe ds subtitles.astd.sdat subtitles.astd.out

Then open OUT file with hex editor and you will be able to see decrypted text.

Edit: You already know that, but let's leave this instruction for others.


But the file format seems to be too complicated to handle packing with longer sentences.

Edit2: I have created this article for future reference http://wiki.xentax.com/index.php/PlayStation_EDAT_SDAT

Thank you very much, but this whole decryption process I'm already doing, I'm having trouble editing the pointers (where the sentence starts and ends), because in translation sometimes the sentence gets longer.
All the subtitles translation I already did, I just wanted to update it.
## Post #8
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2022-04-12T08:15:33+00:00
- Post Title: Driver San Francisco [PS3] - more characters in a translation

Please reupload. 

> Reply from SpeedVash ↑Wed Jan 19, 2022 7:08 am at Wed Jan 19, 2022 7:08 am
>
> 
ikskoks wrote: ↑Wed Jan 19, 2022 6:59 am
Can you upload this "subtitles.astd.sdat" file to some hosting site like mega.nz or google drive?


Follow the file.
https://www.mediafire.com/file/jwlngczs ... p.rar/file
