## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-03-29T13:50:38+00:00
- Post Title: neat API for detouring binary functions

Just found that wonderful M$ library for intercepting binary functions on Windoze.
I'm planning to use it for hooking DirectX calls to receive screenshots for further processing and wanted to share that pearl: [http://research.microsoft.com/en-us/projects/detours/](http://research.microsoft.com/en-us/projects/detours/)
## Post #2
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2010-04-01T11:25:11+00:00
- Post Title: neat API for detouring binary functions

detours can not hook d3d com interface, you have to hook it by yourself, here is a sample of code.

[http://www.mikoweb.eu/index.php?node=28](http://www.mikoweb.eu/index.php?node=28)
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-01T15:19:45+00:00
- Post Title: neat API for detouring binary functions

It is able. That's basically the way [http://taksi.sourceforge.net/](http://taksi.sourceforge.net/) works.

Of course a proxy dll is another possibility. Thanks for the link.
## Post #4
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2010-04-02T04:36:14+00:00
- Post Title: neat API for detouring binary functions

> Reply from Rheini
>
> It is able. That's basically the way http://taksi.sourceforge.net/ works.

Of course a proxy dll is another possibility. Thanks for the link.

I just have checked the src of taksi. I think, which way it use to hook directx is Complex and hard code, but it could work. I still like proxy dll to get full control of d3d.
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2010-05-28T02:56:24+00:00
- Post Title: neat API for detouring binary functions

Yeah, detours has been around for several years.  It also doesn't work on assembly programs either.  I found out you can write a program to make the kernel calls yourself, thereby bypassing the API.  This makes programs that puts hooks into api calls from never getting time.

If you make an API call, all a hooker has to do is find the api call.  Easy as PIE in windows, because the functions are name based, and by doing a LoadLibrary and GetProcAddress, it gives you the location of the start of the function.  You can easily provide a jump into other code from here.  Now, comes the trick, all API boil down to really doing a SYSCALL(in NT KERNELS) or INT (in 95/98 kernels).  If you make that SYSCALL from your program and call the kernel directly, you essentially bypass the API AND any hookers that jacked into it.  It makes it harder to find the SYSCALLs in your code than it is to find the location of a named function.

Thereby, the only reasonable approach to debugging the code is to use a kernel debugger like SoftIce to trap the kernel calls.

And yes, once I did write a program completely without using ANY dlls including kernel.dll and ntdll.dll, just to see if i could do it
