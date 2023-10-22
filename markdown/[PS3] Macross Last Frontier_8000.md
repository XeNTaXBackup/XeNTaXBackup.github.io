## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-06T15:45:19+00:00
- Post Title: [PS3] Macross Last Frontier

Geometry and UV. Some UVs are incorrect because there are 100 vertex formats and I don't have time to go through thousands of textures named in hexadecimal to find the right textures to test the scaling for each format. Most mecha planes are in pieces so it kind of sucks. The game is also just a space shooter so there are no character models other than the Vajra; everything else is either a spaceship, plane, plane part, or architecture.

EDIT: Oops! Forgot to make one change to the code... download again.

[http://www.mediafire.com/?d755385aoiy2o99](http://www.mediafire.com/?d755385aoiy2o99)
* Rip game.
* Run offzip on the dat files.
* Run exe in game root directory, it will search for all HLD files and convert to OBJ.
* Textures must be applied manually.
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-06T17:42:37+00:00
- Post Title: [PS3] Macross Last Frontier

Good Treadh man....
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-06T21:40:30+00:00
- Post Title: [PS3] Macross Last Frontier

Just an exe?
I want to see some code

Or post up the format
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-06T22:03:30+00:00
- Post Title: [PS3] Macross Last Frontier

its nearly identical to dynasty warriors 7 just look at that code.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-06T22:48:21+00:00
- Post Title: [PS3] Macross Last Frontier

Here is source. Macross code is in ps3_macross_frontier.cpp.
[http://www.mediafire.com/?np5q92um3x6h4i3](http://www.mediafire.com/?np5q92um3x6h4i3)

File format is simple chunk based format. All chunks except root chunk have following format:

chunkname (4 bytes)
chunksize (4 bytes)
parameter1 (4 bytes)
parameter2 (4 bytes)
chunkdata (of chunksize variable bytes)

Model data is in the THMG sections or something like that. There are two dwords in chunk I called u01 and u02. These are the vertex byte flags. If high word of u01 is 0x02, for example, vertex structure is 16 bytes. If 0x03, it's 20 bytes, and so on. Low word appears to control format of weights or something else in between the position and uv data. u02 appears to control the UV format, which I know I have wrong in some cases. Game is somewhat similar to chrrox's Valkyria Chronicles I think.

The file names are actually there in the dat file, but I'm just too lazy to write an extractor too at the moment. I've also been so unlucky these past two months... got laid off from teaching at the university... got into a car accident where some lady texting on her cell phone rear-ended me and totaled my car. This is also the second time a Korean lady has totaled my car. And I don't like the insurance company's settlement offer so now I have to sue and shit... I'm telling ya shit hasn't been going well and I need to find another car and job soon. Life sucks and I feel like going postal on people now.
## Post #6
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-01-06T23:52:40+00:00
- Post Title: [PS3] Macross Last Frontier

Excellent work, thanks!!
## Post #7
- Username: sidhi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 10, 2013 11:35 pm
- Post datetime: 2013-05-13T00:25:59+00:00
- Post Title: [PS3] Macross Last Frontier

All of the mediafire links are dead... Please reupload... Thanks...
