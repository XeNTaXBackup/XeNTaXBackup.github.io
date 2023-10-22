## Post #1
- Username: toomanynights
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 22, 2023 4:58 pm
- Post datetime: 2023-08-22T09:08:22+00:00
- Post Title: Crossroads Inn .pak decompile (Esenthel engine)

Hi guys!
Just stumbled upon this game. It seems so amazing, and yet bug-ridden. What's worse, the developers officially ended support of this one, therefore leaving it to exist in its current suboptimal state; obviously, fans are less than happy.
I thought maybe some modding could help fix things a little bit, but surprisingly, there is no information on how to mod this game anywhere.
What I managed to gather so far:
- It's build on Esenthel engine
- All game assets are stored in one huge Project.pak archive
- It can't be opened with any obvious means, including the official Esenthel editor
Has anyone done any research on this game yet? Would appreciate any findings or ideas. Thanks!
## Post #2
- Username: toomanynights
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 22, 2023 4:58 pm
- Post datetime: 2023-08-22T09:15:37+00:00
- Post Title: Crossroads Inn .pak decompile (Esenthel engine)

Turns out there's Esenthel extractor on QuickBMS site, but it returns error  

> Error: incomplete input file 0: C:\Program Files (x86)\Steam\steamapps\common\Crossroads Inn\Bin\Project.pak
>
>        Can't read 12884901888 bytes from offset 00000000515791a1.
>
>        Anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted.
>
>        Please check the following coverage information to know if it's ok.
>
> 
>
>   coverage file 0     9%   1364693409 14249595297 . offset 00000000515791a1
>
> 
>
> Last script line before the error or that produced the error:
>
>   8   log MEMORY_FILE 0 SIZE
>
> 
>
> - OFFSET       0x0000000000000000
>
> - SIZE         0x00000003515791a1
>
>   coverage file 0     9%   1364693409 14249595297 . offset 00000000515791a1
>
>   coverage file -3    0%   0          197        . offset 0000000000000000
## Post #3
- Username: toomanynights
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 22, 2023 4:58 pm
- Post datetime: 2023-08-22T09:52:01+00:00
- Post Title: Crossroads Inn .pak decompile (Esenthel engine)

Tried to use comtype_scan2.bms to maybe detect compression algorithm; unfortunately it produced zero dump files.   A lot of "incomplete input file" errors and nothing to work with.
## Post #4
- Username: DomingoRatliff
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 24, 2023 8:42 pm
- Post datetime: 2023-08-24T14:00:16+00:00
- Post Title: Crossroads Inn .pak decompile (Esenthel engine)

Any update?
## Post #5
- Username: toomanynights
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 22, 2023 4:58 pm
- Post datetime: 2023-08-24T14:14:57+00:00
- Post Title: Crossroads Inn .pak decompile (Esenthel engine)

I wish bud   Yesterday I gave it my best (this phrase for a CInn fan might be painful), at this point I really have no more cards to play and hope for someone else's input. I would mod the heck out of this game, but that would require some direction from more experienced modders. As it is, I have a 13GB .pak file and no idea what to do with it.
