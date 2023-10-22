## Post #1
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-07-08T18:15:37+00:00
- Post Title: Looking for a program that can save .x files in this version

Does anyone know where I could find a 3d editor that could save .X files with the 
```
xof 0302bin 0064
```
 header?
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-08T20:46:42+00:00
- Post Title: Looking for a program that can save .x files in this version

A program that saves in binary directx...

Been awhile since I looked at microsoft's 3D stuff. Presumably they have their own program that allows you to export in their format >.>
## Post #3
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-07-08T21:13:15+00:00
- Post Title: Looking for a program that can save .x files in this version

there is many programs that allow to save in their format but I need this one in specific. Even a plugin would suffice.

what all that means above is

xof= magic number 03=major number 02= minor number bin= binary  0064= 64bit floats
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-07-08T21:22:12+00:00
- Post Title: Looking for a program that can save .x files in this version

I have several programs that can export to this format with that same header but the the last 4 numbers are always a 32 bit floating-point value with no option to change it to 64. I guess they are determined by the OS architecture from which the file was exported on.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-08T21:58:59+00:00
- Post Title: Looking for a program that can save .x files in this version

the 64 means it uses 64 bit floats why would you want that?
also any game should be able to read 3d bit floats if they have a proper .x reader.
what game are you trying to mod?
## Post #6
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-07-08T22:21:54+00:00
- Post Title: Looking for a program that can save .x files in this version

UC gundam online, it uses modified .x files in 64bit floats. I have to modify the data manually after generation but I have already gotten it to work once... kinda.

Here is a 32bit float file "sphere" modified in the client


Doesn't look so good and the terrain kinda molded in with it. I tried instead trying a 64bit file with the 0303 major and minor but they didnt show up in the client, they did crash it afterwards after removing the transformations so I know it works "it also generates an error report about the mesh name so I know it works" Plain and simple the minor needs to be 02 and that simply cannot be hand written.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-08T22:28:44+00:00
- Post Title: Looking for a program that can save .x files in this version

the direct x sdk should have a tool to convert the model to 64 bit i would look there first.
## Post #8
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-07-08T23:41:26+00:00
- Post Title: Looking for a program that can save .x files in this version

I already have the SDK, it doesn't convert in the .x format I need.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-10T02:48:44+00:00
- Post Title: Looking for a program that can save .x files in this version

lol maybe you can send a message to microsoft.
...but I think they've already dropped support for .x files?
