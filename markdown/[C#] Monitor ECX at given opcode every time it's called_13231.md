## Post #1
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-08-21T14:15:25+00:00
- Post Title: [C#] Monitor ECX at given opcode every time it's called

Hello!

How do I monitor ECX register at given ASM opcode? Say, I have a:
FF8.exe+69DD8 - push ecx
Using any ready debugger I can do a breakpoint at given opcode and watch registers. But I need to make an automation software to:
Catch every time 'push ecx' is called and add it to table with the time it was called to know how often is it called. [It's something like cut-scene with different sounds being played, and we need to know what's the time the sounds are played, one after another]

Why I can't use ready softwares for this:
Because when I breakpoint 'push ecx', note ecx register and then step over I'll lose whole timing. I need to do a table with detailed times in which this opcode is accesed. 

Thank you for any tips!
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-09-25T03:13:00+00:00
- Post Title: [C#] Monitor ECX at given opcode every time it's called

> Reply from MaKiPL
>
> Hello!

How do I monitor ECX register at given ASM opcode? Say, I have a:
FF8.exe+69DD8 - push ecx
Using any ready debugger I can do a breakpoint at given opcode and watch registers. But I need to make an automation software to:
Catch every time 'push ecx' is called and add it to table with the time it was called to know how often is it called. [It's something like cut-scene with different sounds being played, and we need to know what's the time the sounds are played, one after another]

Why I can't use ready softwares for this:
Because when I breakpoint 'push ecx', note ecx register and then step over I'll lose whole timing. I need to do a table with detailed times in which this opcode is accesed. 

Thank you for any tips!
Probably best to hook the function and grab the value from the stack before the function returns
