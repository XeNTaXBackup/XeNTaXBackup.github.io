## Post #1
- Username: CurbyGuy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 11, 2019 10:59 am
- Post datetime: 2019-11-11T03:14:17+00:00
- Post Title: Wheel Of Fortune / Jeopardy PS2 .DAT sound archive

I need help extracting and repacking the .dat sound archive Artech Studios had on Wheel of Fortune and Jeopardy for the PS2.

Here are some samples
________________________________
[https://drive.google.com/file/d/1qH8z8S ... 75lyA/view](https://drive.google.com/file/d/1qH8z8Sx2_tBssS7n6flknA_YArN75lyA/view) 
[https://drive.google.com/file/d/1Ttvhqv ... eWu5T/view](https://drive.google.com/file/d/1TtvhqvqSAqV0nMLJIyz1dVaWwCZeWu5T/view)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-11T20:12:17+00:00
- Post Title: Wheel Of Fortune / Jeopardy PS2 .DAT sound archive

This QuickBMS script will extract the audio files:

# Wheel Of Fortune / Jeopardy (PS2)
# By Dave, 2019

Endian Big
IDString "SPAK"

For
	FindLoc OFFSET String "VAGp"

	If OFFSET = 0
		Break
	Endif

	Goto OFFSET
	Get JUNK Long
	Get JUNK Long
	Get JUNK Long
	Get SIZE Long
	Math SIZE + 0x20
	Get JUNK Long
	Get JUNK Long
	Get JUNK Long
	Get JUNK Long
	GetDString FILENAME 0x20
	String FILENAME + ".vag"

	Log FILENAME OFFSET SIZE

Next
## Post #3
- Username: CurbyGuy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 11, 2019 10:59 am
- Post datetime: 2019-11-11T23:38:53+00:00
- Post Title: Wheel Of Fortune / Jeopardy PS2 .DAT sound archive

Thanks.
