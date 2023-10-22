## Post #1
- Username: DeadEx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 16, 2014 12:45 pm
- Post datetime: 2015-01-07T09:51:22+00:00
- Post Title: Phantom Kingdom Portable ANMXXX.dat files

Hi Everyone

Was wandering if there were any tools that can unpack/view/decrypt ANMXXX.dat files from Phantom Kingdom Portable (PSP). I've been told by Ekey they're some kind of binary animation file format. I've uploaded a file.
Any chance someone could look at it

[https://mega.co.nz/#!nhkiWRDA!5pUvM_nv8 ... 8Jg03hRsSc](https://mega.co.nz/#!nhkiWRDA!5pUvM_nv8Eb-iQ3JSSo8ZGRb6hAJE1TPH8Jg03hRsSc)

Thanks in advance
## Post #2
- Username: DeadEx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 16, 2014 12:45 pm
- Post datetime: 2015-01-27T11:39:46+00:00
- Post Title: Phantom Kingdom Portable ANMXXX.dat files

Anyone?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-27T14:23:36+00:00
- Post Title: Phantom Kingdom Portable ANMXXX.dat files

no bone names, no skeleton. Who would waste his time with such vague informations?

"IMY" could mark the start of animation keys (42 bones? in your uploaded dat). The offsets between two IMYs are multiples of 16 but not constant (104x16, 238x16 or 313x16 for example), hinting to some kind of optimized or compressed animation frames.

Seems there's little chance to give the data between 0x4D5F0 and 0x4DBD0 (smallest IMY block) some kind of structure.
