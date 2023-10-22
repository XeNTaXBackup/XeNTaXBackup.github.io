## Post #1
- Username: Typhox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 15, 2009 12:33 am
- Post datetime: 2013-05-09T23:58:25+00:00
- Post Title: Why do some DLL's contain C++ class information?

Opening the server.dll from Dota 2 (a Steam game by Valve) with my disassembler, I find a lot of strings (most of them not xreferenced in the code) that obviously refer to the original source code they come from (sometimes even including pathes to the source files).

There are only 2 exported functions.
Why is that? Why does that compiler keep those data?
Is it possible for me to reproduce that behaviour?
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-05-11T21:14:32+00:00
- Post Title: Why do some DLL's contain C++ class information?

The var names are from the Source engine send tables. And the rest is possibly something like asserts or some other kind of debugging aid.
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2014-02-23T07:27:33+00:00
- Post Title: Why do some DLL's contain C++ class information?

Its not unheard of for software to contain debug output statements that can contain the names of functions, files or other source references.
I know of several games (including Elder Scrolls: Oblivion) that contain such data and it can sometimes be useful to reverse engineering experts.

The Linux version of the dedicated server for Command & Conquer: Renegade contained a full symbol table with full prototypes for every function in the binary.
## Post #4
- Username: mgrandi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 20, 2014 1:55 pm
- Post datetime: 2014-05-21T07:49:37+00:00
- Post Title: Why do some DLL's contain C++ class information?

Its probably just internal logging, its not uncommon for logging frameworks to have macros that when you call LogThisError("something")
it expands to something like ReallyLogSomething(level.Error, __FILE__, _CLASS_, __LINENO__) and whatever, that the c++ compiler fills in when its actually compiled. 

Just looking at my mac os x system log you can see examples of this:

> 5/20/14 11:33:56.909 PM acvpnagent[69]: Function: updatePotentialPublicAddresses File: ../../vpn/AgentUtilities/HostConfigMgr.cpp Line: 1914 Invoked Function: CHostConfigMgr::determinePublicAddrCandidateFromDefRoute Return Code: -24117215 (0xFE900021) Description: ROUTETABLE_ERROR_GETBESTROUTE_FAILED
## Post #5
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-21T12:36:10+00:00
- Post Title: Why do some DLL's contain C++ class information?

lol what are you trying to do in dota?
