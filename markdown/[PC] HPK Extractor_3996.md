## Post #1
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-12-29T00:18:11+00:00
- Post Title: [PC] HPK Extractor

GAME = Imperium Romanum
CATEGORY = Game Specific
FORMATS = .hpk

NAME = HPK Extractor
AUTHOR = Crypton
PLATFORM = PC
SYSTEM = Windows
LICENSE = GPL v3
OPENSOURCE = Yes
LANGUAGE = English
DESCRIPTION =
Tool for extracting HPK Archives, created for Imperium Romanum, but might work with newer games based on its engine as well.

VERSION = 0.1b
RELEASED = 28.12.2009
FILESIZE = 150 KB
DOWNLOAD = [http://www.sendspace.com/file/n0vsej](http://www.sendspace.com/file/n0vsej)

------------------------
PS: I've made this tool back in 2008, it was released at Xentax under my older account, Demander, so if you want to check out original topic, here is link:
[viewtopic.php?f=10&t=2955](http://forum.xentax.com/viewtopic.php?f=10&t=2955)
------------------------

Edit, 10.5.2011: Recompiled version uploaded, infected version deleted. Sorry guys for the problem. 
[HPK_Extractor2011.zip](https://xentaxbackup.github.io/file/4217_HPK_Extractor2011.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-29T00:28:50+00:00
- Post Title: [PC] HPK Extractor

Nice !  You can also attach it to your post. It will preserve it, as these file sharing services tend to run out of time at some point. Max attachment size is 2 Mb.
## Post #3
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-12-30T01:14:40+00:00
- Post Title: [PC] HPK Extractor

Isn't this a format by "Haemimont Games" compatible to "Glory of the Roman Empire"?
I think I started dealing with this almost one year ago, if I'm not wrong.
## Post #4
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-12-30T02:43:28+00:00
- Post Title: [PC] HPK Extractor

> Reply from asmxtx
>
> Isn't this a format by "Haemimont Games" compatible to "Glory of the Roman Empire"?
I think I started dealing with this almost one year ago, if I'm not wrong.

I don't know... but I know that when I was making this tool, there was no unpacker for Imperium Romanum's .hpk format, and it was March 2008 (look at original topic), and I heard that this tool works also for Emperor expansion, so its possible that it works also for "Glory of the Roman Empire" and other games based on it engine, if there is any.
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-05-04T19:51:39+00:00
- Post Title: [PC] HPK Extractor

WARNING!
The HPK extractor contains a Delphi virus, named Win32.Induc.A
## Post #6
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2011-05-08T19:00:03+00:00
- Post Title: [PC] HPK Extractor

> Reply from bacter
>
> WARNING!
The HPK extractor contains a Delphi virus, named Win32.Induc.A

It's a fake warning, which is caused by bug in Delphi compiler (I compiled it with Delphi 7), but the source codes are included, so you can recompile it by yourself, if you're paranoid about that.
## Post #7
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-09T11:15:41+00:00
- Post Title: [PC] HPK Extractor

Sorry mate, but it is NOT fake warning. This is NOT bug in Delphi. Check your SysConst.pas if it is infected or not. There is attached code in the end of file then it is compiled to SysConst.dcu and to every final Delphi program.
## Post #8
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2011-05-09T23:56:12+00:00
- Post Title: [PC] HPK Extractor

> Reply from XRaptor
>
> Sorry mate, but it is NOT fake warning. This is NOT bug in Delphi. Check your SysConst.pas if it is infected or not. There is attached code in the end of file then it is compiled to SysConst.dcu and to every final Delphi program.

I just scanned everything with AVG and I don't have my system infected, everything is okay. But I've compiled that tool almost two years ago and I've reinstalled windows many times since that, so I can't confirm that my system wasn't infected.

But you're right, I just checked the HPKExtractor.exe and there is some malicious code injected. I found description of that virus: [http://www.microsoft.com/security/porta ... %2FInduc.A](http://www.microsoft.com/security/portal/Threat/Encyclopedia/Entry.aspx?Name=Virus%3AWin32%2FInduc.A)

However the only thing that it does is that when executed, it search for file SysConst.dcu and inject same code, so it won't harm your windows, only Delphi installation, so if you don't have Delphi installed, you're safe. Also, the *virus* only attacks older versions of Delphi, i.e. Borland only, before CodeGear.

Anyway, I just recompiled HPKExtractor, using Delphi 2010, which is clean, but size of executable increased twice. 

Sorry for the problem, I'll watch out next time.
Have a nice day.

P.S. Taky jsem Čech
