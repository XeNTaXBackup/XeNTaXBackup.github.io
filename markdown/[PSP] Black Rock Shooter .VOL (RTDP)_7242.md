## Post #1
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2011-08-26T12:28:44+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

Hello!
This game seems to have pretty good assets and models, so I wanted to check what kind of game files it used. I found out that the files are compressed in a similar format to the one used for Arc Rise Fantasia on Wii (which was discussed in this topic: [viewtopic.php?f=10&t=4836](http://forum.xentax.com/viewtopic.php?f=10&t=4836)). The game is by the same developer, after all, just on different platforms.
I tried to open the "BCHR_APL00.VOL" file with a hex editor, and from what I can see it should contain a few different files:

- apl0.bms
- apl0.edx
- param1.bin
- param2.bin
- chr_m_apl00.mdl (the actual model, I think, don't know in which format)
- ... a bunch of .anm files (that should be animations)
- eb205.efp
- btl_apl.phd
- btl_apl.pbd

However, looks like the one used here is a slightly different format. I tried to use the quickbms vol algorithm written to open the .vol file of ARF, but it doesn't matter which file I choose to open, it always shows me this error message:

```
------------------------------
  20030000 1619002112 apl00.bms

- error in src\quickbms.c line 7665: myalloc()
Error: Not enough space

Press RETURN to quit
```


It's obviously not a disk space problem (have 100+GB available on that HDD), rather a different header.

I attached this same file to the post. Could you please take a look at it, and see if there's a way to edit the old algorithm in order to open this kind of .vols, too?
Thank you very much!
[BCHR_APL00.7z](https://xentaxbackup.github.io/file/4667_BCHR_APL00.7z)
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-08-26T22:22:59+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

Looks like its little endian this time.

I think this will do:

```
#    xentax.com
#    .vol BMS script

idstring "RTDP"

endian little

get EOH long
get FILES long
get THISSIZE long

goto 0x20

for i = 1 to FILES

  getdstring FILENAME 32
  get FILESIZE long
  get FILEOFFSET long # relative to EOH

  filexor 0x55
  math FILEOFFSET += EOH
  log FILENAME FILEOFFSET FILESIZE
  filexor 0

next i
```

Just changed WRS' skript to little endian...
## Post #3
- Username: Julinha
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Sep 15, 2010 9:24 am
- Post datetime: 2011-09-01T20:38:56+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

Well,how I can open the .mdl file?x.x
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-10T11:31:57+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

I looked at the mdl files but am not sure if it was extracted properly (maybe it is not just a simple xor?)

Some files: [viewtopic.php?f=21&t=7245](http://forum.xentax.com/viewtopic.php?f=21&t=7245)
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-11T06:29:22+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

I looked at it a while back ago too and the model files do have valid offsets in them so I think it's fine. But I wasn't able to figure the model format out either.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-11T07:43:43+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

I quickly scrolled through it and saw nice floats and all, but then I suddenly came across



Which I can't imagine what it might be.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-11T11:29:47+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

Yep yep yep. There is no obvious index buffer so I figured it was like that one set of games (the disney ones I think and crap like back to the future) that have that mysterious index buffer format, so I gave up on this one. There's a lot of repetition in that section so I thought it might be textures but they aren't.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-11T17:34:32+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

Did you find a way to skip past the section at least?
Maybe leave half the file alone until you hit enlightenment or something
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-12T00:09:15+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

No, if I remember right there were two offsets in the offset table that reference the PTMD section. The first offset always pointed to the PTMD section, the second offset sometimes pointed to the PTMD section, and sometimes pointed to a little after it. It confused the hell out of me. I will look at it again soon since last I looked at it I was sort of a game extractor newbie back then ha ha ha.
## Post #10
- Username: Rysis
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Jul 28, 2010 5:50 am
- Post datetime: 2012-01-02T18:06:17+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

So anyone had success with this?
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-05T00:49:25+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

Bump.

I still can't get anything out of it although I believe the PTMD is supposed to lead to a texture of some sort.

Then again I don't even know if it's extracted properly.
## Post #12
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-13T03:36:16+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

I haven't looked at the files, but my experience in PSP games combined with what's been said here makes me think that there's no index buffer (the vertices need to be drawn as implicit triangles, common in lots of PSP games, and should be immediately evident if you see lots of fully-duplicated vertices near each other), and the vertices are probably defined by the traditional hardware vertex format tag. (it's a 32-bit value that specifies the presence/format of each possible component in the coming vertex array, you can find full details pretty quickly if you dig through the source of any of the PSP emulators out there)
## Post #13
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-14T16:22:26+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

It's quite a nice little format, looks like implicit triangles, found 10 verts in exact same position, not got them to fully cover the model yet, think that's down to the offsets.

Anyway, have a look at the .efp files, these are the same/similar format to the .mdl, and alot simpler in the number of vertices to sort out.
(efp = effects palette?)
The files are in chunks, each starting with the size of the chunk and the chunk name, then you get the offsets, followed by vert data, then PTMD which looks like raw image data, etc... (i dunno)
The verts are in variable size fields, 24,28,36,... bytes, x,y,z being the last 3 floats in each field.

BCHR_YUB01 is the red/black mech in this image: [http://2.bp.blogspot.com/_D-ExyCaQslw/T ... krock3.jpg](http://2.bp.blogspot.com/_D-ExyCaQslw/TO4G2fiy99I/AAAAAAAAFb4/ApFFaOZnHJE/s1600/blackrock3.jpg)
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-14T17:19:45+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

hmm I haven't actually sat down and tried to examine the general structure of the file (last time I looked at it was awhile ago)

Maybe I'll look into it tonight when I'm free.
Maybe I'll finally get black gold saw!



And ya, now that I look at what I posted about PTMD, it would make sense if it's texture data.
## Post #15
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-14T19:51:54+00:00
- Post Title: [PSP] Black Rock Shooter *.VOL (RTDP)

Still not able to make implicit triangles work.
Take a look at this from chr_m_egb01.mdl 
[http://pastebin.com/7EPQL2sN](http://pastebin.com/7EPQL2sN)
The data i'm showing you is the large chunk where each line starts with A2070012 
The left half of the 3rd long looks like offsets to the vert list, so maybe these are triangle descriptions?
The left byte of the 4th long changes frequently from 3 to 4 and back, lower down they go up to 16, could be mostly triangle and quad polygons??
Anyway, going to try doing triangles from the offsets, see if that works.

Edit: Yep, 3rd long is offset from start of 'triangle' list, left byte of 4th long is number of points in the polygon
[http://pastebin.com/LRgrfyeg](http://pastebin.com/LRgrfyeg) 
Hardcoded for one file, and the vertices and faces count are wrong, need to adjust them manually, but it's the method your looking at.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T01:19:35+00:00
- Post Title: Re: [PSP] Black Rock Shooter *.VOL (RTDP)

3D model discussion continued 

[viewtopic.php?f=16&p=69300](http://forum.xentax.com/viewtopic.php?f=16&p=69300)
