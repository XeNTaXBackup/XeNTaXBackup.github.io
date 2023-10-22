## Post #1
- Username: Armus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 15, 2010 10:51 pm
- Post datetime: 2012-03-11T21:08:07+00:00
- Post Title: Program for plotting points in 3d

Can you guys recommend a simple program (preferebly freeware) that can plot points in 3d space?

It would be nice if it could read in a simple format (like a text-format where each line contains a vertex (x,y,z)) and plot them in 3d space.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-11T21:15:14+00:00
- Post Title: Program for plotting points in 3d

Metasequoia. It's free, and it's a text format. And it comes with a fully functional 3D editor.

```
	patch 2
	segment 4
	shading 1
	facet 59.5
	vertex 116 {
		-96.5893 10.8410 -100.6263
		-48.4296 35.4233 -100.7180
		0.0000 48.5441 -100.0000
		50.0000 37.4307 -100.0000
		100.0000 17.8771 -100.0000
		-100.0000 25.0000 100.0000
		-50.0000 25.0000 100.0000
		0.0000 25.0000 100.0000
		50.0000 25.0000 100.0000
...


```


```
		4 V(20 21 23 22) M(0) UV(0.00000 0.00000 0.25000 0.00000 0.25000 1.00000 0.00000 1.00000)
		4 V(24 25 27 26) M(0) UV(0.25000 0.00000 0.50000 0.00000 0.50000 1.00000 0.25000 1.00000)
		4 V(28 29 31 30) M(0) UV(0.50000 0.00000 0.75000 0.00000 0.75000 1.00000 0.50000 1.00000)
		4 V(32 33 35 34) M(0) UV(0.75000 0.00000 1.00000 0.00000 1.00000 1.00000 0.75000 1.00000)
		4 V(36 37 21 20) M(1) UV(0.00000 0.00000 0.25000 0.00000 0.25000 0.00000 0.00000 0.00000)
		4 V(37 39 23 21) M(0) UV(0.25000 0.00000 0.25000 1.00000 0.25000 1.00000 0.25000 0.00000)
		4 V(39 38 22 23) M(0) UV(0.25000 1.00000 0.00000 1.00000 0.00000 1.00000 0.25000 1.00000)
		4 V(38 36 20 22) M(0) UV(0.00000 1.00000 0.00000 0.00000 0.00000 0.00000 0.00000 1.00000)
		4 V(40 5 6 41) M(0) UV(0.00000 0.00000 0.00000 0.00000 0.25000 0.00000 0.25000 0.00000)
		4 V(40 41 37 36) M(0) UV(0.00000 0.00000 0.25000 0.00000 0.25000 0.00000 0.00000 0.00000)
...

```
## Post #3
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-11T21:52:58+00:00
- Post Title: Program for plotting points in 3d

Seconded - Metasequoia
Here's my loong .fak vertex plotter :- [http://uppit.com/f3hyb9a9fqq0/Fakverts.zip](http://uppit.com/f3hyb9a9fqq0/Fakverts.zip)
The bit to just plot vertices is real simple, you make 2 point polys.

```
            of.write("2 V("+str(i)+" "+str(i)+")\n")
```


example for a cube

```
Format Text Ver 1.0

Scene {
	pos 0.0000 0.0000 1500.0000
	lookat 0.0000 0.0000 0.0000
	head -0.4736
	pich 0.5136
	ortho 0
	zoom2 5.0000
	amb 0.250 0.250 0.250
}
Object "obj1" {
	depth 0
	folding 0
	scale 1.000000 1.000000 1.000000
	rotation 0.000000 0.000000 0.000000
	translation 0.000000 0.000000 0.000000
	visible 15
	locking 0
	shading 1
	facet 59.5
	color 0.000 0.000 0.000
	color_type 0
	vertex 8 {
		-50.0000 50.0000 -50.0000
		50.0000 50.0000 -50.0000
		-50.0000 50.0000 50.0000
		50.0000 50.0000 50.0000
		-50.0000 -50.0000 50.0000
		50.0000 -50.0000 50.0000
		50.0000 -50.0000 -50.0000
		-50.0000 -50.0000 -50.0000
	}
	face 8 {
		2 V(0 0)
		2 V(1 1)
		2 V(2 2)
		2 V(3 3)
		2 V(4 4)
		2 V(5 5)
		2 V(6 6)
		2 V(7 7)
	}
}
Eof
```
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-11T22:28:05+00:00
- Post Title: Program for plotting points in 3d

I used mqo as my main exporter awhile back. It was a multi-format 3D converter I had planned to add to blender as well (kind of like the fatImporter for 3d max), with a single interface required for all plugins.

[viewtopic.php?f=29&t=6932](http://forum.xentax.com/viewtopic.php?f=29&t=6932)

Too bad it doesn't support normals.
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-03-12T18:26:23+00:00
- Post Title: Program for plotting points in 3d

> Reply from Armus
>
> Can you guys recommend a simple program (preferebly freeware) that can plot points in 3d space?
It would be nice if it could read in a simple format (like a text-format where each line contains a vertex (x,y,z)) and plot them in 3d space.

Just use the 3D Object Converter's 3D Points .txt load module.

[http://web.t-online.hu/karpo](http://web.t-online.hu/karpo)

See the attachment and in my program turn on the Vertexes using the CTRL+V hotkey !
[dewr_boots002.zip](https://xentaxbackup.github.io/file/5181_dewr_boots002.zip)
