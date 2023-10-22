## Post #1
- Username: zdsmdbh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 13, 2013 10:03 am
- Post datetime: 2015-04-07T05:38:09+00:00
- Post Title: Parse model through disassembling or decompilation?

I just spent 2 hours on parsing bones data,but I still can't understand how they work.

Is is possible to parse model through disassembling or decompilation?
Track the program,and see how it read data,maybe I can figure out how bones data work?

Does anyone try this before?
Or it's impossible at all?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-08T12:52:01+00:00
- Post Title: Parse model through disassembling or decompilation?

> Reply from zdsmdbh
>
> Track the program,and see how it read data,maybe I can figure out how bones data work?Using a debugger nearly everything is possible. But it might take much, much more time than just 2 hours.  

Years ago I debugged games to find/enable hidden developer's consoles which was not easy
but seems to me not as hard as what you want to try out.

2 months ago I was in a render loop of a game to examine a scroll casting in "single frame mode".
Hours later I found me lost in the depth of the assembly code. (What a waste of time and life, hehehe...)

Same as with the analysing of 3D model's formats data you're required to get an idea of the code structure here
(write down the call tree of functions at least).

In a D3D9 game's ASM code I found this line in a jump table:
009F7A9A   $-FF25 1816AE00  JMP DWORD PTR DS:[<&d3dx9_43.D3DXCreateMesh>

You could attach a debugger to the game you want to explore  and try to find a similar line.

Set a breakpoint there. If it is hit continuously trace the code until you meet a better location to place a BP.
On refresh of a scene where new objects are to be displayed that BP might be hit.

Most important: for my experience the game will crash then if it doesn't run in windowed mode.

You might search for code where the LODs of buildings are being processed for example.
Characters would be the second step, I think.
Good luck.
