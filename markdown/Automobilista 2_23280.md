## Post #1
- Username: Jorge Soares
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 04, 2020 3:28 am
- Post datetime: 2021-01-08T21:39:38+00:00
- Post Title: Automobilista 2

hello somebody already consequil breaks the criprocraphy of Automobile 2, I'm wanting to create some 3d models
## Post #2
- Username: Javiliyors
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 08, 2019 5:39 am
- Post datetime: 2021-01-12T19:36:58+00:00
- Post Title: Automobilista 2

+1 im interesting to decrypt 3d models
## Post #3
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2023-05-12T20:55:33+00:00
- Post Title: Automobilista 2

I tried to decrypt the mails using a script PcarsTools, but it doesn't work. It doesn't seem to work. Although there are rumors that the script can decrypt them. Has anyone managed to do this?

[https://github.com/Nenkai/PCarsTools/](https://github.com/Nenkai/PCarsTools/)


D:\3d>PCarsTools_x64.exe decryptmodel -i D:\3D Temp\C3Int\00ba6050.meb
PCarsTools 1.1.2 by Nenkai#9075

Unhandled exception. System.UnauthorizedAccessException: Access to the path 'D:\3D' is denied.
   at Microsoft.Win32.SafeHandles.SafeFileHandle.CreateFile(String fullPath, FileMode mode, FileAccess access, FileShare share, FileOptions options)
   at Microsoft.Win32.SafeHandles.SafeFileHandle.Open(String fullPath, FileMode mode, FileAccess access, FileShare share, FileOptions options, Int64 preallocationSize)
   at System.IO.Strategies.OSFileStreamStrategy..ctor(String path, FileMode mode, FileAccess access, FileShare share, FileOptions options, Int64 preallocationSize)
   at PCarsTools.Model.MeshBinary.Load(String fileName) in C:\Users\nenkai\source\repos\PCarsTools\PCarsTools\Model\MeshBinary.cs:line 19
   at PCarsTools.Program.DecryptModel(DecryptModelVerbs options) in C:\Users\nenkai\source\repos\PCarsTools\PCarsTools\Program.cs:line 152
   at CommandLine.ParserResultExtensions.WithParsed[T](ParserResult`1 result, Action`1 action)
   at PCarsTools.Program.Main(String[] args) in C:\Users\nenkai\source\repos\PCarsTools\PCarsTools\Program.cs:line 26

D:\3d>
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-05-13T03:45:03+00:00
- Post Title: Automobilista 2

> Reply from MichaelBFS ↑Sat May 13, 2023 4:55 am at Sat May 13, 2023 4:55 am
>
> 
I tried to decrypt the mails using a script PcarsTools, but it doesn't work. It doesn't seem to work. Although there are rumors that the script can decrypt them. Has anyone managed to do this?
...
D:\3d>PCarsTools_x64.exe decryptmodel -i D:\3D Temp\C3Int\00ba6050.meb
PCarsTools 1.1.2 by Nenkai#9075

Unhandled exception. System.UnauthorizedAccessException: Access to the path 'D:\3D' is denied.Is "3D Temp" a folder that you've created? If so rename it to "3D_temp" or similar, without blanks.
(Just a wild guess, btw.)
## Post #5
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2023-05-13T12:27:44+00:00
- Post Title: Automobilista 2

@MichaelBFS just wrap the input path in quotes.
In your case, the full commandline arguments will be:

```
PCarsTools_x64.exe decryptmodel -i "D:\3D Temp\C3Int\00ba6050.meb"
```
## Post #6
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2023-05-14T18:06:03+00:00
- Post Title: Automobilista 2

Thanks a lot! It seems to work!
You have to extract and import one object at a time, it takes time, but it works.
[ChevyC3.jpg](https://xentaxbackup.github.io/file/23808_ChevyC3.jpg)
