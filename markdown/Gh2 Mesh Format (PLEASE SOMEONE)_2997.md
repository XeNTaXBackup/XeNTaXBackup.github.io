## Post #1
- Username: CakeIsALie
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 05, 2007 4:04 am
- Post datetime: 2008-04-06T00:48:14+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

PLEASE SOMEONE CRACK THIS
We've done everything with this game but this.
We can edit textures, ADD SONGS(Not replace)
Everything but edit models.
The format can't be THAT hard.
It was made in 3DS Max then exported in a custom format.
Can someone PLEASE look at this?
Someone who made a mesh to output.ms program said it was easy, but no one at Scorehero knows 3D.
I was wondering if someone could make a OBJ to Mesh program or post the specs of the file.
[http://www.savefile.com/files/1486653](http://www.savefile.com/files/1486653)
File Link
MORE FILES:
[http://www.savefile.com/files/1486668](http://www.savefile.com/files/1486668)(this mostly includes bones, but some hair and whatnot) also 666
Gh Exporter + Source! (they never specified what version it works for, I use GMax)
[http://www.savefile.com/files/1486671](http://www.savefile.com/files/1486671)
[74_sh3_model_viewe.rar](https://xentaxbackup.github.io/file/1487_74_sh3_model_viewe.rar)
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-04-06T00:54:28+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

[out]
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-04-07T02:47:11+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

[out]
## Post #4
- Username: CakeIsALie
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 05, 2007 4:04 am
- Post datetime: 2008-04-07T22:46:02+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

Exactly how does this help me convert anything to mesh?
I really want to make my own guitars, but this isn't really helping.
I have converted the meshes to OBJ already, my exporting as a format and using a converter to convert to OBJ.
So, I need someone to CRACK the format, tell the specs and whatnot.
Then I post it at Scorehero, and someone makes a program.
But since I'm banned from it, I'd need someone from here to post it.
But I'm really new to this.
Anyway to decode the 3D file to get the original format?(then convert back to mesh and have it work?)
With some copying and pasting, a created a messed up looking guitar when converting.
Also, if it helps, the source code:

```
#include <assert.h>
#include <math.h>
#include <stddef.h>
#include <stdlib.h>
#include <D3D9.h>
#include <D3DX9.h>
#include <queue>
using namespace std;
#include <string>

// retrieve the local path to the executable;
std::string	GetLocalPath( void )
{
	std::string LocalPath = "";

	char*	pStr, szPath[_MAX_PATH]; 
	GetModuleFileName( NULL, szPath, _MAX_PATH ); 
	pStr = strrchr( szPath, '\\' ); 
	if ( pStr != NULL )
	{
		*( ++pStr ) = '\0';
	}
	LocalPath = szPath;

	return LocalPath;
} // GetLocalPath()

std::string RemoveExtension( const std::string& Path )	// path to remove filename from (keeps trailing slash)
{
	std::string NewPath = Path;

	int	LastSlash	= Path.rfind( "." );
	if( LastSlash >= 0 )
	{
		NewPath = Path.substr( 0, LastSlash + 1 );
	}

	// perform the same check for the other slashes, just in case
	if ( NewPath.length() == Path.length() )
	{
		LastSlash	= Path.rfind( "\\" );
		if( LastSlash >= 0 )
		{
			NewPath = Path.substr( 0, LastSlash + 1 );
		}
	}
	return NewPath;
} // std::string RemoveExtension()

std::string GetFileName( const std::string& Path )	// path to get filename from (keeps trailing slash)
{
	std::string NewPath = Path;

	int	LastSlash	= Path.rfind( "/" );
	if( LastSlash >= 0 )
	{
		NewPath = Path.substr( LastSlash + 1, Path.length() - LastSlash );
	}

	// perform the same check for the other slashes, just in case
	if ( NewPath.length() == Path.length() )
	{
		LastSlash	= Path.rfind( "\\" );
		if( LastSlash >= 0 )
		{
			NewPath = Path.substr( LastSlash + 1, Path.length() - LastSlash );
		}
	}
	return NewPath;
} // std::string GetFileName()
FILE* f = NULL;

// read a string from a binary file of the specified length
std::string ReadString( FILE* pFile,	// pointer to binary file to read from
						int Length )	// length of string to read
{
	std::string	Result;
	char		Character;
	for (int i = 0; i < Length; i++ )
	{
		fread( &Character, 1, 1, pFile );
		Result = Result + Character;
	}
	return Result;
} // ReadString()

// read a string from a binary file until reaching a terminating character
std::string ReadString( FILE* pFile )	// pointer to binary file to read from		
{
	std::string	Result;
	char		Character;
	for ( int i = 0; ; i++ )
	{
		fread( &Character, 1, 1, pFile );
		if ( Character == '\0' )
		{
			break;
		}
		Result = Result + Character;
	}
	return Result;
} // ReadString()

// read a short from a binary file
short ReadShort( FILE* pFile )			// length of string to read
{
	short	ShortValue;

	if ( fread( &ShortValue, sizeof( short ), 1, pFile ) != 1 )
	{
		return( 0 );
	}
	return ShortValue;
} // ReadShort()

// read an int from a binary file
int ReadInt( FILE* pFile )			// length of string to read
{
	int	IntValue;

	if ( fread( &IntValue, sizeof( int ), 1, pFile ) != 1 )
	{
		return( 0 );
	}
	return IntValue;
} // ReadInt()

// read a float from a binary file
float ReadFloat( FILE* pFile )		// length of string to read
{
	float	FloatValue;

	if ( fread( &FloatValue, sizeof( float ), 1, pFile ) != 1 )
	{
		return( 0 );
	}

	return FloatValue;
} // ReadFloat()

// read a byte from a binary file
int ReadByte( FILE* pFile )			// length of string to read
{
	unsigned char	Byte;
	fread( &Byte, 1, 1, pFile );
	return Byte;

} // ReadByte()

// read a bool from a binary file
bool ReadBool( FILE* pFile )			// length of string to read
{
	bool	Bool;
	fread( &Bool, 1, 1, pFile );
	return Bool;

} // ReadBool()


#pragma warning(disable:4996) // deprecated functions


void GetMatrices(const char* filename, D3DXMATRIX* Mat1, D3DXMATRIX* Mat2)
{
FILE *File = NULL;
	const char* file = filename;
	File = fopen( file, "rb" );
	if( !File )
	{
		return;
	}
	fseek( File, 8, SEEK_SET );
	float RX = ReadFloat( File );
	float RY = ReadFloat( File );
	float RZ = ReadFloat( File );
	float UX = ReadFloat( File );
	float UY = ReadFloat( File );
	float UZ = ReadFloat( File );
	float FX = ReadFloat( File );
	float FY = ReadFloat( File );
	float FZ = ReadFloat( File );
	float PX = ReadFloat( File );
	float PY = ReadFloat( File );
	float PZ = ReadFloat( File );
	
	D3DXMatrixIdentity( Mat1 );
	Mat1->_11 = RX;
	Mat1->_12 = RY;
	Mat1->_13 = RZ;
	Mat1->_21 = UX;
	Mat1->_22 = UY;
	Mat1->_23 = UZ;
	Mat1->_31 = FX;
	Mat1->_32 = FY;
	Mat1->_33 = FZ;
	Mat1->_41 = PX;
	Mat1->_42 = PY;
	Mat1->_43 = PZ;

	RX = ReadFloat( File );
	RY = ReadFloat( File );
	RZ = ReadFloat( File );
	UX = ReadFloat( File );
	UY = ReadFloat( File );
	UZ = ReadFloat( File );
	FX = ReadFloat( File );
	FY = ReadFloat( File );
	FZ = ReadFloat( File );
	PX = ReadFloat( File );
	PY = ReadFloat( File );
	PZ = ReadFloat( File );

	D3DXMatrixIdentity( Mat2 );
	Mat2->_11 = RX;
	Mat2->_12 = RY;
	Mat2->_13 = RZ;
	Mat2->_21 = UX;
	Mat2->_22 = UY;
	Mat2->_23 = UZ;
	Mat2->_31 = FX;
	Mat2->_32 = FY;
	Mat2->_33 = FZ;
	Mat2->_41 = PX;
	Mat2->_42 = PY;
	Mat2->_43 = PZ;
	fclose( File );
}

void ConvertFile(const char* filename, D3DXMATRIX* Matr1 = NULL, D3DXMATRIX* Matr2 = NULL)
{
	D3DXMATRIX Mat1;
	D3DXMATRIX Mat2;
	FILE *File = NULL;
	const char* file = filename;
	File = fopen( file, "rb" );
	if( !File )
	{
		return;
	}
	fseek( File, 8, SEEK_SET );
	float RX = ReadFloat( File );
	float RY = ReadFloat( File );
	float RZ = ReadFloat( File );
	float UX = ReadFloat( File );
	float UY = ReadFloat( File );
	float UZ = ReadFloat( File );
	float FX = ReadFloat( File );
	float FY = ReadFloat( File );
	float FZ = ReadFloat( File );
	float PX = ReadFloat( File );
	float PY = ReadFloat( File );
	float PZ = ReadFloat( File );
	
	D3DXMatrixIdentity( &Mat1 );
	Mat1._11 = RX;
	Mat1._12 = RY;
	Mat1._13 = RZ;
	Mat1._21 = UX;
	Mat1._22 = UY;
	Mat1._23 = UZ;
	Mat1._31 = FX;
	Mat1._32 = FY;
	Mat1._33 = FZ;
	Mat1._41 = PX;
	Mat1._42 = PY;
	Mat1._43 = PZ;

	RX = ReadFloat( File );
	RY = ReadFloat( File );
	RZ = ReadFloat( File );
	UX = ReadFloat( File );
	UY = ReadFloat( File );
	UZ = ReadFloat( File );
	FX = ReadFloat( File );
	FY = ReadFloat( File );
	FZ = ReadFloat( File );
	PX = ReadFloat( File );
	PY = ReadFloat( File );
	PZ = ReadFloat( File );

	D3DXMatrixIdentity( &Mat2 );
	Mat2._11 = RX;
	Mat2._12 = RY;
	Mat2._13 = RZ;
	Mat2._21 = UX;
	Mat2._22 = UY;
	Mat2._23 = UZ;
	Mat2._31 = FX;
	Mat2._32 = FY;
	Mat2._33 = FZ;
	Mat2._41 = PX;
	Mat2._42 = PY;
	Mat2._43 = PZ;


	if( Matr1 != NULL )
	{
		Mat1 = *Matr1;
	}
	if( Matr2 != NULL )
	{
		Mat2 = *Matr2;
	}

	int nPos = 117;
	fseek( File, nPos, SEEK_SET );
	int StrLen = ReadInt( File );
	BOOL bHadSubM = FALSE;
	if( StrLen > 255 )
	{
		nPos = 104;
		fseek( File, nPos, SEEK_SET );
		int nSubMs = ReadInt( File );
		for( int m = 0; m < nSubMs; m++ )
		{
			StrLen = ReadInt( File );
			ReadString( File, StrLen );
			if( StrLen > 255 )
			{
				printf("parse error - %s\n", filename);
				return;
			}
		}
		nPos = ftell( File );
		fseek( File, nPos + 9, SEEK_SET );
		bHadSubM = TRUE;
		StrLen = ReadInt( File );
	}
	std::string MeshName = ReadString( File, StrLen );

	ReadByte( File );
	ReadByte( File );
	ReadByte( File );
	ReadByte( File );
	ReadByte( File );

	int SubM = ReadInt( File );
	if( SubM == 0 )
	{
		nPos = ftell( File );
		nPos += 16;

		fseek( File, nPos, SEEK_SET );
	}
	else
	{
		for( int j = 0; j < SubM; j++ )
		{
			StrLen = ReadInt( File );
			std::string SubMeshName = ReadString( File, StrLen );
		}
		nPos = ftell( File ) + 16;
		fseek( File, nPos, SEEK_SET );
	}
	StrLen = ReadInt( File );
	std::string MatName = ReadString( File, StrLen );

	StrLen = ReadInt( File );
	nPos = ftell( File );
	std::string MeshName2 = ReadString( File, StrLen );

	nPos += StrLen + 9;
	fseek( File, nPos, SEEK_SET );
	int nverts = ReadShort( File );

	if( MeshName2 != MeshName )
	{
		if( nverts == 0 )
		{
			ConvertFile( MeshName2.c_str(), &Mat1, &Mat2 );
			fclose( File );
			return;
		}
		else
		{
			GetMatrices( MeshName.c_str(), &Mat1, &Mat2 );
		}
	}

	std::string FinalTexName="none";
	FILE *FMat = fopen( MatName.c_str(), "rb");
	if( FMat )
	{
		fseek( FMat, 68, SEEK_SET );
		StrLen = ReadInt( FMat );
		std::string TexName = ReadString( FMat, StrLen );
		fclose( FMat );

		FILE *FTex = fopen( TexName.c_str(), "rb");
		if( FTex )
		{
			fseek( FTex, 16, SEEK_SET );
			StrLen = ReadInt( FTex );
			FinalTexName = ReadString( FTex, StrLen );
			FinalTexName = GetFileName( FinalTexName );
			FinalTexName = RemoveExtension( FinalTexName );
			FinalTexName = FinalTexName + "tga";
			fclose( FTex );
		}
		else
		{
			FinalTexName = MatName;
			FinalTexName = GetFileName( FinalTexName );
			FinalTexName = RemoveExtension( FinalTexName );
			FinalTexName = FinalTexName + "tga";
		}
	}

	std::vector<float> VertX;
	std::vector<float> VertY;
	std::vector<float> VertZ;
	std::vector<float> NormX;
	std::vector<float> NormY;
	std::vector<float> NormZ;
	std::vector<float> VertR;
	std::vector<float> VertG;
	std::vector<float> VertB;
	std::vector<int> Idx;
	std::vector<float> VertU;
	std::vector<float> VertV;
	int IDontKnow = ReadShort( File );
	for( int i = 0; i < nverts; i++ )
	{
		float X = ReadFloat( File );
		float Y = ReadFloat( File );
		float Z = ReadFloat( File );
		VertX.push_back( X );
		VertY.push_back( Y );
		VertZ.push_back( Z );

		float NX = ReadFloat( File );
		float NY = ReadFloat( File );
		float NZ = ReadFloat( File );

		NormX.push_back( NX );
		NormY.push_back( NY );
		NormZ.push_back( NZ );

		float UK4 = ReadFloat( File );
		float UK5 = ReadFloat( File );
		float UK6 = ReadFloat( File );
		float UK7 = ReadFloat( File );
		UK4 *= UK7;
		UK5 *= UK7;
		UK6 *= UK7;
		VertR.push_back( UK4 );
		VertG.push_back( UK5 );
		VertB.push_back( UK6 );

		float U = ReadFloat( File );
		float V = ReadFloat( File );
		VertU.push_back( U );
		VertV.push_back( V );
	}
	int Faces = ReadShort( File );
	int nindices = Faces * 3;
	int Unknown = ReadShort( File );
	for( i = 0; i < Faces; i++ )
	{
		int IDX1 = ReadShort( File );
		int IDX2 = ReadShort( File );
		int IDX3 = ReadShort( File );
		Idx.push_back( IDX1 );
		Idx.push_back( IDX2 );
		Idx.push_back( IDX3 );
	}

	fclose( File );


	if( nverts == 0 )
	{
		nverts = 4;
		VertY.push_back( -.5 );
		VertZ.push_back( -.5 );
		VertX.push_back( 0 );
		VertU.push_back( 0 );
		VertV.push_back( 0 );
		NormX.push_back( 0 );
		NormY.push_back( 0 );
		NormZ.push_back( 1 );
		VertR.push_back( 1 );
		VertG.push_back( 1 );
		VertB.push_back( 1 );

		VertY.push_back( .5 );
		VertZ.push_back( -.5 );
		VertX.push_back( 0 );
		VertU.push_back( 0 );
		VertV.push_back( 0 );
		NormX.push_back( 0 );
		NormY.push_back( 0 );
		NormZ.push_back( 1 );
		VertR.push_back( 1 );
		VertG.push_back( 1 );
		VertB.push_back( 1 );

		VertY.push_back( 0 );
		VertZ.push_back( .5 );
		VertX.push_back( 0 );
		VertU.push_back( 0 );
		VertV.push_back( 0 );
		NormX.push_back( 0 );
		NormY.push_back( 0 );
		NormZ.push_back( 1 );
		VertR.push_back( 1 );
		VertG.push_back( 1 );
		VertB.push_back( 1 );

		VertY.push_back( 0 );
		VertZ.push_back( 0 );
		VertX.push_back( 3 );
		VertU.push_back( 0 );
		VertV.push_back( 0 );
		NormX.push_back( 0 );
		NormY.push_back( 0 );
		NormZ.push_back( 1 );
		VertR.push_back( 1 );
		VertG.push_back( 1 );
		VertB.push_back( 1 );

		Faces = 4;
		Idx.push_back( 0 );
		Idx.push_back( 1 );
		Idx.push_back( 2 );

		Idx.push_back( 0 );
		Idx.push_back( 3 );
		Idx.push_back( 1 );

		Idx.push_back( 1 );
		Idx.push_back( 3 );
		Idx.push_back( 2 );

		Idx.push_back( 2 );
		Idx.push_back( 3 );
		Idx.push_back( 0 );
		nindices = 12;

	}
	if( nverts > 0 )
		{

		fprintf(f, "fn create = (\ntemp = mesh numverts:%d numfaces:%d\n",
			nverts,
			nindices/3);

		fprintf(f, "setNumTVerts temp %d\nsetNumCPVVerts temp %d\nbuildTVFaces temp\n", nverts, nverts);

		
		for (int i = 0; i < nverts; ++i)
		{
			D3DXVECTOR3 Vec1 = D3DXVECTOR3( VertX[i], VertY[i], VertZ[i] );
			D3DXVec3TransformCoord( &Vec1, &Vec1, &Mat2 );
			fprintf(f, "setVert temp %d [%f,%f,%f]\n", i+1,
				Vec1.x, Vec1.y, Vec1.z);
			fprintf(f, "setTVert temp %d [%f,%f,%f]\n", i+1,
				VertU[i], -VertV[i], 0.0f);
			Vec1 = D3DXVECTOR3( NormX[i], NormY[i], NormZ[i] );
			D3DXVec3TransformCoord( &Vec1, &Vec1, &Mat2 );
			fprintf(f, "setNormal temp %d [%f,%f,%f]\n", i+1,
				Vec1.x, Vec1.y, Vec1.z);

			fprintf(f, "setVertColor temp %d (color %d %d %d)\n", i+1,
				(int)(VertR[i] * 255), (int)(VertG[i] * 255), (int)(VertB[i] * 255));
		}


		
		for (int i = 0; i < Faces; ++i)
		{
			fprintf(f, "setFace temp %d [%d,%d,%d]\n", i+1,
				Idx[i*3+0]+1,
				Idx[i*3+1]+1,
				Idx[i*3+2]+1);
		}


		fprintf(f, "for f = 1 to temp.numfaces do setTVFace temp f (getface temp f)\n");

		fprintf(f, "defaultVCfaces temp\n" );
		fprintf(f, "temp.showvertexcolors = true\n" );
		fprintf(f, "temp.name = \"%s-%s\"\n", filename, MatName.c_str());

		fprintf(f, "inst = 0\n" );
		fprintf(f, "allObj = objects as array\n" );
		fprintf(f, "for o=1 to allObj.count do\n" );
		fprintf(f, "(\n" );
		fprintf(f, "	oMat = allObj[o].material\n" );
		fprintf(f, "	oMatClass = classOf oMat\n" );
		fprintf(f, "	if oMatClass == standardMaterial do\n" );
		fprintf(f, "	(\n" );
		fprintf(f, "		if ((oMat != iMat) and (oMat.name == \"%s\")) then \n", FinalTexName.c_str() );
		fprintf(f, "		(\n" );
		fprintf(f, "		temp.material = allObj[o].material\n" );
		fprintf(f, "		inst=1\n" );
		fprintf(f, "		break\n" );
		fprintf(f, "		)\n" );
		fprintf(f, "	)\n" );
		fprintf(f, ")\n" );
		fprintf(f, "if inst == 0 do\n" );
			fprintf(f, "(\n" );
		fprintf(f, "meditMaterials[1] = Standardmaterial showInViewport:true ()\n" );
		fprintf(f, "meditMaterials[1].name = \"%s\"\n", FinalTexName.c_str() );
		fprintf(f, "meditMaterials[1].diffuseMap = Bitmaptexture fileName:\"%s\"\n", FinalTexName.c_str() );
		fprintf(f, "temp.material = meditMaterials[1]\n" );
				fprintf(f, ")\n" );
		fprintf(f, ")\ncreate()\n");
		printf("added %s\n", filename);

	}
	else
	{
		printf("mesh has no verts - %s\n", filename);
	}

}

int main(int argc, char** argv)
{


	WIN32_FIND_DATA FindFileData;
	HANDLE Find;

	Find = FindFirstFile(  (GetLocalPath() + "/*.mesh" ).c_str(), &FindFileData );

	BOOL Done( FALSE );
       
	f = fopen( "output.ms", "w");
	while ( Find != INVALID_HANDLE_VALUE && !Done )
    {

		if( !( FindFileData.dwFileAttributes & FILE_ATTRIBUTE_DIRECTORY ) )
		{
			ConvertFile( FindFileData.cFileName );
			
		}
		Done = !FindNextFile( Find, &FindFileData );
	}
	fclose(f);
	return 0;
}

```
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-04-09T09:34:12+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

[out]
## Post #6
- Username: CakeIsALie
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 05, 2007 4:04 am
- Post datetime: 2008-04-09T20:00:58+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

I'm so pathetic, but how?
How am I suppose to code? I can't.
Also, tried googling "OBJ reader" but couldn't find one.
Unless you mean something like GMax, but how is that going to help.
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-04-10T18:41:44+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

[out]
## Post #8
- Username: CakeIsALie
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 05, 2007 4:04 am
- Post datetime: 2008-04-10T20:53:09+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

My patheticness prevails again, but could someone do this for me?
Write like a plugin for GMax(or 3dsmax) that exports to .MESH.
Then I shall test it, and see if it works right.
## Post #9
- Username: pmarse
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 24, 2008 1:02 pm
- Post datetime: 2008-08-26T14:16:10+00:00
- Post Title: Gh2 Mesh Format (PLEASE SOMEONE)

Did anyone figure out how to do this? I am extremely interested in editing the mesh files.

Please let me know if there is a program that can open and edit the mesh files, and then export them back into a mesh that is readable by the Guitar Hero 2 PS2 game.


P.S., sorry for resurrecting a months-old topic. I just really want to figure out a way to edit these files. I want to be able to smash heads down to nothing to practically remove them, change the outline of guitars, and remove or modify other body parts. If anyone here can help me figure out a way to edit these files, or to convert the files so that they can be used in a program like 3dsMax, that would be wonderful!

Let me know if you would need any other info about the files, etc. I can also be reached at hockey2112 -a-t- gmail -d-o-t- com . Thanks!
