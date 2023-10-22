## Post #1
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T20:59:44+00:00
- Post Title: Need a beta tester :)

I have created a small tool that extracts the .ogg files from .aud files (piece of cake, I know, but stil l fun  ). I created a setup with Visual Studio .NET 2005 for my project wherin I registerd my application with the .aud filetype and created a shellcommand for it. So far so good.

Double clicking a .aud file triggers the tool, and if a valid file is found, it extracts the file without a problem, saving it to the current dir.

The problem comes when I right-click multiple selected .aud files and select my command to extract it. For some reason, it opens HEX Workshow instead of my application.

I am just wondering if this is an issue that only occurs on my machine or that if other people have problems with it aswel.

Anyway, I have attatched the setup, please get back to me with the results.


Sincerely,


Nick Kusters
[NKCSS aud2ogg v1.0.0.0 beta Setup.zip](https://xentaxbackup.github.io/file/1360_NKCSS aud2ogg v1.0.0.0 beta Setup.zip)
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-10-17T19:52:11+00:00
- Post Title: Need a beta tester :)

Hmm... that sounds more like a problem with the file association than anything. Have you double-checked it?
## Post #3
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-17T19:59:15+00:00
- Post Title: Need a beta tester :)

> Reply from Dinoguy1000
>
> Hmm... that sounds more like a problem with the file association than anything. Have you double-checked it?

Yup, can't find anything wrong with it realy, and found no reason why the hex editor would get the association.

Here's a partial reg dump of the 2 progs concerned here:

```

[HKEY_CLASSES_ROOT\*\shellex\ContextMenuHandlers\HexWorkshopContextMenu]
@="{7bc80fe0-4b41-11cf-8fba-444553540000}"

[HKEY_CLASSES_ROOT\CLSID\{7bc80fe0-4b41-11cf-8fba-444553540000}]
@="Hex Workshop Shell Extension"

[HKEY_CLASSES_ROOT\CLSID\{7bc80fe0-4b41-11cf-8fba-444553540000}\InProcServer32]
@="C:\\Program Files\\BreakPoint Software\\Hex Workshop 3.1\\hwext.dll"
"ThreadingModel"="Apartment"


[HKEY_CLASSES_ROOT\.aud]
@=".aud Game Sound File"

[HKEY_CLASSES_ROOT\.aud\.aud Game Sound File]

[HKEY_CLASSES_ROOT\.aud\.aud Game Sound File\ShellNew]

[HKEY_CLASSES_ROOT\.aud\shell]

[HKEY_CLASSES_ROOT\.aud\shell\open]
@="&Extract Ogg sound file with NKCSS Aud2Ogg"

[HKEY_CLASSES_ROOT\.aud\shell\open\command]
@=""C:\\Program Files\\Nick Kusters Custom Software Solutions\\NKCSS Aud2Ogg\\NKCSS Aud2Ogg.exe" "%1""

[HKEY_CLASSES_ROOT\.aud Game Sound File]
@=".aud Game Sound File"

[HKEY_CLASSES_ROOT\.aud Game Sound File\shell]
@="open"

[HKEY_CLASSES_ROOT\.aud Game Sound File\shell\open]
@="&Extract Ogg sound file with NKCSS Aud2Ogg"

[HKEY_CLASSES_ROOT\.aud Game Sound File\shell\open\command]
@=""C:\\Program Files\\Nick Kusters Custom Software Solutions\\NKCSS Aud2Ogg\\NKCSS Aud2Ogg.exe" "%1""
"command"=hex(7):55,00,5a,00,5e,00,49,00,21,00,31,00,43,00,65,00,6e,00,38,00,\
  49,00,4a,00,2e,00,2d,00,4a,00,6a,00,62,00,77,00,76,00,5b,00,3e,00,65,00,41,\
  00,6c,00,5b,00,72,00,63,00,67,00,71,00,25,00,36,00,4e,00,5f,00,53,00,48,00,\
  62,00,31,00,3f,00,48,00,57,00,3f,00,20,00,22,00,25,00,31,00,22,00,00,00,00,\
  00

```
## Post #4
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-17T20:01:35+00:00
- Post Title: Need a beta tester :)

Before I forget: If i remove the hex= part, It still has the same behaviour.
