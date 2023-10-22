## Post #1
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-07-29T00:48:04+00:00
- Post Title: Robotech Invasion (PS2) DATA.*

Hello everyone, I'd really appreciate any assistance with unpacking DATA.ENG & DATA.PAK files from this game. Just a heads-up: there's a TOC in beginning of those archives.
[You can find cuts from both DATA.* bigfiles here](https://drive.google.com/open?id=1qpRLzzQe-9JUkpM0TGny7MPmyc2JSS-r).

Best regards!
PS. DATA.PAK_end seems to be identical to DATA.ENG_end but I included both nonetheless.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-29T11:39:47+00:00
- Post Title: Robotech Invasion (PS2) DATA.*

As far as I can tell, the files don't appear to be compressed, so this script should extract all the files.

# Robotech: Invasion PS2 DATA.PAK extract
# QuickBMS script

Get ENTRIES Long
Set ENTRY_START 0x800

For A = 1 to ENTRIES

	Goto ENTRY_START
	Get FILENAME String
	Math ENTRY_START + 0x28
	Goto ENTRY_START
	Get OFFSET Long
	Math OFFSET * 0x800
	Get SIZE Long

	Log FILENAME OFFSET SIZE

	Math ENTRY_START + 0x08

Next A
## Post #3
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2019-07-30T09:57:14+00:00
- Post Title: Robotech Invasion (PS2) DATA.*

Thanks a ton!
