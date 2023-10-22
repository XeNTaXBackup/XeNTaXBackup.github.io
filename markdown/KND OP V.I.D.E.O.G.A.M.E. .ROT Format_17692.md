## Post #1
- Username: Mattzocrazy
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 22, 2015 9:06 am
- Post datetime: 2018-02-12T14:26:46+00:00
- Post Title: KND OP V.I.D.E.O.G.A.M.E. .ROT Format

So im trying to pull models from Kids Next Door: Operation V.I.D.E.O.G.A.M.E. I unpacked the .JAM files using a BMS script aluigi made but i cant find anything on what im pretty sure is the mesh format, ill attach a sample if anyone can give it a once over thatd be great!  
[00000099.zip](https://xentaxbackup.github.io/file/13903_00000099.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-02-12T17:11:04+00:00
- Post Title: KND OP V.I.D.E.O.G.A.M.E. .ROT Format

the .rot file contains rotation and transition data of the skeleton only:

```
LocalDrawingTransform[34]
CoordSys
{
	RotTransCoordSys "rootR"
	{
		Position -0.005029 -6.339650 70.022797
		Orientation 0.000000 0.000000 0.707106 0.707107
		LocalDrawingTransform 1.000000 0.000000 0.000000 0.000000  0.000000 1.000000 0.000000 0.000000  0.000000 0.000000 1.000000 0.000000  0.000000 0.000000 0.000000 1.000000
	}
...
	RotTransCoordSys "lidR"
	{
		Position 32.185459 -2.372370 0.014450
		Orientation 0.702325 -0.082099 0.702324 -0.082098
		Parent "spine1R"
		LocalDrawingTransform 0.000001 -0.918623 -0.395134 0.000000  1.000000 0.000001 0.000000 0.000000  0.000000 -0.395134 0.918623 0.000000  -0.014465 14.461403 -59.333328 1.000000
	}
}
```
## Post #3
- Username: Mattzocrazy
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 22, 2015 9:06 am
- Post datetime: 2018-02-12T22:39:58+00:00
- Post Title: KND OP V.I.D.E.O.G.A.M.E. .ROT Format

> Reply from shakotay2
>
> the .rot file contains rotation and transition data of the skeleton only[/code]
Ah is see, shite, okay, guess i gotta go look through the rest of the files lol thanks bro!
