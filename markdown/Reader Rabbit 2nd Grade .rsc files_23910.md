## Post #1
- Username: Polestar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 19, 2021 11:42 pm
- Post datetime: 2021-05-19T16:06:05+00:00
- Post Title: Reader Rabbit: 2nd Grade .rsc files

I know this is a strange game to extract assets from, but I'd like some help with retrieving the graphics (sprites, backgrounds, etc).
It appears that all the game data is stored in .rsc files. I have been able to extract all the audio using Ravioli Explorer and Dragon UnPACKer, but no graphics whatsoever.
I've linked a few examples of files in the game that I haven't been able to extract anything from. They may or may not contain graphics, but they definitely contain something. Any help would be appreciated, thanks!

[https://drive.google.com/file/d/1i51Bp3 ... sp=sharing](https://drive.google.com/file/d/1i51Bp3iPKF9xIdfsaZV4m2CRPE8p6RWs/view?usp=sharing)

___________________________________________________________________________________________________________________________
Edit: Moderator ikskoks has informed me that the files appear to be old DOS executable files, despite having the .rsc file extension. Knowing this, the files can be read and analyzed by programs that can read executable files (if you change the .rsc file extension to .exe). Since I'm not knowledgeable about this stuff, I can't make heads or tails of any of the information in the files. If anyone wants to take a look them and take a crack at it, I would be very grateful.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-19T19:20:10+00:00
- Post Title: Reader Rabbit: 2nd Grade .rsc files

Well, those are not archives, they seems to be Pascal DOS executables with MZP signature.
They are matching New Executable (NE) Windows file format
and they can be opened with tools like ExeScope, HT Editor, IDA and ResEdit if you change file extension to EXE.

See below how it looks from my side:
[https://i.imgur.com/2uFsn0D.png](https://i.imgur.com/2uFsn0D.png)
[https://i.imgur.com/LYuXHTq.png](https://i.imgur.com/LYuXHTq.png)
[https://i.imgur.com/UFjbEGv.png](https://i.imgur.com/UFjbEGv.png)

You could probably extract some raw resources and analyse code in IDA, but extracting working files is something that requires further investigation for sure.

Here you have links to some additional resources regarding this topic:
[https://en.wikipedia.org/wiki/New_Executable](https://en.wikipedia.org/wiki/New_Executable)
[https://bytepointer.com/resources/win16 ... win3.0.htm](https://bytepointer.com/resources/win16_ne_exe_format_win3.0.htm)
[https://stackoverflow.com/questions/553 ... e/38880152](https://stackoverflow.com/questions/5531874/help-with-finding-hex-header-information-of-file/38880152)
[https://en.wikipedia.org/wiki/Object_Windows_Library](https://en.wikipedia.org/wiki/Object_Windows_Library)
[https://sourceforge.net/projects/hte/](https://sourceforge.net/projects/hte/)

I have also created an article on the wiki for the future reference
[http://wiki.xentax.com/index.php/Windows_Executable_EXE](http://wiki.xentax.com/index.php/Windows_Executable_EXE)
## Post #3
- Username: Polestar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 19, 2021 11:42 pm
- Post datetime: 2021-05-19T20:37:24+00:00
- Post Title: Reader Rabbit: 2nd Grade .rsc files

> Reply from ikskoks ↑Thu May 20, 2021 3:20 am at Thu May 20, 2021 3:20 am
>
> 
Well, those are not archives, they seems to be Pascal DOS executables with MZP signature.
They are matching New Executable (NE) Windows file format
and they can be opened with tools like ExeScope, HT Editor, IDA and ResEdit if you change file extension to EXE.

See below how it looks from my side:
https://i.imgur.com/2uFsn0D.png
https://i.imgur.com/LYuXHTq.png
https://i.imgur.com/UFjbEGv.png

You could probably extract some raw resources and analyse code in IDA, but extracting working files is something that requires further investigation for sure.

Here you have links to some additional resources regarding this topic:
https://en.wikipedia.org/wiki/New_Executable
https://bytepointer.com/resources/win16 ... win3.0.htm
https://stackoverflow.com/questions/553 ... e/38880152
https://en.wikipedia.org/wiki/Object_Windows_Library
https://sourceforge.net/projects/hte/

I have also created an article on the wiki for the future reference
http://wiki.xentax.com/index.php/Windows_Executable_EXE

Hey, thanks so much for replying. This is definitely new information to me, and at this point, any information helps. I'll look into it and see what I can do
