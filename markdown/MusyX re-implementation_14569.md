## Post #1
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2016-06-26T05:56:46+00:00
- Post Title: MusyX re-implementation

Over the past month and a half my friend has been hard at work re-implementing MusyX from the ground up, and while it's not feature complete (missing environmental effects, emitters, and listeners) the basic functionality is complete, this includes the sequencer, and sound macros.

Details on the individual portions of MusyX can be found at:
[http://www.metroid2002.com/retromodding ... le_Format)](http://www.metroid2002.com/retromodding/wiki/AGSC_%28File_Format%29)
and
[http://www.metroid2002.com/retromodding ... le_Format)](http://www.metroid2002.com/retromodding/wiki/CSNG_%28File_Format%29)

Our library and test applications can be found on the projects github page here: [https://github.com/AxioDL/amuse](https://github.com/AxioDL/amuse)

Amuse is aiming to be a faithful recreation in terms final output, the techniques it uses have been modernized, but the overall premise has remained untouched. However since the project is still very young we need testers with MusyX powered games to really give Amuse a run for it's money, so any help on this front is greatly appreciated.
## Post #2
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-06-26T19:50:26+00:00
- Post Title: MusyX re-implementation

I never knew this existed. Thanks!
I have one question, however: does it also support exporting soundbanks to SF2/DLS format?

Besides, I'm having incorrect output on those Rogue Squadron ROMs I have(the exported MIDI length are up to 10+ hours and they don't play at all).

Also I'm having this issue with the amuseplay tool in which when I drag-and-drop a N64 Rogue Squadron ROM, this happens:

```
12:  - 0x0
11: raise - 0x7FFC431C8980
10: abort - 0x7FFC431C98B0
9: abort - 0x7FFC431C98B0
8: abort - 0x7FFC431C98B0
7: abort - 0x7FFC431C98B0
6: abort - 0x7FFC431C98B0
5: abort - 0x7FFC431C98B0
4: abort - 0x7FFC431C98B0
3: abort - 0x7FFC431C98B0
2: abort - 0x7FFC431C98B0
1: BaseThreadInitThunk - 0x7FFC450380E0
0: RtlUserThreadStart - 0x7FFC479FC580
```


Am I doing something wrong?
## Post #3
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2016-06-26T20:49:16+00:00
- Post Title: MusyX re-implementation

Are you on Windows 7? There is a known issue with windows 7 and this is exactly why we need testing.

EDIT
Wait, D3D12, you can't be on 7, this is odd, yeah I have no idea what's going on, I forwarded your complaint to the primary developer, but do you mind creating an issue in the tracker?

EDIT2: 
Currently SF2 is unsupported with no current plans to implement it, though porting SF2 to sound macros should be relatively trivial, the reverse, however, is not feasible.
I don't think we have support for DLS quite yet, though it's definitely planned (the original implementation used DLS for the examples).
## Post #4
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-06-26T21:00:16+00:00
- Post Title: MusyX re-implementation

> Reply from antidote
>
> Wait, D3D12, you can't be on 7, this is odd, yeah I have no idea what's going on, I forwarded your complaint to the primary developer, but do you mind creating an issue in the tracker?Sure thing, just let me create my account first.
EDIT: Done.
## Post #5
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2016-06-26T21:16:02+00:00
- Post Title: MusyX re-implementation

I posted a potential solution, and Jack has provided some more details, as well as a couple inquiries.
