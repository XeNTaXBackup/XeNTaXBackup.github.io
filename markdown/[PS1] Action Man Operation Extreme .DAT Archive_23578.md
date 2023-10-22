## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-03-11T15:03:37+00:00
- Post Title: [PS1] Action Man: Operation Extreme .DAT Archive

Hello, Xentax Forums! Today I am asking about a way to extract files from one of my favorite childhood games, Action Man: Operation Extreme for the Playstation 1. There is little to no documentation on this game, understandably so as it is extremely underrated and unbeknownst to many. 



Upon extracting the ISO I discovered the following:
Several different sound archives ".XA "
One large archive most likely containing assets for the game ".DAT "

I attached an overview of the files as well as uploaded the ACTION.dat file for further inspection.

Here is the link to the .DAT file.

Thank you for your time and I look forward to your replies!
[Action_Man_Files.png](https://xentaxbackup.github.io/file/19699_Action_Man_Files.png)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-11T21:50:11+00:00
- Post Title: [PS1] Action Man: Operation Extreme .DAT Archive

Your DAT file may not contain any offsets, filenames or sizes, so they probably can be stored in the main executable.

Structure of DAT archive looks like this:

```
{
   x bytes - file data
   x bytes - padding
}
```


Offsets and sizes for few first files looks like this:

```
file1      0         7205
file2      16384     28338
file3      45060     13547
file4      59392     317175
```


So you have two options here. Extract data manually in hex editor or find the offset array in the main executable and try to do it automatically.
Data doesn't seem to be compressed, so you may probably also try some ripping tools like PSound etc.
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-03-11T23:02:18+00:00
- Post Title: [PS1] Action Man: Operation Extreme .DAT Archive

Just an update on this one.  The file offsets are stored in the table at the start of the file.  You can use this QuickBMS script to extract the raw files, but no filenames or file type info.


Goto 4

Get ENTRIES Long

For A = 1 To ENTRIES
	Get MISC1 Long
	Get OFFSET Long
	XMath OFFSET "(OFFSET * 0x800) + 0x4000"
	Get SIZE Long

	String FILENAME P "ACTION_%A%"

	Log FILENAME OFFSET SIZE

Next A
