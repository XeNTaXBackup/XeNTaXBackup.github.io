## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-01T22:24:08+00:00
- Post Title: Legend of Edda

Legend of Edda archive is .pak but I tried both signsrch and offzip but could not get anywhere 

The game has quite simple models, but look at them! They have so much cuteness that its just plain cool





Archive with 2 .pak
[http://www.2shared.com/file/coeMmyWc/Graphic.html](http://www.2shared.com/file/coeMmyWc/Graphic.html)

actually I get this in signsrch:

padding used in hashing
libavcodec ff_mjpeg_val_ac_luminance
libavcodec ff_mjpeg_val_ac_chrominance
DMC compression [32.le.16&]
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-03-02T03:40:52+00:00
- Post Title: Legend of Edda

ummm well looking files I get this files.

*anm (animations)
*chx & mod (think models)
*dds (textures)





[Legend of Edda 2D-3D Samples](http://www.mediafire.com/download.php?y26cbm46atfxs89)
## Post #3
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-03-02T03:50:26+00:00
- Post Title: Legend of Edda

Luna 2 (Luna Plus)  You can try

[http://www.progamercity.net/game-files/ ... actor.html](http://www.progamercity.net/game-files/2747-dev-luna-2-pak-packer-extractor.html)
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-01-12T02:09:22+00:00
- Post Title: Legend of Edda

sorry for necro but could someone upload the script from progamer?
## Post #5
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2019-01-21T22:50:56+00:00
- Post Title: Legend of Edda

hi im spanish member
Legend of Edda is same luna online reborn

I started a little while ago I start to analyze this structure

.chx is load from client. it only contains data of models and animation that the client will load
.anm  most likely bone structure and animation
.mod model, bone information, collision and other things that have not been found out

try my script



```
FUNCTION RFS FSTREAM NCHAR =
(
	TXT = ""
	NULL = FALSE
	FOR I = 1 TO NCHAR DO 
	(
		CHR = READBYTE FSTREAM #UNSIGNED 
		IF CHR == 0 THEN
		(
			NULL = TRUE
		)
		IF NULL == TRUE THEN
		(
			CONTINUE
		)
		TXT += BIT.INTASCHAR(CHR)
	)
	RETURN TXT
)
/* READ MATRIX 4X4 */
FUNCTION READ_MTX44 FSTREAM =
(
	M11 = READFLOAT FSTREAM; M12 = READFLOAT FSTREAM; M13 = READFLOAT FSTREAM;M14 = READFLOAT FSTREAM
	M21 = READFLOAT FSTREAM; M22 = READFLOAT FSTREAM; M23 = READFLOAT FSTREAM;M24 = READFLOAT FSTREAM
	M31 = READFLOAT FSTREAM; M32 = READFLOAT FSTREAM; M33 = READFLOAT FSTREAM;M34 = READFLOAT FSTREAM
	M41 = READFLOAT FSTREAM; M42 = READFLOAT FSTREAM; M43 = READFLOAT FSTREAM;M44 = READFLOAT FSTREAM
	MTX = MATRIX3 [M11, M12, M13] [M21, M22, M23] [M31, M32, M33] ([M41, M42, M43]) 
	RETURN MTX
)
/* READ NODE INFO */
FUNCTION READ_NODE F =
(
	N_ANGLE = READFLOAT F
	N_POSITION = [READFLOAT F,READFLOAT F,READFLOAT F]
	N_AXIS = [READFLOAT F,READFLOAT F,READFLOAT F]
	N_SCALE = [READFLOAT F,READFLOAT F,READFLOAT F]
	N_SCALEAXIS = [READFLOAT F,READFLOAT F,READFLOAT F]
	N_SCALEANGLE = READFLOAT F
	N_MTX = READ_MTX44 F
	N_MTXINVERSE = READ_MTX44 F
)
/* READ BASE INFO */
FUNCTION READ_BASE F =
(
	INDEX = READLONG F
	READ_NODE F
	CHILDNUM = READLONG F
	PARENTINDEX = READLONG F
	OBJNAME = RFS F 128
	FOR K = 1 TO CHILDNUM DO
	(
		CHILDID = READLONG F
	)
)
/* READ COLLITION INFO */
FUNCTION READ_COL F =
(
	/* BOUNDING BOX */
	BBOX1 = [READFLOAT F,READFLOAT F,READFLOAT F]
	BBOX2 = [READFLOAT F,READFLOAT F,READFLOAT F]
	BBOX3 = [READFLOAT F,READFLOAT F,READFLOAT F]
	BBOX4 = [READFLOAT F,READFLOAT F,READFLOAT F]
	BBOX5 = [READFLOAT F,READFLOAT F,READFLOAT F]
	BBOX6 = [READFLOAT F,READFLOAT F,READFLOAT F]
	BBOX7 = [READFLOAT F,READFLOAT F,READFLOAT F]
	BBOX8 = [READFLOAT F,READFLOAT F,READFLOAT F]
	/* BOUNDING SPHERE */
	BS_POINT = [READFLOAT F,READFLOAT F,READFLOAT F]
	BS_UNK = READFLOAT F
	/* BOUNDING CYLINDER */
	BC_POINT = [READFLOAT F,READFLOAT F,READFLOAT F]
	BC_UNK1 = READFLOAT F
	BC_UNK2 = READFLOAT F
	/* DATA INFO */
	COL_INDEX = READLONG F
	COL_NAME = RFS F 128
)
/* READ MESH INFO */
VERT = #()
TVERT = #()
FACE = #()
FUNCTION READ_MESH F VER =
(
	FREE VERT;FREE TVERT;FREE FACE
	MAXVERTNUM = READLONG F
	VERTNUM = READLONG F
	OVERTNUM = READLONG F
	EVERTNUM = READLONG F
	TVERTNUM = READLONG F
	MTLINDEX = READLONG F
	FACEGROUP = READLONG F
	FLAG = READLONG F
	GRIDINDEX = READLONG F
	DIR = [READFLOAT F,READFLOAT F,READFLOAT F]
	/* VERTEX */
	FOR K = 1 TO VERTNUM DO
	(
		APPEND VERT [READFLOAT F,READFLOAT F,READFLOAT F]
	)
	/* TEXTURE VERTEX */
	FOR K = 1 TO TVERTNUM DO
	(
		APPEND TVERT [READFLOAT F,-READFLOAT F,0.0]
	)
	/* UNK */
	FOR K = 1 TO EVERTNUM DO
	(
		READLONG F
	)
	/* READ FACES */
	FOR K = 1 TO FACEGROUP DO
	(
		MTLINDEX = READLONG F
		INDEX = READLONG F
		FACENUM = READLONG F
		MAXFACENUM = READLONG F
		VERTINDEXNUM = READLONG F
		LIGHTUV1 = READLONG F
		LIGHTUV2 = READLONG F
		FOR J = 1 TO FACENUM DO
		(
			APPEND FACE [READSHORT F + 1,READSHORT F + 1,READSHORT F + 1]
		)
		FOR J = 1 TO LIGHTUV1 DO
		(
			[READSHORT F,READSHORT F]
		)
		FOR J = 1 TO LIGHTUV2 DO
		(
			[READSHORT F,READSHORT F]
		)
	)
	/* PHYSIQUE BONE */
	IF(VER == 0X00000002) THEN
	(
		-- HEADER
		PVERT = READLONG F
		PBONES = READLONG F
		PBONES2 = READLONG F
		FOR K = 1 TO PVERT DO
		(
			PBONES_NUM = READBYTE F
			PBONES_ID = READLONG F
		)
		FOR K = 1 TO PBONES DO
		(
			B_ID = READLONG F
			B_WEIGHT = READFLOAT F
			B_OFFSET = [READFLOAT F,READFLOAT F,READFLOAT F]
			B_NORMAL = [READFLOAT F,READFLOAT F,READFLOAT F]
			B_TAGEN = [READFLOAT F,READFLOAT F,READFLOAT F]
		)
	)
	/* NORMAL VERTEX */
	IF(FLAG == 0X00000000) THEN -- NEED FIX
	(
		-- HEADER
		PL_NUM = READLONG F
		PL_WIDTH = READLONG F
		PL_HEIGHT = READLONG F
		FOR K = 1 TO PL_NUM DO
		(

		)
	)
	ELSE
	(
		IF(FLAG != 0X00000030) THEN
		(
			FOR K = 1 TO TVERTNUM DO
			(
				[READFLOAT F,READFLOAT F,READFLOAT F]
			)
		)
	)
	MSH = MESH VERTICES:VERT FACES:FACE TVERTS:TVERT
	BUILDTVFACES MSH
	FOR I = 1 TO MSH.NUMFACES DO
	(
		SETTVFACE MSH I (GETFACE MSH I)
	)
)
/* READ MOD FILE INFO */
FUNCTION READ_MOD F =
(
	-- MOD HEADER
	VERSION	= READLONG F
	OBJNUM		= READLONG F
	MTLNUM		= READLONG F
	MSHNUM	= READLONG F
	LGTNUM		= READLONG F
	CAMNUM	= READLONG F
	BONENUM	= READLONG F
	FORMAT "DATA: VER:% [%][%][%][%][%][%]\n" VERSION OBJNUM MTLNUM MSHNUM LGTNUM CAMNUM BONENUM
	-- READ MTL
	IF(MTLNUM >= 1) THEN
	(
		FOR K = 1 TO MTLNUM DO
		(
			FORMAT "MATERIAL #%\n" K
			MTL_TYPE = READLONG F
			MTL_SIZE = READLONG F
			IF(MTL_TYPE == 0X00F00000) THEN
			(
				TEX_NUM = READLONG F
				TEX_DIFFUSE = READLONG F 
				TEX_AMBIENT = READLONG F 
				TEX_SPECULAR = READLONG F 
				TEX_TRANSPARENCI = READFLOAT F 
				TEX_SHINE = READFLOAT F 
				TEX_SHINESTRENG = READFLOAT F 
				FOR K = 1 TO 10 DO
				(
					TEX_NAME = RFS F 128
					IF(TEX_NAME != "") THEN
					(
						FORMAT "TEXTURE:%\n" TEX_NAME
					)
				)
				TEX_MTL = RFS F 128
				TEX_INDEX = READLONG F
				TEX_FLAG = READLONG F
			)
		)	
	)	
	-- READ OBJ
	IF(OBJNUM >= 1) THEN
	(
		FOR K = 1 TO OBJNUM DO
		(
			--FORMAT "OBJECT #%\n" K
			MSH_TYPE = READLONG F
			MSH_SIZE = READLONG F
			--FORMAT "TYPE:%\n" (BIT.INTASHEX(MSH_TYPE))
			IF(MSH_TYPE == 0XF4000000) THEN
			(
				READ_BASE F
				READ_MESH F VERSION
			)
			ELSE IF(MSH_TYPE == 0XF5000000) THEN
			(
				READ_BASE F
				READ_COL F
			)
			ELSE
			(
				FORMAT "NEW TYPE FOUND [%]\n" (BIT.INTASHEX(MSH_TYPE))
			)
		)
	)
)
-- START OPEN FILE
FILE = GETOPENFILENAME CAPTION:"IMPORT MODEL" TYPES:"LUNA PLUS MOD|*.mod"
IF(FILE != UNDEFINED) THEN
(
	CLEARLISTENER()
	F	= FOPEN FILE "rb"
	READ_MOD F
	FCLOSE F
)

```
