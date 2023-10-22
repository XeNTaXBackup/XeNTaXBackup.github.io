## Post #1
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-11-08T06:21:15+00:00
- Post Title: "Advanced" techniques for figuring out a format 100% ?

If you had time and energy available, what other techniques besides using a hex editor and investigation would you use to figure out a model format entirely?

I really want to start writing exporters, but I always end up only knowing like 80% of the total model format.
(need to know what other data represents  but vertices/normals/uvs, meshesLOD, etc.)

Some ideas I came up with, but some don't know how to implement

1) Study directx/game programming in depth to know what to expect
2) Use Ida pro to try to find out the structures/loading of the model there (is this possible?)
3) Read memory dumps (similar to 2) ? really don't know how to do it, but I read it was used for figuring out some animations structures in a PS2 emulator)
4) Change some small bytes of info in the model, run it. (Not very useful since many times the game would just crash)

any other ideas, or how to apply 2) and examples if possible?

Cheers.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-08T11:06:58+00:00
- Post Title: "Advanced" techniques for figuring out a format 100% ?

> Reply from Bastien
>
> 1) Study directx/game programming in depth to know what to expect
May help. But the problems I face are like this:
instead of using a standard Vertex block v vn vt (3 floats, 3 floats, 2 floats) 
there is 3 half floats and a zero byte for the v position (just as an example).

Even the very best directx knowledge won't help you in this case, I guess.

> 2) Use Ida pro to try to find out the structures/loading of the model there (is this possible?)
This is the very best solution, imho. (Though I'm using ollyDbg.)
You'll need: the game exe and ASM knowledge (x86 assembler for intel/AMD cpus)
But there a two  caveats:
Supposed you have a legal copy of the game you'll often face a copy protection.
Means before it comes to debugging you'll have to crack the protection. This being more complicated than getting the model data.

When debugging finally you'll face 100s of function calls to find your path through.
Setting some breakpoints at chosen locations will help.
For example
[](http://www.pic-upload.de/view-21268500/OllyDBG_BP_for_File_read.jpg.html)

Once you start reading the model file (file read fct.) byte per byte (or DWORD) in the debugger you should get a clue about the format.

But often you'll find the data being read into a filebuffer. Then you will have to set a memory break point at the buffer start to find the code section where to proceed.

Even more game resource data almost ever being compressed. So some experience is required to know where to set the breakpoints behind the uncompress routines to speed up analysis.

If there exist some modding tools for the game (i.e. a map editor or something like that) you could chose a small model to load which could make things easier.

> 3) Read memory dumps (similar to 2) ? really don't know how to do it, but I read it was used for figuring out some animations structures in a PS2 emulator)You'll need the emulator.

For pc there are tools to read the RAM (WinHex, menu Tools, RAM editor). 
Or with some coding skills you could use ReadProcessMemory() in your own tool.

But the amount of RAM data on pc being excessive. 
Maybe a tool like ReClass (from DRUNKEN CHEETAH) might help. (Up to now I was too lazy to learn the required basics.)
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-08T16:10:04+00:00
- Post Title: "Advanced" techniques for figuring out a format 100% ?

> Reply from Bastien
>
> If you had time and energy available, what other techniques besides using a hex editor and investigation would you use to figure out a model format entirely?

I really want to start writing exporters, but I always end up only knowing like 80% of the total model format.
(need to know what other data represents  but vertices/normals/uvs, meshesLOD, etc.)

Some ideas I came up with, but some don't know how to implement

1) Study directx/game programming in depth to know what to expect
2) Use Ida pro to try to find out the structures/loading of the model there (is this possible?)
3) Read memory dumps (similar to 2) ? really don't know how to do it, but I read it was used for figuring out some animations structures in a PS2 emulator)
4) Change some small bytes of info in the model, run it. (Not very useful since many times the game would just crash)

any other ideas, or how to apply 2) and examples if possible?

Cheers.

Disassembly using Olly or IDA is one of the best methods I've found. For example if a format uses XOR encryption sometimes cracking it could be as simple as reading the assembly which tells you the key in order to XOR it.
## Post #4
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-11-08T19:45:25+00:00
- Post Title: "Advanced" techniques for figuring out a format 100% ?

Thanks for the reply and tips, guys.

I think going the dissasembler way is what I'll do. 
I've got [this ebook](http://www.amazon.com/IDA-Pro-Book-Unofficial-Disassembler/dp/1593271786/ref=pd_bbs_sr_1?ie=UTF8&s=books&qid=1231262432&sr=8-1&tag=securityxcom-20)
and so far I'm kinda lost even decompiling my own 30 lines .exes lol. I think the book assumes some Assembler knowledge, so I'll have to go back and research/learn that as well.
Which sound pretty interesting to me, but also quite challenging, since I don't have a computer science background.

So far I've only seen tutorials on how to get encryption keys using IDA pro for GTA games. 
And correct me if I'm wrong but I think is actually quite hard/tedious/time consuming to disassemble a game .exe to find structures, and that's why there are tons of importers which only
use the bare minimum data, and not many exporters ?

I think it will be great if some experienced coder in dissasembling process could write a tutorial on how to even get started (remove copy protection like you shakotay said).
Or if you have some time could you Shakotay/cra0 be my "mentors" in finding out the missing data for the model formats I want using disassembling techniques? 
We could use this thread or a separate one for the format and then I could translate the knowledge to a tutorial form for the wiki.

Thanks! cheers
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-08T23:16:49+00:00
- Post Title: "Advanced" techniques for figuring out a format 100% ?

> Reply from Bastien
>
> Or if you have some time could you Shakotay/cra0 be my "mentors"Just speaking for me only I can say that I don't want to be a mentor in my free time, sry. And I don't have the time for writing tutorials.

The name "Nynaeve" ("Adventures in Windows debugging and reverse engineering") is coming into my mind concerning debugging. That's a smart guy you can learn from amazing things.

> in finding out the missing data for the model formats I want using disassembling techniques?
What game(s) we are talking about?
If it's on pc and I accidentally owe the game in question I could have a look at it using ollyDbg.
But don't expect too much. I just could tell you whether it makes sense to debug it or not.

And yes, for me it was always time consuming to debug games.
Especially for the more complex model formats (Mafia2, Witcher 2) it made more sense to me to use the blender scripts from Mariusz Szkaradek for example than wasting my life time.
## Post #6
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-11-10T13:34:18+00:00
- Post Title: "Advanced" techniques for figuring out a format 100% ?

I usually locate/reverse engineer the model loaders using IDA and then use PIX where possible to make sense of data, like you can tell the input layout of vertex buffers and such.
## Post #7
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-11-19T00:15:04+00:00
- Post Title: "Advanced" techniques for figuring out a format 100% ?

A quick blurb I have on following through assembly; it may or may not be relevant: if you have a debugger attached, just step through the instructions and look for changes in registers and the stack. It's usually easier if you find a pattern in the data changes than trying to figure out the purpose of each instruction. Don't use IDA on its own. It's more of a tool to supplement Olly than a standalone debugger. IDA for me is mainly a "find functions that Olly won't and also better string refs" tool. For any real debugging work it's still Olly. OllyDbg 2.* has much better code path visualization than 1.*, but if you hit upon wrapped code 1.* works a bit better, since it has a lot of plugins and doesn't do stupid things such as treat unpacked code as data and refuse to analyze it.
## Post #8
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2013-11-28T08:28:24+00:00
- Post Title: "Advanced" techniques for figuring out a format 100% ?

[This](http://ref.x86asm.net/coder32-abc.html) is an excellent reference of x86 opcodes and their associated details.

[edit]
I remembered what else I was going to say...
Check low for hanging fruit. Look at the strings in the program in your debugger and where they're used. If you have already inferred what file has the data you're looking for in it you can sometimes easily find the loading methods by cross referencing its file name.
