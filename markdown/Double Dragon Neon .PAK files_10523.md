## Post #1
- Username: jimmhoo
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 20, 2011 1:03 am
- Post datetime: 2013-06-16T21:37:15+00:00
- Post Title: Double Dragon Neon .PAK files

I managed to extract from xbox 360 version of the game some .pak files, but I cant find a tool to extract them, someone know about a tool to do that?
## Post #2
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-06-17T22:30:17+00:00
- Post Title: Double Dragon Neon .PAK files

I have only ps3 version, try maybe pak files same

```
get filetable long
get files long
get dummy longlong
math filetable + 0x40
for i = 0 < files
get offset long
math offset + filetable
get size long
getct name string 0x3a
getct filename string 0x00
savepos off
math b = 0x4
math a = off
math a % 0x4
if a == 0
get dummy longlong
else
math b - a
math off + b
goto off
get dummy longlong
endif
log filename offset size
next i  
```
## Post #3
- Username: jimmhoo
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 20, 2011 1:03 am
- Post datetime: 2013-06-19T18:32:02+00:00
- Post Title: Double Dragon Neon .PAK files

> Reply from Thief1987
>
> I have only ps3 version, try maybe pak files same
Code: Select allendian big
get filetable long
get files long
get dummy longlong
math filetable + 0x40
for i = 0 < files
get offset long
math offset + filetable
get size long
getct name string 0x3a
getct filename string 0x00
savepos off
math b = 0x4
math a = off
math a % 0x4
if a == 0
get dummy longlong
else
math b - a
math off + b
goto off
get dummy longlong
endif
log filename offset size
next i

its bash/c/python script?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-19T19:24:36+00:00
- Post Title: Double Dragon Neon .PAK files

quickbms script
## Post #5
- Username: jimmhoo
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 20, 2011 1:03 am
- Post datetime: 2013-06-19T23:01:28+00:00
- Post Title: Double Dragon Neon .PAK files

thanks thief1987 and chrrox I will try it
## Post #6
- Username: jimmhoo
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 20, 2011 1:03 am
- Post datetime: 2013-06-25T19:38:38+00:00
- Post Title: Double Dragon Neon .PAK files

thanks for the script, it worked very well with pak files for the 360 version too

I managed to extract the gr2 files and converted to 3dstudiomax scripts using grnreader98 v1.4.0.3.debug

then exported to obj using 3dstudio max

now I have the linda lash model in blender and looks good

now I will search for textures or something


edit: textures are in the same gr2 files, I can see them using granny viewer, will search for a tool to extract them(granny viewer dont give me an option)
