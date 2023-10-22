## Post #1
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-09-01T10:51:51+00:00
- Post Title: Hot Wheels Jetz .MDL & .MDF Files

Helo everybody!

I'm coming back with another big mess: here, I've got .MDL files (beacuse are 2 files, and a few KB .MDF, like 10 KB, per model) 3D files from this 2001 videogame: Hot Wheels Jetz.

I've tried to play it to rip it: the game won't work (neither on VirtualBox, with WinXP and Win98!)

So, the only possibility that I've got is open this files, but how? I've tried with the Flight Simulator X open files, but nothing happens.

Someone can help me, please 

p.s.
In attach, the files (4 in total):

A10.mdl
[https://www.dropbox.com/s/f3z2zuvivr6k8lm/A10.mdl?dl=0](https://www.dropbox.com/s/f3z2zuvivr6k8lm/A10.mdl?dl=0)
A10.mdf
[https://www.dropbox.com/s/5nnt5t9rc7ircha/A10.mdf?dl=0](https://www.dropbox.com/s/5nnt5t9rc7ircha/A10.mdf?dl=0)
A10_sw.mdl
[https://www.dropbox.com/s/n8aosl8a4unzd ... w.mdl?dl=0](https://www.dropbox.com/s/n8aosl8a4unzdnh/A10_sw.mdl?dl=0)
A10_sw.mdf
[https://www.dropbox.com/s/cgdj7thx0vvhv ... w.mdf?dl=0](https://www.dropbox.com/s/cgdj7thx0vvhvon/A10_sw.mdf?dl=0)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-01T16:21:06+00:00
- Post Title: Hot Wheels Jetz .MDL & .MDF Files

not sure whether they are using triangle strips (maybe standard triangles and a mix of tris and quads?):



A10-mdl.jpg (77.75 KiB) Viewed 103 times
## Post #3
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-09-01T16:45:23+00:00
- Post Title: Hot Wheels Jetz .MDL & .MDF Files

> Reply from shakotay2
>
> not sure whether they are using triangle strips (maybe standard triangles and a mix of tris and quads?):
A10-mdl.jpg

shakotay2 thank you! and... i don't know
## Post #4
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-05-21T10:10:27+00:00
- Post Title: Hot Wheels Jetz .MDL & .MDF Files

Ok, I open the .mdl files from this game with 3d Model Researcher, but the only thing I found are the verticles. :/
[https://www.dropbox.com/s/hr4lpbte5nscb ... 0.png?dl=0](https://www.dropbox.com/s/hr4lpbte5nscbf2/A10.mdl_Wed_May_20_21-44-19_2020.png?dl=0)
For the faces, I think they starts around here:
[https://www.dropbox.com/s/r6gi6m0ro3h5j ... 2.jpg?dl=0](https://www.dropbox.com/s/r6gi6m0ro3h5j23/Immagine2.jpg?dl=0)
but they are all skewed up :/
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-21T10:53:12+00:00
- Post Title: Hot Wheels Jetz .MDL & .MDF Files

dunno. maybe it's just finding the correct face index start and stop addresses:
.



A10-mld.png (29.87 KiB) Viewed 55 times

(using triangle strips and toggle "face culling")

0x1007A 801
Vb1
32 99
0xEED8 141
020000
0x0 255
## Post #6
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-05-21T11:13:47+00:00
- Post Title: Hot Wheels Jetz .MDL & .MDF Files

Where you find the start address?

And... a stupid question: what is face cull?
