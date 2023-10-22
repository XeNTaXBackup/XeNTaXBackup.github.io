## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-13T02:53:09+00:00
- Post Title: Ragnarok Online

Hello guys, well today I install this game, I unpack files and got some files with a lot extentions, like:

-RSW
-RSM
-GAT
-LUB
-BMP

a lot more, so well my question is if somebody cna take a look into 3D model format? ok many thanks for all and hope somebody can make a something with samples, grateful for support.



ok and here some info about files.

> - texture paths are relative to the Ragnarok folder.
>
> - size specified as structure or data type or in bytes 
>
> - structure sizes and content listed in type definitions below
>
> 
>
> Data/Field	Size				Notes
>
> ======================================================================================		
>
> <HEADER>	
>
> --------------------------------------------------------------------------------------
>
> 'GRSM'		4				RSM identifier/header
>
> todo 		27				Unknown, labled "todo"
>
> nTextures	int				Number of textures (int)
>
> text_name	ro_string * nTextures		
>
> 
>
> <MESH>						Keep reading in a mesh until EOF or
>
> 						30 meshes are read in		
>
> ---------------------------------------------------------------------------------------
>
> name		ro_string			name of mesh
>
> todo		int				integer, only read for first mesh
>
> parent_name	ro_string
>
> ftodo		int * 10			Array of 10 floats, only read for first mesh
>
> ntextures	int				number of textures for this mesh
>
> n		int * ntextures			see code
>
> transf		float * 22			used in transformations...
>
> 
>
> npos_vtx	int				number of vertices
>
> pos_vtx		ro_vertex_t * npos_vtx		array of vertices
>
> 
>
> ntex_vtx	int				number of texture coordinates
>
> tex_vtx 	ro_vertex_t * ntex_vtx		array of coordinates (see code)
>
> 
>
> nall_faces	int				number of faces
>
> all_faces 	ro_face_t * nall_faces		array of face structures
>
> 
>
> nframes		int				number of frame animations
>
> frames 		ro_frame_t * nframes		array of frame structures
>
> 
>
> 
>
> So RSM layout is:
>
> <HEADER>
>
> <MESH>
>
> <MESH>
>
>  .
>
>  .
>
>  .
>
> <MESH>
>
> 
>
> or usually just one mesh
>
> 
>
> 
>
> 
>
> Here's the code:
>
> ================
>
> //Type definitions
>
> 
>
> typedef char ro_string_t[40];		// The RO path string, 40 bytes wide
>
> 
>
> typedef struct {			// RSM Header
>
> 	char filecode[4];		
>
> 	char todo[27];
>
> } rsm_header_t;
>
> 
>
> typedef struct {			// Used by app to store position information
>
> 	GLfloat x;
>
> 	GLfloat y;
>
> 	GLfloat z;
>
> 	GLfloat rx;
>
> 	GLfloat ry;
>
> 	GLfloat rz;
>
> 	GLfloat sx;
>
> 	GLfloat sy;
>
> 	GLfloat sz;
>
> } ro_position_t;
>
> 
>
> typedef float ro_vertex_t[3];		// Stores vertex information
>
> 
>
> typedef struct {
>
> 	short v[3];			// Indexed vertices to use for this face
>
> 	short t[3];			// Indexed texture coordinates to use for this face
>
> 	unsigned short	  text;		// Which texture to use for this surface
>
> 	unsigned short	todo1;		// ???
>
> 	unsigned int   todo2;		// ???
>
> 	unsigned int   nsurf;		// ???
>
> } ro_face_t;
>
> 
>
> typedef struct {
>
> 	unsigned int text;	// Which texture to use for this surface
>
> 	int nvertex;		// Number of Vertexes 
>
> 	int nfaces;		// Number of Faces/Triangles
>
> 	gl_vertex_t *vertex;	
>
> 	gl_face_t *faces;
>
> } ro_surface_t;
>
> 
>
> typedef struct {
>
> 	GLfloat todo[22];	// ???
>
> } ro_transf_t;
>
> 
>
> typedef float ro_quat_t[4];
>
> 
>
> typedef struct {
>
> 	int time;
>
> 	ro_quat_t orientation;
>
> } ro_frame_t;
>
> 
>
> typedef struct {
>
> 	GLfloat max[3];
>
> 	GLfloat min[3];
>
> 	GLfloat range[3];
>
> } bounding_box_t;
>
> 
>
> //Classes
>
> class RSM  
>
> {
>
> public:
>
> 	RSM();							// Constructor
>
> 	bool Load(char *ragnapath, char *filename);		// RSM Loader
>
> 	void Display(ro_position_t pos);			
>
> 	void DisplayMesh(bounding_box_t *b, int n, ro_transf_t *ptransf=NULL);
>
> 	virtual ~RSM();
>
> 
>
> private:
>
> 	void BoundingBox();
>
> 
>
> private:
>
> 	bounding_box_t box;
>
> 	int *father;
>
> 	GLfloat range[3];
>
> 	GLfloat min[3];
>
> 	GLfloat max[3];
>
> 	rsm_header_t header;
>
> 	int nmeshes;
>
> 	RSM_Mesh *meshes;
>
> 	int ntextures;
>
> 	GLuint *textures;
>
> 	ro_string_t *textures_name;
>
> 	bool *alphatex;
>
> };
>
> 
>
> 
>
> class RSM_Mesh  
>
> {
>
> public:
>
> 	RSM_Mesh();
>
> 	bool Load(FILE *fp, GLuint *all_textures, bool *alphatex, bool main);
>
> 	void Display(bounding_box_t *box, ro_transf_t *ptransf = NULL);
>
> 	virtual ~RSM_Mesh();
>
> 	ro_transf_t transf;
>
> 	ro_vertex_t *pos_vtx;
>
> 	GLfloat range[3];
>
> 	GLfloat min[3];
>
> 	GLfloat max[3];
>
> 	void BoundingBox(ro_transf_t *ptransf=NULL);
>
> 	ro_string_t	name;
>
> 	ro_string_t parent_name;
>
> 	bool only;
>
> 
>
> private:
>
> 
>
> 
>
> //Parsing
>
> bool RSM::Load(char *ragnapath, char *filename)
>
> {
>
> 	FILE *fp;
>
> 	int i;
>
> 
>
> 	fp = fopen(filename, "rb");
>
> 
>
> 	if (!fp) {
>
> 		return false;
>
> 	}
>
> 
>
> 	//Read in the header
>
> 	fread (&header, sizeof(rsm_header_t), 1, fp);
>
> 
>
> 	//Get the number of textures
>
> 	fread (&ntextures, sizeof(int), 1, fp);
>
> 
>
> 	textures = new GLuint[ntextures];
>
> 	alphatex = new bool[ntextures];
>
> 	textures_name = new ro_string_t[ntextures];
>
> 
>
> 	//Read texture paths into an array of strings 40 bytes wide each...
>
> 	fread (textures_name, sizeof(ro_string_t), ntextures, fp);
>
> 
>
> 	//prepare textures for openGL
>
> 	glGenTextures(ntextures, textures);
>
> 
>
> 	//Load textures
>
> 	for (i = 0; i < ntextures; i++)
>
> 		LoadTexture (ragnapath, textures_name, textures, &alphatex);
>
> 
>
> 	meshes = new RSM_Mesh[30];
>
> 
>
> 	//Read in mesh structure until we hit end-of-file or 30 meshes
>
> 	while (file_status(fp) != 0) {
>
> 		meshes[nmeshes].Load(fp, textures, alphatex, (nmeshes == 0));
>
> 		nmeshes++;
>
> 		if (nmeshes > 29)
>
> 			break;
>
> 	}
>
> 
>
> 	if (nmeshes == 1)
>
> 		meshes[0].only = true; 	//Set if only one mesh was read...
>
> 	else
>
> 		meshes[0].only = false;
>
> 	fclose (fp);
>
> 
>
> 	//create mesh heirarchy
>
> 	father = new int[nmeshes];
>
> 	father[0] = 0;
>
> 	for (i = 0; i < nmeshes; i++)
>
> 		for (int j = 0; j < nmeshes; j++)
>
> 			if ((j != i) && (!strcmp(meshes[j].parent_name, meshes.name)))
>
> 				father[j] = i;
>
> 
>
> 	BoundingBox();		//Set up bounding box
>
> 
>
> 	return true;
>
> }
>
> 
>
> 
>
> 
>
> AUX_RGBImageRec *LoadBMP(char *Filename)
>
> {
>
>   FILE *File=NULL;	
>
> 
>
>   if (!Filename)	
>
>     {
>
>       return NULL;	
>
>     }
>
> 
>
>   File=fopen(Filename,"r");
>
> 
>
>   if (File)		
>
>     {
>
>       fclose(File);			
>
>       return auxDIBImageLoad(Filename);
>
>     }
>
> 
>
>   return NULL;
>
> }
>
> 
>
> #define coord3(t, x, y, o) t[3*((x)+(y)*w)+o] 
>
> #define coord4(t, x, y, o) t[4*((x)+(y)*w)+o] 
>
> 
>
> bool LoadTexture(char *ragnapath, char *filename, GLuint texture, bool *alpha)
>
> {
>
> 	int h, w, j, k;
>
> 	unsigned char *cdata;
>
> 	unsigned char *ndata;
>
> 	char buffer[512];
>
> 	int l;
>
> 	l = strlen(filename);
>
> 
>
> 	sprintf (buffer, "%s\\data\\texture\\%s", ragnapath, filename);
>
> 
>
> 	if ((filename[l-3] == 'b' && 
>
> 		filename[l-2] == 'm' &&
>
> 		filename[l-1] == 'p') || (filename[l-3] == 'B' && 
>
> 		filename[l-2] == 'M' &&
>
> 		filename[l-1] == 'P')) {
>
> 
>
> 	AUX_RGBImageRec *image;
>
> 	image = LoadBMP(buffer);
>
> 	if(!image) image = LoadBMP("blank.bmp");
>
> 	h = image->sizeY;
>
>     	w = image->sizeX;
>
> 
>
>       cdata = (unsigned char *) image->data;
>
>       ndata = (unsigned char *) malloc (sizeof(unsigned char)*4*h*w);
>
> 
>
>     for (j = 0; j < h; j++) 
>
>       for (k = 0; k < w; k++) {
>
>       unsigned char a, r, g, b;
>
> 
>
>       b = coord3(cdata, k, h-1-j, 0);
>
>       g = coord3(cdata, k, h-1-j, 1);
>
>       r = coord3(cdata, k, h-1-j, 2);
>
> 
>
>       ndata[4*(j*w+k)] = b;
>
>       ndata[4*(j*w+k)+1] = g;
>
>       ndata[4*(j*w+k)+2] = r;
>
>       if (g==0 && r>253 && b>253)
>
> 		ndata[4*(j*w+k)+3] = 0;
>
>       else
>
> 		ndata[4*(j*w+k)+3] = 255;
>
>     }
>
> 
>
>     glBindTexture(GL_TEXTURE_2D, texture);
>
> 
>
>     glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_S, GL_REPEAT);
>
>     glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_T, GL_REPEAT);
>
>     glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MAG_FILTER, GL_LINEAR);
>
>     glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MIN_FILTER, GL_LINEAR);
>
> 
>
> 	gluBuild2DMipmaps ( GL_TEXTURE_2D, GL_RGBA, w, h,
>
> 		GL_RGBA, GL_UNSIGNED_BYTE, ndata );
>
> 
>
> 		if (alpha)
>
> 			*alpha = false;
>
> 	} else if ((filename[l-3] == 't' &&
>
> 		filename[l-2] == 'g' &&
>
> 		filename[l-1] == 'a') || (filename[l-3] == 'T' &&
>
> 		filename[l-2] == 'G' &&
>
> 		filename[l-1] == 'A')) {
>
> 
>
> 
>
> 		image_t   p;
>
> 
>
> 	    glBindTexture(GL_TEXTURE_2D, texture);
>
> 	    tgaLoad  ( buffer, &p, TGA_NO_PASS);
>
> 
>
>     h = p.info.height;
>
>     w = p.info.width;
>
> 
>
>     cdata = (unsigned char *) p.data;
>
>     ndata = (unsigned char *) malloc (sizeof(unsigned char)*4*h*w);
>
> 
>
>     for (j = 0; j < h; j++) 
>
>       for (k = 0; k < w; k++) {
>
>       unsigned char a, r, g, b;
>
> 
>
>       r = coord4(cdata, k, h-1-j, 0);
>
>       g = coord4(cdata, k, h-1-j, 1);
>
>       b = coord4(cdata, k, h-1-j, 2);
>
>       a = coord4(cdata, k, h-1-j, 3);
>
> 
>
>       ndata[4*(j*w+k)] = r;
>
>       ndata[4*(j*w+k)+1] = g;
>
>       ndata[4*(j*w+k)+2] = b;
>
> 	  ndata[4*(j*w+k)+3] = a;
>
>     }
>
> 
>
> 		char buf[512];
>
> 		sprintf(buf, "%d\n", p.info.tgaColourType);
>
> 	//	MessageBox(NULL, buf, NULL, 0);
>
> 
>
> 	    glTexEnvf(GL_TEXTURE_ENV,GL_TEXTURE_ENV_MODE,GL_REPLACE);
>
> 
>
> 	    glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_S, GL_REPEAT);
>
> 		glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_WRAP_T, GL_REPEAT);
>
> 	    glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MAG_FILTER, GL_LINEAR);
>
> 		glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MIN_FILTER, GL_LINEAR);
>
> 
>
> 		gluBuild2DMipmaps ( GL_TEXTURE_2D, p.info.tgaColourType, p.info.width,
>
>                   p.info.height, p.info.tgaColourType, GL_UNSIGNED_BYTE, ndata );
>
> 
>
> 		if (alpha)
>
> 			*alpha = true;
>
> 	} else {
>
> 		MessageBox (NULL, "Unknown texture type", "Error", 0);
>
> 		return false;
>
> 	}
>
> 
>
> 	return true;
>
> }
>
> 
>
> 
>
> bool RSM_Mesh::Load(FILE *fp, GLuint *all_textures, bool *all_alphatex, bool main)
>
> {
>
> 	int i;
>
> 	char buffer[1024];
>
> 	int *surfnum;
>
> 	FILE *fout;
>
> 
>
> 	//Get the name of this mesh
>
> 	fread (name, sizeof(ro_string_t), 1, fp);
>
> 
>
> 	if (main)
>
> 		fread (&todo, sizeof(int), 1, fp);
>
> 
>
> 	fread (parent_name, sizeof(ro_string_t), 1, fp);
>
> 
>
> 	if (main)
>
> 		fread (ftodo, sizeof(float), 10, fp);
>
> 
>
> 	fread (&ntextures, sizeof(int), 1, fp);
>
> 
>
> 	textures = new GLuint[ntextures];
>
> 	alphatex = new bool[ntextures];
>
> 	which = new int[ntextures];
>
> 
>
> 	for (i = 0; i < ntextures; i++) {
>
> 		int n;
>
> 		fread (&n, sizeof(int), 1, fp);
>
> 		which = n;
>
> 		textures = all_textures[n];
>
> 		alphatex = all_alphatex;
>
> 	}
>
> 
>
> 	fread (&transf, sizeof(ro_transf_t), 1, fp);
>
> 
>
> 	fread (&npos_vtx, sizeof(int), 1, fp);
>
> 	pos_vtx = new ro_vertex_t[npos_vtx];
>
> 	fread (pos_vtx, sizeof(ro_vertex_t), npos_vtx, fp);
>
> 
>
> 	fread (&ntex_vtx, sizeof(int), 1, fp);
>
> 	tex_vtx = new ro_vertex_t[ntex_vtx];
>
> 	fread(tex_vtx, sizeof(ro_vertex_t), ntex_vtx, fp);
>
> 
>
> 	fread(&nall_faces, sizeof(int), 1, fp);
>
> 	all_faces = new ro_face_t[nall_faces];
>
> 	fread (all_faces, sizeof(ro_face_t), nall_faces, fp);
>
> 
>
> 	if (file_status(fp) != 2) {
>
> 		return true;
>
> 	}
>
> 
>
> 	fread (&nframes, sizeof(int), 1, fp);
>
> 	frames = new ro_frame_t[nframes];
>
> 	fread (frames, sizeof(ro_frame_t), nframes, fp);
>
> 
>
> 	return true;
>
> }
>
> 
>
> 
>
> 
>
> void RSM_Mesh::BoundingBox(ro_transf_t *ptransf)
>
> {
>
> 	int main = (ptransf == NULL);
>
> 	GLfloat Rot[16];
>
> 	GLfloat *Transf;
>
> 	int i;
>
> 	int j;
>
> 	int k;
>
> 	GLfloat pmax[3], pmin[3];
>
> 
>
> 	Rot[0] = transf.todo[0];
>
> 	Rot[1] = transf.todo[1];
>
> 	Rot[2] = transf.todo[2];
>
> 	Rot[3] = 0.0;
>
> 
>
> 	Rot[4] = transf.todo[3];
>
> 	Rot[5] = transf.todo[4];
>
> 	Rot[6] = transf.todo[5];
>
> 	Rot[7] = 0.0;
>
> 
>
> 	Rot[8] = transf.todo[6];
>
> 	Rot[9] = transf.todo[7];
>
> 	Rot[10] = transf.todo[8];
>
> 	Rot[11] = 0.0;
>
> 
>
> 	Rot[12] = 0.0;
>
> 	Rot[13] = 0.0;
>
> 	Rot[14] = 0.0;
>
> 	Rot[15] = 1.0;
>
> 
>
> 	max[0] = max[1] = max[2] = -999999.0;
>
> 	min[0] = min[1] = min[2] = 999999.0;
>
> 
>
> 	for (i = 0; i < npos_vtx; i++) {
>
> 		GLfloat vtemp[3], vout[3];
>
> 
>
> 		MatrixMultVect(Rot, pos_vtx, vout);
>
> 		for (j = 0; j < 3; j++) {
>
> 			GLfloat f;
>
> 			if (!only)
>
> 				f = vout[j]+transf.todo[12+j]+transf.todo[9+j];
>
> 			else
>
> 				f = vout[j];
>
> 
>
> 			min[j] = MIN(f, min[j]);
>
> 			max[j] = MAX(f, max[j]);
>
> 		}
>
> 	}
>
> 
>
> 	for (j=0; j < 3; j++)
>
> 		range[j] = (max[j]+min[j])/2.0;
>
> }

http://puu.sh/bwK4O/f0d23504d0.7z
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-09-13T09:00:34+00:00
- Post Title: Ragnarok Online

The 3D Object Converter supports the .rsm format since 2005.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-08T05:23:36+00:00
- Post Title: Ragnarok Online

> Reply from Karpati
>
> The 3D Object Converter supports the .rsm format since 2005.well I check it and no load or convert any of this files, so whats happen? 

When try load file I got it.

Unrecognized or unsupported file type! (or no valid object found)

Batch Converter Log.

> Conversion started on 08/10/2014 at 2:21:09
>
> Unrecognised file: D:\Unpacked\Ragnarok\abbey01.rsw
>
> Conversion finished on 08/10/2014 at 2:21:09
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-10-08T06:52:37+00:00
- Post Title: Ragnarok Online

My program supports the .rsm format NOT the .rsw ones...
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-08T06:58:59+00:00
- Post Title: Ragnarok Online

> Reply from Karpati
>
> My program supports the .rsm format NOT the .rsw ones...ok thanks for report, so my mistake, let me check now.

PD. well checked and loaded, so my question is in folder have unicode characters no work, is possible add this support? because koreans folders no load if we don't rename them :S
