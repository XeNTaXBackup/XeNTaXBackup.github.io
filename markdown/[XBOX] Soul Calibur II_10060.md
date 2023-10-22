## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-01-19T22:32:00+00:00
- Post Title: [XBOX] Soul Calibur II

I'm having an issue with scale, the armor, main mesh, and skeleton are all off from each other 

anyone interested in helping? I attached my maxscript below and also typed up structs if that makes the format clearer to understand




 VMXthingyv02.zip
(5.88 KiB) Downloaded 116 times



You'll Also need OLK Explorer to Extract Files from SC2. Find root.olk and open it in OLKExplorer, and expand File5. Expand any PKG to look for VMX files. VMX are the model files
I've uploaded the tool here
[http://www.gamefront.com/files/22865640 ... 283%29.zip](http://www.gamefront.com/files/22865640/olkexplorer+%283%29.zip)

> Reply from mariokart64n
>
> 
VMX Format:
-(Xbox)Little Endian, (Gamecube)Big Endian
-All Values Unsigned, unless otherwise noted

VMX_Header {
LONG magic 		// "VMX.","VMG"
BYTE version 		// 0x02=Xbox?, 0x03=Gamecube, 0x04=Xbox
BYTE ukn01		// usually 0
BYTE ukn02		// ? usually 0x0D
BYTE ukn03		// usually 0
BYTE ukn04		// usually 0
BYTE contents		// 0x00=Stage, 0x01=Character, 0x02=Weapon
SHORT num_of_matrices
SHORT num_of_objects1
SHORT num_of_objects2
SHORT num_of_objects3
SHORT num_of_bones
SHORT num_of_materials
SHORT num_of_meshes	// always 1?
LONG vtx_data_offset
LONG material_offset
LONG texture_table_offset
LONG matrix_table_offset
LONG ukn01_offset
LONG layer1_Object_Entry_offset
LONG layer2_Object_Entry_offset
LONG layer3_Object_Entry_offset
LONG weight_table_offset
LONG ukn02_offset
LONG bone_offset
LONG name_offset
LONG ukn03_offset
}


layer_Object_Entry {
SHORT object_type		// 0x00=Static, 0x04=Skinned
SHORT primitive_type		// 0x00=TriangleStrip, 0x01=TriangleList
LONG num_of_faces
LONG mtx_offset
LONG mat_offset
LONG face_offset
LONG buffer1_offset		// for skinned meshes this is the vertex buffer
LONG buffer2_offset
LONG buffer3_offset
LONG buffer4_offset
LONG unk1			// "Aman" describes this section as "Center+Radius Offset"
}

texture_table {
SHORT type		// 0x01=Diffuse, 0x02=Effects, 0x03=Animating, 0x04=?, 0x05=SpecBall
SHORT size		// size of entry?
FLOAT32 u_tile
FLOAT32 v_tile
FLOAT32 ukn01
FLOAT32 ukn02
FLOAT32 ukn03
FLOAT32 ukn04
FLOAT32 ukn05
FLOAT32 ukn06
FLOAT32 ukn07
}

weight_table {
LONG vert_count1		// number of vertices with 1 bone weight per vertex
LONG vert_count2		// number of vertices with 2 bone weight per vertex
LONG vert_count3		// number of vertices with 3 bone weight per vertex
LONG vert_count4		// number of vertices with 4 bone weight per vertex
LONG weight_buffer_offset	// weight buffer, also contains vertices and normals
LONG vertex_buffer1_offset	// Vertex Buffer
LONG vertex_buffer2_offset	// Vertex Buffer2, Redundant?
}

ukn01 {				// data Present in stage files? boundaries?
SHORT unk1
SHORT matrix2_count
SHORT matrix2_offset		// if count is 0, then this will point to the material block
}

matrix {			// entry stride is 400bytes
SHORT ukn1
SHORT bone_index		// parent object to this bone?
SHORT ukn2
LONG ukn3			// on stages files an offset is present
LONG ukn4
LONG ukn5
MATRIX4X4 object_transform
BYTE[80] whitespace		// ? why soo much white space
}

material_table {
BYTE type
BYTE ukn1
BYTE ukn2
BYTE cull_mode			// 0x00=DrawnBothSides, 0x08=DrawnOneSide
LONG opacity_source		//
LONG vtx_offset1
LONG vtx_offset2
LONG vtx_offset3
LONG map1_table_offset
LONG map2_table_offset
LONG map3_table_offset
FLOAT32 col01R			// colour, Red Channel
FLOAT32 col01G			// colour, Green Channel
FLOAT32 col01B			// colour, Blue Channel
FLOAT32 col01A			// colour, Alpha Channel
FLOAT32 col02R			// colour, Red Channel
FLOAT32 col02G			// colour, Green Channel
FLOAT32 col02B			// colour, Blue Channel
FLOAT32 col02A			// colour, Alpha Channel
FLOAT32 col03R			// colour, Red Channel
FLOAT32 col03G			// colour, Green Channel
FLOAT32 col03B			// colour, Blue Channel
FLOAT32 col03A			// colour, Alpha Channel
}

bone_info { 			// bone positions relative to its parent
FLOAT32 x_child_position
FLOAT32 y_child_position
FLOAT32 z_child_position
FLOAT32 xyz_child_scale
FLOAT32 x_position
FLOAT32 y_position
FLOAT32 a_position
FLOAT32 xyz_scale
FLOAT32 x_rotation // eulerangles, degrees (n*360)
FLOAT32 y_rotation
FLOAT32 z_rotation
FLOAT32 ukn01
FLOAT32 ukn02
FLOAT32 ukn03
FLOAT32 ukn04
BYTE ukn05
BYTE bone_parent
BYTE bone_index // used for name look up?
BYTE ukn06
}

name_table {
STRING name
}

VTX_header {}

vert_def {
FLOAT32 x_position
FLOAT32 y_position
FLOAT32 z_position
FLOAT32 xyz_scale
FLOAT32 x_normal
FLOAT32 y_normal
FLOAT32 z_normal
FLOAT32 xyz_nscale
}

tvert_def {
BYTE V_colourR			// divide 255 to get float
BYTE V_colourG
BYTE V_colourB
BYTE V_colourA
FLOAT32 U_coordinate
FLOAT32 V_coordinate
}

weight_def {
FLOAT32 x_position		// positions relative to assigned bone
FLOAT32 y_position
FLOAT32 z_position
FLOAT32 bone_weight
FLOAT32 x_normal
FLOAT32 y_normal
FLOAT32 z_normal
LONG bone_index
}

face_def {
SHORT face_index
}

EDIT1
Added support for the gamecube files aswell. the file structure is the same, except for the vertices and faces.
the object entries are larger now, because they define extra buffers. in the xbox they use one buffer to store positions and normals. 
in the GC format, they are storing positions to one buffer, and normals to a second buffer.... the weight buffer is also different, instead of using 32bit floats, they switched to 16bit floats.

and of course the face format, follows the typical gamecube spec using packed strip flags [0x98,0x90, ... etc]

expanding support to GC, may open more doors in solving the remaining unknowns I hope..



EDIT2
the bones are not expressed as matrices.. which I found odd. But figured hey, maybe they didnt need it.
but later in the file they do store matrices, referenced to by the various armor

I wrote over this area with zero's tonight only to find no change in armor positions O_o
I also overwrote the vertex buffer, actually buffers 1 to 4... which contained carious vertex components.

Oddly none of this seemed to affect the model when loaded

there is however index info with the matrices, which from my test overrides the given matrix. 
So ingame the object will take the matrix of a bone, instead of from the matrix for that object

in this test below, I relinked the main mesh to bone "0" resulting in the model going horizontal off the from of the models idle pose..
proving that all the vertex buffers and the matrix data gets ignore. and that everything is being assigned around the given skeleton
