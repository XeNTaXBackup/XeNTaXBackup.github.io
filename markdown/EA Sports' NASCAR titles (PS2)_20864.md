## Post #1
- Username: Scar7752
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 07, 2017 4:03 am
- Post datetime: 2019-07-27T03:08:59+00:00
- Post Title: EA Sports' NASCAR titles (PS2)

I'm looking for a few textures from EA Sports' NASCAR titles that were on the PS2.

Their archives are in a DAT file, which I know isn't helpful, but I wonder if a Madden tool could be reworked to work with these.

[Here's a few files of interest](https://drive.google.com/drive/folders/1HlPnPAeTchrsdk01w1Xm9UkN6-axWytk?usp=sharing) from NASCAR 06, 07 and 09. They all run on the same engine so they should all work together in theory. I can upload more if you need more guinea pigs.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-27T11:38:36+00:00
- Post Title: EA Sports' NASCAR titles (PS2)

Would a QuickBMS script be of use to you?  It will give you a bunch of .tmf and .3ds files.

I did this a while ago, but I think it works.  I'm not an expert on textures, so hopefully you can do something with the extracted files.


# NASCAR DAT file extract
# By Dave

ComType EA_MADDEN

Get ARC_SIZE asize
Set CHUNK_START 0

Do
	Goto CHUNK_START
	Get CHUNK_NAME Long
	Get CHUNK_SIZE Long

	If CHUNK_NAME = 0x46524554
		Get JUNK Long
		Get JUNK Short
		Get ENTRIES Long
	Endif

	If CHUNK_NAME = 0x31524944
		SavePos DIR_START Long
	Endif

	If CHUNK_NAME = 0x504d4f43
		SavePos COMP_START Long
	Endif

	if CHUNK_NAME = 0x41544144
		Set DATA_START CHUNK_START
	Endif

	Math CHUNK_START + CHUNK_SIZE

While CHUNK_START < ARC_SIZE


For A = 1 to ENTRIES

	Goto DIR_START
	Get OFFSET Long
	Math OFFSET + DATA_START
	Get ZSIZE Long
	Math DIR_START + 8

	Goto COMP_START
	Get COMP_FLAG Long
	Get SIZE Long
	Math COMP_START + 8

	If COMP_FLAG = 5
		CLog "" OFFSET ZSIZE SIZE
	Else
		Log "" OFFSET ZSIZE
	Endif

Next A
## Post #3
- Username: Scar7752
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 07, 2017 4:03 am
- Post datetime: 2019-07-27T17:05:25+00:00
- Post Title: EA Sports' NASCAR titles (PS2)

I dug through some of the files and noticed that the 3DS files, when viewed in a HEX editor, start with "MMAP". Those are most likely textures then, right?
[00000000.zip](https://xentaxbackup.github.io/file/16540_00000000.zip)
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-27T19:00:21+00:00
- Post Title: EA Sports' NASCAR titles (PS2)

I'm not an expert on this side of things, but yes they do look like textures to me.  The .tmf files may be the 3D models, but I wouldn't know what to do with either of those file types, unfortunately.
## Post #5
- Username: Scar7752
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 07, 2017 4:03 am
- Post datetime: 2020-05-22T07:16:21+00:00
- Post Title: EA Sports' NASCAR titles (PS2)

Update!

This is the full UI_CARS.DAT file from NASCAR 2005: CFTC. I know this either completely or almost completely contains texture files. Can anyone help convert them into something readable? 

[https://drive.google.com/open?id=1kvM6W ... K37h4XlRyw](https://drive.google.com/open?id=1kvM6WiK4nP_eaY3c5eIRlUK37h4XlRyw)
## Post #6
- Username: TheKingOfRockNRoll
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 05, 2023 8:34 am
- Post datetime: 2023-03-06T23:18:43+00:00
- Post Title: EA Sports' NASCAR titles (PS2)

It is very strange that all files are the same size

Do you have any progress in this matter?
