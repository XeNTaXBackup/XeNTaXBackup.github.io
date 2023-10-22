## Post #1
- Username: maxeuwe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 30, 2015 7:19 am
- Post datetime: 2016-05-24T19:21:22+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

I need help fixing a Noesis plugin for Ai Sp@ce dxg files, and hope some can help me. The plugin is here: [http://himeworks.com/redirect.php?type= ... ispace_dxg](http://himeworks.com/redirect.php?type=noesis&name=aispace_dxg)

Currently it is broken, because it opens only some dxg model files (about 10%). The rest just show a blank screen.

The screenshot above shows an example of a correctly loaded model (hat) and not working model (face). The textured screenshots in the bottom row are from another program (dxgviewer4) - unfortunately, it can't export or do anything with files, so it's useless - I just used it to make sure the dxg files are correct and not corrupted or something.

Two screenshots marked as "random edit" are my experiments with the broken Noesis plugin. At the very bottom, I replaced the line:

```
mesh.idxBuff = self.parse_faces(mesh.numFaces * 3)
```

with

```
mesh.idxBuff = self.parse_faces(mesh.numFaces * 4+20)
```

and

```
mesh.idxBuff = self.parse_faces(mesh.numFaces * 5+20)
```


After that I got a distorted face model instead of just blank page. My guess is that the whole problem is about incorrect data offset, and can be easily fixed just by editing a few numbers or a couple lines of code. Unfortunately, my knowledge is very limited, so I never was able to progress past getting these distorted models.

Files in the archive attached:
10000020_1_0.dxg - hat (correctly loading)
100201_1_02_000.dxg - face (not working)
10500010_1_0.dxg - boots (not working)

I would be very thankful if somebody helped me with this. 
[aisp_dxg.rar](https://xentaxbackup.github.io/file/10970_aisp_dxg.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-24T20:52:19+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

don't have the time to care for the script but a quick glance at 100201_1_02_0000.dxg reveals that 
the startaddress of vertices: 0x12fc used by the script is deadly wrong, it's 0x1638.

Simply add
self.inFile.seek(0x1638)
before
mesh.vertBuff = self.inFile.readBytes(numCoords * 12)

Take care of the indents, works for this file only, just to show you the idea.



face_dxg.jpg (19.02 KiB) Viewed 262 times
## Post #3
- Username: maxeuwe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 30, 2015 7:19 am
- Post datetime: 2016-05-24T21:32:19+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

> Reply from shakotay2
>
> don't have the time to care for the script but a quick glance at 100201_1_02_0000.dxg reveals that 
the startaddress of vertices: 0x12fc used by the script is deadly wrong, it's 0x1638.

Simply add
self.inFile.seek(0x1638)
before
mesh.vertBuff = self.inFile.readBytes(numCoords * 12)

Take care of the indents, works for this file only, just to show you the idea.
That works, thank you!
Can you please explain a bit how do I look for correct start address of vertices in files? I assume this can be done by opening dxg files with a hex editor and looking for some specific values? Sorry if this sounds as a stupid question, but as my forum rank says, I'm an ultra-noob, and I only began learning 3D modelling recently.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-24T22:04:00+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

it can be done rather simple in this case: skip the bone names and search for the first float value.
You'll need to know how floats are expressed as 4 hex values, first vertex: x,y,z -> 3 floats -> 3x4 hex bytes (little endian): 

A48CB837 2099FB40 B2A21441
## Post #5
- Username: maxeuwe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 30, 2015 7:19 am
- Post datetime: 2016-05-24T23:24:38+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

> Reply from shakotay2
>
> it can be done rather simple in this case: skip the bone names and search for the first float value.
You'll need to know how floats are expressed as 4 hex values, first vertex: x,y,z -> 3 floats -> 3x4 hex bytes (little endian): 

A48CB837 2099FB40 B2A21441
Okay, I think I understand how it works now. I figured out the correct start address for the third sample file (boots) - 0x13AC, and it loads fine, so I guess this method will work for all other dxg files. That's all I needed to know.

I really appreciate that you spent your time to help to solve this problem. Thanks again!
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-25T10:29:32+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

> Reply from maxeuwe
>
> I really appreciate that you spent your time to help to solve this problem. Thanks again!Your welcome - but it's a workaround only. The problem is solved once we got the formula to skip the bones block.

It's 0x12FC..0x1638 = 0x33C = 828 dec. (104)
0x105c..0x13ac = 0x350 = 848 dec.  (80)

The value in the parenthesis is a maybe  count but there's no simple way to get the size 828, because 104x8=832.

Seems I found the offset address for the start of vertices, it's 0x15CC and 0x1354. 

0x68: 0x15CC + 0x68 +4= 0x1638
0x54: 0x1354 + 0x54 +4= 0x13AC

But to get 0x68 (or 0x54) you've to analyze the file header completely - I really hate such.  

I'd do it like this (in 'C' of course, not using damned python  ): search for FFFF, seek backwards -10.

Would result in 0x72-0xA= 0x68 and 0x5E-0xA= 0x54.
-------------------------------------------------------------

Well, the solution is even simpler - there's an unused variable sectionSize in the script which contains the offset I spoke of.

```
        offs= self.inFile.tell()
        startofverts= sectionSize+offs

[...]
        self.inFile.seek(startofverts)
        mesh.vertBuff = self.inFile.readBytes(numCoords * 12)
```
## Post #7
- Username: maxeuwe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 30, 2015 7:19 am
- Post datetime: 2016-05-25T17:56:34+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

> Reply from shakotay2
>
> Well, the solution is even simpler - there's an unused variable sectionSize in the script which contains the offset I spoke of.
It works great, thank you.
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-26T01:12:10+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

> Reply from shakotay2
>
> I'd do it like this (in 'C' of course, not using damned python  ): search for FFFF, seek backwards -10.
How do you do this in Noesis python script?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-26T16:35:50+00:00
- Post Title: Need help fixing a Noesis plugin [SOLVED]

as I wrote: "I never would"  
Guess you've to code it manually in python with two nested loops for example.

I tried

```
        index = string.find(b"\xFF")
```

and astonishingly index contained a correct offset address. But iirc find() was intended to be used for textual search only. I just abused it for a binary search, so use it on your own risk.

(There's zeroes in that "string" and strings are often terminated by 0x00.)
