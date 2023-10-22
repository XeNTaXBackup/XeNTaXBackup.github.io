## Post #1
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-12T12:46:31+00:00
- Post Title: how about making an OpenGL ripper?

There are tools like OGLE which often fail and there is 3DRipperDX which is for DirectX. Both of these never get stuff in t-pose. There is also GameAssassin which I've heard does amazing stuff but is not free and has some very odd payment method, plus it's not completely translated to english.

Has anyone ever thought of making a program like this himself?
I use Python so I could probably use PyOpenGL. However I have no idea how this can be done. You would need to "inject" the ripper to the game, but how would you access the stuff it sends to the GPU? I have no idea.
I guess it would be possible to get t-posed geometry if the skinning is done on the GPU for that game, not on the CPU by the game engine.

I make games, but this is totally different. I never needed to know if you can get stuff sent to the GPU, etc.
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-01-12T16:31:22+00:00
- Post Title: how about making an OpenGL ripper?

3d via rips opengl
## Post #3
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-12T16:56:30+00:00
- Post Title: how about making an OpenGL ripper?

To a format which almost nothing opens, almost never gets textures right and of course never manages to get the t-posed geometry.

If I knew where to look, I'd give it a shot myself, but there doesn't seem to be any documentation on accessing stuff in the GPU anywhere.
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-12T21:01:41+00:00
- Post Title: how about making an OpenGL ripper?

All you'd need to do is create an opengl32.dll wrapper and put your own hooks in to override draw calls and pull data out of the bound buffers. (and accumulate your own data for immediate mode drawing, and store VBO handles locally, and possibly some other stuff) This would get you T-pose data minus bones/weights for any game that does skinning in a vertex shader, assuming it's feeding a T-pose in and isn't doing skinning in joint-local space. Getting texture data is just as easy, all you'd need to do is keep track of uploaded textures in your wrapper and you can dump them at any time. If you had any idea what you were doing, getting bones and weights wouldn't be that difficult either (for games that skin on the GPU) but would require a small amount of custom handling on a per-title basis.

If you wanted to do this, I'm sure there are plenty of opengl wrappers already that you could hijack for the purpose, although auto-generating a wrapper from a DLL is also fairly trivial. (Noesis will spit out wrapper code for DLL's with unmangled export names for you as well, if you try exporting any Windows PE file) All that said, I have absolutely no interest in something like this. Good luck though!
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-12T22:46:56+00:00
- Post Title: how about making an OpenGL ripper?

I don't think python supports hooking so you'll have to man up to the platform sdk. Hooking is not hard with regular api functions. I was thinking of doing it to get the rage textures.
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-13T00:42:49+00:00
- Post Title: how about making an OpenGL ripper?

> Reply from howfie
>
> I don't think python supports hooking so you'll have to man up to the platform sdk. Hooking is not hard with regular api functions. I was thinking of doing it to get the rage textures.
Oh, Rage is on my todo list as well, whenever I get around to installing the PC version. From what Carmack has said, it sounds like it just uses a simple wavelet-based image compression. Shouldn't be hard to figure it out from the disassembly.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-13T00:46:35+00:00
- Post Title: how about making an OpenGL ripper?

That sounds like it will take a lot of time lol.
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-13T01:01:10+00:00
- Post Title: how about making an OpenGL ripper?

> Reply from howfie
>
> That sounds like it will take a lot of time lol.
If it were a console game, maybe, but when you have IDA with online debugging and data breakpoints, no. Typically it takes me a few hours to isolate the code I care about and break it out into my own module. From there it's just a matter of translating the code back up to C, and given that this algorithm has to be fast enough to regularly decode large volumes of texture pages on the fly, I doubt it's going to be more than 40 pages or so of x86. That means, collectively, 1-2 days of real effort. Which in my case is probably around 3-4 real days, around playing SWTOR (god help me) and doing things which could very loosely define me as a valuable member of society. I might move it above FF12 in the queue, since it's actually likely to be less of a pain in the ass.
## Post #9
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-13T13:52:12+00:00
- Post Title: how about making an OpenGL ripper?

I don't think I'll be able to do it without learning more OpenGL and learning C then.

BTW, the word "wrapper" in python is usually used for a code which makes a non-python library callable by python.

I think what you mean is to rewrite the OpenGL library where the required functions are replaced with your own "wrapper" functions, which dump geometry before passing them to the actual function. Sounds a lot of work.
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-13T20:52:11+00:00
- Post Title: how about making an OpenGL ripper?

The entire point of a DLL wrapper is that you don't have to rewrite the original DLL.
## Post #11
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2012-01-14T07:39:16+00:00
- Post Title: how about making an OpenGL ripper?

Well how would that work?
Would you need to rename the original dll, create a dll with the original name and tell it to use the renamed dll, so it will get needed data before passing it to the original (renamed)?
