## Post #1
- Username: millez
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 12, 2019 10:23 am
- Post datetime: 2019-10-12T02:34:13+00:00
- Post Title: NDS: Last Window's .pack files

Hey! I've been looking at the unpacked ROM contents of Last Window: The Secret Of Cape West and discovered that most of the game's content is stored inside a .pack archive. Here's what they look like:


I don't really understand how the file structure works due to a complete lack of knowledge and experience when it comes to these things. If anyone can figure it out and chuck together a QuickBMS script you'd be a life saver!
Here's the file that I took a screenshot of:
[https://drive.google.com/open?id=1rvM9K ... -iYNY2-LZv](https://drive.google.com/open?id=1rvM9KiZsFxr5jjLhJnw1KQ-iYNY2-LZv)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-10-12T12:05:51+00:00
- Post Title: NDS: Last Window's .pack files

This script should extract and decompress the files.


# Last Window extract
# By Dave, 2019

ComType zlib

Get JUNK Long

Get ENTRIES Long
REVERSELONG ENTRIES

Get DATA_START Long
REVERSELONG DATA_START
Math DATA_START + 4

Get JUNK Long

For A = 1 to ENTRIES

	Get LENGTH Byte
	GetDString FILENAME LENGTH
	Get ZSIZE Long
	REVERSELONG ZSIZE
	Math ZSIZE - 4
	SavePos TABLE_POS

	Goto DATA_START
	Get SIZE Long
	Math DATA_START + 4

	CLog FILENAME DATA_START ZSIZE SIZE
	Math DATA_START + ZSIZE

	Goto TABLE_POS

Next A
