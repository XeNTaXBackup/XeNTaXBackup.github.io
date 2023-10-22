## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-14T06:05:29+00:00
- Post Title: Rohan Online: GMF Models

can anyone looking into this if they got time. I'm a n00b at findingfloats, and can't seem to find any logical xyz coordinates. I'm not even sure the first ones I'm pulling out are even vertices.. maybe there bone positions 

[http://www.datafilehost.com/download.php?file=13f7272e](http://www.datafilehost.com/download.php?file=13f7272e)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-14T20:54:14+00:00
- Post Title: Rohan Online: GMF Models

This game looks petty good that why I am interest!

Here is what I found about GMF:

```

```
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-14T23:50:39+00:00
- Post Title: Rohan Online: GMF Models

wow that whole upper chunk was just all info on the bones in the transform matrix eh

surprising, there where just static items in the game too. that seems memory consuming, with all that junk.

you want me to upload a few character files?
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-17T20:07:41+00:00
- Post Title: Rohan Online: GMF Models

I want to download the whole client but I can't found any download in their website? [http://www.rohan.cn/](http://www.rohan.cn/)
Could you point me to the right direction!?
## Post #5
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2007-08-18T05:12:11+00:00
- Post Title: Rohan Online: GMF Models

[http://rohan.jp/media/neffy_rohan_pop_action.asp](http://rohan.jp/media/neffy_rohan_pop_action.asp)

[http://rohan.nefficient.jp/rohan/downlo ... _Japan.exe](http://rohan.nefficient.jp/rohan/download/RohanOnline_Japan.exe)

Hope you get it work ^^
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-18T07:17:45+00:00
- Post Title: Rohan Online: GMF Models

1.8G for the client and it's in Japanese!?  >_<!
I lost my interest to download it!

Could you upload some character models with textures for me.  So I can look up for the format.
## Post #7
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2007-08-29T16:13:03+00:00
- Post Title: Rohan Online: GMF Models

[http://www.bibabibo.net/A.rar](http://www.bibabibo.net/A.rar)

Here guy, a plenty of GMF file (6M compressed), many of them is ver 1000, abit different from 900 and 1200, hope you findout soon ^^
If you needed a texture, I will upload later
Regards,
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-29T22:59:22+00:00
- Post Title: Rohan Online: GMF Models

Holy shit! I was wrong about the format before! I think the 1st and the 2nd section should be another mesh with bone/skin data!

Does this game use Normal Map, Specular Map etc!? It seem to have more than 1 layer of texture coordinate as well!

And also there should have some external skeleton files as well as animation files!

Could you upload:
1. Texture files for the about mesh
2. Material files
3. Skeleton files and/or animation files

PS: I think ver 900 and 1000 are the same! Will post the new format I found later.
## Post #9
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2007-08-30T06:53:44+00:00
- Post Title: Rohan Online: GMF Models

Hey guys, here [http://www.bibabibo.net/Data.rar](http://www.bibabibo.net/Data.rar) (9M)
GAF file is for animation
GRF file is material
GTX file is texture
GMF is mesh, of course ^_^
As I see, Rohan just used standard texture, not normal map.
Next day I will upload bigger package containt all monster data ^_^
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-30T08:54:05+00:00
- Post Title: Rohan Online: GMF Models

I had a quick look on the animation file(GAF)! There is no bones structure(skeleton parent/child info.) inside!

Is there any skeleton file as well!?
## Post #11
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2007-08-30T16:29:33+00:00
- Post Title: Rohan Online: GMF Models

0h 5h!t, I just forgot it ^_^
Here [http://www.bibabibo.net/Ske.ra](http://www.bibabibo.net/Ske.ra)
## Post #12
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-30T22:28:40+00:00
- Post Title: Rohan Online: GMF Models

OK, here is what I got so far!
I use the "0bear01_01.gmf" as base and wonder if "m_bear101.grf" exist? Otherwise the name for looking up the material use internal name for it!? Maybe there are some script/info file to control the conbination of all sort of files together.

Format of the Mesh/Geometry file: GMF
Strange enough there are 3 meshes in one GMF, all with same verts and faces count!? And the direction of V texture coordinate in mesh 1 oppisite in Mesh 2 and Mesh 3. Mesh 2 usually divided in small pieces like for the explosiion!?

```
Header Section
==============
char[4]		header	//CMF
dword		ver	//Version
dword		??	
dword		nMLen	//length of material name
char[nMLen]	sMtl	//material name(internal)??

==============
Mesh 1 Section
==============
dword		nVerts	//Verts count
dword		nFaces	//Faces count
dword		??
dword		nLayer	//No. of UV layers
*dword		??	//appears in version 1200 only
struct VertPool {
 float X 3	posXYZ	//Position XYZ
 float X 3	norXYZ	//Normal XYZ
 byte X 7	??	//always FF
 dword		??	//always 0
 struct TexCoord {
  float X 2	uv	
 } TexCoord[nLayer]
 dword		nABone	//No. of Bones for this vert
 struct BoneSkin {			//appears when bFlag == 1
   dword	nBLen	//length of Bone name
   char[nBLen]	sBone	//Bone name
   float	wgt	//Bone weight
   float X 3		//another set of position ??
   float X 3		//another set of normal ??
 } BoneSkin[nABone]
} VertPool[nVerts]
struct Face {
 dword 		nIdx1	//Face index 1
 dword 		nIdx2	//Face index 2
 dword 		nIdx3	//Face index 3
} Face[nFace]

==============
Mesh 2 Section
==============
dword		nLOD	//always 20
dword		nPart	//No. parts of this mesh
struct MeshPart {
 dword		nBone	//No. bones for this part
 struct BonesData {
  dword		nLen	//length of bone name
  char[nLen]	sBName	//Bone name
 } BonesData[nBone]
 dword		nFidx	//face index count
 struct face {
  word	f1	//face index 1
  word	f2	//face index 2
  word	f3	//face index 3
 } face[nFidx/3]
 dword	nVert	//vert count
 struct vertPool {
  float X 3	vt	//Position xyz
  byte X 4	??	//Vert color??
  float X 3	norl	//Normal
  float X 3	??
  *dword		??	//appears in version 1200 only
  float X 2	uv	//Texture coordinate
  *float X	??	//7 bytes for ver 1200, 5 for the others
 } vertPool[nVert]
} MeshPart[nPart]
==============
Mesh 3 Section
==============
Same as Mesh 2 Section
```


Format of the material file: GRF

```
dword		ver	//Version
dword		nMLen	//length of material name
char[nMLen]	sMtl	//material name (Internal name)??
byte X 4 	colAmb	//Ambient Color RGB, 4th byte possibly not used
byte X 4 	colDif	//Diffuse Color RGB
byte X 4 	colSpc	//Specular Color RGB
byte X 4	??	//possibly another color
dword		nTex	//Texture count
byte		??	//always 1, terminator
struct Texture {
 dword		nTLen	//length of Texture name
 char[nMLen]	sTex	//texture name
} Texture[nTex]
```


Format of the Skeleton file: GSF

```
dword		ver	//Version
dword		nBones	//Bones count
struct Bone {
 dword		nBLen	//length of Bone name
 char[nBLen]	sBone	//Bone name
 float X 3	pos1	//Position XYZ
 float X 4	rot1	//Rotation Quat XYZW
 float X 3	pos2	//another set of Position XYZ ??
 float X 4	rot2	//another set of Rotation Quat XYZW ??
 dword		nPLen	//length of Parent name
 char[nBLen]	sPBone	//Parent name
 dword		nChild	//Children count
 struct ChildBone {
  dword		nCLen	//length of Child name
  char[nBLen]	sCBone	//Child name
 } ChildBone[nChild]
} Bone[nBones]
```


Format of the Animation file: GAF

```
dword		ver	//Version
float		fTime	//Length of this animation in second
dword		??	//always 1, No. of amnimation ??
dword		nBones	//No. of bones
struct Animation {
 dword		nBLen	//length of Bone name
 char[nBLen]	sBone	//Bone name
 dword		nKeys	//no. of key frames
 struct KeyData {
  float		fKTime	//key time
  float	X 3	posXYZ	//position XYZ
  float X 4     rotXYZW	//rotation quat XYZW
 } KeyData[nKeys]
} Animation[nBones]
```


The last one texture file: GTX is actually DDS file. Just rename it will do.

I havn't tested the skeleton and animation file so not sure if they are correct!
[test.jpg](https://xentaxbackup.github.io/file/1328_test.jpg)
## Post #13
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-09-04T19:14:53+00:00
- Post Title: Rohan Online: GMF Models

yay, i can't wait to see more  ..any luck on the characters
## Post #14
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-05T16:14:18+00:00
- Post Title: Rohan Online: GMF Models

There are no different between Items and Characters.

The formats above had been tested!
[chars.jpg](https://xentaxbackup.github.io/file/1332_chars.jpg)
## Post #15
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-05T16:23:21+00:00
- Post Title: Rohan Online: GMF Models

Forgot to mention that the skeleton format had been tested correct as well. 
Since I am not going to write any program for it so I am not able to test the animation. I should leave these for anyone who interested in!  
[charsbones.jpg](https://xentaxbackup.github.io/file/1333_charsbones.jpg)
## Post #16
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-09-14T18:19:03+00:00
- Post Title: 

no program
## Post #17
- Username: spintz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 19, 2008 11:02 am
- Post datetime: 2008-08-29T01:18:31+00:00
- Post Title: 

These file formats are no longer accurate.  I've got meshes parsed out, and have even pared the material files with them, to get models converted into a custom 3D format I use for my 3D engine.  To start with, Here's the source code for a program that will extract files from the gel/gem archives :

```
#include <windows.h>
#include <tchar.h>
#include <stdlib.h>
#include <stdio.h>
#include <string>

struct GELHeader
{
	int i1;
	int i2;
	int numberOfElements;
	int i4;
	int i5;
	int i6;

	void print()
	{
		//printf( "i1 = %d\n", i1 );
		//printf( "i2 = %d\n", i2 );
		printf( "numberOfElements = %d\n", numberOfElements );
		//printf( "i4 = %d\n", i4 );
		//printf( "i5 = %d\n", i5 );
		//printf( "i6 = %d\n", i6 );
		printf( "\n" );
	}
};

struct GELEntry
{
	int i1;
	int i2;
	char filename[128];
	int i3;
	int startOffset;
	int dataSize;
	int i6;

	void print()
	{
		//printf( "i1 = %d\n", i1 );
		//printf( "i2 = %d\n", i2 );
		printf( "filename = %s\n", filename );
		//printf( "i3 = %d\n", i3 );
		printf( "startOffset = %d\n", startOffset );
		printf( "dataSize = %d\n", dataSize );
		//printf( "i6 = %d\n", i6 );
		printf( "\n" );
	}
};

// Set this to the .GEL file that you want to extract
std::string srcGel = "C:\\Rohan\\res\\model\\Building\\skeleton.gel";
// Set this to the .GEM file that matches the .GEL file you want to extract
std::string srcGem = "C:\\Rohan\\res\\model\\Building\\skeleton.gem";
// This is the path where all the files will be extracted to
std::string destPath = "C:\\RohanData\\model\\Building";

int main()
{
	FILE* gelFP = 0;
	fopen_s( &gelFP, srcGel.c_str(), "rb" );

	if( gelFP )
	{
		FILE* gemFP = 0;
		fopen_s( &gemFP, srcGem.c_str(), "rb" );

		if( gemFP )
		{
			GELHeader gelHeader;
			fread( &gelHeader, sizeof( GELHeader ), 1, gelFP );
			//gelHeader.print();

			for( int i=0; i<gelHeader.numberOfElements; i++ )
			{
				GELEntry gelEntry;
				fread( &gelEntry, sizeof( GELEntry ), 1, gelFP );
				//gelEntry.print();
				printf( "\b\b\b\b\b\b\b%d", i + 1 );

				if( gelEntry.dataSize > 0 )
				{
					// Create the file
					std::string sFilename = gelEntry.filename;
					size_t pos = sFilename.find_last_of( "\\" );

					std::string path = sFilename.substr( 0, pos + 1 );
					std::string filename = sFilename.substr( pos + 1, sFilename.length() - pos );
					//printf( "Path = %s\nFile = %s\n", path.c_str(), filename.c_str() );

					std::string newPath = destPath;
					newPath.append( path );
					CreateDirectory( newPath.c_str(), NULL );

					// Detect GTX files (DDS files with the header changed and the extension changed
					pos = filename.find_last_of( "." );
					//printf( "pos = %d\n", pos );
					std::string ext = filename.substr( pos + 1, filename.length() - pos - 1 );
					//printf( "ext = %s\n", ext.c_str() );

					if( ext.find( "gtx" ) != std::string::npos )
					{
						//printf( "Found GTX file!\n" );
						char* data = (char*)malloc( gelEntry.dataSize );
						fseek( gemFP, gelEntry.startOffset, 0 );
						fread( data, gelEntry.dataSize, 1, gemFP );

						if( data[0] == 'G' && data[1] == 'E' && data[2] == 'O' )
						{
							// Most gtx files are DDS files with the "Magic Word" changed to GEO.  We change that here, before
							// writing the file
							filename.replace( pos + 1, 3, "dds" );
							std::string fullPath = newPath;
							fullPath.append( "\\" );
							fullPath.append( filename );

							data[0] = 'D';
							data[1] = 'D';
							data[2] = 'S';
							FILE* outFP = 0;
							fopen_s( &outFP, fullPath.c_str(), "wb" );
							if( outFP )
							{
								fwrite( data, gelEntry.dataSize, 1, outFP );
								fclose( outFP );
							}
						}
						else if( data[0] == 'D' && data[1] == 'D' && data[2] == 'S' )
						{
							// Sometimes, DDS files have the proper header in them
							filename.replace( pos + 1, 3, "dds" );
							std::string fullPath = newPath;
							fullPath.append( "\\" );
							fullPath.append( filename );

							FILE* outFP = 0;
							fopen_s( &outFP, fullPath.c_str(), "wb" );
							if( outFP )
							{
								fwrite( data, gelEntry.dataSize, 1, outFP );
								fclose( outFP );
							}
						}
						else
						{
							// Haven't come across this yet, but just in case, we'll know.
							printf( "\n" );
							printf( "Encountered UNKNOWN GTX file!\n" );
							printf( "%c %c %c\n", data[0], data[1], data[2] );
							printf( "\n" );
						}

						free( data );
					}
					else
					{
						std::string fullPath = newPath;
						fullPath.append( "\\" );
						fullPath.append( filename );
					
						FILE* outFP = 0;
						fopen_s( &outFP, fullPath.c_str(), "wb" );
						if( outFP )
						{
							void* data = malloc( gelEntry.dataSize );
							fseek( gemFP, gelEntry.startOffset, 0 );
							fread( data, gelEntry.dataSize, 1, gemFP );
							fwrite( data, gelEntry.dataSize, 1, outFP );
							free( data );
							fclose( outFP );
						}
					}
				}
			}

			printf( "\n\n" );
			fclose( gemFP );
		}

		fclose( gelFP );
	}

	return 0;
}

```


Check the comments by the srcGel, srcGem and destPath std::string's.  They are pretty self-explanatory, but I added the comments just in case.  Soon, I'll post the updated .GMF and .GRF format and source code for converting the .GMF files into .OBJ meshes.

Some teasers tho -
## Post #18
- Username: ICON
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 12, 2008 2:51 am
- Post datetime: 2008-10-11T22:57:20+00:00
- Post Title: 

Thanks for your help on this. Just w8ting to see the converters.
## Post #19
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2008-10-15T23:40:36+00:00
- Post Title: 

I've been looking into the non DDS gtx files. They seem to be Truevision TGA files (uncompressed in ARGB format) but with a slightly different header.

I think I've exported it properly, but if you zoom in, the edges don't seem to align correctly. I've attached my exported file, but if anyone has any ideas on these type of images, please let me know.
[test.png](https://xentaxbackup.github.io/file/1687_test.png)
## Post #20
- Username: liquidwad
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 10, 2008 6:47 am
- Post datetime: 2008-11-01T01:06:59+00:00
- Post Title: 

Thank you to fatduck for figuring out and releasing numerous file formats for rohan.  Thanks also to Spintz for the extraction code.  One problem when extracting all the meshes and textures is that it hard to tell what pieces go together.  IEF files contain this information, so I would like to share its format with you:

```
 * BY PRINCEWADII
 * 01/27/08 4:50 AM
 * Description: .ief files group all meshes that 
 * belong together and store their .gmf file names
 * and material names.
 */

//=============
//   HEADER
//=============
dword header		//always 0x00 00 00 00
dword typeCount  	

//============
//    DATA
//============

struct Type[typeCount]   //normal armor, event armor, head deco, etc..
{
	dword typeID     	
	dword setCount 		 

	struct Set[setCount]  //combination of parts that form a full armor for example
	{
		dword setID 
		struct Part[4]
		/*Parts always come in sets of 4 (ex: upper body, 
		lower body, glove, boot)*/
		{
			dword partLen  		
			char[partLen] bodyPart   //Example: Upper Body
			dword meshCount		//Number of meshes per part

			struct Mesh [meshCount]
			{
				dword meshLen		
				char[meshLen] meshName	//example: c_am_body01.gmf 
				dword matCount		//Number of materials per mesh
				struct Materials [matCount]
				{
					dword matLen		
					char[matLen] material	//Example: Material #01001 
				}
			}
		}
	}
}
```


Just as an example, using .ief files, I was able to do this:



(This tool will also extract and convert full sets from .gmf to .x. I plan on releasing it once it is 100% perfect).
## Post #21
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-11-02T23:27:49+00:00
- Post Title: 

That's a crazy cool tool!  I will eagerly wait for a tool. I love the rohan models
## Post #22
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2008-11-17T22:35:39+00:00
- Post Title: 

Very nice liquidwad. Have you figured out what the type/set IDs mean?
## Post #23
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-19T01:54:54+00:00
- Post Title: 

Pretty cool, though the *.x mesh format has little documentation or at least a low support rating for modeling programs. Though ironically, free modeling programs like Blender do.

Still, I love to see converting and viewing of 3D models, and 3D in general, can't wait to see the results. It's good that a converter is being made, and from what I've seen, it was worth the wait. Not exactly familiar with Rohan, but the models look interesting. 

Oh yeah, does the converter put out the animations intact as well?
## Post #24
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-11-19T11:24:36+00:00
- Post Title: 

cant you make it fbx that support model, animation lightning etc?
## Post #25
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-20T00:06:03+00:00
- Post Title: 

Hm... fbx IS a good format and seems widely supported. Though isn't it difficult to make a converter for? Not sure, but I do like the format for those perks, and even Milkshape seems to support it WITH animations (most imports in MS3D come WITHOUT animations).
## Post #26
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-11-20T00:20:47+00:00
- Post Title: 

.ms3d is also quite a good format. i think looking at blender scripts can give alot of hints...but dont ask me cause i dont know anything about those things
## Post #27
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-05-01T00:32:46+00:00
- Post Title: 

bumping this 

another good format is md5
## Post #28
- Username: ChaosPower
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 22, 2009 2:51 am
- Post datetime: 2009-05-27T02:51:56+00:00
- Post Title: 

EDITED: How did you delete the first 3 hexes in the file?

This is what I did, 

file.gtx -> containing geo header -> replace with dds characters.

in hex editor, there contain readable character which is TRUEVISION-XFile which is a tga file located at the bottom.

These are the first 16

44 44 53 00 00 02 00 00 00 00 00 00 00 00 00 20

Target
00 00 02 00 00 00 00 00 00 00 00 00 20

I need to delete index 0 1 2 in the c++ code, how to do this?

I'm thinking if I rewrite the output to skip data[2] and start with data[3] onwards

EDITED: Used another programming language for solution
## Post #29
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-03-05T20:13:47+00:00
- Post Title: 

bumping this beauty again. just saw a character creatin vid on youtube and remember this still has some cool models. Any viewer/converter out there longing for my harddrive?
## Post #30
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-14T21:36:19+00:00
- Post Title: 

Nothing News abouth the program to convert?
## Post #31
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-14T21:40:56+00:00
- Post Title: Re:

> Reply from fatduck
>
> Forgot to mention that the skeleton format had been tested correct as well. 
Since I am not going to write any program for it so I am not able to test the animation. I should leave these for anyone who interested in!

Something maxscript to load meshes, and how to extract these formats i see only geel and gem.
## Post #32
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-14T22:01:22+00:00
- Post Title: Re:

> Reply from Rimbros
>
> fatduck wrote:Forgot to mention that the skeleton format had been tested correct as well. 
Since I am not going to write any program for it so I am not able to test the animation. I should leave these for anyone who interested in!  

Something maxscript to load meshes, and how to extract these formats i see only geel and gem.

I realy like this models are beautyfull, i not need the skeleton only need import the models also the models i posted in the tread of most wanted models are very beautifull bot more hard than this models of rohan to decript.
## Post #33
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-19T01:45:58+00:00
- Post Title: Re:

> Reply from liquidwad
>
> Thank you to fatduck for figuring out and releasing numerous file formats for rohan.  Thanks also to Spintz for the extraction code.  One problem when extracting all the meshes and textures is that it hard to tell what pieces go together.  IEF files contain this information, so I would like to share its format with you:
Code: Select all/* ROHAN ONLINE .IEF FORMAT
 * BY PRINCEWADII
 * 01/27/08 4:50 AM
 * Description: .ief files group all meshes that 
 * belong together and store their .gmf file names
 * and material names.
 */

//=============
//   HEADER
//=============
dword header		//always 0x00 00 00 00
dword typeCount  	

//============
//    DATA
//============

struct Type[typeCount]   //normal armor, event armor, head deco, etc..
{
	dword typeID     	
	dword setCount 		 

	struct Set[setCount]  //combination of parts that form a full armor for example
	{
		dword setID 
		struct Part[4]
		/*Parts always come in sets of 4 (ex: upper body, 
		lower body, glove, boot)*/
		{
			dword partLen  		
			char[partLen] bodyPart   //Example: Upper Body
			dword meshCount		//Number of meshes per part

			struct Mesh [meshCount]
			{
				dword meshLen		
				char[meshLen] meshName	//example: c_am_body01.gmf 
				dword matCount		//Number of materials per mesh
				struct Materials [matCount]
				{
					dword matLen		
					char[matLen] material	//Example: Material #01001 
				}
			}
		}
	}
}

Just as an example, using .ief files, I was able to do this:



(This tool will also extract and convert full sets from .gmf to .x. I plan on releasing it once it is 100% perfect).

Posted: Sat Nov 01, 2008 2:06 am, around  years ago, i think you leave the project, can please share the information abouth this to others can continue with the project? thanks
## Post #34
- Username: ghoul
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 02, 2011 11:11 pm
- Post datetime: 2011-01-04T18:11:11+00:00
- Post Title: Re:

Guys do anyone know how to import gmf files to 3ds max? Thanks to spintz I finally extract .gem and .gel files. Now I need some meshes but I dont have any idea how to use .gmf files. I see some codes in c++ but Im not good programist so do anyone can explain me how can I use code I can see above? Ultimate Unwrap 3D is little expensive for me so please guys if anyone know or have something I can use to get that meshes then please share it. I MUST HAVE SOME ARMORS from this excellent game!!! xD

Im sorry for my english Im from Poland.
## Post #35
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-18T21:05:30+00:00
- Post Title: Re:

> Reply from ghoul
>
> Guys do anyone know how to import gmf files to 3ds max? Thanks to spintz I finally extract .gem and .gel files. Now I need some meshes but I dont have any idea how to use .gmf files. I see some codes in c++ but Im not good programist so do anyone can explain me how can I use code I can see above? Ultimate Unwrap 3D is little expensive for me so please guys if anyone know or have something I can use to get that meshes then please share it. I MUST HAVE SOME ARMORS from this excellent game!!! xD

Im sorry for my english Im from Poland.

Can you make a guide how to unpack the files? a friend tell me maybe he can make a guide too abouth import gmf files, but its not easy.
## Post #36
- Username: ghoul
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 02, 2011 11:11 pm
- Post datetime: 2011-01-21T21:56:21+00:00
- Post Title: Re:

First you need to download Program Dev C++ from internet, use google. Install it and run. Then choose: File -> New-> Source Code. 
Copy this 
```
#include <windows.h>
#include <tchar.h>
#include <stdlib.h>
#include <stdio.h>
#include <string>

struct GELHeader
{
   int i1;
   int i2;
   int numberOfElements;
   int i4;
   int i5;
   int i6;

   void print()
   {
      //printf( "i1 = %d\n", i1 );
      //printf( "i2 = %d\n", i2 );
      printf( "numberOfElements = %d\n", numberOfElements );
      //printf( "i4 = %d\n", i4 );
      //printf( "i5 = %d\n", i5 );
      //printf( "i6 = %d\n", i6 );
      printf( "\n" );
   }
};

struct GELEntry
{
   int i1;
   int i2;
   char filename[128];
   int i3;
   int startOffset;
   int dataSize;
   int i6;

   void print()
   {
      //printf( "i1 = %d\n", i1 );
      //printf( "i2 = %d\n", i2 );
      printf( "filename = %s\n", filename );
      //printf( "i3 = %d\n", i3 );
      printf( "startOffset = %d\n", startOffset );
      printf( "dataSize = %d\n", dataSize );
      //printf( "i6 = %d\n", i6 );
      printf( "\n" );
   }
};

// Set this to the .GEL file that you want to extract
std::string srcGel = "F:\\Paker\\animation.gel";
// Set this to the .GEM file that matches the .GEL file you want to extract
std::string srcGem = "F:\\Paker\\animation.gem";
// This is the path where all the files will be extracted to
std::string destPath = "F:\\Paker\\Animation\\";

int iiii = 0;
/*
char hextoascii(char a, char b)
{
char hex[5], *stopper;
hex[0] = '0';
hex[1] = 'x';
hex[2] = a;
hex[3] = b;
//hex[4] = '0';
return strtol(hex, &stopper, 16);

}
*/
int main()
{
   FILE* gelFP;
   gelFP = fopen(srcGel.c_str(), "rb" );

   if( gelFP )
   {
      FILE* gemFP;
      gemFP = fopen(srcGem.c_str(), "rb" );

      if( gemFP )
      {
         GELHeader gelHeader;
         fread( &gelHeader, sizeof( GELHeader ), 1, gelFP );
         //gelHeader.print();
        printf("Extracting Files: \n");
         for( int i=0; i<gelHeader.numberOfElements; i++ )
         {
            GELEntry gelEntry;
            fread( &gelEntry, sizeof( GELEntry ), 1, gelFP );
            //gelEntry.print();
            printf( "\b\b\b\b\b\b\b%d", i + 1 );

            if( gelEntry.dataSize > 0 )
            {
               // Create the file
               std::string sFilename = gelEntry.filename;
               size_t pos = sFilename.find_last_of( "\\" );

               std::string path = sFilename.substr( 0, pos + 1 );
               std::string filename = sFilename.substr( pos + 1, sFilename.length() - pos );
               //printf( "Path = %s\nFile = %s\n", path.c_str(), filename.c_str() );

               std::string newPath = destPath;
               newPath.append( path );
               CreateDirectory( newPath.c_str(), NULL );

               // Detect GTX files (DDS files with the header changed and the extension changed
               pos = filename.find_last_of( "." );
               //printf( "pos = %d\n", pos );
               std::string ext = filename.substr( pos + 1, filename.length() - pos - 1 );
               //printf( "ext = %s\n", ext.c_str() );

               if( ext.find( "gtx" ) != std::string::npos )
               {
                  //printf( "Found GTX file!\n" );
                  char* data = (char*)malloc( gelEntry.dataSize );
                  fseek( gemFP, gelEntry.startOffset, 0 );
                  fread( data, gelEntry.dataSize, 1, gemFP );
                  printf("%d",gelEntry.startOffset);
                  if( data[0] == 'G' && data[1] == 'E' && data[2] == 'O' )
                  {
                     // Most gtx files are DDS files with the "Magic Word" changed to GEO.  We change that here, before
                     // writing the file
                     filename.replace( pos + 1, 3, "tga" );
                     std::string fullPath = newPath;
                     fullPath.append( "\\" );
                     fullPath.append( filename );
                     //data[0] = hextoascii('0','0');
                     //data[1] = hextoascii('0','0');
                     //data[2] = hextoascii('0','a');
                     //data[0] = NULL;
                     //data[1] = NULL;
                     //data[2] = NULL;


                     FILE* outFP;
                     outFP = fopen(fullPath.c_str(), "wb" );
                     if( outFP )
                     {
                        fwrite( data, gelEntry.dataSize, 1, outFP );
                        fclose( outFP );
                     }
                  }
                  else if( data[0] == 'D' && data[1] == 'D' && data[2] == 'S' )
                  {
                     // Sometimes, DDS files have the proper header in them
                     filename.replace( pos + 1, 3, "dds" );
                     std::string fullPath = newPath;
                     fullPath.append( "\\" );
                     fullPath.append( filename );

                     FILE* outFP;
                     outFP = fopen(fullPath.c_str(), "wb" );
                     if( outFP )
                     {
                        fwrite( data, gelEntry.dataSize, 1, outFP );
                        fclose( outFP );
                     }
                  }
                  else
                  {

                     // Haven't come across this yet, but just in case, we'll know.
                     printf( "\n" );
                     printf( "Encountered UNKNOWN GTX file!\n" );
                     printf( "%c %c %c\n", data[0], data[1], data[2] );
                     printf( "\n" );
                  }

                  free( data );
               }
               else
               {
                  std::string fullPath = newPath;
                  fullPath.append( "\\" );
                  fullPath.append( filename );

                  FILE* outFP;
                  outFP = fopen(fullPath.c_str(), "wb" );
                  if( outFP )
                  {
                     void* data = malloc( gelEntry.dataSize );
                     fseek( gemFP, gelEntry.startOffset, 0 );
                     fread( data, gelEntry.dataSize, 1, gemFP );
                     fwrite( data, gelEntry.dataSize, 1, outFP );
                     free( data );
                     fclose( outFP );
                  }
               }
            }
         }

         printf( "\n\nProcess Completed\n\n" );
         fclose( gemFP );
      }

      fclose( gelFP );
   }

   return 0;
}

```

And paste it to Dev C++.

```
std::string srcGel = "F:\\Paker\\animation.gel";
// Set this to the .GEM file that matches the .GEL file you want to extract
std::string srcGem = "F:\\Paker\\animation.gem";
// This is the path where all the files will be extracted to
std::string destPath = "F:\\Paker\\Animation\\";

```

This is part of code you should edit to your own. Then Compile and run.
## Post #37
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-22T00:17:52+00:00
- Post Title: Re:

Thanks goul, this its very usefull.
## Post #38
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-24T21:40:05+00:00
- Post Title: Re:

Well this its the end of the way, a friend send me to this forum to investigate this, take a look i see more advances of Rohan extraction models
LINK
[http://shader.tistory.com/category/%EA% ... me%20Model](http://shader.tistory.com/category/%EA%B2%8C%EC%9E%84%EC%9E%90%EC%82%B0%28%20%EA%B2%8C%EC%9E%84%EB%A6%AC%EC%86%8C%EC%8A%A4%20%29/Game%20Model)
 Image


LINK
[http://shader.tistory.com/category/%EA% ... x%20Script](http://shader.tistory.com/category/%EA%B0%9C%EB%B0%9C%ED%99%98%EA%B2%BD/Max%20Script)



Bad very Bad i not found the scrip to import the files inside of max, if you found please share.

I think this man its fatduck but now he its called MrShaderKr

I see something offsets can be readed maybe its posible found this and make a script for max from the trash. MarioKart its expert in maxscripts he make a guide.
## Post #39
- Username: ghoul
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 02, 2011 11:11 pm
- Post datetime: 2011-02-06T20:10:15+00:00
- Post Title: Re:

It's a dead end...
## Post #40
- Username: deadlydata
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 02, 2006 7:48 am
- Post datetime: 2011-02-11T12:13:53+00:00
- Post Title: Re:

```
{
	int m_ID;
	int m_Version;
	int m_MaxAllocFileNum;
	int m_MissingFileSize;
	int m_Reserved;
	int m_Reserved1;
};

```


```
{
	int m_Index;
	int m_FullIndex;
	char m_FileName[128];
	int m_TablePos;
	int m_DataPos;
	int m_DataSize;
	int m_Reserved;

};

```


```
{
  DWORD v4; // ebp@1
  int v5; // eax@1
  char *v6; // eax@5
  const char *v7; // eax@6
  HANDLE v8; // ebx@8
  void *v9; // esi@12
  char *v10; // eax@14
  int v11; // edx@16
  char v12; // cl@17
  size_t v13; // eax@18
  const char *v14; // ecx@18
  void *v15; // eax@21
  int v16; // eax@22
  void *v17; // eax@26
  int v18; // eax@27
  int result; // eax@46
  void *ha; // [sp+0h] [bp-3Ch]@1
  void **v21; // [sp+4h] [bp-38h]@1
  void *v22; // [sp+8h] [bp-34h]@21
  int dwTransferred; // [sp+Ch] [bp-30h]@32
  std::basic_string<char,std::char_traits<char>,std::allocator<char> > lowername; // [sp+10h] [bp-2Ch]@5
  unsigned int v25; // [sp+2Ch] [bp-10h]@1
  int v26; // [sp+30h] [bp-Ch]@1
  int (*v27)(); // [sp+34h] [bp-8h]@1
  int v28; // [sp+38h] [bp-4h]@1

  v28 = -1;
  v27 = _ehhandler__GOpenArchive;
  v26 = v5;
  v25 = (unsigned int)&ha ^ __security_cookie;
  v4 = 0;
  v21 = phGEM;
  ha = 0;
  if ( !szGemName || !*szGemName || !phGEM )
    v4 = 87;
  v6 = strlwr((char *)szGemName);
  lowername._Myres = 15;
  lowername._Mysize = 0;
  lowername._Bx._Buf[0] = 0;
  std__basic_string_char_std__char_traits_char__std__allocator_char____assign(&lowername, v6, strlen(v6));
  v28 = 0;
  if ( !v4 )
  {
    v7 = *(const char **)&lowername._Bx._Buf[0];
    if ( lowername._Myres < 0x10 )
      v7 = (const char *)&lowername._Bx;
    v8 = CreateFileA(v7, dwFlags, 1u, 0, 3u, 0, 0);
    if ( v8 == (HANDLE)-1 )
    {
      GetLastError();
      if ( lowername._Myres >= 0x10 )
        operator delete(*(void **)&lowername._Bx._Buf[0]);
      goto LABEL_46;
    }
    v9 = malloc(0x240u);
    ha = v9;
    if ( v9 )
    {
      memset(v9, 0, 0x240u);
      v10 = *(char **)&lowername._Bx._Buf[0];
      if ( lowername._Myres < 0x10 )
        v10 = (char *)&lowername._Bx;
      v11 = (int)(v10 + 1);
      do
        v12 = *v10++;
      while ( v12 );
      v14 = *(const char **)&lowername._Bx._Buf[0];
      v13 = (size_t)&v10[-v11];
      if ( lowername._Myres < 0x10 )
        v14 = (const char *)&lowername._Bx;
      strncpy((char *)v9, v14, v13);
      *((_DWORD *)v9 + 65) = v8;
      if ( !*((_DWORD *)v9 + 142) )
      {
        v15 = operator new(0x10u);
        v22 = v15;
        LOBYTE(v28) = 1;
        if ( v15 )
          CFileTableListManager__CFileTableListManager((CFileTableListManager *)v15);
        else
          v16 = 0;
        LOBYTE(v28) = 0;
        *((_DWORD *)v9 + 142) = v16;
      }
      if ( !*((_DWORD *)v9 + 143) )
      {
        v17 = operator new(0x600u);
        v22 = v17;
        LOBYTE(v28) = 2;
        if ( v17 )
          CHashFileTableManager__CHashFileTableManager((CHashFileTableManager *)v17);
        else
          v18 = 0;
        LOBYTE(v28) = 0;
        *((_DWORD *)v9 + 143) = v18;
      }
      *((_BYTE *)v9 + 560) = usememorymap;
      if ( SetFilePointer(*((HANDLE *)v9 + 65), 0, 0, 0) != -1 || (v4 = GetLastError(), !v4) )
      {
        if ( ReadFile(*((HANDLE *)v9 + 65), (char *)v9 + 264, 8u, (LPDWORD)&dwTransferred, 0)
          || (v4 = GetLastError(), !v4) )
        {
          if ( dwTransferred != 8 )
          {
            v4 = 11;
            SetLastError(0xBu);
          }
          if ( *((CWorldMgr **)v9 + 66) == (CWorldMgr *)((char *)&g_WorldManager.m_world[5].m_heightMap[102512] + 1) )
          {
            if ( !v4 )
            {
              v4 = GOpenListFile((GemArchive *)v9, dwFlags);
              if ( !v4 )
                goto LABEL_41;
            }
          }
          else
          {
            v4 = 11;
            SetLastError(0xBu);
          }
        }
      }
    }
    else
    {
      v4 = 8;
    }
  }
  FreeGemArchive((GemArchive **)&ha);
  SetLastError(v4);
  v9 = ha;
LABEL_41:
  *v21 = v9;
  if ( !v4 )
  {
    if ( usememorymap )
      *((_DWORD *)v9 + 141) = CreateFileMappingA(
                                *((HANDLE *)v9 + 65),
                                (LPSECURITY_ATTRIBUTES)v4,
                                2u,
                                v4,
                                v4,
                                (LPCSTR)v4);
  }
  if ( lowername._Myres >= 0x10 )
    operator delete(*(void **)&lowername._Bx._Buf[0]);
LABEL_46:
  __security_check_cookie((unsigned int)&ha ^ v25);
  return result;
}

```


```
{
  int v2; // eax@1
  DWORD v3; // ebx@1
  char v4; // cl@2
  HANDLE v5; // edi@3
  int result; // eax@16
  unsigned int v7; // ebp@18
  void *v8; // edi@19
  int dwTransferred; // [sp+0h] [bp-8B4h]@1
  char *v10; // [sp+4h] [bp-8B0h]@3
  std::basic_string<char,std::char_traits<char>,std::allocator<char> > name; // [sp+8h] [bp-8ACh]@1
  char filetitle[64]; // [sp+24h] [bp-890h]@1
  char drive[64]; // [sp+64h] [bp-850h]@1
  char dir[1024]; // [sp+A4h] [bp-810h]@1
  char string; // [sp+4A4h] [bp-410h]@24
  unsigned int v16; // [sp+8A4h] [bp-10h]@1
  int v17; // [sp+8B0h] [bp-4h]@1

  v3 = 0;
  v16 = (unsigned int)&dwTransferred ^ __security_cookie;
  name._Myres = 15;
  name._Mysize = 0;
  name._Bx._Buf[0] = 0;
  v17 = 0;
  _splitpath(ha->szGemFileName, drive, dir, filetitle, 0);
  v2 = (int)filetitle;
  do
    v4 = *(_BYTE *)v2++;
  while ( v4 );
  std__basic_string_char_std__char_traits_char__std__allocator_char____assign(
    &name,
    filetitle,
    v2 - (_DWORD)&filetitle[1]);
  std__basic_string_char_std__char_traits_char__std__allocator_char____append(&name, ".gel", 4u);
  v10 = ha->szGelFileName;
  sprintf(ha->szGelFileName, "%s%s%s");
  v5 = CreateFileA(ha->szGelFileName, dwFlags, 1u, 0, 3u, 0, 0);
  if ( v5 != (HANDLE)-1 || (v3 = GetLastError(), !v3) )
  {
    if ( SetFilePointer(v5, 0, 0, 0) != -1 || (v3 = GetLastError(), !v3) )
    {
      ha->hGelFile = v5;
      if ( ReadFile(v5, &ha->m_GelHeader, 0x18u, (LPDWORD)&dwTransferred, 0) || (v3 = GetLastError(), !v3) )
      {
        if ( dwTransferred != 24 )
          v3 = 11;
        if ( ha->m_GelHeader.m_ID != 269488144 )
          v3 = 11;
        if ( ha->m_GelHeader.m_Version == ha->m_GemHeader.m_Version )
        {
          if ( !v3 )
          {
            v7 = 0;
            if ( ha->m_GelHeader.m_MaxAllocFileNum )
            {
              do
              {
                v8 = malloc(0x98u);
                if ( !ReadFile(ha->hGelFile, v8, 0x98u, (LPDWORD)&dwTransferred, 0) )
                {
                  GetLastError();
                  _snprintf(&string, 0x400u, "error: %d file: %s");
                  MessageBoxA(0, "open gel file failed", "error", 0);
                  ExitProcess(0);
                }
                CFileTableListManager__Add(ha->m_TableManager, (GelFileTable *)v8);
                if ( *((_DWORD *)v8 + 36) != -1 )
                  CHashFileTableManager__Add(ha->m_HashManager, (GelFileTable *)v8);
                ++v7;
              }
              while ( v7 < ha->m_GelHeader.m_MaxAllocFileNum );
            }
          }
        }
      }
    }
  }
  if ( name._Myres >= 0x10 )
    operator delete(*(void **)&name._Bx._Buf[0]);
  __security_check_cookie((unsigned int)&dwTransferred ^ v16);
  return result;
}

```


```
{
  unsigned int *v4; // eax@1
  DWORD v5; // esi@1
  int v6; // eax@1
  int v7; // edi@7
  unsigned int v8; // eax@8
  int v9; // edx@8
  int v10; // esi@8
  int v11; // edi@13
  unsigned int v12; // eax@16
  int v13; // ecx@16
  bool result; // al@20
  char v15; // [sp-Ch] [bp-28h]@1
  unsigned int dwBytes; // [sp+0h] [bp-1Ch]@1
  char *v17; // [sp+4h] [bp-18h]@1
  int v18; // [sp+Ch] [bp-10h]@1
  int (__cdecl *v19)(int, _EH3_EXCEPTION_REGISTRATION *, int); // [sp+10h] [bp-Ch]@1
  int v20; // [sp+14h] [bp-8h]@1
  int v21; // [sp+18h] [bp-4h]@1

  v21 = -1;
  v20 = (int)dword_6F08C0;
  v19 = _except_handler3;
  v18 = v6;
  v17 = &v15;
  dwBytes = 0;
  v5 = 0;
  v4 = pdwRead;
  if ( pdwRead )
    *pdwRead = 0;
  if ( !hFile || !lpBuffer )
    v5 = 87;
  if ( !v5 )
  {
    v7 = *((_DWORD *)hFile + 1);
    if ( v7 )
    {
      v10 = *((_DWORD *)hFile + 2);
      v8 = *(_DWORD *)(*((_DWORD *)hFile + 4) + 144);
      v9 = dwToRead;
      if ( v8 < v10 + dwToRead )
        v9 = v8 - v10;
      memcpy(lpBuffer, (const void *)(v7 + v10), v9);
      v21 = -1;
      *((_DWORD *)hFile + 2) += v9;
      if ( pdwRead )
        *pdwRead = v9;
      dwBytes = v9;
      goto LABEL_27;
    }
    v11 = dwToRead;
    if ( dwToRead )
    {
      if ( SetFilePointer(
             *(HANDLE *)(*((_DWORD *)hFile + 3) + 260),
             *((_DWORD *)hFile + 2) + *(_DWORD *)(*((_DWORD *)hFile + 4) + 140),
             0,
             0) == -1 )
        v5 = GetLastError();
      v13 = *((_DWORD *)hFile + 2);
      v12 = *(_DWORD *)(*((_DWORD *)hFile + 4) + 144);
      if ( v13 + dwToRead > v12 )
      {
        dwToRead = v12 - v13;
        v11 = v12 - v13;
      }
      if ( !v5 )
      {
        if ( !GeoReadFileTry(*(void **)(*((_DWORD *)hFile + 3) + 260), lpBuffer, v11, &dwBytes) )
        {
          GetLastError();
          return 0;
        }
        if ( dwBytes == -1 )
        {
          SetLastError(0x3EBu);
          return 0;
        }
      }
      *((_DWORD *)hFile + 2) += dwBytes;
      v4 = pdwRead;
    }
    if ( v4 )
      *v4 = dwBytes;
  }
  v9 = dwToRead;
LABEL_27:
  if ( dwBytes >= v9 )
  {
    result = 1;
  }
  else
  {
    SetLastError(0x26u);
    result = 0;
  }
  return result;
}

```


```
{
  char *v2; // eax@1
  CGemManager *v3; // edi@1
  int v4; // eax@1
  void *v5; // eax@3
  char *v6; // esi@3
  void *v7; // esi@4
  const char *v8; // eax@9
  _iobuf *v9; // eax@11
  const char *v10; // eax@28
  void *result; // eax@42
  std::basic_string<char,std::char_traits<char>,std::allocator<char> > lowername; // [sp+0h] [bp-48h]@1
  std::basic_string<char,std::char_traits<char>,std::allocator<char> > tempstring; // [sp+1Ch] [bp-2Ch]@1
  unsigned int v14; // [sp+38h] [bp-10h]@1
  int v15; // [sp+3Ch] [bp-Ch]@1
  int (*v16)(); // [sp+40h] [bp-8h]@1
  int v17; // [sp+44h] [bp-4h]@1

  v17 = -1;
  v16 = _ehhandler__OpenFileForRead;
  v15 = v4;
  v14 = (unsigned int)&lowername ^ __security_cookie;
  v3 = this;
  tempstring._Myres = 15;
  tempstring._Mysize = 0;
  tempstring._Bx._Buf[0] = 0;
  std__basic_string_char_std__char_traits_char__std__allocator_char____assign(&tempstring, name, 0, 0xFFFFFFFFu);
  v2 = *(char **)&tempstring._Bx._Buf[0];
  v17 = 0;
  if ( tempstring._Myres < 0x10 )
    v2 = (char *)&tempstring._Bx;
  v6 = strlwr(v2);
  lowername._Myres = 15;
  lowername._Mysize = 0;
  lowername._Bx._Buf[0] = 0;
  std__basic_string_char_std__char_traits_char__std__allocator_char____assign(&lowername, v6, strlen(v6));
  LOBYTE(v17) = 1;
  v5 = operator new(0x2Cu);
  if ( v5 )
  {
    *((_DWORD *)v5 + 8) = 15;
    *((_DWORD *)v5 + 7) = 0;
    *((_BYTE *)v5 + 12) = 0;
    *((_DWORD *)v5 + 10) = 0;
    *(_DWORD *)v5 = 0;
    *((_DWORD *)v5 + 9) = 0;
    *((_BYTE *)v5 + 4) = 0;
    v7 = v5;
  }
  else
  {
    v7 = 0;
  }
  if ( v3->m_UseGemFile )
  {
    if ( !CGemManager__CheckUsePackAndLock(v3, &lowername, (MultiFilePointer *)v7) )
    {
      if ( v7 )
      {
        if ( *((_DWORD *)v7 + 8) >= 0x10u )
          operator delete(*((void **)v7 + 3));
        *((_DWORD *)v7 + 8) = 15;
        *((_DWORD *)v7 + 7) = 0;
        *((_BYTE *)v7 + 12) = 0;
        operator delete(v7);
      }
      if ( lowername._Myres >= 0x10 )
        operator delete(*(void **)&lowername._Bx._Buf[0]);
      lowername._Myres = 15;
      lowername._Mysize = 0;
      lowername._Bx._Buf[0] = 0;
      if ( tempstring._Myres >= 0x10 )
        operator delete(*(void **)&tempstring._Bx._Buf[0]);
      goto LABEL_42;
    }
  }
  else
  {
    *((_BYTE *)v7 + 4) = 0;
  }
  if ( !*((_BYTE *)v7 + 4) )
  {
    v8 = *(const char **)&lowername._Bx._Buf[0];
    if ( lowername._Myres < 0x10 )
      v8 = (const char *)&lowername._Bx;
    v9 = fopen(v8, "rb");
    *(_DWORD *)v7 = v9;
    if ( !v9 )
    {
      if ( *((_DWORD *)v7 + 8) >= 0x10u )
        operator delete(*((void **)v7 + 3));
      *((_DWORD *)v7 + 8) = 15;
      *((_DWORD *)v7 + 7) = 0;
      *((_BYTE *)v7 + 12) = 0;
      operator delete(v7);
      if ( lowername._Myres >= 0x10 )
        operator delete(*(void **)&lowername._Bx._Buf[0]);
      lowername._Myres = 15;
      lowername._Mysize = 0;
      lowername._Bx._Buf[0] = 0;
      if ( tempstring._Myres >= 0x10 )
        operator delete(*(void **)&tempstring._Bx._Buf[0]);
      goto LABEL_42;
    }
    goto LABEL_38;
  }
  if ( *((_DWORD *)v7 + 8) < 0x10u )
    v10 = (char *)v7 + 12;
  else
    v10 = (const char *)*((_DWORD *)v7 + 3);
  GOpenFileForReading(*((void **)v7 + 9), v10, (void **)v7);
  if ( *(_DWORD *)v7 )
  {
LABEL_38:
    if ( lowername._Myres >= 0x10 )
      operator delete(*(void **)&lowername._Bx._Buf[0]);
    lowername._Myres = 15;
    lowername._Mysize = 0;
    lowername._Bx._Buf[0] = 0;
    if ( tempstring._Myres >= 0x10 )
      operator delete(*(void **)&tempstring._Bx._Buf[0]);
    goto LABEL_42;
  }
  EnterCriticalSection(&v3->m_cs);
  --*(_DWORD *)(*((_DWORD *)v7 + 10) + 64);
  LeaveCriticalSection(&v3->m_cs);
  if ( *((_DWORD *)v7 + 8) >= 0x10u )
    operator delete(*((void **)v7 + 3));
  *((_DWORD *)v7 + 8) = 15;
  *((_DWORD *)v7 + 7) = 0;
  *((_BYTE *)v7 + 12) = 0;
  operator delete(v7);
  if ( lowername._Myres >= 0x10 )
    operator delete(*(void **)&lowername._Bx._Buf[0]);
  lowername._Myres = 15;
  lowername._Mysize = 0;
  lowername._Bx._Buf[0] = 0;
  if ( tempstring._Myres >= 0x10 )
    operator delete(*(void **)&tempstring._Bx._Buf[0]);
LABEL_42:
  __security_check_cookie((unsigned int)&lowername ^ v14);
  return result;
}

```


```
{
  void *v3; // esi@1
  int v4; // eax@1
  DWORD v5; // edi@3
  char *v6; // eax@3
  const char *v7; // eax@4
  GelFileTable *v8; // eax@6
  unsigned int v9; // ebp@12
  LPVOID v10; // eax@14
  int v11; // ebp@14
  int v12; // edi@14
  DWORD v13; // eax@14
  int result; // eax@19
  DWORD nError; // [sp+0h] [bp-5Ch]@1
  void *hf; // [sp+4h] [bp-58h]@1
  void **v17; // [sp+8h] [bp-54h]@1
  _SYSTEM_INFO systeminfo; // [sp+Ch] [bp-50h]@13
  std::basic_string<char,std::char_traits<char>,std::allocator<char> > lowername; // [sp+30h] [bp-2Ch]@3
  unsigned int v20; // [sp+4Ch] [bp-10h]@1
  int v21; // [sp+50h] [bp-Ch]@1
  int (*v22)(); // [sp+54h] [bp-8h]@1
  int v23; // [sp+58h] [bp-4h]@1

  v23 = -1;
  v22 = _ehhandler__GOpenFileForReading;
  v21 = v4;
  v20 = (unsigned int)&nError ^ __security_cookie;
  v17 = phFile;
  nError = 0;
  v3 = malloc(0x14u);
  hf = v3;
  if ( !v3 )
    nError = 8;
  v6 = strlwr((char *)szFileName);
  lowername._Myres = 15;
  lowername._Mysize = 0;
  lowername._Bx._Buf[0] = 0;
  std__basic_string_char_std__char_traits_char__std__allocator_char____assign(&lowername, v6, strlen(v6));
  v5 = nError;
  v23 = 0;
  if ( nError )
    goto LABEL_8;
  *(_DWORD *)v3 = 0;
  *((_DWORD *)v3 + 1) = 0;
  *((_DWORD *)v3 + 2) = 0;
  *((_DWORD *)v3 + 3) = 0;
  *((_DWORD *)v3 + 4) = 0;
  *((_DWORD *)v3 + 3) = hGEM;
  v7 = *(const char **)&lowername._Bx._Buf[0];
  if ( lowername._Myres < 0x10 )
    v7 = (const char *)&lowername._Bx;
  v8 = CHashFileTableManager__Get(*((CHashFileTableManager **)hGEM + 143), v7);
  *((_DWORD *)v3 + 4) = v8;
  if ( !v8 )
  {
    nError = 2;
    v5 = 2;
LABEL_8:
    FreeGemFile((GemFile **)&hf);
    SetLastError(v5);
    v3 = hf;
  }
  *v17 = v3;
  if ( !v5 && *((_BYTE *)hGEM + 560) && *((_DWORD *)hGEM + 141) )
  {
    v9 = granularity;
    if ( !granularity )
    {
      GetSystemInfo(&systeminfo);
      v9 = systeminfo.dwAllocationGranularity;
      granularity = systeminfo.dwAllocationGranularity;
    }
    v12 = *((_DWORD *)v3 + 4);
    v13 = v9 * *(_DWORD *)(v12 + 140) / v9;
    v11 = *(_DWORD *)(v12 + 140) - v13;
    v10 = MapViewOfFile(*((HANDLE *)hGEM + 141), 4u, 0, v13, v11 + *(_DWORD *)(v12 + 144));
    *(_DWORD *)v3 = v10;
    if ( !v10 )
    {
      std__basic_string_char_std__char_traits_char__std__allocator_char_____basic_string_char_std__char_traits_char__std__allocator_char__(&lowername);
      goto LABEL_19;
    }
    *((_DWORD *)v3 + 1) = (char *)v10 + v11;
  }
  if ( lowername._Myres >= 0x10 )
    operator delete(*(void **)&lowername._Bx._Buf[0]);
LABEL_19:
  __security_check_cookie((unsigned int)&nError ^ v20);
  return result;
}


```
## Post #41
- Username: Tadur
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 15, 2011 12:31 am
- Post datetime: 2011-02-14T16:33:09+00:00
- Post Title: Re:

Where u enter this Code ?
What Program u use for this Code ?
What are the filenames ?
## Post #42
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-16T20:17:53+00:00
- Post Title: Re:

I like the tutorial how to use this codes... thanks deadlydata by the explanation.
## Post #43
- Username: Tadur
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 15, 2011 12:31 am
- Post datetime: 2011-02-21T14:36:01+00:00
- Post Title: Re:

Can u pls send me the guide how to use this code ?
## Post #44
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-27T13:49:04+00:00
- Post Title: Re:

The contents of this post was deleted because of possible forum rules violation.
[rohan.jpg](https://xentaxbackup.github.io/file/3996_rohan.jpg)
## Post #45
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-28T18:10:59+00:00
- Post Title: Re:

JAJAJAJAJAJA Its this a jocke man?, thousands of treads in forums, and lots of experts asking abouth this, and you make the script for blender in a few days   , where are you? from other planet or something?... RESPECT x 10000000000 for you.
## Post #46
- Username: Tadur
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 15, 2011 12:31 am
- Post datetime: 2011-03-01T20:14:21+00:00
- Post Title: Re: Rohan Online: GMF Models

How to create the IEF Files ?

Loading GSF works
Loading GMF works
Loading Materials , nothing happens
Loading Texture - there are no textures to load

Do u have a special texture file format or a special exporter ?
My Texture Files working fine in DDS Viewer but not in Bender, names tested with DDS,TGA,GXF

Thx
## Post #47
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-01T20:49:50+00:00
- Post Title: Re: Rohan Online: GMF Models

The contents of this post was deleted because of possible forum rules violation.
## Post #48
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-03-01T21:35:16+00:00
- Post Title: Re: Rohan Online: GMF Models

Ok only to clear this, its necesary load the *.IEF files to show the textures right?
I put ief files too, i make all right but its the same textures and material are not loaded right.
Something its wrong bro, cause the others blender importers you make not have this problem.
## Post #49
- Username: Aghmar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 07, 2011 11:12 am
- Post datetime: 2011-04-07T03:52:51+00:00
- Post Title: Re: Rohan Online: GMF Models

Good Day All.

Can Anybody Give me A simple tool, to view Rohan Object and animation after Extraction, i use Rohan tool to extract GMF file into 6 different folder: animation, Bin, material, mesh, skeleton and texture folder.
Or, I just need a simple guide or short tutorial to Use blender 3d, Please help
Thnx
## Post #50
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-04-07T20:04:11+00:00
- Post Title: Re: Rohan Online: GMF Models

Textures Load work fine only with 1% of the models bro, maybe can take review?.
Tested in Costumes.
## Post #51
- Username: Aghmar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 07, 2011 11:12 am
- Post datetime: 2011-04-09T02:00:52+00:00
- Post Title: Re: Rohan Online: GMF Models

hi rimbors, can u give short tutorial about exporting and importing rohans file. and how to viewthe file,
step by step guide pls
## Post #52
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2014-11-29T09:06:47+00:00
- Post Title: Re: Rohan Online: GMF Models

> Reply from Aghmar
>
> hi rimbors, can u give short tutorial about exporting and importing rohans file. and how to viewthe file,
step by step guide pls

Sorry for late, yea i send u tomorrow.
## Post #53
- Username: kthxbai2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 18, 2017 8:53 am
- Post datetime: 2019-07-29T21:58:46+00:00
- Post Title: Re: Rohan Online: GMF Models

I've been working on importer (blender 2.79) /exporter for a bit and i got stuck on importing skeletal data, the original script posted by szkaradek didnt import it correctly either. I dont know much about 3d graphics so it would be great if someone could help me with this.


The game is using modified version of cal3d, there's a snippet for parsing skeletal data:
[https://github.com/mp3butcher/Cal3D/blo ... .cpp#L1040](https://github.com/mp3butcher/Cal3D/blob/120f3165f7a7e5c67e24051a09b02f7ae14af880/cal3d/src/cal3d/loader.cpp#L1040)

This is what i got so far but it seems all wrong.
## Post #54
- Username: indukai
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 16, 2018 9:43 am
- Post datetime: 2021-01-13T15:39:52+00:00
- Post Title: Re: Rohan Online: GMF Models

> Reply from Szkaradek123 ↑Sun Feb 27, 2011 9:49 pm at Sun Feb 27, 2011 9:49 pm
>
> 
The contents of this post was deleted because of possible forum rules violation.

sir can you share blender script export / import for blender 2.8 / 2.7
## Post #55
- Username: indukai
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 16, 2018 9:43 am
- Post datetime: 2021-01-14T07:40:08+00:00
- Post Title: Re: Rohan Online: GMF Models

> Reply from kthxbai2 ↑Tue Jul 30, 2019 5:58 am at Tue Jul 30, 2019 5:58 am
>
> 
I've been working on importer (blender 2.79) /exporter for a bit and i got stuck on importing skeletal data, the original script posted by szkaradek didnt import it correctly either. I dont know much about 3d graphics so it would be great if someone could help me with this.


The game is using modified version of cal3d, there's a snippet for parsing skeletal data:
https://github.com/mp3butcher/Cal3D/blo ... .cpp#L1040

This is what i got so far but it seems all wrong.

can u share this blender script for me sir ?
