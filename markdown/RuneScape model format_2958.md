## Post #1
- Username: triton
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Mar 05, 2007 10:41 am
- Post datetime: 2008-03-02T20:02:43+00:00
- Post Title: RuneScape model format

I guess this one is easy but I have no experience with 3D models.

If someone could help, I would be grateful. 
[newcache.zip](https://xentaxbackup.github.io/file/1469_newcache.zip)
## Post #2
- Username: triton
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Mar 05, 2007 10:41 am
- Post datetime: 2008-04-16T18:17:53+00:00
- Post Title: RuneScape model format

Already figured out, thanks to those who gave it a look anyway.
## Post #3
- Username: kzap
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 11, 2008 5:31 pm
- Post datetime: 2009-05-01T14:33:57+00:00
- Post Title: RuneScape model format

question is how did you extract these models?
## Post #4
- Username: triton
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Mar 05, 2007 10:41 am
- Post datetime: 2009-05-02T01:36:30+00:00
- Post Title: RuneScape model format

Coincidentally, I found some documents about the RuneScape models today. I haven't touched this stuff in a big while. 

These were not written by me. At the time I managed to extract some stuff, but this seems much more detailed and accurate.

Sorry, it's a little big.  



> The following document is written by a 'Mr Potato Head', I claim no ownership.
>
> 
>
> 
>
> 
>
> 
>
> File format specification for old format (pre 474) - still used
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> VERTEX_DIRECTION_Chunk : Bytes; Number of verices in length.
>
> 
>
> This chunk contains Vertex direction data, the data contained in each byte is a set Bit of Flags. Only the first 3 bits are used. 
>
> Each Flag determines whether an addition is made to the x,y, or z axis when calculating the next vertex point. 
>
> Example: The start point is always 0,0,0, so if the first vertex is at point 10,10,10 then the All the Flags will be set and the byte value = 7. 
>
> 
>
> ALWAYS Required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> TRIANGLE_TYPE_Chunk : Bytes; Number of triangles in length.
>
> 
>
> This chunk contains Triangle type data, the data is an integer Flag, of value 1-4, used to control how Triangles vertex numbers are loaded. 
>
> Type_1 = New Triangle. Load v1, v2 and v3.
>
> Type_2 = v2=v3, load v3, v1=v1
>
> Type_3 = v1=v3, load v3, v2=v2
>
> Type_4 = v1=v2, v2=v1, load v3
>
> 
>
> NOTE: Type_4 is rare, Type_1 can be used to replace type 4 with only a small loss in compression. 
>
> 
>
> Type_4 can only exist in 2 instances, 
>
> a) when a new triangle is loaded and the next triangle type is of type_4. 
>
> b) when the normal of the next triangle is inverted.
>
> Otherwise the vast majority of triangles will be of type_2 and type_3
>
> 
>
> ALWAYS Required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> TRIANGLE_PRIORITY_Chunk : Bytes; Number of triangles in length.
>
> 
>
> This chunk contains integer values used to calculate which triangles are drawn first, The higher the value the later they are drawn.
>
> 
>
> Used only when triangle priority is required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> TRIANGLE_SKIN_Chunk : Bytes; Number of triangles in length.
>
> 
>
> This chunk contains integer values that are applied to triangles in order to display animation data. The value represents the group the triangle belongs to.
>
> 
>
> Used only when animation is required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> TEXTURE_POINTER_Chunk : Bytes; Number of triangles in length.
>
> 
>
> This chunk contains integer values that point to which texture mapping triangle is used to texture the model triangle. 
>
> A Value of 0 represents NO texture mapping.
>
> 
>
> Used only when texture mapping is required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> VERTEX_SKIN : Bytes; Number of vertices in length.
>
> 
>
> This chumck contains integer values that describe which vertex skin group a vertex belongs to.
>
> 
>
> Used only when animation is required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> TRIANGLE_ALPHA_Chunk : Bytes; Number of Triangles in length
>
> 
>
> This chunk conatins integer values that are used to determine how transparent the model triangle is. 
>
> 
>
> Used only when transparency is required.
>
> 
>
> -----------------------------------------------------------------------
>
> TRIANGLE_DATA_CHUNK : Bytes and/or Words; Length is Triangle_Data Length.
>
> 
>
> This chunk contains signed bytes and words that are used to calculate which vertices are used to describe the triangle. The value has an offset of 64 to determine wether the value is stored as a byte or a word. A base value of 0 is used. The values are stored as offsets to the next vertex.
>
> Example: the model starts with a triangle that uses vertices 2,3,4. 
>
> The offsets from the base value will be +2,+1,+1 
>
> This will be stored as 66,65,65 (or in Hex 42,41,41)
>
> 
>
> ALWAYS Required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> COLOR_DATA_Chunk : Words; Number of triangles in length.
>
> 
>
> This chunk contains integer values that describe which color, from the 65,536 color lookuptable, is used for the model triangle.
>
> 
>
> ALWAYS Required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> UV_MAP_TRIANGLES_Chunk : Word,Word,Word; Number of texture triangles in length.
>
> 
>
> This chunk contains the positions of the UV(0,0), UV(0,1) and UV(1,0) information required to calculate the UV coordinates for textured model triangles. The 'texture triangle' represents the flat mapped texture which the model triangles are projected onto to produce the UV coordinates.
>
> 
>
> Used only when texture mapping is required. 
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> X_DATA_Chunk : Byte and/or Word; XdataLength in length
>
> 
>
> This chunk contains signed bytes or words, used to calculate the X value for the vertex position. A base offset of 0 is used and the number stored is the offset from one vertex position to the next.
>
> An offset of 64 is also applied to the data to determine if the value is stored as a byte or a word.
>
> 
>
> ALWAYS Required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> Y_DATA_Chunk : Byte and/or Word; YdataLength in length
>
> 
>
> This chunk contains signed bytes or words, used to calculate the Y value for the vertex position. A base offset of 0 is used and the number stored is the offset from one vertex position to the next.
>
> An offset of 64 is also applied to the data to determine if the value is stored as a byte or a word.
>
> 
>
> ALWAYS Required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> Z_DATA_Chunk : Byte and/or Word; ZdataLength in length
>
> 
>
> This chunk contains signed bytes or words, used to calculate the Z value for the vertex position. A base offset of 0 is used and the number stored is the offset from one vertex position to the next.
>
> An offset of 64 is also applied to the data to determine if the value is stored as a byte or a word.
>
> 
>
> ALWAYS Required.
>
> 
>
> -----------------------------------------------------------------------
>
> 
>
> FILE_FOOTER_Chunk : Bytes and Words; Length is 18 bytes.
>
> 
>
> This chunk contains the data lengths and data flags used to store the file.
>
> 
>
> Word - Number of vertices
>
> Word - Number of triangles
>
> Byte - Number of Texture triangles
>
> Byte - Use textures FLAG
>
> Byte - Use Triangle Priorities FLAG (FF for True)
>
> Byte - Use Transparency FLAG
>
> Byte - Use Triangle Skinning FLAG
>
> Byte - Use Vertex Skinning FLAG
>
> Word - X_DATA length
>
> Word - Y_DATA length
>
> Word - Z_DATA length
>
> Word - Triangle_Data length
>
> 
>
> ALWAYS Required.
