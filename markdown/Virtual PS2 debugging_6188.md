## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-03-07T20:15:54+00:00
- Post Title: Virtual PS2 debugging

Does anyone know of a PS2 emulator with a working disassembler+debugger (with execution breakpoints) or hooks to IDA Pro?

The only one I've been able to find is PCSX2. I grabbed the latest SVN code and made a dev build to enable the debugger, then switched to interpreted mode. Unfortunately their way of allowing breakpoints is to lock the entire process under a loop in the debugger dialog, so my first attempt at running with a breakpoint caused it to unsync with the GE thread and crash. So I went back and disabled GE multithreading, restarted, loaded the game up, switched to interpreted mode, set my breakpoint, and tried again. Crash in interrupt test code. At this point I just said screw it, cause this crap is too broken to bother trying.

The whole motivation here is that I've tracked down the location of some decompression code for this game in IDA, but knowing what's actively in memory at the time of code execution would make understanding/translating this code trivial instead of a complete nightmare and a special exercise in intellectual masochism.

I'll be kinda surprised if it turns out there's no workable emulated PS2 debugging solution presently in existence after all, and am hoping I just don't know where to look. I'd also be open to using PCSX2, though, if anyone knows a way to make their debugger actually function as intended. Looking at the code it seems to me that it is just horribly and fundamentally broken. (breakpoints via an isolated loop in the dialog proc that doesn't even perform message pumps is possibly the worst approach they could have taken)

Although, I suppose if I absolutely have to, I can set to interpreted mode, then debug the actual emulator with a conditional breakpoint on the EE's program counter, then step through the CPU emulation as a way of stepping through instructions one at a time on the EE. While looking at the memory in the emulator's actual process space. Just thinking about that makes me cry a little inside, though.
## Post #2
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-03-07T20:39:54+00:00
- Post Title: Virtual PS2 debugging

Never thought to ask this here, heh.  I would be interested in this as well, as i had planned on making my own conversion for either IDA Pro, or another more open source debugger.  Just that it would be a really big project at the moment.

Unfortunately the last i checked the pcsx2 team cannibalized the debugger quite a few versions back, and i don't think it was deemed important enough to upkeep.

I have a problem with a number of the emulators that are out when it comes to debugger support.  Would definitely like to use dolphin more effectively for gcn/wii debugging, but all of them have issues when it comes to being required to be in interpreter mode, which can be slow in some cases if you are trying to wait until code it hit a good deal further in the game's execution.

Debugging is fun...A lot of my progress in areas would be aided greatly with better debugger support, either in emulation, or even better with actual dev hardware, heh.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-03-08T08:35:48+00:00
- Post Title: Virtual PS2 debugging

Yeah, I remember you mentioning the desire to make some interfaces to let emulators hook into IDA Pro. I have no idea what that would entail, and have never looked at the IDA Pro SDK, but it seems like an even better idea now.  I think I'll find the SDK and have a look. It would be great if it's as simple as just telling IDA about pc/register status and giving it some pointers to memory in the emulator's process space, then making some set hooks for things like "break", "resume", etc.

I was thinking, too, that you really shouldn't need to set interpreted mode yourself for this. When you set a breakpoint in original EE binary, you can just determine where the start of the nearest recompiled code page is on the spot, and at worst, make a hook to switch to interpreted mode when you hit that page. You can also go to interpreted automatically on any kind of debug break.

I'll be getting back on gtalk pretty soon here, maybe we can collaborate on this thing. Once I see take a look at the IDA SDK and see how much work it'll actually be.
## Post #4
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-03-08T09:30:44+00:00
- Post Title: Virtual PS2 debugging

Yeah, since all the emulators should know the start and end addresses of dynamically recompiled blocks of code, should hopefully be somewhat trivial to sort of set up an interface to set break points at the pseudo instruction locations and catch the related exceptions that are thrown.  i have been meaning to look into the x86 emulator plugin for ida to get ideas.

Time will only tell what it might take to realize this given how easy or difficult it might be to actually modify an emulator to support this.  But getting it working would be a great accomplishment, heh.

Guess i'l re-look into a few things as well...
## Post #5
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-04-09T13:59:32+00:00
- Post Title: Virtual PS2 debugging

try with this: [http://www.romhacking.net/utils/617/](http://www.romhacking.net/utils/617/)

altough, it's a very old build so your game could not even start. Anyway, I suggest you to take a ram dump (aka savestate) and find the decompressed data so that the "intellectual masochism" would be less painful
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-09T20:59:03+00:00
- Post Title: Virtual PS2 debugging

> Reply from Vash
>
> try with this: http://www.romhacking.net/utils/617/

altough, it's a very old build so your game could not even start. Anyway, I suggest you to take a ram dump (aka savestate) and find the decompressed data so that the "intellectual masochism" would be less painful
Cool, I'll have a look at it.

I have of course been using ram dumps, as noted when I posted in the bouncer thread some time ago.  Unfortunately, that is not too helpful in a lot of cases, especially when you just want to see how raw data is handled by the original program. An actual full description of my current process, since I just wrote it up on my blog in reply to someone asking me what I do anyway, is:

> I've been using PCSX2, IDA, and my own R5900 debugger/disassembler. Which has not been too pleasant, but it's a usable setup. Since PCSX2's debugger is totally broken and unusable, I've actually been debugging PCSX2 itself, and doing stuff like inserting custom code segments into the VIF unpack routine in order to catch model data that I want to take a look at, and otherwise just setting data breakpoints in system/VU memory to find code that deals with the particular data I'm interested in.
>
> 
>
> Unfortunately, I haven't found any good alternatives. The most important thing for me is to be able to debug games in their normal operating conditions, and to that end I'm not aware of any PS2 emulators that actually do a better job than PCSX2. I would consider fixing their debugger myself, if not for the fact that it is a really terrible hack that just sits on top of the app and does not play nicely with anything else. (e.g. handling breakpoints by trying to step the CPU in its own private loop, endlessly, in interpreted mode, choking every other system in the emulator) So I think if I were going to take up that job, my time would be much better-spent integrating support with IDA Pro.
>
> 
>
> It's also a big pain in the ass to try to step through binary in interpreted mode and match it to my pre-disassembled code. Occasionally I've just left dynarec on, and stepped through dynarec'd x86 for EE/VU code instead.

Edit: Oh, and if there is a VU0/1 microcode disassembler, that would be useful too. I haven't come across one. And to clarify that last statement, I mean that stepping actual instruction executions in MSVC running PCSX2 while looking at the CPU context/registers in the MSVC debugger watch window and reading code over in IDA is the big pain in the ass part. I am a spoiled manbaby and need the ability to just mouseover a register to view its contents and get a convenient readout of where it may be pointing in memory.
## Post #7
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2013-03-28T17:18:08+00:00
- Post Title: Virtual PS2 debugging

> Reply from Vash
>
> try with this: http://www.romhacking.net/utils/617/

altough, it's a very old build so your game could not even start. Anyway, I suggest you to take a ram dump (aka savestate) and find the decompressed data so that the "intellectual masochism" would be less painful

Nice debugger, but crash when click "go". what's wrong of it?
## Post #8
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2013-03-28T17:44:21+00:00
- Post Title: Virtual PS2 debugging

> Reply from kawayide
>
> Vash wrote:try with this: http://www.romhacking.net/utils/617/

altough, it's a very old build so your game could not even start. Anyway, I suggest you to take a ram dump (aka savestate) and find the decompressed data so that the "intellectual masochism" would be less painful

Nice debugger, but crash when click "go". what's wrong of it?

forgot to turn off recompiler,ok.

I want see call stack.
## Post #9
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-06-02T16:21:29+00:00
- Post Title: Virtual PS2 debugging

Please don't hate me for reviving this thread but any progress on this.
I just started to learn MIPS (over coming a fear of assembly) and i was hoping it would make deciphering file formats a bit easier

At the moment i just dump the pcsx2 process and open it with ps2dis, probably stupid but i dont know where to start and i wanted to get the complete sequence of instructions called on level load.
But that file is ridiculously large.

It is very manual labour ( I wish i knew this stuff when i was 16).
## Post #10
- Username: GHzGangster
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 15, 2014 1:00 pm
- Post datetime: 2014-08-22T20:35:08+00:00
- Post Title: Virtual PS2 debugging

I know this is probably not quite what you were looking for, but if you wish to debug a retail PS2, you can use Kermit DBG by SilverBull of ASSEMblergames.
It's the only debugging solution I could find for the PS2, other than buying a TOOL. It's quite useful, but it does have it's issues, from what I could remember when I used it last.
## Post #11
- Username: Ryusui
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 02, 2014 1:43 pm
- Post datetime: 2014-09-23T08:00:42+00:00
- Post Title: Virtual PS2 debugging

The latest dev builds of PCSX2 have a new debugger. I've fiddled with it a bit, but I don't know enough about PS2 hardware to determine how good it is. Mainly I was thinking of having a crack at the .WAD format of Sly 3, but I'll admit I'm stymied as to how to catch the system in the act of reading from the main SLY3.WAD file. I've had experience cracking compression on other platforms, including DS (which also uses a filesystem), but I can't find any docs anywhere to help me get started.
