## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-06-19T21:32:49+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

Just spent the last hour or so writing C programs like this

```
    int i = 5;
    i++;
    i *= 6
    return i;
}

```


```
   for (int i = 0; i < 10; i++) {
      printf("hello world\n");
   }
   return 0;
}

```


And dropping the compiled executables into IDA to look at the instructions that are generated.

Wrote a bunch of simple programs encompassing arithmetics, comparisons, conditionals, jumps, loops, function calls, and found that they were pretty straightforward to understand since there are plenty of references on x86 instructions.

Is that enough to be able to hook a debugger onto a real windows program and be able to figure out what's going on?
Or are there other common problems that I'll run into?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-20T08:36:56+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

depends on the programs - many game exes have copy protections and/or anti debugging features.
Ollydbg has an anti-anti-debugger plugin (for IDA I don't know).

If you try to debug your legal earned copy protected game exe you'll find this being impossible
when starting the exe by the debugger. 
Often this can be solved by running the exe and then hooking the debugger as you know.

2nd great hurdle is just the size of the exes. Todays game exes having a size of 15MB and greater.
Though you can use different breakpoints (such as on memory access) it's hard to find
a specific algorithm among thousands of instructions.

In ollydbg you can Analyse code and write out a textual file (>100MB!) which I found easier to analyse
for example by searching for "hash" or something similar. This often helped tracing the hashing code.

```
..
0068D4F9  |. C705 343A6001 >MOV DWORD PTR DS:[1603A34],rage.00FF77D8 ;  ASCII "HASHTABLE"
```
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-06-20T20:15:43+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

I recommend taking a tutorial on x86 assembly before digging too deep, just to make sure you get the basics right. The tutorial I looked at was Ketman's x86 assembly tutorial (you'll need to find an archived version, and DosBox). Also, OllyDbg 2.x has built in instruction help, if you're into that, but few plugins.

The single most useful feature in OllyDbg for me is "search all strings". Usually whatever you're looking for will need a string at some point. Also, place a breakpoint on the instruction just before "retn" in kernel32.IsDebuggerPresent, if you're debugging something with anti-debugging. Some noob protection software only checks its return value.
## Post #4
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-06-22T02:09:06+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

I was just about to ask how to find file loading  in an assembler. Every time I found references to the file i am looking for it was always in the data section so i cant debug it/break point
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-06-22T02:54:45+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

> Reply from JohnHudeski
>
> I was just about to ask how to find file loading  in an assembler. Every time I found references to the file i am looking for it was always in the data section so i cant debug it/break point
On Windows, you'll typically want to place a breakpoint on kernel32.CreateFileA and kernel32.CreateFileW. Those are the only two user-mode APIs available to open files (AFAIK). The "A" version is for ASCII paths, and "W" for Unicode paths. The version used depends on whether the program is a Unicode program or not. Note if you place breakpoints on both, you will notice that the "A" version will call the "W" version. Usually you'll only need to break on one. Also to look for are references to the strings "r", "rb", "w", "wb", "+w", etc. Those are calls to the standard C function fopen(), so if you can find its usage, it'll save you a lot of backtracing from CreateFile(). You can also assume that subsequent functions in fopen()'s calling function will contain a number of calls to other C I/O functions.

Edit: You said assembler. I'm thinking more OllyDbg. The analysis system in OllyDbg is quite useful, and will make it much easier to find code you're looking for.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-06-24T17:41:08+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

I've decided to start with reversing an image format by looking at how it's read.

I'm looking at a DOS game in IDA, and in the list of strings there's a reference to one of the images.
I went and found where it might be loaded, and instead of fopen calls, I see calls to __open directly, usually like this

```
push    8000h           ; int
push    eax             ; char *
call    __open

```


I'm assuming this __open function is just some really low-level way to open a file, taking the filename and the file mode.
I'm assuming the 8000h is just the flag for read mode.

Is there anywhere I can find info about these?
## Post #7
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-06-25T02:23:00+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

Google gave me [this](http://gd.tuwien.ac.at/languages/c/programming-bbrown/c_075.htm). Note that names prefixed with many underscores are usually the same as functions with less (or no) prefixed underscores.
## Post #8
- Username: mgrandi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 20, 2014 1:55 pm
- Post datetime: 2014-06-25T02:56:02+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

doesn't windows , when you compile things with C make it so all the function calls have underscores infront of them? I remember this because mac/linux doesn't do that so i was having problems calling stuff from assembly
## Post #9
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-06-25T13:38:50+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

Not necessarily. C++ programs compiled with Visual C++ tend to have their symbols mangled so the linker can exactly match names. The mangled names contain the class and namespace, as well as argument types and return type. GCC uses a different mangling scheme than Visual C++. Standard C programs usually just export their function names as is.
## Post #10
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-06-26T10:01:10+00:00
- Post Title: Some idea how x86 works, can I reverse algorithms now?

> Reply from mgrandi
>
> doesn't windows , when you compile things with C make it so all the function calls have underscores infront of them? I remember this because mac/linux doesn't do that so i was having problems calling stuff from assembly
Depends on the calling convention. cdecl, stdcall and fastcall are the most prominent ones, and each of them has different rules about name mangling (underscores, @-suffixes, etc). Generally you would ignore all underscores in front and everything after the @ after the name
