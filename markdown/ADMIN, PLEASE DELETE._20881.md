## Post #1
- Username: zeaofsuos
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Apr 19, 2019 10:07 pm
- Post datetime: 2019-07-31T03:15:17+00:00
- Post Title: ADMIN, PLEASE DELETE.

ADMIN, PLEASE DELETE.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-31T11:22:37+00:00
- Post Title: ADMIN, PLEASE DELETE.

You can extract the files with this QuickBMS script.

The music is in the WaveBank.xwb file.  You can then extract that with something like unxwb.


# SAR file extract

IDString "SARCFV\x01\x01"

Goto 0x0008
Get ENTRIES Long
Get FILE_TABLE Long

Goto FILE_TABLE

For A = 1 to ENTRIES

	Get LENGTH byte
	GetDString FILENAME LENGTH
	Get JUNK byte
	Get OFFSET Long
	Get SIZE Long
	Get SIZE2 Long

	Log FILENAME OFFSET SIZE

Next A
