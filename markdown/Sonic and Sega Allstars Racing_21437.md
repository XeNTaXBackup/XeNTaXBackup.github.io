## Post #1
- Username: NVtom
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 09, 2019 3:00 am
- Post datetime: 2019-11-27T01:22:11+00:00
- Post Title: Sonic and Sega Allstars Racing

Hi 
Im looking for some textures but i dont know how to get to them ...
In this post here is a file with the extension .zig .
[viewtopic.php?f=16&t=13462&p=129718&hilit=Zig#p129718](https://forum.xentax.com/viewtopic.php?f=16&t=13462&p=129718&hilit=Zig#p129718)
I know that these .zig files include 2 models (textures) and i wanna know how i can get to them. Would be nice if you could kinda teach me how to do so.      (in the post there was a answer where shakotay2 "solved" it)

If you could help i would appreciate that a lot.
Its for a little "project" for my friends and i.

[Sry for my bad english]
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-11-27T03:33:56+00:00
- Post Title: Sonic and Sega Allstars Racing

here is a quick quickbms script to cut the dds textures from decompressed .zig file.  

```
math i = 1
findloc OFFSET string "DDS "
do
    goto OFFSET
    goto 0x14 0 seek_cur
    get SIZE long
    math SIZE + 0x80
    string NAME p "%s\%d.dds" FOLDER i
    log NAME OFFSET SIZE
    findloc NEXT_OFFSET string "DDS " 0 "" -1
    math OFFSET = NEXT_OFFSET
    math i + 1
while NEXT_OFFSET != ""

```

cuts top level mip only
maybe later i will improve it to get all mips unless someone else does first.
