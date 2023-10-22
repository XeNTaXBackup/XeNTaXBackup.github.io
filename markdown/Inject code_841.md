## Post #1
- Username: Tredo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 02, 2004 3:22 am
- Post datetime: 2004-08-05T13:44:48+00:00
- Post Title: Inject code

Does anyone know a tutorial or something about how to inject code to D3D dll instead of OpenGl processes?
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-05T13:46:52+00:00
- Post Title: Inject code

Depends, what language are you talking about. And to do code injection you have to have a disassembler also.  Do you know how code injection works?
## Post #3
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-05T13:51:03+00:00
- Post Title: Inject code

Sorry scratch that, you don't HAVE to have a disassembler.  There are 2 methods of hijacking DLLs.  Through the processes import table, and through the loaded dll in the processes.
## Post #4
- Username: Tredo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 02, 2004 3:22 am
- Post datetime: 2004-08-05T17:59:34+00:00
- Post Title: Inject code

Yes! I have tried several deassamblers, like Resource analyser. LOL, Im a nOOb at thinks like this. Im working on it  You have to start somewhere... A deassambler must work to....Ass i Sad, Im working on It but I want tips and trix you know.....the code we are talking about Is for the game Painkiller. For an example, If you want to hook at OpenGL you use something like this.....

FARPROC WINAPI myGetProcAddress(HMODULE hModule,LPCSTR lpProcName) 
{ 
    if(HIWORD(lpProcName)) 
    { 
            // Your GlHooking Code Goes Here 
    } 
    return GetProcAddress(hModule,lpProcName); 
} 

Now what this does is now that you have hooked GetProcAddress everytime the target application calls it, it will use your function instead, this enables you to return whatever function address you like, weather it be your custom fucntion or the real one. So you ask, what goes in // your glhooking code here well it shuld look something like this: 

typedef void(APIENTRY *func_glBegin)(GLvoid); 

func_glBegin org_glBegin; 

void APIENTRY my_glBegin(GLvoid) 
{ 
    // Your Stuff Here 

    org_glBegin(); 
} 

and so on.....

BUT! My question GetProcAddress for OpenGL, what Is for D3D?
Has someone extract the painkiller.exe and so on and looked at It? 
Im learning to code to so have undertanding to me at my nOOb questions.....

I know there are a tool out there with the name Evilhack, I cant find It  Its help you to inject code....
## Post #5
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-06T15:07:18+00:00
- Post Title: Inject code

> Reply from Tredo
>
> Yes! I have tried several deassamblers, like Resource analyser. LOL, Im a nOOb at thinks like this. Im working on it  You have to start somewhere... A deassambler must work to....Ass i Sad, Im working on It but I want tips and trix you know.....the code we are talking about Is for the game Painkiller.

Why are you trying to hook to the game?  Are you having problems that a simple debugger can't handle? 

> Reply from Tredo
>
> For an example, If you want to hook at OpenGL you use something like this.....

FARPROC WINAPI myGetProcAddress(HMODULE hModule,LPCSTR lpProcName) 
{ 
    if(HIWORD(lpProcName)) 
    { 
            // Your GlHooking Code Goes Here 
    } 
    return GetProcAddress(hModule,lpProcName); 
} 

Now what this does is now that you have hooked GetProcAddress everytime the target application calls it, it will use your function instead, this enables you to return whatever function address you like, weather it be your custom fucntion or the real one.

Two things here

1) Since when is GetProcAddress apart of OpenGL, last time i check it was part of the Win32 API.

2) No you haven't hooked GetProcAddress, what you've done is created a POSSIBLE hooking function.

> Reply from Tredo
>
> So you ask, what goes in // your glhooking code here well it shuld look something like this: 

typedef void(APIENTRY *func_glBegin)(GLvoid); 

func_glBegin org_glBegin; 

void APIENTRY my_glBegin(GLvoid) 
{ 
    // Your Stuff Here 

    org_glBegin(); 
} 

and so on.....

Has someone extract the painkiller.exe and so on and looked at It? 
Im learning to code to so have undertanding to me at my nOOb questions.....

I know there are a tool out there with the name Evilhack, I cant find It  Its help you to inject code....

Note: This is usually something for advanced coders,  not noobs.  Beginners and Intermediates usually have a hard time in grasping these kinds of concepts.

Yes or if you use Delphi there is madCodeHook.

There are a couple of theories on code hooking.

1) Rename the original DLL, then replace that dll with your own, that loads the original and makes the original calls.  This is pretty easy to do, and even people with only VB skills can accomplish this.

Upside: Easy to use, easy to program for.  No need for assembly skills, and should work for windows 32 and windows 64.
Downside: If you have multiple programs using this dll, you will have to extra work to make sure your getting the program you want to debug.

2) Open the process, create new memory in the process, write code into the process, flag memory as EXECUTABLE.

Upside: Allows you to work with a single processes function call instead of everyones.
Downside: May or may not require assembly knowledge, and you need seperate code to handle win32 or win64.

Now #2 can get done in 2 ways
  A) Modify the processes Import Table for the DLL function call, and replace it with address of the memory you just allocated.  OR you use your memory to do a LoadLibrary on a DLL you wrote to do the hooking (cleanest in my opinion) and then change the import table to point at your dll function.
Upside:  Fairly straight forward, no knowledge of assembly needed, and very easy to remove the hook just by changing the address back to the original.
Downside: If the module is statically bound, it might not use the import table, but requires the module to be loaded at a specific point in memory and all calls the function directly. (Note: Although this is a problem, its normally NOT done anymore, its a reminant of Win16 days.)

  B) Modify the "function you want to hook"'s assembly code, this is generally the best method, but can get a little messy.  First step is to disassemble instructions in the function,  at least 5 bytes.  This is so you can overwrite the function with a JUMP into your function, then your function has to save all the register values, do your stuff, return the register values, execute the assembly code you just copied and then jump back to the original code in the dll.
Upside: This should work for all function calls, even statically bound ones
Downside: A little bit harder to remove the hook.


I personally use the 2B method.


> Reply from Tredo
>
> BUT! My question GetProcAddress for OpenGL, what Is for D3D?

Its really not that much different from other functions, except you can only get the function Direct3DCreate8/Direct3DCreate9 with the GetProcAddress, everything else you have to get using the methods.  It depends on what functions you wanna hook to though.
## Post #6
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-06T15:11:34+00:00
- Post Title: Inject code

Dammit! it logged me out.... but that was my reply up there.
## Post #7
- Username: Tredo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 02, 2004 3:22 am
- Post datetime: 2004-08-07T09:25:08+00:00
- Post Title: Inject code

Hey! Yes thats thrue. If you read my thread againg you will understand that I havent hooked IT yet. Its ha hookfunction. Forcelibrary, you can read more about It  Thanks for your teori, lol I have already read them.
## Post #8
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T10:40:56+00:00
- Post Title: Inject code

> Reply from Tredo
>
> Hey! Yes thats thrue. If you read my thread againg you will understand that I havent hooked IT yet. Its ha hookfunction. Forcelibrary, you can read more about It  Thanks for your teori, lol I have already read them.

If you read the theories, you should know how to hook into D3D then.
## Post #9
- Username: bjuuuu
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-07T15:09:25+00:00
- Post Title: Inject code

Not exactly. I also want to know different methods.
## Post #10
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T16:10:59+00:00
- Post Title: Inject code

In delphi, i can

```
  X: IDirect3D9;
  Y: Pointer;
begin
  X := Direct3DCreate9(D3D_SDK_VERSION);
  Y := Addr(X.GetAdapterCount);
  // Now Y = Address of GetAdapterCount
end;

```


Unfortunately, this will only work for normal interfaces, and not interfaces derived from IDispatch, which uses dispatch id's to call function.

This should work for most functions in directx but not all.

The only way to really DO this, is in the code space of the other process, as D3D.dll could be loaded into a different address.
## Post #11
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-07T18:31:03+00:00
- Post Title: Inject code

> Reply from Anonymous
>
> Why are you trying to hook to the game?  Are you having problems that a simple debugger can't handle?
A good reason to do this is to make a game compatible with Windows 9X.  More games are starting to use functions which only exist in Windows NT-based DLL's which would otherwise work in Windows 9X, like GlobalMemoryStatusEx.  Hooking would fix this in a better and more universal way than trying to path the game's executables especially since many games use copy-protection.
## Post #12
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T18:48:46+00:00
- Post Title: Inject code

[quote=Riley Pizt]A good reason to do this is to make a game compatible with Windows 9X. More games are starting to use functions which only exist in Windows NT-based DLL's which would otherwise work in Windows 9X, like GlobalMemoryStatusEx. Hooking would fix this in a better and more universal way than trying to path the game's executables especially since many games use copy-protection.[/quote]

Then your not really "hooking" because, hooking means your attaching yourself to an already existing function.
## Post #13
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-07T21:27:06+00:00
- Post Title: Inject code

> Reply from Rahly
>
> Then your not really "hooking" because, hooking means your attaching yourself to an already existing function.
Well you are intercepting calls to the original DLL and passing everying else to it that you don't rewrite.  Functions you modify from the original DLL are existing so that is hooking.  Functions which you add that don't exist in the original of course wouldn't be.
## Post #14
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-08T04:56:28+00:00
- Post Title: Inject code

Sounds like a lot more work than its worth.  There are so many functions you'd have to hook to, include the GetVersion and GetVersionEx function, as well as every version of every system dll it uses.  Hooking also tends to slow down code quite a bit.  It would be easier, and faster to replace the system dlls that it uses.  Then again, there are alright projects out there that does this for you.
## Post #15
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-09T00:44:38+00:00
- Post Title: Inject code

> Reply from Rahly
>
> Sounds like a lot more work than its worth.  There are so many functions you'd have to hook to
I disagree.  For example, many programs which would otherwise run on Windows 9X will not simply because the developer chose to use "GlobalMemoryStatusEx" instead of "GlobalMemoryStatus".  Hooking Kernel32.dll on Windows 9X systems to handle the slight differences between these two functions would seem trivial.

> It would be easier, and faster to replace the system dlls that it uses.
True, but how do you write a DLL to pass all function calls that you don't want to modify (or possibly don't even know exist since some functions in Windows DLL's like Kernel32.dll are undocumented) to the real DLL when you don't have the source code to the original DLL? 

> Then again, there are alright projects out there that does this for you.
Such as?
## Post #16
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T05:31:30+00:00
- Post Title: 

> Reply from Riley Pizt
>
> I disagree.  For example, many programs which would otherwise run on Windows 9X will not simply because the developer chose to use "GlobalMemoryStatusEx" instead of "GlobalMemoryStatus".  Hooking Kernel32.dll on Windows 9X systems to handle the slight differences between these two functions would seem trivial.

SEEM trivial, and ARE trivial, are 2 different things though.   Not only do you have to write the functions that are missing, you have to "fool" the calling programs into thinking its an NT version.  Which developers use GetVersion/GetVersionEx and some even use the DLL version numbers, which can be messy, cuz you don't know what dll its getting a version from.  It may even make calls to NTDLL.DLL, in which case, you have to recreate that DLL, which isn't on non NT kernels.  Like I said, It would be work than its worth.

> Reply from Riley Pizt
>
> True, but how do you write a DLL to pass all function calls that you don't want to modify (or possibly don't even know exist since some functions in Windows DLL's like Kernel32.dll are undocumented) to the real DLL when you don't have the source code to the original DLL?

(example is in Delphi, but you can do it in C++ too)
1) Use a program, such as "depends.exe".  This will list ALL exported functions the DLL provides.

2) Get the address for the function (for sample purposes, i'll use CreateFileA)

var CFAPointer: Pointer;

CFAPointer := GetProcAddress(OriginalKernel32Handle, "CreateFileA");

3) Make a function (remember you don't know the calling convention or whats passed it or EVEN what it returns)

procedure CreateFileA();
asm
  JMP CFAPointer
end;

4) Export Your New function.

This is exact how an import table USUALLY is

Program calls into the Import Table, the import table JUMPs to the real function.

> Reply from Riley Pizt
>
> Then again, there are alright projects out there that does this for you.
Such as?

Wine is one of them.  Which is a cross platform emulation of the system dlls.
## Post #17
- Username: Tredo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 02, 2004 3:22 am
- Post datetime: 2004-08-09T10:34:48+00:00
- Post Title: 

Use the toll DLL to LIB. Forget NT =)
## Post #18
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-09T17:37:17+00:00
- Post Title: 

> Reply from Rahly
>
> Which developers use GetVersion/GetVersionEx and some even use the DLL version numbers, which can be messy, cuz you don't know what dll its getting a version from.  It may even make calls to NTDLL.DLL, in which case, you have to recreate that DLL, which isn't on non NT kernels.  Like I said, It would be work than its worth.
It would depend on how many missing functions the program uses.  Right now Kernel32.dll functions seem to be the only thing standing in the way of the couple of programs I have in mind.

> Wine is one of them.  Which is a cross platform emulation of the system dlls.
Thanks, I'll take a look at it.
## Post #19
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-10T20:47:27+00:00
- Post Title: 

> Reply from Riley Pizt
>
> It would depend on how many missing functions the program uses.  Right now Kernel32.dll functions seem to be the only thing standing in the way of the couple of programs I have in mind.

Unfortunately, there is no 100% way to find every function a program uses, except to execute the program for 100% of its worth.  I've seen some CRAZY programming too, anything from LoadLibrary'ing everything instead of static importing to Loading the library themselves to calling the RING 0 functions themselves.
## Post #20
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-11T04:38:11+00:00
- Post Title: 

> Reply from Anonymous
>
> Unfortunately, there is no 100% way to find every function a program uses, except to execute the program for 100% of its worth.
I agree, but that comment was based upon following the error messages displayed.
