## Post #1
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-11T10:45:48+00:00
- Post Title: Conception 2's .cfsi archive full of air?

I've got a problem with [this](https://drive.google.com/open?id=1YS4RC4foC8w7AXQGK013Jii7zPDgXHmQ) big file from Conception 2: Children of the Seven Stars for PC: The size of that one is at about 2.7GB, but I only see the file 00000000 (size is 10KB) when opening this archive with 7z. On the other hand, 7z notes that there are data behind the lonesome file I see. Question for me is now:
How can I make all those other files visible? It can't be that the file I can unpack from that one is the only file in it, 'cause that would make this file full of air...
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-11T12:53:27+00:00
- Post Title: Conception 2's .cfsi archive full of air?

There are over 8,500 files in that archive.

This script should extract them all for you.  It's specific to this archive, so probably won't work on anything else.


# CFSI extract

Set DATA_START 0x2d7a0
Goto 0x0003

For B = 1 to 405

# Get folder name/entry count

Get NAME_SIZE Byte
GetDString FOLDER_NAME NAME_SIZE
Get FOLDER_ITEMS Byte

If FOLDER_ITEMS = 0xFC
	Get FOLDER_ITEMS Short
Endif


# Process entries for this folder

For A = 1 to FOLDER_ITEMS

	Get NAME_SIZE Byte
	GetDString FILENAME NAME_SIZE
	Get OFFSET Long
	XMath OFFSET "DATA_START + (OFFSET * 0x10)"
	Get SIZE Long
	Set OUT_FILE ""
	String OUT_FILE + FOLDER_NAME
	String OUT_FILE + FILENAME

	Log OUT_FILE OFFSET SIZE

Next A

Next B
