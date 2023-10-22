## Post #1
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-03-28T19:09:54+00:00
- Post Title: Automation:Car maker Tycoon

I recently bought the game and was rooting around in the file system when I found the files for the cars. I looked it up through google and it has no idea what file format this is.
The sample below should have the 3d mesh for a car. any help on how to open this and how to convert this would be greatly appreciated.

[http://www.mediafire.com/file/p7m3t48hq ... Sedan2.zip](http://www.mediafire.com/file/p7m3t48hqjnp1i4/60Sedan2.zip)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-29T07:29:39+00:00
- Post Title: Automation:Car maker Tycoon

Very interesting format:

```
Byte		StringLength(Unicode)
String 	Name(null-terminated)
Long		Unknown

Long	vertexCount
for i = 0 < vertexCount
{
	Long	vPosition x
	Long	vPosition y
	Long	vPosition z
	Long	vNormal x
	Long	vNormal y
	Long	vNormal z
	Long	vTangent x
	Long	vTangent y
	Long	vTangent z
	Long	U
	Long	V
	Byte	BoneCount
	for j = 0 < BoneCount
	{
		Byte	BoneIdx
	}
	for j = 0 < BoneCount
	{
		float	BoneWeight
	}
	Long	Marker(0x15FFFFFF)
}

Long		SubmeshCount
for i = 0 < SubmeshCount
{
	Long	IndicesCount
	for j = 0 < IndicesCount
	{
		Long	Index[j]
	}
	Byte		StringLength(Unicode)
	String 	TextureName(null-terminated)
	Byte		Null
	Byte		StringLength2(Unicode)
	
	if(StringLength2 != 0)
	{
		String 	TextureName(null-terminated)
	}
	
}

for i = 0 < SubmeshCount
{
	Bones
	{
		float[4]	Rotations?
		float[3]	Translations?
		float[3]	Scales?
	
		Byte		StringLength(Unicode)
		String 	BoneName(null-terminated)
		Byte		0xFF
	}
}

```


However there's no way to validate the mesh structure via Hex2Obj so it's just the result of my simple research. But it's not difficult to write a convertor though.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-29T12:19:46+00:00
- Post Title: Automation:Car maker Tycoon

Alright, exactly as I expected:



Here a simple obj convertor for the kjc model files:


 kjcConvertor.rar
(57.59 KiB) Downloaded 18 times


Just drag and drop a kjc file on it and you'll get the converted obj file in the same folder. If you want to convert mutiple files, use batch command instead.

Didn't swap UVs as I don't know if they would match the textures or not.
## Post #4
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-03-29T22:58:16+00:00
- Post Title: Automation:Car maker Tycoon

> Reply from Bigchillghost
>
> Alright, exactly as I expected:



Here a simple obj convertor for the kjc model files:
kjcConvertor.rar
Just drag and drop a kjc file on it and you'll get the converted obj file in the same folder. If you want to convert mutiple files, use batch command instead.

Didn't swap UVs as I don't know if they would match the textures or not.

Thank you so much for the conversion this is mainly what I needed. I appreciate your hard work.
