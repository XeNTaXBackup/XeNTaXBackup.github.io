## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:19:45+00:00
- Post Title: Writing an Obj Convertor in C

Attention: This topic is subject to the Programming Section under the tutorial An Imitable Workflow for Reverse Engineering A Game Model.

Part III. Writing an Obj Convertor in C

In this part I'll demonstrate you how to write a simple obj convertor in C (using C11 function models) for the nif files from Marvel Avengers: Battle for Earth.
Note that this tutorial won't explain you every detail about C syntax. It is assumed that you knew the basis of C programming and how to compile the code.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:24:58+00:00
- Post Title: Writing an Obj Convertor in C

About OBJ format:

Obj is a simple, flexible ascii 3D format. In an obj file, different elements are distinguished by an unique tag, where position is marked as 'v', UV as "vt", normals as "vn", face as 'f'. And comment starts with a '#'.

Every member of every element carries a corresponding tag. Below is an example template.

```
v  1.000000 0.000000 0.000000
v  0.000000 1.000000 0.000000
v  0.000000 0.000000 1.000000

# normals
vn 0.577350 0.577350 0.577350
vn 0.577350 0.577350 0.577350
vn 0.577350 0.577350 0.577350

# UVs
vt 1.000000 0.000000 0.000000
vt 0.000000 1.000000 0.000000
vt 0.000000 0.000000 1.000000 

# faces
f 1/1/1 2/2/2 3/3/3 

```

A triangle is defined by 3 vertex/texture/normal indices. Indices of the same vertex are separated by a '/'.
If you want more details about the format, check the wiki [here](https://en.wikipedia.org/wiki/Wavefront_.obj_file).
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:34:50+00:00
- Post Title: Writing an Obj Convertor in C

Start coding:

There're still some preparation to be done. Our PC uses little-endian for storage of data so we need a small function for conversion of endianness. Besides, we need a half-float to float/double convertion for vertices since half-float is not a basic data type in C.

Now let's solve the problems one by one.

I. Endianness Conversion

```
#include <stdio.h>
#include <Windows.h>
#include <stdlib.h>

/* Function Prototypes & Declarations */
void EndianBigRead(void*  _Buffer, size_t _BufferSize, 
	size_t _ElementSize, size_t _ElementCount, FILE*  _Stream); // The fread_s() function for big-endian
void Swap16(WORD *value); // Swap 16 bit integers
void Swap32(ULONG32 *value); // Swap 32 bit integers

/* Function Definitions */
void EndianBigRead(void*  _Buffer, size_t _BufferSize, size_t _ElementSize, size_t _ElementCount, FILE*  _Stream)
{
	fread_s(_Buffer, _BufferSize, _ElementSize, _ElementCount, _Stream);
	switch (_ElementSize)
	{
	case 2:
		WORD *pWORD; 
		pWORD = (WORD *)_Buffer; 
		for (ULONG32 i = 0; i < _ElementCount; i++)
			Swap16(pWORD + i); 
		break;
	case 4:
		ULONG32 *pLONG; 
		pLONG = (ULONG32 *)_Buffer;
		for (ULONG32 i = 0; i < _ElementCount; i++)
			Swap32(pLONG + i);
		break;
	default: break;
	}
}

void Swap16(WORD *value)
{
	*value = (*value & 0x00FFU) << 8 | (*value & 0xFF00U) >> 8;
}

void Swap32(ULONG32 *value)
{
	*value = (*value & 0x000000FFU) << 24 | (*value & 0x0000FF00U) << 8 |
		(*value & 0x00FF0000U) >> 8 | (*value & 0xFF000000U) >> 24;
}

```

You don't have to take care of the details within these funtions. Just remember that EndianBigRead() has no difference in usage from the fread_s() function.
Now save this piece of code into a .c file called "BigEndian.c" for later use.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:37:29+00:00
- Post Title: Writing an Obj Convertor in C

II. half-float Conversion

We don't care about the details of how half-float is implemented, so we just introduce a third party library for half-float conversion:
[C source code to convert between IEEE double, single, and half precision](http://www.mathworks.com/matlabcentral/fileexchange/23173).

We'll need only the "ieeehalfprecision.c" within.

Two functions we could use:

```
int halfp2doubles(void *target, void *source, int numel); // convert half-floats to doubles

```
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:42:52+00:00
- Post Title: Writing an Obj Convertor in C

For convenience of demonstration, I'll put here the structure of the nif model format:

```
long	NULL
long	SubmeshCount
for i = 0 < SubmeshCount
{
	long	FIstartIndex[i]
	long	FIcount[i]
}

long 	MarkerCount	// 0x00000001
long 	FaceMarker		// 0x00010215
short	FaceIndices[]
byte 	aByte

long	TotalVertexSize
long	NULL
long	SubmeshCount
for i = 0 < SubmeshCount
{
	long	VertexStartIndex[i]
	long	VertexCount[i]
}

long	FVFcodeCount
if (FVFcodeCount == 5)
{
	long	FVFcode[5]
	for i = 0 < SubmeshCount
	{
		for j = 0 < VertexCount[i]
		{
			half-float		vPosition[3]
			short  			0x3C00
			half-float		vNormal[3]
			short  			0x3C00
			half-float		vBinormal[3]
			short  			0x3C00
			half-float		vTangent[3]
			short  			0x3C00
			half-float		vTexcoord[2]
		}
	}
}
else if (FVFcodeCount == 7)
{
	long	FVFcode[7]
	for i = 0 < SubmeshCount
	{
		for j = 0 < VertexCount[i]
		{
			half-float		vTexcoord[2]
			half-float		vPosition[3]
			short  			0x3C00
			half-float		vNormal[3]
			short  			0x3C00
			half-float		vBinormal[3]
			short  			0x3C00
			half-float		vTangent[3]
			short  			0x3C00
			byte				BlendIndices[4]
			short  			0x3C00
			byte				BlendWeights[4]
			short  			0x3C00
		}
	}
}

```


The above structure is a template for all mesh groups, and there would be at least one mesh group in a nif archive, usually more.
So we need to figure out how to locate to the next mesh group. 

Since we didn't research the whole file structure, we will use the Marker for face buffer(00 01 02 15) to locate to next mesh group.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:44:31+00:00
- Post Title: Writing an Obj Convertor in C

You need to be clear about the main steps of extracting all models:
1. Locate to a submesh group. In this case we'll search for the FI marker 00 01 02 15;
2. Call the function to convert the submesh group we located;
3. Repeat the above process untill we reach the end of file.

For the function to handle each mesh group, the main steps are as following:
1. Read the FI header;
2. Read FI to buffer;
3. Read the vertices header;
4. Read vertices to buffer;
5. Process and rearrange the data;
6. Writting the data to an obj file.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:46:40+00:00
- Post Title: Writing an Obj Convertor in C

Now we do it upward, starting from the implement of this function. Below is an implement with detailed comments.

Some formatting about the comments in the codes:
/*--*/ Comment for the following block
/**/ Comment for the following structure
// Comment for current line

```
{
	ULONG32 FIsize, FIsum;					// FI data size, total FI count
	ULONG32 SubmeshNum;					   // Submesh count for current mesh group
	ULONG32 Vsize, Vsum;					 // Vertex data size, total vertex count
	ULONG32 FIord = 1;						// Accumulated FI order, start by 1 in obj format
	ULONG32 FVFcodeCount;					// FVFcode field count
	ULONG32 *FIcount, *Vcount;				// Pointers(PTR) to count array
	WORD *pFtmp;							// Temp PTR to face buffer
	WORD *pFIbuf, *pVbuf, *pUVbuf, *pNMbuf;	// PTRs to source face, position, UV and normal buffers
	float *pfVbuf, *pfUVbuf, *pfNMbuf;		// PTRs to destination position, UV and normal buffers
	float *pfVtmp, *pfUVtmp, *pfNMtmp;		// Temp PTRs to destination position, UV and normal buffers
	FILE *fpOBJ;							// File PTR to output obj file
	char OBJName[256] = { 0 };				// String buffer for output obj filename

	EndianBigRead(&FIsize, 4, 4, 1, fpXPR);			// Read TotalFIsize
	fseek(fpXPR, 4L, SEEK_CUR);						// Skip the NULL field
	EndianBigRead(&SubmeshNum, 4, 4, 1, fpXPR);		// Read SubmeshCount

	FIcount = (ULONG32 *)malloc(4 * SubmeshNum);	// Allocate memory for storing FI counts
	Vcount = (ULONG32 *)malloc(4 * SubmeshNum);		// Allocate memory for storing vertex counts
	pFIbuf = (WORD *)malloc(FIsize);				// Allocate memory for storing FI
	pFtmp = pFIbuf;									// Assign FI buffer pointer(PTR) to temporary PTR

	/* Read each face indices count */
	for (BYTE i = 0; i < SubmeshNum; i++)
	{
		fseek(fpXPR, 4L, SEEK_CUR);					// Skip FIstartIndex since we don't ever need it
		EndianBigRead(FIcount + i, 4, 4, 1, fpXPR);	// Read face indices count
	}

	fseek(fpXPR, 8L, SEEK_CUR);						// Skip the MarkerCount and the FaceMarker 00 01 02 15 sequence
	
	FIsum = FIsize / 2;								// FIsum == FI chunk size / sizeof(WORD)
	EndianBigRead(pFIbuf, FIsize, 2, FIsum, fpXPR);	// Read face indices
	
	fseek(fpXPR, 1L, SEEK_CUR);						// Skip aByte
	EndianBigRead(&Vsize, 4, 4, 1, fpXPR);			// Read TotalVertexSize

	fseek(fpXPR, 8L, SEEK_CUR);						// Skip 2 LONGs(a NULL and a SubmeshCount)
	
	/* Read vertex counts */
	for (BYTE i = 0; i < SubmeshNum; i++)			
	{
		fseek(fpXPR, 4L, SEEK_CUR);					// Skip VertexStartIndex since we don't ever need it
		EndianBigRead(Vcount + i, 4, 4, 1, fpXPR);	// Read vertex count
	}
	EndianBigRead(&FVFcodeCount, 4, 4, 1, fpXPR);	// Read FVFcodeCount 
	fseek(fpXPR, FVFcodeCount * 4, SEEK_CUR);		// Skip FVFCodes
	
	if (FVFcodeCount == 7)
		Vsum = Vsize / 48;							// FVF size == 48
	else if (FVFcodeCount == 5)
		Vsum = Vsize / 36;							// FVF size == 36
	else
		return 1;									// In case there're other types

	pVbuf = (WORD *)malloc(Vsum * 6);			// Allocate memory for storing vertex positions(source)
	pUVbuf = (WORD *)malloc(Vsum * 4);			// Allocate memory for storing vertex texture positions(source)
	pNMbuf = (WORD *)malloc(Vsum * 6);			// Allocate memory for storing vertex normal vectors(source)
	pfVbuf = (float *)malloc(Vsum * 12);		// Allocate memory for storing vertex positions(destination)
	pfUVbuf = (float *)malloc(Vsum * 8);		// Allocate memory for storing vertex texture positions(destination)
	pfNMbuf = (float *)malloc(Vsum * 12);		// Allocate memory for storing vertex normal vectors(destination)
	pfVtmp = pfVbuf;							// Temporary PTR to vertex buffer
	pfUVtmp = pfUVbuf;							// Temporary PTR to UV buffer
	pfNMtmp = pfNMbuf;							// Temporary PTR to normal buffer
	
	/* Read vertex data */
	if (FVFcodeCount == 7)
	{
		for (ULONG32 j = 0; j < Vsum; j++)
		{
			EndianBigRead(pUVbuf + 2 * j, 4, 2, 2, fpXPR);	// Read UV
			EndianBigRead(pVbuf + 3 * j, 6, 2, 3, fpXPR);	// Read position
			fseek(fpXPR, 0x2, SEEK_CUR);					// Skip 3C 00
			EndianBigRead(pNMbuf + 3 * j, 6, 2, 3, fpXPR);	// Read normals
			fseek(fpXPR, 0x1E, SEEK_CUR);					// Skip rest bytes
		}
	}
	else if (FVFcodeCount == 5)
	{
		for (ULONG32 j = 0; j < Vsum; j++)
		{
			EndianBigRead(pVbuf + 3 * j, 6, 2, 3, fpXPR);	// Read position
			fseek(fpXPR, 0x2, SEEK_CUR);					// Skip 3C 00
			EndianBigRead(pNMbuf + 3 * j, 6, 2, 3, fpXPR);	// Read normals
			fseek(fpXPR, 0x12, SEEK_CUR);					// Skip bionormals, tangents and 3x 3C 00
			EndianBigRead(pUVbuf + 2 * j, 4, 2, 2, fpXPR);	// Read UV
		}
	}
	else
		return 1;	// Just in case

	/* Convert half-float to float */
	halfp2singles(pfVbuf, pVbuf, Vsum * 3);		// Positions
	halfp2singles(pfUVbuf, pUVbuf, Vsum * 2);	// UVs
	halfp2singles(pfNMbuf, pNMbuf, Vsum * 3);	// Normals
	
	/* Free allocated memories */
	free(pVbuf);	// Free vertex buffer
	free(pUVbuf);	// Free UV buffer
	free(pNMbuf);	// Free normal buffer
	
	/* Flip UV */
	for (ULONG32 v = 0; v < Vsum; v++)
		pfUVbuf[v * 2 + 1] = 1.0f - pfUVbuf[v * 2 + 1];	// Flip the v asix

	/* --- Write data to file --- */
	strcpy_s(OBJName, 256, MeshName);					// Copy MeshName to OBJName
	strcat_s(OBJName, 256, ".obj");						// OBJName + ".obj" extension
	if (fopen_s(&fpOBJ, OBJName, "w") != 0)				// Security check
	{
		printf("error! cannot open file %s!\n", OBJName);
		exit(1);
	}
	printf("writting file \"%s\"...\n", OBJName);		// Print status message
	/* Write data to obj file */
	for (BYTE i = 0; i < SubmeshNum; i++)
	{

		fprintf_s(fpOBJ, "#\n# object %s_%d\n#\n\n", MeshName, i);	// File comments

		/* Write vertex positions */
		for (ULONG32 j = 0; j < Vcount[i]; j++)
		{
			fprintf_s(fpOBJ, "v  %f %f %f\n", pfVtmp[0], pfVtmp[1], pfVtmp[2]); // Print positions as floats
			pfVtmp += 3;														// Temp PTR move forwards 3 units
		}
		fprintf_s(fpOBJ, "# %d vertices\n\n", Vcount[i]);						// Comment for vertex count

		/* Write vertex normals */
		for (ULONG32 j = 0; j < Vcount[i]; j++)
		{
			fprintf_s(fpOBJ, "vn %f %f %f\n", pfNMtmp[0], pfNMtmp[1], pfNMtmp[2]);	// Print normals as floats
			pfNMtmp += 3;															// Temp PTR move forwards 3 units
		}
		fprintf_s(fpOBJ, "# %d vertex normals\n\n", Vcount[i]);						// Comment for vertex normal count

		/* Write vertex UVs */
		for (ULONG32 j = 0; j < Vcount[i]; j++)
		{
			fprintf_s(fpOBJ, "vt %f %f\n", pfUVtmp[0], pfUVtmp[1]);	// Print UVs as floats
			pfUVtmp += 2;											// Temp PTR move forwards 2 units
		}
		fprintf_s(fpOBJ, "# %d texture coords\n\n", Vcount[i]);		// Comment for UV count

		/* Write polygon indices */
		fprintf_s(fpOBJ, "g %s_mesh_%d\n", MeshName, i);	// Print object name
		FIcount[i] /= 3;									// Calculate polygon count
		for (ULONG32 j = 0; j < FIcount[i]; j++)
		{
			fprintf_s(fpOBJ, "f %d/%d/%d %d/%d/%d %d/%d/%d \n",
				pFtmp[0] + FIord, pFtmp[0] + FIord, pFtmp[0] + FIord,	// v/vt/vn
				pFtmp[1] + FIord, pFtmp[1] + FIord, pFtmp[1] + FIord,
				pFtmp[2] + FIord, pFtmp[2] + FIord, pFtmp[2] + FIord);  // Print polygone indices
			pFtmp += 3;													// Temp PTR move forwards 3 units
		}
		fprintf_s(fpOBJ, "# %d polygons\n\n", FIcount[i]);				// Comment for polygon count

		FIord += Vcount[i];												// Accumulate current vertex count in FIord
	}

	fclose(fpOBJ);			// Close output file
	printf("succeed!\n");	// Print status message

	/* Free allocated memories */
	free(FIcount);	// Free FIcount array
	free(Vcount);	// Free Vcount array
	free(pFIbuf); 	// Free FI buffer
	free(pfVbuf); 	// Free destination vertex buffer
	free(pfUVbuf); 	// Free destination UV buffer
	free(pfNMbuf); 	// Free destination normal buffer

	return 0;
}

```
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:48:54+00:00
- Post Title: Writing an Obj Convertor in C

When that is done we can call it in the main() function when we find a mesh group:

```
{
	FILE *fpXPR;	// Pointer to XPR file
	WORD m = 0;		// Counter for FileID
	ULONG32 filesize; // Searching scope
	ULONG32 MAGIC;	// Marker
	BYTE Flag = 0; // Flag to skip useless SFX element meshes	
	char MeshName[256] = { 0 }, FileID[4] = { 0 };
	char *pChar;	// Pointer to char
	
	if (argc < 2)	// Argument count < 2, no input file
		return 0;
		
	if (fopen_s(&fpXPR, argv[1], "rb") != 0) // Security check
	{
		printf("error! cannot open file %s\n", argv[1]);
		system("pause");
		exit(1); // Terminate the program
	}

	/* Get Archive Size */
	fseek(fpXPR, 0L, SEEK_END); 	// Jump to end of file(EOF)
	filesize = ftell(fpXPR) - 100;	// For security, search till there're 100 bytes to the EOF

	rewind(fpXPR);				// Reset the file offset pointer

	while ((ULONG)ftell(fpXPR) < filesize) // Scan one byte after another untill the filesize is reached
	{
		fread_s(&MAGIC, 4, 4, 1, fpXPR);	// Read 4 bytes to MAGIC
		if (MAGIC == 0x15020100)		// if the FI marker is found
		{
			fseek(fpXPR, -16L, SEEK_CUR);	// seek backwards to 4 bytes before the last FI count

			/* Search for the NULL field after the TotalFIsize */
			do
			{
				fread_s(&MAGIC, 4, 4, 1, fpXPR);	// Read 4 bytes to MAGIC
				fseek(fpXPR, -8L, SEEK_CUR);	// seek backwards 8 bytes
			} while (MAGIC != 0);

			fseek(fpXPR, -8L, SEEK_CUR);	// seek backwards 8 bytes where TotalFIsize is located

			pChar = strrchr(argv[1], 92);	// Find the last backslash in argv[1]
			if (pChar == NULL)				// If no backslash is found
				pChar = argv[1];			// Reset pChar
			else
				pChar++;	// Skip the last backslash
			strncpy_s(MeshName, 256, pChar, strlen(pChar) - 4); // Copy basename of input file to MeshName
			strcat_s(MeshName, 256, "_");		// MeshName + "_"
			sprintf_s(FileID, "%d", m);			// Convert integer m to string
			strcat_s(MeshName, 256, FileID);	// MeshName + FileID
			Flag = Nif2Obj(fpXPR, MeshName);	// Call Nif2Obj() 
			if (!Flag)	// Convertion succeeded
				m++;	// Counter + 1
		}
		else	// if the FI marker is NOT found
		{
			fseek(fpXPR, -3L, SEEK_CUR);	// seek backwards 3 bytes 
		}
	}

	fclose(fpXPR);	// Close input file when it's done

    return 0;
}

```
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-15T09:50:02+00:00
- Post Title: Writing an Obj Convertor in C

Compile the above code with VS and you'll get the executable. Its original name is "Nif2Obj.exe". You can also get a binary [here](https://forum.xentax.com/viewtopic.php?f=16&t=16931).
Drag and drop a nif file onto the exe, or run a cmd file containing the following commands 

```
for %%f in (*.nif) do Nif2Obj.exe "%%f"
pause

```

and you'll get the output obj files.

That's all for this course.

[Return to the main tutorial.](https://forum.xentax.com/viewtopic.php?p=138998#p138998)
