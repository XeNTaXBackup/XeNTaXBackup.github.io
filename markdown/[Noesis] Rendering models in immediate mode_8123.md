## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-25T06:11:17+00:00
- Post Title: [Noesis] Rendering models in immediate mode

This guide is just a working demo on how to render models using the imm methods using the noesis python API.

It assumes you are familiar with python.
It assumes that you already know how to follow specs and can render it using the rpgBind... methods.
It doesn't include the full source, it just gives you an idea how to use it.

Since there's a Shaiya Online tutorial already, and the format is simple, let's just go with that.
Instead of 3DC format I'll just use 3DO cause it's even simpler.

```
uint32 numVerts

numVerts Vertex {
    float[3] vx, vy, vz
    float[3] nx, ny, nz
    float[2] tu, tv
}

uint32 numFaces
numFaces Face {
   uint16[3] v1, v2, v3
}

```


If you were to write a plugin for this using buffer binds, it would look something like this

```
def parse_file(bs):
	bs.readUInt()
	 
	numVerts = bs.readUInt()
	vertBuff = bs.readBytes(numVerts*32)
	rapi.rpgBindPositionBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 0)
	rapi.rpgBindNormalBufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 12)
	rapi.rpgBindUV1BufferOfs(vertBuff, noesis.RPGEODATA_FLOAT, 32, 24)

	numIndex = bs.readUInt() * 3 
	idxBuff = bs.readBytes(numIndex*2)
	rapi.rpgCommitTriangles(idxBuff, noesis.RPGEODATA_USHORT, numIdx, noesis.RPGEO_TRIANGLE, 1)

```


So clearly, it's pretty easy to use the buffer binding functions to do it.
With imm methods, instead of passing in bytes you're passing in a list of python values.

Depending on your own preferences, there are various ways you can build those lists.
I prefer to just toss everything into a list and then index them as I need them.

```
	bs.readUInt()
	numVerts = bs.readUInt()

```


The start of the function is the same. It's your usual parsing.
Then you parse the vertices.

```
	bs.readUInt()
	numVerts = bs.readUInt()
	 
	positions = []
	normals = []
	uvs = []
	for i in range(numVerts):
		vx, vy, vz, nx, ny, nz, tu, tv = bs.read('8f')
		positions.append([vx, vy, vz])
		normals.append([nx, ny, nz])
		uvs.append([tu, tv])

```


Here I declared some lists, and then added lists of floats to them.
Cause you know, a single 3D position consists of 3 floats...etc.

Now we just need to render them. We know they're all triangles, so something like this would work.

```
	bs.readUInt()
	numVerts = bs.readUInt()
	 
	positions = []
	normals = []
	uvs = []
	for i in range(numVerts):
		vx, vy, vz, nx, ny, nz, tu, tv = bs.read('8f')
		positions.append([vx, vy, vz])
		normals.append([nx, ny, nz])
		uvs.append([tu, tv])

	numIdx = bs.readUInt()
	rapi.immBegin(noesis.RPGEO_TRIANGLE)
	for i in range(numIdx):
		index = bs.readUShort()
		rapi.immVertex3(positions[index])
		rapi.immNormal3(normals[index])
		rapi.immUV2(uvs[index])
	rapi.immEnd()

```


Now you can just call constructModel and do whatever you need to do.



Those imm methods expect a list of values, which is why I chose to store them as lists of lists (also because of how the data is stored). But again, there are countless ways you can build those lists.

In theory, anything you can do with buffer binding can be done with imm. And vice-versa.
It's true that buffer binding for this format was a lot cleaner (and faster).

If you've already worked with the buffer binding approach, you should see that immediate-mode rendering provides greater flexibility for loading your model, especially for more complicated formats. Like maybe if stores a list of positions, normals, and UV's, and then each face indexes the positions, normals, and UV's separately.

Some 3DO files are attached.
[3DO.zip](https://xentaxbackup.github.io/file/5012_3DO.zip)
