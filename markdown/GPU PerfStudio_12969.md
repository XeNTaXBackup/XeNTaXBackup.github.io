## Post #1
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-06-21T22:38:50+00:00
- Post Title: GPU PerfStudio

Hello

i have take a look on GPU PerfStudio
it's like the Intel Graphic Frame Analyser

with GPU PerfStudio , i can export 2 files
IndexBuffer.txt and VertexBuffer.txt



this soft load many things in memory

[https://drive.google.com/file/d/0B38_2a ... sp=sharing](https://drive.google.com/file/d/0B38_2aQCnZ7bb01ZekVMWWprVXc/view?usp=sharing)

question:

how convert the VertexBuffer file into an obj file ?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-22T11:03:17+00:00
- Post Title: GPU PerfStudio

> Reply from CZW
>
> with GPU PerfStudio , i can export 2 files
IndexBuffer.txt and VertexBuffer.txtAre you sure it can't export more than that?
For example to export the model it shows in any 3D format?

> how convert the VertexBuffer file into an obj file ?Rather simple if you know File I/O in any programming language:



Dolphin.JPG (37.3 KiB) Viewed 73 times

The face indices are triangle strips with an 0xFFFF terminal (too lazy to convert that, too).

btw: there are QNANs and other probs in the txt files you uploaded:
0.000000  -1.#QNAN0  0.000000 -1.#QNAN0  0.000000  -1.#QNAN0 0.000000  -1.#QNAN0

0.000000  -191408831393027890000000000000000000000.000000  4.615234 2.274414  -20.257813  0.000000 

Maybe that's the reason why the Studio can't export the model.
