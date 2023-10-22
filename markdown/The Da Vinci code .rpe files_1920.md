## Post #1
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-05-24T16:49:37+00:00
- Post Title: The Da Vinci code .rpe files

Hello,

Could you help me and take a look to the .rpe and .ddb files of the Da Vinci code. These files contain the speeches.

thx
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-05-24T21:10:56+00:00
- Post Title: The Da Vinci code .rpe files

Try a file ripper, are wav pcm
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-24T22:34:56+00:00
- Post Title: The Da Vinci code .rpe files

> Reply from SilentHill
>
> Hello,

Could you help me and take a look to the .rpe and .ddb files of the Da Vinci code. These files contain the speeches.

thx

Well, we always help, but we need example files.
## Post #4
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-05-25T05:17:57+00:00
- Post Title: The Da Vinci code .rpe files

Here are the files.

the .rpe file: [http://nexuspc.hu/~methos05/m11_dialogue.zip](http://nexuspc.hu/~methos05/m11_dialogue.zip)
[m11_dialogue.zip](https://xentaxbackup.github.io/file/750_m11_dialogue.zip)
## Post #5
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-08-05T17:43:10+00:00
- Post Title: The Da Vinci code .rpe files

Hy guys,

Did you have any luck with this game?
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-19T04:34:37+00:00
- Post Title: The Da Vinci code .rpe files

Jaeder Naub or FileStripper is your friend on the RPE file.
just set it to rip RIFF wave, and the cookies are all yours.
## Post #7
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-19T11:47:38+00:00
- Post Title: The Da Vinci code .rpe files

I didn't see this thread, but with a quick look on the supplied archive; this is what I find out:

```
04 - number of files 
24 - null

// for each file

	06 - filename
	26 - unknown
	04 - file offset
	04 - file length
	04 - unknown

// for each file

	 x - file data
	 x - null padding
```


BMS-script:

```
Get TEMP Long 0 ;
Get FILENUM Long 0 ;
GoTo 32 0 ;
For F = 1 To FILENUM ;
GetDString FNAME 6 0 ;
SavePos TEMP 0 ;
Math TEMP += 26 ;
GoTo TEMP 0 ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
SavePos FSIZEX 0 ;
Get FSIZE Long 0 ;
Get TEMP Long 0 ;
Log FNAME FOFFSET FSIZE FOFFSETX FSIZEX ;
Next F ;
```

[rpe.zip](https://xentaxbackup.github.io/file/794_rpe.zip)
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T15:27:18+00:00
- Post Title: The Da Vinci code .rpe files

Good job    PXR   thanks for script
