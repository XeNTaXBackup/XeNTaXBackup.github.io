## Post #1
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2016-02-21T05:27:29+00:00
- Post Title: About convert .z3m file

Anyone can help, if have a converter to .obj of this file .z3m, from the game Risk your Life?
this post talk something about, but finale00 if possible can help ?
[viewtopic.php?f=16&t=7017](http://forum.xentax.com/viewtopic.php?f=16&t=7017)
[Examples of Z3m.rar](https://xentaxbackup.github.io/file/10511_Examples of Z3m.rar)
## Post #2
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-02-21T06:53:49+00:00
- Post Title: About convert .z3m file

Here you go.  
[fmt_riskyourlife_z3m.rar](https://xentaxbackup.github.io/file/10512_fmt_riskyourlife_z3m.rar)
## Post #3
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2016-02-22T11:31:42+00:00
- Post Title: About convert .z3m file

Ohh man, thnks  a lot. But, 1 more question: how to save back to format .z3m? Its possible save back to format .z3m with this plugin? I wish to xtract in .obj, edit in 3dmax for example, and so import back to game in .z3m. Do you know how to do this? I wiah to add new models, cause with 3d object converter, only files with same number of vertices can be done.

Its possible make Noesis export files in .z3m format too with this plugin? Or its only for open files? I think a .dll its needed..Or is impossible?
## Post #4
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-02-22T18:55:55+00:00
- Post Title: About convert .z3m file

I personally don't know how to export know formats into others especially through Noesis as I had to read a tutorial to write this script, but I imagine it wouldn't be that hard since this format is fairly simple. But if there's already a converter that can only change models with the same amount of vertices, I have confidence to say that there's a chance something in game is keeping people from importing custom verts, probably something among the lines of a check sum and another exporter would do you no good, but take this with a grain of salt as my knowledge is still fairly limited.
## Post #5
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2016-02-23T14:27:18+00:00
- Post Title: About convert .z3m file

> Reply from killercracker
>
> I personally don't know how to export know formats into others especially through Noesis as I had to read a tutorial to write this script, but I imagine it wouldn't be that hard since this format is fairly simple. But if there's already a converter that can only change models with the same amount of vertices, I have confidence to say that there's a chance something in game is keeping people from importing custom verts, probably something among the lines of a check sum and another exporter would do you no good, but take this with a grain of salt as my knowledge is still fairly limited.

The owner of 3d object converter, said that its hard to him, cause doesnt know well this format. He said:
"I closed the development of the .z3m export module (to create the .z3m file without using the original .z3m file) based on the following problem:
The vertex bone reference values (range: 0-255) are much more greater than the number of used bones (usually: about 26)."

So i dont know how to start to make this... Can you help me with this?
Here you can see some of waht is happening about it:
[http://forum.ragezone.com/f563/3d-objec ... ost8499576](http://forum.ragezone.com/f563/3d-object-converter-1027242/#post8499576)
## Post #6
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-02-23T17:44:43+00:00
- Post Title: About convert .z3m file

I remember see that part and not knowing what that was. Normally meshes that use skeletal animation have 4 weights and 4 bone id's assigned to each vert. I'm only seeing what looks like 1 weight and 2 bone id's. I believe they may be compressed, but I'm not all to sure. I'll look into it more when I have more time.
## Post #7
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2016-02-24T19:06:53+00:00
- Post Title: About convert .z3m file

killercracker, ill apreciate your help...when you have some time, try to see what can be done, if its possible to make an export plugin to the noesis about .z3m. There is a program called Rmodel, done by alphaest, but he doesn´t release the program. it seems he sold the project to guys, and that guys, dont release it. More infos here:
[http://alpha.lutsu.ee/forum/viewtopic.php?f=18&t=70](http://alpha.lutsu.ee/forum/viewtopic.php?f=18&t=70)

have a program, called rmap. inside the source code, have a folder called r3s to 3ds, with a subfolder called Converters. There, have a lot of conversions way (objToZ3m.cs;z3mToObj.cs, etc..). Take a look there. I'll upload here this folder, and the complete program ok?

The complet source program:
[http://www.mediafire.com/download/q268l ... source.rar](http://www.mediafire.com/download/q268l79xndyi7td/rMap_source.rar)

If need more some file, just ask me ok? Thnks for your help killer!
[r3s_to_3ds.rar](https://xentaxbackup.github.io/file/10524_r3s_to_3ds.rar)
## Post #8
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2016-02-28T23:22:14+00:00
- Post Title: About convert .z3m file

Any news about?
## Post #9
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2016-03-06T19:59:26+00:00
- Post Title: About convert .z3m file

killercracker, have seen something about?
