## Post #1
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2020-11-12T19:19:46+00:00
- Post Title: File format documentation... format

Hello, I am new to these forums and this is my first post.

I am an amateur programmer (Python), and I am working on my favorites games revere engineering resource files.
I am quite new to this stuff, and when I documented my findings, I tried several different formatting styles.

here are a few examples:

```
Byte Order - Little Endian
Byte chunk grouping - 4 Byte


Start of 1st Archive Part

	1 chunk
		1st byte - unknown, could be file ID or mark beginning of file, always 14
		2nd byte - unknown, could be file ID or mark beginning of file, always 00
		3rd byte - unknown
		4th byte - unknown

	1 chunk
		1st - 4th byte - offset pointer to 2nd Archive Header

	all remaining chunks
		any byte - Undocumented, there are names of sub-meshes in text form from this file and corresponding global .PLM file. Looks like it has coordinates for sub-meshes


End of 1st Archive Part


Start of 2nd Archive Header (offsets are counted from 2nd Archive Header)

	1 chunk
		1st byte - unknown, could be file ID or mark beginning of file, always 30
		2nd byte - unknown, could be file ID or mark beginning of file, always 06
		3rd byte - unknown, could be flag, always 00, changes to 1 when model is loaded into RAM (need more testing)
		4th byte - number of textures (textures are stored in external files)

	1 chunk
		1st - 4th byte - offset pointer to textures (textures are stored in external files)

	1 chunk
		1st - 4th byte - number of sub-meshes in this file
		OR
		1st byte - number of sub-meshes in this file
		2nd - 4th byte - empty space with 00

	1 chunk
		1st - 4th byte - offset pointer to sub-mesh list section

	1 chunk
		1st - 4th byte - offset pointer to mesh order list

End of 2nd Archive Header


Start of Directory

	6 chunks x (number of textures (textures are stored in external files))
		1st - 24th byte - name of textures in text form (textures are stored in external files)
		OR
		1st - 8th byte - name of textures in text form (textures are stored in external files)
		9th - 24th byte - empty space with 00

	4 chunks x (number of sub-meshes in this file)
		1st - 2nd chunks
			1st - 8th byte - name of sub-mesh in text form
		3rd chunk
			1st - 4th byte - unknown data
		4th chunk
			1st - 4th byte - offset pointer to sub-mesh section

	1 byte x (number of sub-meshes in this file) (rounded to fit in chunks)
		1st chunk
			any byte - filled with 00, could be flags to loaded meshes

	1 byte x (number of sub-meshes in this file) (rounded to fit in chunks)
		1st chunk
			any byte - mesh order counting from 0, unknown purpose, if number of sub-meshes in this file does not divides from 4, then last bytes in chunks are filled with 00 and will be ignored

End of Directory


Start of Sub-Mesh Section x (number of sub-meshes in this file)

	Start of Sub-Mesh Header

		1 chunk
			1st byte - number of polygons in this sub-mesh
			2nd byte - number of vertices in this sub-mesh
			3rd byte - number of unknown data in section 3 of this sub-mesh
			4th byte - number of unknown data in section 4 of this sub-mesh

		1 chunk
			1st - 4th byte - offset pointer to polygons data

		1 chunk
			1st - 4th byte - offset pointer to vertices of XY axis (need to confirm if this is really XY)

		1 chunk
			1st - 4th byte - offset pointer to vertices of Z axis (need to confirm if this is really Z)

		1 chunk
			1st - 4th byte - offset pointer to unknown data in section 3

		1 chunk
			1st - 4th byte - offset pointer to unknown data in section 4

	End of Sub-Mesh Header

	Start of Sub-Mesh Data

		Polygon section
		20 bytes x (number of polygons of this sub-mesh)
			1st chunk
				1st byte - U1 coordinate
				2nd byte - V1 coordinate
				3rd byte - unknown, could be palette info
				4th byte - unknown, could be palette info
			2nd chunk
				1st byte - U2 coordinate
				2nd byte - V2 coordinate
				3rd byte - unknown, could be palette info, almost always 00
				4th byte - unknown, could be palette info, almost always 00
			3rd chunk
				1st byte - U3 coordinate
				2nd byte - V3 coordinate
				3rd byte - U4 coordinate, exist only if there is F4, otherwise it is 00 and is ignored
				4th byte - V4 coordinate, exist only if there is F4, otherwise it is 00 and is ignored
			4th chunk
				1st byte - F1 face index
				2nd byte - F2 face index
				3rd byte - F3 face index
				4th byte - F4 face index, strip triangle (if exist, uses F2, F3 and F4). If doesn't exist, then it is FF and is ignored
			5th chunk
				1st - 4th byte - unknown data

		XY Vertices section
		4 bytes x (number of vertices of this sub-mesh)
			1st chunk
				1st - 2nd byte - X axis vertex coordinate
				3rd - 4th byte - Y axis vertex coordinate

		Z Vertices section
		2 bytes x (number of vertices of this sub-mesh) (rounded to fit in chunks)
			1st chunk
				1st - 2nd byte - Z axis vertex coordinate
				3rd - 4th byte - Z axis vertex coordinate, if there is odd number of vertices, then it will be 00 00 and will be ignored

		Unknown section 3
		4 bytes x (number of unknown data in section 3 of this sub-mesh)
			1st chunk
				1st - 4th byte - unknown data

		Unknown section 4
		1 byte x (number of unknown data in section 4 of this sub-mesh) (rounded to fit in chunks)
			1st chunk
				any byte - unknown data, if number of unknown data does not divide from 4, then last bytes will be filled with 00 and will be ignored

	End of Sub-Mesh Data

End of Sub-Mesh Section


Start of Footer Section

	any chunk
		any byte - unused garbage data, usually copy of the beginning of the file

End of Footer Section

```


```

        Suffix: .plm or .ilm
Suffix meaning: unknown
          Type: binary
    Byte order: little endian



  str = String
  int = Signed Integer
u_int = Unsigned Integer
float = Floating Point
const = Constant

 8 bits = 1 byte
16 bits = 2 bytes
32 bits = 4 bytes
64 bits = 8 bytes

+----------------------------------------------------------+
|   Table name : File's header                             |
|   Offset     : Relative 0x0                              |
|   Size       : 20 bytes                                  |
|   Repeats by : Doesn't repeat                            |
+----------------------------------------------------------+
| 1 byte  |    0x30 | File format ID                       |
| 1 byte  |       6 | Version (only 6 is known)            |
| 1 byte  | boolean | File flag                            |
|         |         | (always 0, crashes when set to 1)    |
| 1 byte  |   u_int | Number of textures                   |
| 4 bytes |   u_int | Relative pointer to textures list    |
| 4 bytes |   u_int | Number of objects                    |
| 4 bytes |   u_int | Relative pointer to objects list     |
| 4 bytes |   u_int | Relative pointer to object order     |
+----------------------------------------------------------+

+----------------------------------------------------------+
|   Table name : Textures list                             |
|   Offset     : Relative pointer to textures list         |
|   Size       : 24 bytes                                  |
|   Repeats by : Number of textures                        |
+----------------------------------------------------------+
| 8 bytes |     str | Texture name                         |
| 4 bytes | unknown | Undocumented texture properties      |
|         |         | (looks like always 0)                |
| 4 bytes | unknown | Undocumented texture properties      |
|         |         | (looks like always 0)                |
| 4 bytes | unknown | Undocumented texture properties      |
|         |         | (looks like always 0)                |
| 4 bytes | unknown | Undocumented texture properties      |
|         |         | (looks like always 0)                |
+----------------------------------------------------------+

+----------------------------------------------------------+
|   Table name : Objects list                              |
|   Offset     : Relative pointer to objects list          |
|   Size       : 16 bytes                                  |
|   Repeats by : Number of objects                         |
+----------------------------------------------------------+
| 8 bytes |     str | Object name                          |
| 1 byte  |   u_int | Number of meshes                     |
| 1 byte  |   u_int | Vertex shift                         |
| 1 byte  |   u_int | Normals shift                        |
|---------+---------+--------------------------------------|
| 1 bit   | boolean | Shading rendering mode               |
| 1 bit   | boolean | Unknown object render properties     |
| 1 bit   | boolean | Unknown object render properties     |
| 1 bit   | boolean | Unknown object render properties     |
| 1 bit   | boolean | Unknown object render properties     |
| 1 bit   | boolean | Transparency rendering mode          |
| 1 bit   | boolean | Unknown object render properties     |
| 1 bit   | boolean | Unknown object render properties     |
|---------+---------+--------------------------------------|
| 4 bytes |   u_int | Relative pointer to object data      |
+----------------------------------------------------------+

+----------------------------------------------------------+
|   Table name : Object order                              |
|   Offset     : Relative pointer to object order          |
|   Size       : 1 byte                                    |
|   Repeats by : Number of objects                         |
+----------------------------------------------------------+
| 1 byte  |   u_int | Object number (starting from 0)      |
+----------------------------------------------------------+

+--------------------------------------------------------------------------+
|   Table name : Objects data                                              |
|   Offset     : Relative pointer to object data                           |
|   Size       : Variable                                                  |
|   Repeats by : Number of objects                                         |
+--------------------------------------------------------------------------+
|                                                                          |
|   +----------------------------------------------------------+           |
|   |   Table name : Object's mesh header                      |           |
|   |   Offset     : Relative pointer to object data           |           |
|   |   Size       : 24 bytes                                  |           |
|   |   Repeats by : Number of meshes                          |           |
|   +----------------------------------------------------------+           |
|   | 1 byte  |   u_int | Number of primitives                 |           |
|   | 1 byte  |   u_int | Number of vertices                   |           |
|   | 1 byte  |   u_int | Number of normals                    |           |
|   | 1 byte  |   u_int | Number of unknown                    |           |
|   | 4 bytes |   u_int | Relative pointer to primitives       |           |
|   | 4 bytes |   u_int | Relative pointer to XY vertices      |           |
|   | 4 bytes |   u_int | Relative pointer to Z vertices       |           |
|   | 4 bytes |   u_int | Relative pointer to normals          |           |
|   | 4 bytes |   u_int | Relative pointer to unknown          |           |
|   +----------------------------------------------------------+           |
|                                                                          |
|   +------------------------------------------------------------------+   |
|   |   Table name : Object's mesh data                                |   |
|   |   Offset     : Relative pointer to primitives                    |   |
|   |   Size       : Variable                                          |   |
|   |   Repeats by : Number of meshes                                  |   |
|   +------------------------------------------------------------------+   |
|   |                                                                  |   |
|   |   +----------------------------------------------------------+   |   |
|   |   |   Table name : Object's mesh's primitives                |   |   |
|   |   |   Offset     : Relative pointer to primitives            |   |   |
|   |   |   Size       : 20 bytes                                  |   |   |
|   |   |   Repeats by : Number of primitives                      |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |   | 1 byte  |   u_int | Texture's U1 coordinate              |   |   |
|   |   | 1 byte  |   u_int | Texture's V1 coordinate              |   |   |
|   |   |---------+---------+--------------------------------------|   |   |
|   |   | 6 bits  |   u_int | X coordinate of CLUT in VRAM?        |   |   |
|   |   | 9 bits  |   u_int | Y coordinate of CLUT in VRAM?        |   |   |
|   |   | 1 bit   | unknown | Unknown                              |   |   |
|   |   |---------+---------+--------------------------------------|   |   |
|   |   | 1 byte  |   u_int | Texture's U2 coordinate              |   |   |
|   |   | 1 byte  |   u_int | Texture's V2 coordinate              |   |   |
|   |   | 1 byte  | unknown | Unknown                              |   |   |
|   |   |---------+---------+--------------------------------------|   |   |
|   |   | 7 bits  |   u_int | Used texture number (starting from 0)|   |   |
|   |   | 1 bit   | boolean | Texture's semi-transparency mode     |   |   |
|   |   |---------+---------+--------------------------------------|   |   |
|   |   | 1 byte  |   u_int | Texture's U3 coordinate              |   |   |
|   |   | 1 byte  |   u_int | Texture's V3 coordinate              |   |   |
|   |   | 1 byte  |   u_int | Texture's U4 coordinate              |   |   |
|   |   |         |         | (only in strips, otherwise 0)        |   |   |
|   |   | 1 byte  |   u_int | Texture's V4 coordinate              |   |   |
|   |   |         |         | (only in strips, otherwise 0)        |   |   |
|   |   | 1 byte  |   u_int | Face's 1st index                     |   |   |
|   |   | 1 byte  |   u_int | Face's 2nd index                     |   |   |
|   |   | 1 byte  |   u_int | Face's 3rd index                     |   |   |
|   |   | 1 byte  |   u_int | Face's 4th index                     |   |   |
|   |   |         |         | (only in strips, otherwise 0)        |   |   |
|   |   | 1 byte  |   u_int | Unknown index                        |   |   |
|   |   | 1 byte  |   u_int | Unknown index                        |   |   |
|   |   | 1 byte  |   u_int | Unknown index                        |   |   |
|   |   | 1 byte  |   u_int | Unknown index                        |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |                                                                  |   |
|   |   +----------------------------------------------------------+   |   |
|   |   |   Table name : Object's mesh's XY vertices               |   |   |
|   |   |   Offset     : Relative pointer to XY vertices           |   |   |
|   |   |   Size       : 4 bytes                                   |   |   |
|   |   |   Repeats by : Number of vertices                        |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |   | 2 bytes |     int | Mesh's vertex X coordinate           |   |   |
|   |   | 2 bytes |     int | Mesh's vertex Y coordinate           |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |                                                                  |   |
|   |   +----------------------------------------------------------+   |   |
|   |   |   Table name : Object's mesh's Z vertices                |   |   |
|   |   |   Offset     : Relative pointer to Z vertices            |   |   |
|   |   |   Size       : 2 bytes                                   |   |   |
|   |   |   Repeats by : Number of vertices                        |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |   | 2 bytes |     int | Mesh's vertex Z coordinate           |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |                                                                  |   |
|   |   +----------------------------------------------------------+   |   |
|   |   |   Table name : Object's mesh's normals                   |   |   |
|   |   |   Offset     : Relative pointer to normals               |   |   |
|   |   |   Size       : 4 bytes                                   |   |   |
|   |   |   Repeats by : Number of normals                         |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |   | 1 byte  |     int | Mesh's normal vertex I coordinate    |   |   |
|   |   | 1 byte  |     int | Mesh's normal vertex J coordinate    |   |   |
|   |   | 1 byte  |     int | Mesh's normal vertex K coordinate    |   |   |
|   |   | 1 byte  |   u_int | Number of time used?                 |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |                                                                  |   |
|   |   +----------------------------------------------------------+   |   |
|   |   |   Table name : Object's mesh's unknown                   |   |   |
|   |   |   Offset     : Relative pointer to unknown               |   |   |
|   |   |   Size       : 1 byte                                    |   |   |
|   |   |   Repeats by : Number of unknown                         |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |   | 1 byte  |  u_int? | Unknown index?                       |   |   |
|   |   +----------------------------------------------------------+   |   |
|   |                                                                  |   |
|   +------------------------------------------------------------------+   |
|                                                                          |
+--------------------------------------------------------------------------+

```


```
	"metadata": {},
	"data": [
		{
			"type": "header",
			"name": "File header",
			"size": 20,
			"size type": "byte",
			"offset": 0,
			"repeats": 1,
			"condition": true,
			"content": [
				{
					"type": "data",
					"name": "File format ID",
					"size": 1,
					"size type": "byte",
					"value type": "0x30",
					"comment": null
				},
				{
					"type": "data",
					"name": "Version",
					"size": 1,
					"size type": "byte",
					"value type": 6,
					"comment": "only 6 is known"
				},
				{
					"type": "data",
					"name": "File flag",
					"size": 1,
					"size type": "byte",
					"value type": "boolean",
					"comment": "always 0, crashes when set to 1"
				},
				{
					"type": "data",
					"name": "Number of textures",
					"size": 1,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				},
				{
					"type": "data",
					"name": "Relative pointer to textures list",
					"size": 4,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				},
				{
					"type": "data",
					"name": "Number of objects",
					"size": 4,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				},
				{
					"type": "data",
					"name": "Relative pointer to objects list",
					"size": 4,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				},
				{
					"type": "data",
					"name": "Relative pointer to object order",
					"size": 4,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				}
			]
		},
		{
			"type": "header",
			"name": "Textures list",
			"size": 24,
			"size type": "byte",
			"offset": "Relative pointer to textures list",
			"repeats": "Number of textures",
			"condition": true,
			"content": [
				{
					"type": "data",
					"name": "Texture name",
					"size": 8,
					"size type": "byte",
					"value type": "string",
					"comment": null
				},
				{
					"type": "data",
					"name": "Undocumented texture properties",
					"size": 4,
					"size type": "byte",
					"value type": "unknown",
					"comment": "looks like always 0"
				},
				{
					"type": "data",
					"name": "Undocumented texture properties",
					"size": 4,
					"size type": "byte",
					"value type": "unknown",
					"comment": "looks like always 0"
				},
				{
					"type": "data",
					"name": "Undocumented texture properties",
					"size": 4,
					"size type": "byte",
					"value type": "unknown",
					"comment": "looks like always 0"
				},
				{
					"type": "data",
					"name": "Undocumented texture properties",
					"size": 4,
					"size type": "byte",
					"value type": "unknown",
					"comment": "looks like always 0"
				}
			]
		},
		{
			"type": "header",
			"name": "Objects list",
			"size": 16,
			"size type": "byte",
			"offset": "Relative pointer to objects list",
			"repeats": "Number of objects",
			"condition": true,
			"content": [
				{
					"type": "data",
					"name": "Object name",
					"size": 8,
					"size type": "byte",
					"value type": "string",
					"comment": null
				},
				{
					"type": "data",
					"name": "Number of meshes",
					"size": 1,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				},
				{
					"type": "data",
					"name": "Vertex shift",
					"size": 1,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				},
				{
					"type": "data",
					"name": "Normals shift",
					"size": 1,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				},
				{
					"type": "data",
					"name": "Shading rendering mode",
					"size": 1,
					"size type": "bit",
					"value type": "boolean",
					"comment": null
				},
				{
					"type": "data",
					"name": "Unknown object render properties",
					"size": 1,
					"size type": "bit",
					"value type": "boolean",
					"comment": null
				},
				{
					"type": "data",
					"name": "Unknown object render properties",
					"size": 1,
					"size type": "bit",
					"value type": "boolean",
					"comment": null
				},
				{
					"type": "data",
					"name": "Unknown object render properties",
					"size": 1,
					"size type": "bit",
					"value type": "boolean",
					"comment": null
				},
				{
					"type": "data",
					"name": "Unknown object render properties",
					"size": 1,
					"size type": "bit",
					"value type": "boolean",
					"comment": null
				},
				{
					"type": "data",
					"name": "Transparency rendering mode",
					"size": 1,
					"size type": "bit",
					"value type": "boolean",
					"comment": null
				},
				{
					"type": "data",
					"name": "Unknown object render properties",
					"size": 1,
					"size type": "bit",
					"value type": "boolean",
					"comment": null
				},
				{
					"type": "data",
					"name": "Unknown object render properties",
					"size": 1,
					"size type": "bit",
					"value type": "boolean",
					"comment": null
				},
				{
					"type": "data",
					"name": "Relative pointer to object data",
					"size": 4,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": null
				}
			]
		},
		{
			"type": "header",
			"name": "Objects order",
			"size": 1,
			"size type": "byte",
			"offset": "Relative pointer to object order",
			"repeats": "Number of objects",
			"condition": true,
			"content": [
				{
					"type": "data",
					"name": "Object number",
					"size": 1,
					"size type": "byte",
					"value type": "unsigned integer",
					"comment": "starting from 0"
				}
			]
		},
		{
			"type": "header",
			"name": "Object data",
			"size": "unknown",
			"size type": "byte",
			"offset": "Relative pointer to object data",
			"repeats": "Number of objects",
			"condition": true,
			"content": [
				{
					"type": "header",
					"name": "Object's mesh header",
					"size": "24",
					"size type": "byte",
					"offset": "Relative pointer to object data",
					"repeats": "Number of meshes",
					"condition": true,
					"content": [
						{
							"type": "data",
							"name": "Number of primitives",
							"size": 1,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						},
						{
							"type": "data",
							"name": "Number of vertices",
							"size": 1,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						},
						{
							"type": "data",
							"name": "Number of normals",
							"size": 1,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						},
						{
							"type": "data",
							"name": "Number of unknown",
							"size": 1,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						},
						{
							"type": "data",
							"name": "Relative pointer to primitives",
							"size": 4,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						},
						{
							"type": "data",
							"name": "Relative pointer to XY vertices",
							"size": 4,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						},
						{
							"type": "data",
							"name": "Relative pointer to Z vertices",
							"size": 4,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						},
						{
							"type": "data",
							"name": "Relative pointer to normals",
							"size": 4,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						},
						{
							"type": "data",
							"name": "Relative pointer to unknown",
							"size": 4,
							"size type": "byte",
							"value type": "unsigned integer",
							"comment": null
						}
					]
				},
				{
					"type": "header",
					"name": "Object's mesh data",
					"size": "unknown",
					"size type": "byte",
					"offset": "Relative pointer to primitives",
					"repeats": "Number of meshes",
					"condition": true,
					"content": [
						{
							"type": "header",
							"name": "Object's mesh's primitives",
							"size": "20",
							"size type": "byte",
							"offset": "Relative pointer to primitives",
							"repeats": "Number of primitives",
							"condition": true,
							"content": [
								{
									"type": "data",
									"name": "Texture's U1 coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Texture's V1 coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "X coordinate of CLUT in VRAM?",
									"size": 6,
									"size type": "bit",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "X coordinate of CLUT in VRAM?",
									"size": 9,
									"size type": "bit",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Unknown",
									"size": 1,
									"size type": "bit",
									"value type": "boolean",
									"comment": null
								},
								{
									"type": "data",
									"name": "Texture's U2 coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Texture's V2 coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Unknown",
									"size": 1,
									"size type": "byte",
									"value type": "unknown",
									"comment": null
								},
								{
									"type": "data",
									"name": "Used texture number",
									"size": 7,
									"size type": "bit",
									"value type": "unsigned integer",
									"comment": "starting from 0"
								},
								{
									"type": "data",
									"name": "Texture's semi-transparency mode",
									"size": 1,
									"size type": "bit",
									"value type": "boolean",
									"comment": null
								},
								{
									"type": "data",
									"name": "Texture's U3 coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Texture's V3 coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Texture's U4 coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": "only in strips, otherwise 0"
								},
								{
									"type": "data",
									"name": "Texture's V4 coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": "only in strips, otherwise 0"
								},
								{
									"type": "data",
									"name": "Face's 1st index",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Face's 2nd index",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Face's 3rd index",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Face's 4th index",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": "only in strips, otherwise 0"
								},
								{
									"type": "data",
									"name": "Unknown index",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Unknown index",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Unknown index",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Unknown index",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								}
							]
						},
						{
							"type": "header",
							"name": "Object's mesh's XY vertices",
							"size": "4",
							"size type": "byte",
							"offset": "Relative pointer to XY vertices",
							"repeats": "Number of vertices",
							"condition": true,
							"content": [
								{
									"type": "data",
									"name": "Mesh's vertex X coordinate",
									"size": 2,
									"size type": "byte",
									"value type": "signed integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Mesh's vertex Y coordinate",
									"size": 2,
									"size type": "byte",
									"value type": "signed integer",
									"comment": null
								}
							]
						},
						{
							"type": "header",
							"name": "Object's mesh's Z vertices",
							"size": "2",
							"size type": "byte",
							"offset": "Relative pointer to Z vertices",
							"repeats": "Number of vertices",
							"condition": true,
							"content": [
								{
									"type": "data",
									"name": "Mesh's vertex Z coordinate",
									"size": 2,
									"size type": "byte",
									"value type": "signed integer",
									"comment": null
								}
							]
						},
						{
							"type": "header",
							"name": "Object's mesh's normals",
							"size": "2",
							"size type": "byte",
							"offset": "Relative pointer to normals",
							"repeats": "Number of normals",
							"condition": true,
							"content": [
								{
									"type": "data",
									"name": "Mesh's normal vertex I coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "signed integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Mesh's normal vertex J coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "signed integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Mesh's normal vertex K coordinate",
									"size": 1,
									"size type": "byte",
									"value type": "signed integer",
									"comment": null
								},
								{
									"type": "data",
									"name": "Number of time used?",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								}
							]
						},
						{
							"type": "header",
							"name": "Object's mesh's unknown",
							"size": "1",
							"size type": "byte",
							"offset": "Relative pointer to unknown",
							"repeats": "Number of unknown",
							"condition": true,
							"content": [
								{
									"type": "data",
									"name": "Unknown index?",
									"size": 1,
									"size type": "byte",
									"value type": "unsigned integer",
									"comment": null
								}
							]
						}
					]
				}
			]
		}
	]
}
```


These are the same file but in different styles. The first one was the first, and I didn't knew what I was doing. The second is the most readable. At least to me. But it is hard to write in this style. When I experimented with JSON formating. Maybe it is better for programs to read in JSON format if I need it anytime.

When I searched the internet for example. These are the most common:
[http://wiki.xentax.com/index.php/Silent ... mories_ARC](http://wiki.xentax.com/index.php/Silent_Hill:_Shattered_Memories_ARC)
[http://wiki.xentax.com/index.php/Silent_Hill_3_ARC](http://wiki.xentax.com/index.php/Silent_Hill_3_ARC)
They look simple to write and understand.

Then I found quickBMS and it's a scripting language. These scripts look very easy to write, look compact but hard to read as file documentation because it's not it's purpose.

My question is, do you have any tips for documentation style formatting? I want it to be as universal as possible (maybe there are some standards?), and if possible to look like a programming language, because I would like to parse it to Python for other stuff (like reprinting it for more readable styles).

Thanks for your answers, and sorry, if this question looks dumb - I am quite noob to this stuff.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-13T08:10:34+00:00
- Post Title: File format documentation... format

This style from Silent Hill Shattered Memories ARC is mine   
I write articles on Wiki or Github in this style, so I could definitely recommend you to use this, 
because is super easy to write and understand as you said in your post.


This second style from SH 3 ARC article on wiki is WATTO's style.
He was adding those articles in 2005. It looks nice, but you need to use a lot of HTML tags in this style.


As for tips, it's always good to:
- use types (like uint32 etc.)
- use number of bytes
- make comments + put some examples in comments
- always write notes and comments if you have any
- use structures if they are present
- always tell if it is little endian or big endian

As for code, in my opinion it's always good to have real code
than pseudocode, so you can link to some Python examples
in your documentation.


Good use of comments you can see here where I have listed
all available values for all fields [http://wiki.xentax.com/index.php/Overboard!_Save_File](http://wiki.xentax.com/index.php/Overboard!_Save_File)
## Post #3
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2020-11-14T12:14:06+00:00
- Post Title: File format documentation... format

Thanks for the tips!
How would you describe individual bits? Let's say we have some flags in 8bits or 565 RGB? Would you describe MSB or LSB first? Or do you do it differently?
How about doing it like this:

```
0000 0100 - render flag
1100 0000 - model flag
```
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-14T13:33:56+00:00
- Post Title: File format documentation... format

I would start with MSB and describe it like this:

```
               // bit 2 - flag2
               // etc.

```


But your idea seems to be ok.
## Post #5
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2020-11-14T22:50:04+00:00
- Post Title: File format documentation... format

I don't think that

```
               // bit 2 - flag2
               // etc.
```

is a good idea, because, how to you describe if there are several bits per data? like RGB565, or RGB1555? Maybe this is better?

```
                // 6 bits - green
                // 5 bits - blue
```

To tell not wich bit, but how many? Or just simply do the other way, as you said:

```
00000111 11100000 - green
00000000 00011111 - blue
```
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-14T23:03:38+00:00
- Post Title: File format documentation... format

> like RGB565, or RGB1555? Maybe this is better?
Yeah, I meant exactly that what you said. I have just described the situation where you have one flag per one bit.
Just remember when you describe RGB565 value then you have 2 bytes of data (16 bits), not 1 byte.

> Or just simply do the other way, as you said:
This is also fine for me.


You can also leave it like this:

```
2 bytes - RGB565
```

if it is something common like RGB value.
## Post #7
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2020-11-14T23:07:53+00:00
- Post Title: File format documentation... format

> Reply from ikskoks ↑Sun Nov 15, 2020 7:03 am at Sun Nov 15, 2020 7:03 am
>
> 
Just remember when you describe RGB565 value then you have 2 bytes of data (16 bits), not 1 byte.
Oh yeah, sorry!
