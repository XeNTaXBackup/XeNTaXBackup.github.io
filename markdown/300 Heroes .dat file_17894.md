## Post #1
- Username: alphax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 28, 2018 8:23 pm
- Post datetime: 2018-03-28T13:45:33+00:00
- Post Title: 300 Heroes .dat file

Hi there. Recently I tried to rip a character model from the game 300 heroes. 3dsmax or maya couldn't open this file format, so I started searching. Following your instructions that i found on site I converted the .x file using offzip and got 2 other files: .dat and .wuy. But, when it came to use Hex2Obj I lost it completely. Can anyone help? I will be very grateful! I'll attach a link to .rar with the files.
[https://drive.google.com/open?id=1dRa6v ... sVvozdZihX](https://drive.google.com/open?id=1dRa6vSZ7cq5iuWEIMAnBcZsVvozdZihX)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-28T17:21:38+00:00
- Post Title: 300 Heroes .dat file

The model data is easy to find. Search for "00 00 01 00 02 00" to find the start of the indices. After the indices end, there is some other data with lots of 0s (didn't investigate what it might be). After that the vertex data starts, should be easy to spot by looking at the ASCII view. The data is sequential : first vertex positions, after that normals, followed by uvs. So when you find the start offset of the vertex positions, you would do offset + 24 * vertex count to get the uv offset.

2 examples in hex2obj (000023c8.dat) :
