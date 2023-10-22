## Post #1
- Username: zeaofsuos
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Apr 19, 2019 10:07 pm
- Post datetime: 2019-10-09T12:13:28+00:00
- Post Title: ADMIN, PLEASE DELETE.

ADMIN, PLEASE DELETE.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-10-09T23:04:15+00:00
- Post Title: ADMIN, PLEASE DELETE.

This script will do the GameCube archive:

# The Sims 2 - GameCube .arc extractor
# By Dave, 2019

Endian Big

Goto 0x10
Get ENTRIES Long

For A = 1 to ENTRIES

	Get JUNK Long
	Get OFFSET Long
	Get SIZE Long
	Get FILENAME String
	String FILENAME + ".dsp"
	Get JUNK Long
	Get JUNK Long

	Log FILENAME OFFSET SIZE

Next A
