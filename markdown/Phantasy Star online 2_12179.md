## Post #1
- Username: TheJensons
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 01, 2014 12:00 pm
- Post datetime: 2014-11-01T04:07:35+00:00
- Post Title: Phantasy Star online 2

So I have been trying to figure out how to get the audio from this game but it seems as though there is not tool to unpack the sound files for PSO2.
I do not even know where to begin. I know that I have seen a few audio like files but I have no clue on how to unpack them. The files are listed as

11_sound_voice_st_025010 AU Sound Format
11_sound_voice_st_025010.acb


I could be in the wrong area but I have no clue. I was wondering if someone figured out how to rip the sounds from PSO2 I know the models have been done but the sound effects such as voices and SFX are no where to be found.
## Post #2
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2014-11-02T02:33:20+00:00
- Post Title: Phantasy Star online 2

I would like to know this as well.
## Post #3
- Username: TheJensons
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 01, 2014 12:00 pm
- Post datetime: 2014-11-02T07:55:50+00:00
- Post Title: Phantasy Star online 2

> Reply from ShinKun
>
> I would like to know this as well.

Yea they have some good VA and SFX in the game.
## Post #4
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2014-11-02T23:28:00+00:00
- Post Title: Phantasy Star online 2

If you get the acb file, you can remove everything above the header "@UTF", Then you can use PES2014 File Exporter to extract the hca files, then use HCA2WAV to convert. It works, but some sound files appears to be misnamed or something like that.
## Post #5
- Username: TheJensons
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 01, 2014 12:00 pm
- Post datetime: 2014-11-03T01:13:05+00:00
- Post Title: Phantasy Star online 2

> Reply from ShinKun
>
> If you get the acb file, you can remove everything above the header "@UTF", Then you can use PES2014 File Exporter to extract the hca files, then use HCA2WAV to convert. It works, but some sound files appears to be misnamed or something like that.
Could you take some pictures on the procedure?
## Post #6
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2014-11-03T22:44:37+00:00
- Post Title: Phantasy Star online 2

It's really not biggie. Whn you open up a acb file in a hex editor such as HxD, you'll see this.
 

Just remove everything above the @UTF header and save the file. You should be left with the "@UTF" header at the top of the file. 
It's really not biggie. Whn you open up a acb file in a hex editor such as HxD, you'll see this.
 

Then just use PES2014 File Explorer to view the file and you can extract the file 1 by 1... If we can get someone to make an extractor for the acb file, then we'd be in business.

If anyone's interested, I can PM you the files.
## Post #7
- Username: TheJensons
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 01, 2014 12:00 pm
- Post datetime: 2014-11-04T05:27:41+00:00
- Post Title: Phantasy Star online 2

> Reply from ShinKun
>
> It's really not biggie. Whn you open up a acb file in a hex editor such as HxD, you'll see this.
 

Just remove everything above the @UTF header and save the file. You should be left with the "@UTF" header at the top of the file. 
It's really not biggie. Whn you open up a acb file in a hex editor such as HxD, you'll see this.
 

Then just use PES2014 File Explorer to view the file and you can extract the file 1 by 1... If we can get someone to make an extractor for the acb file, then we'd be in business.

If anyone's interested, I can PM you the files.

I run into an error using Hcadec the hca files extract but with no playable sounds. Files are just blanks.

My process
1. Delete the lines before @UTF



2. Save and open in PES2014


3.Then export block to file which gives Hca files.


4.Run Hcadec and here is end result.
## Post #8
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2014-11-04T12:31:08+00:00
- Post Title: Phantasy Star online 2

It's possible some went wrong. That PES2014 file explorer is geared towards whatever game it supports I think. Some files will export right, how the name doesn't match the sounds...
## Post #9
- Username: TheJensons
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 01, 2014 12:00 pm
- Post datetime: 2014-11-04T20:23:48+00:00
- Post Title: Phantasy Star online 2

> Reply from ShinKun
>
> It's possible some went wrong. That PES2014 file explorer is geared towards whatever game it supports I think. Some files will export right, how the name doesn't match the sounds...
 Yea you are right some files will export right and others won't. Hopefully someone makes an .acb extractor.
## Post #10
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2014-11-05T14:04:28+00:00
- Post Title: Phantasy Star online 2

That could happen if someone with the knowledge cares enough about it.
