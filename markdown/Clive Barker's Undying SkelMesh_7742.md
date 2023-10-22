## Post #1
- Username: azraelaxel
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 24, 2011 10:01 am
- Post datetime: 2011-11-24T16:42:46+00:00
- Post Title: Clive Barker's Undying SkelMesh

After a time without posting, i come back with some interesting notes about 3D Model Format of Clive Barker's Undying...
I have started this investigations because i want to make a papercraft model of each character of the game...

So well... we gotta start...

The Models are compressed under a unknown method inside the Aeons.U. There's no way to extract them with the UCC.exe batchexport inside the game system (for those that don't know about the unreal engine, the UCC.exe it's a program that's combine the script compiler with some other tools, it's a kind of primordial editor).

I find a way to extract all archives in raw formats with this program [http://www.watto.org/extract/info.html](http://www.watto.org/extract/info.html) (i hope that don't close my post for show another tool to extract game resource).

The models apparently was added with the SkelMesh format extension (something that a tried to export with the UCC without success).

After that i decided to use a hexadecimal editor checking strings in the exe of the game.... and i found something interesting... apparently the exe call two libraries one called NGF.dll and another called DWI.dll (both inside the system folder) and both make some subprocess of the models and show it's in the game (like a superimposed photo).

and here it's the questions... anybody know how to intercept that information (like it does the 3d ripper dx with the DirectX)?, or know about a tool that you can import/export that kind of format or edit?...

Thanks in advance...
and sorry for my poor english
