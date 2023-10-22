## Post #1
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-05-25T11:30:59+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

Hello, again...on this game, I noticed that in the game files, there is a .ban file in each folder of a character next to the 3d model. I "THINK" these .ban files are the skeletons of the characters but I don't know how to open them. If someone has the talent to examine them, it would be really nice   
Link (.ban + .msh (3d models)): [https://www.mediafire.com/file/xy1ddrqg ... s.rar/file](https://www.mediafire.com/file/xy1ddrqg62cqdak/.BAN_Files.rar/file)

Thank you
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-25T12:56:56+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from SilesVyr ↑Mon May 25, 2020 7:30 pm at Mon May 25, 2020 7:30 pm
>
> I "THINK" these .ban files are the skeletons of the charactersWhy do you think so? The first 3040 bytes block looks like so:

address 0x0:
   66    10 39128     0   752     0 55702 16911 48172     1    24     0  3032     0  3080     0 
 3128     0  3176     0  3224     0  3272     0  3320     0  3368     0  3416     0  3464     0 
 3512     0  3560     0  3608     0  3656     0  3704     0  3752     0  3800     0  3848     0 
 3896     0  3944     0  3992     0  4040     0  4088     0  4136     0  4184     0  4232     0 
 4280     0  4328     0  4376     0  4424     0  4472     0  4520     0  4568     0  4616     0 
 4664     0  4712     0  4760     0  4808     0  4856     0  4904     0  4952     0  5000     0 
...
address 0xa00:
33464     0 33512     0 33560     0 33608     0 33656     0 33704     0 33752     0 33800     0 
33848     0 33896     0 33944     0 33992     0 34040     0 34088     0 34136     0 34184     0 
34232     0 34280     0 34328     0 34376     0 34424     0 34472     0 34520     0 34568     0 
34616     0 34664     0 34712     0 34760     0 34808     0 34856     0 34904     0 34952     0 
35000     0 35048     0 35096     0 35144     0 35192     0 35240     0 35288     0 35336     0 
35384     0 35432     0 35480     0 35528     0 35576     0 35624     0 35672     0 35720     0 
35768     0 35816     0 35864     0 35912     0 35960     0 36008     0 36056     0 36104     0 
36152     0 36200     0 36248     0 36296     0 36344     0 36392     0 36440     0 36488     0 
36536     0 36584     0 36632     0 36680     0 36728     0 36776     0 36824     0 36872     0 
36920     0 36968     0 37016     0 37064     0 37112     0 37160     0 37208     0 37256     0 
37304     0 37352     0 37400     0 37448     0 37496     0 37544     0 37592     0 37640     0 
37688     0 37736     0 37784     0 37832     0 37880     0 37928     0 37976     0 38024     0 
38072     0 38120     0 38168     0 38216     0 38264     0 38312     0 38360     0 38408     0 
38456     0 38504     0 38552     0 38600     0 38648     0 38696     0 38744     0 38792     0 
38840     0 38888     0 38936     0 38984     0 39032     0 39080     0 20544   351 16146     0 

Then follow blocks with many identical bytes. I don't see how to get valuable information/skeleton data (?) from the bytes with blue underlinings:
.



ban file_.png (20.89 KiB) Viewed 261 times
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-25T15:47:40+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

There're 752 offsets followed by the same amount of entries with the same stride 0x30 in the ban file. 752 bones for one model would sound insane for a 2005 game.
Obviously the bones are in the same file as the model.



anakinhooddown.gif (184.32 KiB) Viewed 252 times
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-25T17:16:21+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

Loading the skeleton via Noesis and the model via AMR:



anakinhooddown.jpg (185.3 KiB) Viewed 248 times



Noesis code for this file:

```
	bs = NoeBitStream(data)
	bs.seek(0x1A4A0, NOESEEK_ABS)
	boneCount = bs.readUInt()
	bones = []
	for i in range(0, boneCount):
		pos = bs.tell() + 0x20
		boneName = bs.readString()
		bs.seek(pos, NOESEEK_ABS)
		boneMat = NoeMat43.fromBytes(bs.readBytes(48)).transpose().inverse()
		bonePIndex = bs.readShort()
		bones.append(NoeBone(i, boneName, boneMat, None, bonePIndex))
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	return 1

```
## Post #5
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-05-25T18:16:05+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

It's awesome! So by examining the animation files .bnm you think it could work?

Links: [https://www.mediafire.com/file/khctmops ... s.rar/file](https://www.mediafire.com/file/khctmopsimalls2/.BNM_Files.rar/file)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-26T14:23:08+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

Thing is, I don't deal with animation data.
## Post #7
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-05-26T15:18:26+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

> Thing is, I don't deal with animation data.
okay that's not a problem. Just how did you find the skeleton? I will do the same thing for the other characters
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-28T17:01:48+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

Here's a Noesis script that'll import the meshes and the skeletons from the msh samples you uploaded.
[fmt_StarWarsEp3RotS_msh.zip](https://xentaxbackup.github.io/file/18461_fmt_StarWarsEp3RotS_msh.zip)
## Post #9
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-05-28T19:35:09+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

> Here's a Noesis script that'll import the meshes and the skeletons from the msh samples you uploaded. Bone weights are not handled yet.
Thank you so much!  

edit: here are .msh files that don't work, thank you for your time and attention   
link: [https://www.mediafire.com/file/394rxlqg ... t.rar/file](https://www.mediafire.com/file/394rxlqg02b704c/Samples_Script.rar/file)
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-29T16:50:13+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

Script updated at the same post.
## Post #11
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-05-29T17:20:09+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

Awesome!
## Post #12
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-07-11T17:00:32+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

Hello!, 
there are some .msh that bug or don't work with the plugin. There are also .msh levels files which have a lot of 3d models (small).

I also have a question, is the rigging information for the characters in the .msh files?

Thank you again!   

Samples: [https://www.mediafire.com/file/dy622tp9 ... 2.rar/file](https://www.mediafire.com/file/dy622tp9a2cnzob/Noesis_Script_Samples2.rar/file)
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-13T05:16:03+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from SilesVyr ↑Sun Jul 12, 2020 1:00 am at Sun Jul 12, 2020 1:00 am
>
> 
I also have a question, is the rigging information for the characters in the .msh files?
Of course, they just weren't handled back then though.

> Reply from SilesVyr ↑Sun Jul 12, 2020 1:00 am at Sun Jul 12, 2020 1:00 am
>
> 
there are some .msh that bug or don't work with the plugin. There are also .msh levels files which have a lot of 3d models (small).
Script updated at the same post. Skin info is supported now.



weightTest.png (95 KiB) Viewed 130 times



Tested on all samples found in this thread up to now and everything works fine.
## Post #14
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-07-13T09:11:05+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

Thank you so much, levels files work very well! (just maybe 1 or 2 missing polygon, but it can be fixed by hand) 
There are just the last .msh files that do not work: (hope it will not create other bug  )
[https://www.mediafire.com/file/zj15gryz ... t.rar/file](https://www.mediafire.com/file/zj15gryzfiq3f5j/Last_Fix_Script.rar/file)

Thank you again!
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-13T10:41:04+00:00
- Post Title: Skeleton files - Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from SilesVyr ↑Mon Jul 13, 2020 5:11 pm at Mon Jul 13, 2020 5:11 pm
>
> 
levels files work very well! (just maybe 1 or 2 missing polygon, but it can be fixed by hand)
The script now handles triangle/triangle strip encoding correctly so it's unlikely to miss anything.

> Reply from SilesVyr ↑Mon Jul 13, 2020 5:11 pm at Mon Jul 13, 2020 5:11 pm
>
> 
There are just the last .msh files that do not work: (hope it will not create other bug  )
Patch done.
## Post #16
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-07-13T12:21:37+00:00
- Post Title: Re: Skeleton files .BAN ? Star Wars: Ep III - RotS (2005) [XBOX]

There is a problem with cin.msh 
[cin.rar](https://xentaxbackup.github.io/file/18460_cin.rar)
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-13T12:59:40+00:00
- Post Title: Re: Skeleton files .BAN ? Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from SilesVyr ↑Mon Jul 13, 2020 8:21 pm at Mon Jul 13, 2020 8:21 pm
>
> 
There is a problem with cin.msh
It appears that there's an empty mesh so guess you hadn't tested it before.  

Script updated.
[viewtopic.php?f=16&t=22200&p=163643#p163643](viewtopic.php?f=16&t=22200&p=163643#p163643)
## Post #18
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-07-13T16:07:41+00:00
- Post Title: Re: Skeleton files .BAN ? Star Wars: Ep III - RotS (2005) [XBOX]

ah okay.
I extract and found this... you know what it could be ?
[new file.rar](https://xentaxbackup.github.io/file/18462_new file.rar)
## Post #19
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-08-10T06:51:11+00:00
- Post Title: Re: Skeleton files .BAN ? Star Wars: Ep III - RotS (2005) [XBOX]

Anyone think they'd be willing to take a look at the game's .bnm animation format? I've got a handful of complete samples here, let me know if you need anything else: [https://mega.nz/file/8Kw3mBbI#J7JM_xKiH ... iMNxyN0BxA](https://mega.nz/file/8Kw3mBbI#J7JM_xKiHpARhZ56Eq8NI7REcqZjo3TfwiMNxyN0BxA)
## Post #20
- Username: SolarisBravo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 14, 2020 1:10 am
- Post datetime: 2020-08-13T17:13:15+00:00
- Post Title: Re: Skeleton files .BAN ? Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from TrumpetPro ↑Mon Aug 10, 2020 2:51 pm at Mon Aug 10, 2020 2:51 pm
>
> 
Anyone think they'd be willing to take a look at the game's .bnm animation format? I've got a handful of complete samples here, let me know if you need anything else: https://mega.nz/file/8Kw3mBbI#J7JM_xKiH ... iMNxyN0BxA

Bump
