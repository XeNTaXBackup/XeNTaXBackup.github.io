## Post #1
- Username: techie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 14, 2005 6:31 pm
- Post datetime: 2005-12-14T10:40:51+00:00
- Post Title: WinMerge PE .dll .exe comparison plugin

Frankly speaking I'm too busy to carry on with development, but some of you folks may found this proposal to winmerge useful. Perhaps smb. even has a ready piece of code to easily wrap into a plugin. Would be nice to see. 

It is about the way how to compare two .dll or .exe PE files with different compile time and perhaps on different machines. I wonder if such tools are already available?

[http://sourceforge.net/tracker/index.ph ... tid=363216](http://sourceforge.net/tracker/index.php?func=detail&aid=1380300&group_id=13216&atid=363216)
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-12-15T00:01:43+00:00
- Post Title: WinMerge PE .dll .exe comparison plugin

why is something like this even needed?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-16T22:02:29+00:00
- Post Title: WinMerge PE .dll .exe comparison plugin

Comparing 2 executables is not so simple, but I think that the first step is being sure that the executables are in plain-text (aka not encrypted/compressed) so you must launch them and dump the process memory (although this is probably not enough with some rare strongly encrypted files).
Then you must compare all the various PE sections.
But as the previous post said: what's the real usage ot this thing?
## Post #4
- Username: techie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 14, 2005 6:31 pm
- Post datetime: 2007-01-09T09:52:08+00:00
- Post Title: WinMerge PE .dll .exe comparison plugin

Well, because there is no tool to compare if two different executables compiled on various machines are actually the same. I thought that file format experts may have this tool at hand.

It can be used to detect changes when using various compiler options, like stripped debugging info or symbols, relocation tables etc. Release test could check that no development executables with debug info are packed into release. It could be later used as basis for building database for executable analyzer with hints how to boost compiler options for optimal performance.
## Post #5
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-10T21:25:31+00:00
- Post Title: WinMerge PE .dll .exe comparison plugin

I don't claim to be anywhere near an expert on it (or even have a passable knowledge of it, for that matter), but if you want to be sure that a developer's version of an executable doesn't make it into the final product, the easiest method would probably be to have any dev exe's identify themselves as such at runtime. As for boosting compiler optimization, it would seem to me that most compilers worth using have been around for so long, and have undergone so much review and improvement, that they are at least as optimized as you could achieve by handwriting the assembly code yourself.
