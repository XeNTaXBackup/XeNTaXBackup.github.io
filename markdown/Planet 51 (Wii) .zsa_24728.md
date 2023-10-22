## Post #1
- Username: jaqueando
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 09, 2021 12:04 am
- Post datetime: 2021-11-11T14:57:28+00:00
- Post Title: Planet 51 (Wii) .zsa

Hello everyone, new here and with much to learn.

I've successfully exported some files from the game Planet 51 (Wii) using Noesis plugins made by this forum member Zheneq. He did a great job and models with UVs and rigging can be obtained. I want to get one step further parsing the animation files (.zsa) but I'm struggling to identify everything within the files. You can find the idle animation attached. I really don't know how the data blocks are storing info, pretty sure one is for location (x,y,z), second for rotation and las scale. Tried FP16 with big endian but got some NaN problems. Many thanks in advance.

Here's what I've found out after a couple of days reading in HxD:
- Numbers are big endian
- Blocks are made by 2 bytes
- Header
0		2641	        1		1		#000 same for all files
16880	0		0		17		17 = frames in animation
0		0		0		0		- blank
0		0		0		0		- blank
0		0		0		0		- blank
16256	0		0		11		11 = number of bones
- Bone definition example
Bo		ne		_H		ea		#1E8 bone name
d0		0		0		0		- bone name
0		0		0		0		- bone name
0		0		0		0		- blank
0		0		0		0		- blank
0		0		0		0		- blank
0		0		0		0		- blank
0		0		0		0		- blank
0		15		0		2		- data block 1, frame 15 first, frames to read 2
0		28		0		15		- data block 2, frame 28 first, frames to read 15
0		0		0		0		- data block 3, frame 0 first, frames to read 0
- First data block at #3F8 defines 45 frames. Example (at 3FC):
0000 A0F8 9DFA 0000 - Frame 0
0010 A0F8 9DFA 0000 - Frame 16
- Second data block at #564 defines 62 frames. Same structure as first block
- Third data block. empty in this file (says 0 frames)
[rover_reposo.zip](https://xentaxbackup.github.io/file/21197_rover_reposo.zip)
## Post #2
- Username: jaqueando
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 09, 2021 12:04 am
- Post datetime: 2021-11-12T17:19:07+00:00
- Post Title: Planet 51 (Wii) .zsa

I've edited original post with some clarifications I've found in another animation that you can find attached in this reply.
[rover_scan.zip](https://xentaxbackup.github.io/file/21200_rover_scan.zip)
