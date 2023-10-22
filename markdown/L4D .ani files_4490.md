## Post #1
- Username: Disseminate
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 06, 2010 12:03 am
- Post datetime: 2010-05-23T01:02:54+00:00
- Post Title: L4D .ani files

It's possible to decompile the models from L4D using cannonfodder's HL2 decompile tools with a few quick hex editor hacks. However, I'm looking to get the animations from them in 3ds. So far, I've been unsuccessful and was wondering if anyone else here has any idea as to what to do.

Here's a couple rough notes I've taken over the last couple months, if any of it helps

```
- The actual models have the header <IDST1>, or model revision 47 (TF2 <IDST0>/13, HL2 <IDST,>/7).
- .ani files have the header <IDAG1>
- You can decompile an anim file by changing the headers of both the x_anim.mdl and x_anim.ani to <IDST,>.
- To decompile it with cannonfodder's mdldecompiler 0.5, you put the .ani file in the same directory as mdldecompiler and with the .mdl file. The .mdl file can be anywhere
- This will export a .qc file that's perfectly valid, as well as every .smd animation.
- The .smd animations generated from the above method are junk - every frame is the model's ragdoll animation on every anim.
- No hacked decompiler I've tested works with these.
```


Here's some stuff I uploaded

Valid QC file generated from decompiling the boomer animations - [http://luaforfood.com/anim_boomer_decompile.txt](http://luaforfood.com/anim_boomer_decompile.txt)
One of the junk generated boomer animation .smd files - [http://luaforfood.com/a_RunN.txt](http://luaforfood.com/a_RunN.txt)
Boomer original files - [http://luaforfood.com/uploads/boomersource.zip](http://luaforfood.com/uploads/boomersource.zip)

Basically, you can decompile anim_boomer.mdl which references anim_boomer.ani near the end of the file. So far, I'm at a dead end with a load of junk animation files. If anyone has any insight, that'd be great.
## Post #2
- Username: Disseminate
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 06, 2010 12:03 am
- Post datetime: 2010-05-24T15:02:50+00:00
- Post Title: L4D .ani files

Anyone have any ideas?
