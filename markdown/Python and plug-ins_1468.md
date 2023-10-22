## Post #1
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-29T10:51:32+00:00
- Post Title: Python and plug-ins

I've read this whole forum, and there appears to be a discussion about creation new plug-in specs for Delphi (?), while the current MultiEx is written in VB. And that .NET is only an option for cross-platform, but as a language it is not suitable because you need a compiler.

A simple solution to this would be to use Python scripts. Python has its own 'compiler' inside the runtime DLL so you can just add scripts at runtime. Furthermore, it can be very easily embedded in Delphi using Python for Delphi (though the embedding has a steep learning curve).

Another advantage of Python is one can make extensions for it in C, C++ and Delphi, and is undistinguishable from a module written in Python.

For those of you know thinking, yeah right: I have a small-scale generic interface to reading game files inside my [TibEd](http://www.tibed.net) game editor. In the current development version I have separated out the game archive handling code into a Python module and a Delphi Python extension. And now it is used inside my main Delphi program (so that's Delphi->Python->Delphi) and I'm no longer limited to Delphi code only 

The formats my extension supports are:
- MIX for C&C: Tiberian Sun/Dawn, Red Alert 1/2. This needs an extra C DLL as well, and a database with filenames, since the format uses file IDs
- BIG for Generals/Zero Hour/BFME
- MIX for C&C: Renegade (different MIX format)
- (on standby at the moment): RAR archives
- (on standby at the moment): RFX/RFD files for Emperor: Battle for Dune

I do not like the interface my module currently has. And maybe the idea of using Python is useful for MultiEx, because it is cross-platform. The Delphi bits require Kylix on Linux, but having base scripts in Python would already make a difference.

Okay I'll stop typing now before everyone falls asleep
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-29T11:45:33+00:00
- Post Title: Python and plug-ins

Actually, XeNTaX already tried this approach in 2003. 

OpenMex (Open MultiEx) was an app completely written in Python, by Captain  Corny, with already an interface much like MultiEx Commander. 

A quote from October 18 2003: 

> = "OpenMex supports a large number of games because we've been able toautomate conversion from old MultiEx Commander scripts to new OpenMex scripts. While this means that OpenMex 'supports' 138 different games, we've only been able to test OpenMex on about 10% of all the supported games (it's pretty hard to find archives of all supported games). This means that there are probably some non-working scripts. If you happen to find one, please tell us about it in the XeNTaX forums."

However, Captain quit the project in january 2004 : [viewtopic.php?t=635&highlight=openmex](http://forum.xentax.com/viewtopic.php?t=635&highlight=openmex)

Yet, you should be able to get the latest source code from 

[http://sourceforge.net/projects/openmex](http://sourceforge.net/projects/openmex)

Perhaps you could discuss this with Captain.
## Post #3
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-08-29T11:54:04+00:00
- Post Title: Python and plug-ins

I think it's a great idea to extend MultiEx to work with Python script. As a matter of fact, OpenMex was supposed to operate in the same way as you describe, through python scripts that are loaded at runtime. Unfortunately, I had to abandon the project because it was just too much work.

If there's an easy way to implement this, I'd be very interested. We'll have to  decide on an API though. Maybe we can use the same one as Rahly's pluginmanager.
## Post #4
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-29T13:45:56+00:00
- Post Title: Python and plug-ins

I've had a look at OpenMEX... and all that code basically already implements a generic reader interface. A Delphi wrapper around it is possible. There'd need to be some changes and I think dropping the Python GUI is a good idea.
Adhering to Rahly's pluginmanager specs is doable, with some reservations:
- IStream. Don't know it, never used it. This cannot be passed around easily to Python, so it will be some work. Is this perhaps the interface version of a Delphi TStream? If so, then it is doable.
- Specific documentation. There'll need to be some good descriptions of the functions to prevent stupid bugs.
- Is the API finalized already?
- What's with those cache-something functions? Should they really be part of a specification?
- License issues. OpenMEX is GPL, and would prevent me from using it in my program. LGPL would be much nicer, because then I could use it and give back changes. At least, that is how I understand LGPL. A Python or ZLIB license would be even cooler, but the copyright holder has everything to say because only he can relicense it.

Okay, I'm getting ahead of myself a little bit... my time is limited as well so we'll just have to see how this works out.
## Post #5
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-29T22:09:42+00:00
- Post Title: Python and plug-ins

Been looking... IStream can be fixed probably. I need to really get an example or some docs of a Rahly plugin. Or is it a whole plug-in manager?
Overall the OpenMEX Delphi wrapper DLL needs to expose multiple plugins to keep the overhead low. The API appears to be done because I just saw it in MultiEx 4.2.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-29T22:49:10+00:00
- Post Title: Python and plug-ins

That's correct. The first version of the manager was released. Mind, it's still only in testing phase. Rahly has some plugins that need a bit of work, but hopefully will be completed soon. So we can see if it works. The test archives work (more or less).
## Post #7
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-30T05:00:01+00:00
- Post Title: Python and plug-ins

> Reply from Neko
>
> IStream can be fixed probably.

Fixed? what needs to be fixed? No IStream has NOTHING to do with delphi.  [IStream](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/stg/stg/istream.asp) is a microsoft api interface.

> Reply from Neko
>
> OpenMEX Delphi wrapper DLL

the plugins have nothing to do with delphi, other than that was the language i original wrote it in.  The plugins can easily be a C or C++, or anything that can output a DLL with raw function names, unfortunately VB cannot do this, which is why there is support for COM plugins.  C# can make a raw dll as well or any other .NET compiler that supports a DLL compiling, as long as its marshalled correctly.

We could support all kinds of scripts, perl, php, ruby, parrot, etc.  Python isn't really that special.  All you need to do is embed the interpreter into a dll that exposes the archive functions.  I'm working on a wiki page for the new plugin manager for documentation, as well as some plugins.
## Post #8
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-30T09:08:21+00:00
- Post Title: Python and plug-ins

> All you need to do is embed the interpreter into a dll that exposes the archive functions.
Very true. That is what I wanted to do. And I want to embed it in a Delphi DLL, because then I can use Python for Delphi which is really easy to use.
And then that DLL can wrap the OpenMEX engine and expose your interface.

I used the wrong word on IStream, I meant addressed instead of fixed. The problem that I do not know it can be addressed
## Post #9
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-08-30T15:05:31+00:00
- Post Title: Python and plug-ins

Ahh ok, all you'd have to do is make a manager for the manager.  not too hard, but the manager reads all plugins at startup time, the application can tell the manager to refresh the plugin list.  For example, Mexcom calls me to refresh the plugin list. i go and read the directory of all plugins, and i ask every plugin for its format list (aka all the file formats it supports), if someone were to add a script during runtime, mexcom, would have to refresh, in order to reload you and get new script names.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-30T15:09:25+00:00
- Post Title: Python and plug-ins

Well that last bit is not a very big problem, if we write an interface in MexCom like "Add archive plugin..." that will copy the runtime script to the correct plugin directory and refresh MexCom / Pluginmanager subsequently.
## Post #11
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-08-30T15:53:17+00:00
- Post Title: Python and plug-ins

> Reply from Neko
>
> I've had a look at OpenMEX... and all that code basically already implements a generic reader interface. A Delphi wrapper around it is possible. There'd need to be some changes and I think dropping the Python GUI is a good idea.
OpenMEX is 90% GUI code. The script API is pretty basic and one of the reasons I stopped development is that I wasn't happy with the API, but didn't want to invest the time required to rework all the scripts to another API. It's probably better to not use OpenMex code at all and start from scratch.
## Post #12
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-31T17:29:16+00:00
- Post Title: Python and plug-ins

Okay I was thinking too complicated before. I thought the plugin had to be a manager to support multiple formats, but as it turns out a plug-in can easily support multiple formats. Defining a whole new API on my own... just what I was trying to avoid   . Ah well... saves me learning the existing OpenMEX.
Any suggestions for naming this plugin? I'm terrible at names.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-31T17:38:56+00:00
- Post Title: Python and plug-ins

Yes, and another thing why it wouldn't be advisable to use the OpenMex method is because it was created to implement MultiEx scripts (OpenMex was to replace MultiEx Commander and start off with support for all formats). 

Seeing that MultiEx Commander IS the main project, MultiEx scripts are handled by multiex.dll at run-time. No need to recreate what is already there.
## Post #14
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-31T17:59:29+00:00
- Post Title: Python and plug-ins

Aha. That's fine with me. Converting the scripts sounded ambitious anyway. Someone other than me with time to spare could do it later, if they really want it
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-31T18:21:25+00:00
- Post Title: Python and plug-ins

> Reply from Neko
>
> Aha. That's fine with me. Converting the scripts sounded ambitious anyway. Someone other than me with time to spare could do it later, if they really want it

Well,the idea to be able to convert MultiEx scripts is still valid, when I rethink it, as you'd want cross-platform compatibility right? Then perhaps mulitex.dll is not the most cross-platformish solution.
## Post #16
- Username: Neko
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 29, 2005 6:35 pm
- Post datetime: 2005-08-31T22:03:57+00:00
- Post Title: 

Converting the scripts is an option. But perhaps emulating the MultiEx interpreter can work as well... that's just harder. I had best not get into this discussion right now. Looking that far into the future is not good
