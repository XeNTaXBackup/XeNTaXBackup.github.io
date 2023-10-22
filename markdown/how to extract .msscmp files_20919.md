## Post #1
- Username: RonaldGriggs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 06, 2019 10:40 am
- Post datetime: 2019-08-06T09:20:47+00:00
- Post Title: how to extract .msscmp files?

there is a file in minecraft console edition (xbox 360) i need to extract it, its a sound archive (Minecraft.msscmp), i can convert .binka file to .wav, but i cant extract it from the archive.
link: [https://raw.githubusercontent.com/DjGam ... aft.msscmp](https://raw.githubusercontent.com/DjGamerDz/mine-inno/master/Minecraft.msscmp)
help me please
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-06T19:44:12+00:00
- Post Title: how to extract .msscmp files?

This QuickBMS script should extract the audio files from that archive:


# Minecraft MSSCMP extract

IDString "BANK"

Goto 0x18
Get FILE_TABLE Long
ReverseLong FILE_TABLE

Goto 0x34
Get ENTRIES Long
ReverseLong ENTRIES


For A = 1 to ENTRIES

	Goto FILE_TABLE
	Get FOLDERNAME_OFF Long
	ReverseLong FOLDERNAME_OFF
	Get FILE_INFO Long
	ReverseLong FILE_INFO

	Goto FILE_INFO
	Get JUNK Long
	Get FILENAME_OFF Long
	ReverseLong FILENAME_OFF
	Math FILENAME_OFF + FILE_INFO
	Get OFFSET Long
	Get JUNK Long
	Get JUNK Long
	Get SAMP_RATE Long
	ReverseLong SAMP_RATE
	Get SIZE Long
	ReverseLong SIZE

	Goto FOLDERNAME_OFF
	Get FOLDER_NAME String
	Goto FILENAME_OFF
	Get FILENAME String

	String FOLDER_NAME + "\"
	String FOLDER_NAME + FILENAME

	Log FOLDER_NAME OFFSET SIZE

	Math FILE_TABLE + 8

Next A
## Post #3
- Username: zugebot
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 18, 2020 3:09 am
- Post datetime: 2020-11-17T19:11:53+00:00
- Post Title: how to extract .msscmp files?

> Reply from RonaldGriggs ↑Tue Aug 06, 2019 5:20 pm at Tue Aug 06, 2019 5:20 pm
>
> 
there is a file in minecraft console edition (xbox 360) i need to extract it, its a sound archive (Minecraft.msscmp), i can convert .binka file to .wav, but i cant extract it from the archive.
link: https://raw.githubusercontent.com/DjGam ... aft.msscmp
help me please

Can you send me a download for the .binka to .wav converter please?
