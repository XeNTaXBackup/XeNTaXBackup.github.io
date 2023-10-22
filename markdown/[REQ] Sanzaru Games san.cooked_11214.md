## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-17T13:32:44+00:00
- Post Title: [REQ] Sanzaru Games *san.cooked

Can anyone help in unpacking the files in the san.coolked files that Sanzaru likes to keep everything in?
Everything seems to be uncompressed and and the format also looks to be unchanged throughout all their games.


Here are some examples from 3 games each from different systems.

Secret Agent Clank [ps2/psp]
[https://www.dropbox.com/s/hdzantrffkpsh ... san.cooked](https://www.dropbox.com/s/hdzantrffkpsh41/sacLevel.san.cooked)

Bentley's Hackpack [IOS/Android]
[https://www.dropbox.com/s/pa39eaar7ba1l ... .cooked.7z](https://www.dropbox.com/s/pa39eaar7ba1ltw/bhpAll_Combined.san.cooked.7z)

Sly Cooper: Theives in Time [ps3/psvita]
[https://www.dropbox.com/s/pa39eaar7ba1l ... .cooked.7z](https://www.dropbox.com/s/pa39eaar7ba1ltw/bhpAll_Combined.san.cooked.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-17T14:51:10+00:00
- Post Title: [REQ] Sanzaru Games *san.cooked

Its not meant to be extracted its meant to be loaded.
This file is just a bunch of chunk data containing textures, materials, models ext.
each section starts with
PROF followed by the size if you want to look at each section.
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-02T19:57:25+00:00
- Post Title: [REQ] Sanzaru Games *san.cooked

That format is pretty straight forward

```
	{
		FORM = MAKEID( 'F', 'O', 'R', 'M' ),
		PLAT = MAKEID( 'P', 'L', 'A', 'T' ),
		COOK = MAKEID( 'C', 'O', 'O', 'K' ),
		TEXR = MAKEID( 'T', 'E', 'X', 'R' ),
		MATL = MAKEID( 'M', 'A', 'T', 'L' ),
		MESH = MAKEID( 'M', 'E', 'S', 'H' ),
		GEOB = MAKEID( 'G', 'E', 'O', 'B' ),
		GINS = MAKEID( 'G', 'I', 'N', 'S' ),
		TBLK = MAKEID( 'T', 'B', 'L', 'K' )
	};

	enum MeshTypes
	{
		MSHH = MAKEID( 'M', 'S', 'H', 'H' ),
		SMSH = MAKEID( 'S', 'M', 'S', 'H' ),
		MHDR = MAKEID( 'M', 'H', 'D', 'R' ),
		MPAL = MAKEID( 'M', 'P', 'A', 'L' ),
		MVTX = MAKEID( 'M', 'V', 'T', 'X' ),
		MIDX = MAKEID( 'M', 'I', 'D', 'X' )

	};

	struct MSHH_Struct
	{
		DWORD BlockSize;
		DWORD Data[ 6 ];
	};


	struct Vert_t
	{
		Vec3f Pos; 
		BYTE VertexCol[4];
		Vec3f duno;
		Vec3f duno1;
		Vec3f Normals; // these are not actually normals I've just mapped it to some arbitrary data for now.
		Vec2<float> Uvs;
		BYTE Post[8];

	};

```
