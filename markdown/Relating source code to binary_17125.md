## Post #1
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2017-10-12T00:05:20+00:00
- Post Title: Relating source code to binary

Hey, I've acquired the source code to an old PSX/PC game, and I'm currently working a level editor for the game. I'd like to be able to modify the .exe's binary data. (IE: Map registries, modify the information about texture id, theme id, etc). How can I calculate the hex position of values in a .exe if I have the source code? Unfortunately I do not have the exact values, so I cannot do a search in a hex editor. (The exact values were in a dynamically generated header file created upon building the main game archive, as to which I do not have the means of building yet.)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-10-12T21:36:07+00:00
- Post Title: Relating source code to binary

> Reply from Kneesnap
>
> Hey, I've acquired the source code to an old PSX/PC game, and I'm currently working a level editor for the game. I'd like to be able to modify the .exe's binary data. (IE: Map registries, modify the information about texture id, theme id, etc). How can I calculate the hex position of values in a .exe if I have the source code? Unfortunately I do not have the exact values, so I cannot do a search in a hex editor. (The exact values were in a dynamically generated header file created upon building the main game archive, as to which I do not have the means of building yet.)

ooh good question!!

if you have the source code you should be able to compile the code to .exe - why do you need to modify existing binary data?

(and you won't be able to know the actual address of any source code unless you can build (byte for byte) using the same compiler, and build settings)
## Post #3
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2017-12-06T18:52:42+00:00
- Post Title: Relating source code to binary

> Reply from WRS
>
> Kneesnap wrote:Hey, I've acquired the source code to an old PSX/PC game, and I'm currently working a level editor for the game. I'd like to be able to modify the .exe's binary data. (IE: Map registries, modify the information about texture id, theme id, etc). How can I calculate the hex position of values in a .exe if I have the source code? Unfortunately I do not have the exact values, so I cannot do a search in a hex editor. (The exact values were in a dynamically generated header file created upon building the main game archive, as to which I do not have the means of building yet.)

ooh good question!!

if you have the source code you should be able to compile the code to .exe - why do you need to modify existing binary data?

(and you won't be able to know the actual address of any source code unless you can build (byte for byte) using the same compiler, and build settings)

Oops, I somehow didn't get notified for this topic. I can't compile it right now for several reasons. The source code I have was not the final build of the game, and the PC port is not complete yet. I'm still working on building the PSX version though. I've been slowly learning and been using a disassembler to find most things, but I'm still having trouble finding stuff in some of the more complex parts, like trying to disable culling
