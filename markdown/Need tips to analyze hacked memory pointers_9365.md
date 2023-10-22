## Post #1
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-07-28T18:02:56+00:00
- Post Title: Need tips to analyze hacked memory pointers

Hello,

I am trying to create an anti-cheat detection system for several wide-spread cheating tools/DLLs.
Most of those cheating tools work by injecting the game process and changing several values.
I started of with one of them and by using IDA I could track the memory pointers by looking at the WriteMemoryProcess area in the debugger.
The problem I'm having is with my second attempt with another cheating DLL where I can't seem to be able to find any useful references to track down the static memory pointers that are changed by it. The anti-cheat technique is very basic, I use memcmp() to detect the cheat injection, for example:

```
if (memcmp(cleanMem, (void*)0x4AC590, 2))
{
// Cheat detected, take action.
}

```


The code above, even if it might not be the best approach, works fine. The memory pointer 0x4AC590 is just an example for the one I was able to pinpoint on my first attempt. The problem I'm having is pinpointing the exact game addresses that are targeted by the injected DLL. I'm having a real hard time doing it and most tutorials I have read so far were either too broad or had too much overwhelming info that I couldn't follow every aspect of it. I would appreciate if someone could give me a few tips on how to precisely track them down.

Thank you.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-01T07:48:41+00:00
- Post Title: Need tips to analyze hacked memory pointers

oh well, I wrote a reply but the timedout login deleted it.

in short that thing it's caused by relocations (like aslr) and heap memory (allocations) so the solution is tracking the functions that read/create the memory and referring to the module base address for the relocations
