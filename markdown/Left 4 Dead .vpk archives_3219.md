## Post #1
- Username: Mystfit
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 07, 2008 6:13 am
- Post datetime: 2008-11-13T04:21:17+00:00
- Post Title: Left 4 Dead .vpk archives

With the release of the Left 4 Dead demo, a bunch of us were looking forward to playing around with the new models and resources that came with the game. 
Surprisingly though, Valve decided to include their files not in the standard .gcf file format used with other Source engine games, but in a series of .vpk files.

These .vpk's don't seem to be the same as the only other .vpk files used in a Source game, in Vampire: The Masquerade Bloodlines.

Here's a link to some of the vpk files that came with the demo: [https://dl.getdropbox.com/u/127934/left4dead.zip](https://dl.getdropbox.com/u/127934/left4dead.zip)

Anyone have any ideas how to get into these archives?
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-11-14T10:07:47+00:00
- Post Title: Left 4 Dead .vpk archives

[http://blog.gib.me/2008/11/14/left4dead ... w-with-ui/](http://blog.gib.me/2008/11/14/left4dead-vpk-extraction-tools-now-with-ui/)
## Post #3
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-11-26T23:05:31+00:00
- Post Title: Left 4 Dead .vpk archives

This program doesn't work for me in XP. It simply does nothing.
After I patched the .EXE from GUI- to console-mode, it writes this error message in the console window:

```
embly 'System.Windows.Forms, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b7
7a5c561934e089' or one of its dependencies.
File name: 'System.Windows.Forms, Version=2.0.0.0, Culture=neutral, PublicKeyTok
en=b77a5c561934e089'
   at Gibbed.Valve.ExtractPackage.Program.Main()

WRN: Assembly binding logging is turned OFF.
To enable assembly bind failure logging, set the registry value [HKLM\Software\M
icrosoft\Fusion!EnableLog] (DWORD) to 1.
Note: There is some performance penalty associated with assembly bind failure lo
gging.
To turn this feature off, remove the registry value [HKLM\Software\Microsoft\Fus
ion!EnableLog].
```

What should I do? Have I to install some nasty stuff?
## Post #4
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-11-26T23:48:05+00:00
- Post Title: Left 4 Dead .vpk archives

it looks like you don't have .net 2.0 framework installed, try installing it if you dont have it
## Post #5
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-11-27T22:25:35+00:00
- Post Title: Left 4 Dead .vpk archives

Yes. thanks - this was the problem. Now it works.
