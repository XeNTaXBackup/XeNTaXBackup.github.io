## Post #1
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-08-05T01:41:07+00:00
- Post Title: Is there a Hex Editor that do batch delete byte?

Hi, so I have a bunch of DDS textures I extracted from a CryEngine game but all the texture files have some random bytes before the extension .DDS...
I will be able to view those file(s) as normal dds texture as long as I delete those bytes using a hex editor and gave it the .DDS extension afterward. 

So my question is, is it possible to automate this process? Some kind of command-line tool to patch these files?
Or is there any Hex Editor that will allow you to write a script (or any sort of the like) that tell the Hex Editor to look through all the files of (say Texture Folder) and delete everything (bytes) that come before DDS then save it/rename it/override it (or whatever work as long as it delete those byte).

It look like these screenshots for all of the texture files.




If anyone have any idea of how to tackle this kind of problem then please do share them and help a brother out, huh?

Sample 

 406588021295361925817424315325322206345.rar
(206.16 KiB) Downloaded 18 times
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-08-05T02:06:11+00:00
- Post Title: Is there a Hex Editor that do batch delete byte?

here is a script for Quickbms that will do what you want.  

```

get NAME basename
get SIZE asize
string NAME + ".dds"
findloc OFFSET binary "\x44\x44\x53\x20"
math SIZE - OFFSET
log NAME OFFSET SIZE

```
## Post #3
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-08-05T04:33:46+00:00
- Post Title: Is there a Hex Editor that do batch delete byte?

> Reply from Acewell ↑Wed Aug 05, 2020 10:06 am at Wed Aug 05, 2020 10:06 am
>
> 
here is a script for Quickbms that will do what you want.  
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

get NAME basename
get SIZE asize
string NAME + ".dds"
findloc OFFSET binary "\x44\x44\x53\x20"
math SIZE - OFFSET
log NAME OFFSET SIZE

Oh WOW! You're my hero! If only I had ask a little sooner lol... I spent a few hours deleting those annoying bytes manually for the meshes.  
Thanks a bunch... it works perfectly... Really saved my ass...
