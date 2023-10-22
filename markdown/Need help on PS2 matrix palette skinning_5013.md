## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-09-12T07:56:57+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

I am looking for some help on PS2 titles which use "matrix palette skinning" to transform the model's vertices back to it's original position!
There are two type of skinning:
1: only one base position with different bones and weights
From what I found on the net, it should be

> These vertices are not transformed directly by the joint matrices of the animated skeleton but the joint matrices are first multiplied with the inverse joint matrices for the base pose. These inverse joint matrices can be precalculated because the same base pose is used during all animation. The joint matrices of the animated skeleton can then be multiplied with these inverse joint matrices of the base pose before skinning the mesh. The following pseudo code shows how a single vertex is transformed.
>
> 
>
> accumulated = matrix0 * weight0; 
>
> accumulated += matrix1 * weight1; 
>
> accumulated += matrix2 * weight2; 
>
> ... 
>
> position = accumulated * basePosition; 
>
> normal = accumulated * baseNormal; 
>
> tangent = accumulated * baseTangent;

example PS2 title: Saint Seiya The Hades
[](http://img205.imageshack.us/i/mpsv.jpg/)

]as you can see in the pictures, when there is only one bone for each vertex, the position is correct, but for more than 1 bones, all vertices mess up.

attached are some models file and a log file(for 00h.gmi) 

Could anyone take a look at this?
Thank!
[GMI_File.rar](https://xentaxbackup.github.io/file/3434_GMI_File.rar)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-09-12T08:56:49+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

Forgot to post the GMI format!
Here you go:

```
dword           GMIsize
dword           HeaderSize?
dword           padding?
word            numBones
word            numMesh
dword           ofsBones
dword           ofsMesh
dword           ??
dword           ??

struct Bone {                   //Base on parent coordinate
  float_16      Matrix4X4
  word          ParentID
  word          ??
  word          ??
  char[42]      BoneName
}

struct MeshInfo {
  word          MeshType?
  dword         numVerts
  dword         numFaceControl?
  word          padding
  dword         ofsVertCoord
  dword         ofsNormal
  dword         ??              //must be offset of something
  dword         ofsUV
  dword         ofsBoneIndices
  dword         ofsWeight
}

struct VertCoord {              //Base on Bone Transform
  float_3       CoordXYZ
  float         FaceControl     //1.0 = build Face
}

struct Normal {
  word_3        NormalXYZ
  word          Padding?
}

struct UV {
  float_2       TexUV
}

struct BoneIndices {
  byte          Index1
  byte          index2
  byte_2        Padding
}

struct Weight {
  float         Weight1
  float         Weight2  
}
```
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-09-14T23:34:39+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

I think what you are missing is perhaps the "by the joint matrices of the animated skeleton but the joint matrices are first multiplied with the inverse joint matrices for the base pose" part.

What you have there looks to be the geometry and its matching skeleton base pose. This means that you want to transform your actual bone matrices to be used for the vertex transforms by the inverse of the corresponding base pose bone matrices. If your bones have not moved from the base pose, this will give you an identity matrix for every bone. Naturally, transforming every vertex by an identity matrix regardless of weights, will give you the same output as the input you fed into the transform.

If you are transforming against identity matrices and seeing bad results with more than 1 weight, then the problem is in your weighting transforms. That can actually be done in multiple ways, but I've actually started favoring pre-multiplying the matrices, as it works out to be fewer calculations this way when you are also transforming the normals. In gles shading language, it goes something like this:

```
	int bidx;
	bidx = int(boneIdx.x);
	mt[0].xyzw = boneMats[bidx][0].xyzw * boneWgt.x;
	mt[1].xyzw = boneMats[bidx][1].xyzw * boneWgt.x;
	mt[2].xyzw = boneMats[bidx][2].xyzw * boneWgt.x;
	mt[3].xyzw = boneMats[bidx][3].xyzw * boneWgt.x;
	bidx = int(boneIdx.y);
	mt[0].xyzw += boneMats[bidx][0].xyzw * boneWgt.y;
	mt[1].xyzw += boneMats[bidx][1].xyzw * boneWgt.y;
	mt[2].xyzw += boneMats[bidx][2].xyzw * boneWgt.y;
	mt[3].xyzw += boneMats[bidx][3].xyzw * boneWgt.y;
	bidx = int(boneIdx.z);
	mt[0].xyzw += boneMats[bidx][0].xyzw * boneWgt.z;
	mt[1].xyzw += boneMats[bidx][1].xyzw * boneWgt.z;
	mt[2].xyzw += boneMats[bidx][2].xyzw * boneWgt.z;
	mt[3].xyzw += boneMats[bidx][3].xyzw * boneWgt.z;
	bidx = int(boneIdx.w);
	mt[0].xyzw += boneMats[bidx][0].xyzw * boneWgt.w;
	mt[1].xyzw += boneMats[bidx][1].xyzw * boneWgt.w;
	mt[2].xyzw += boneMats[bidx][2].xyzw * boneWgt.w;
	mt[3].xyzw += boneMats[bidx][3].xyzw * boneWgt.w;
	highp vec4 transPos = mt * position;
	gl_Position = mvpMatrix * transPos;
	mat3 m33 = mat3(mt[0].xyz,
					mt[1].xyz,
					mt[2].xyz);
	lowp vec3 transNrm = normalize(m33 * normal);

```
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-15T18:34:07+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

Well, fatduck fail on this and mr.adults its the only have idea   , its the end of the way.
## Post #5
- Username: qslash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 28, 2011 7:05 am
- Post datetime: 2011-04-05T02:09:19+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

Sorry for bumping this thread , but  Im also trying to figure out the matrix palette skin for this format , and so far I got the Skel defined but the transformation of the vertices is the problem, my question is when you mentioned  that the joint matrix has to be multiplied by the inverse of the joint matrix of the base pose , does it has to be the one already accumulated  as a world matrix or the local?.

What I mean is in the follow diagram  : 

M root -> M joint 1 (child) -> M Joint11 (child)

*the local is = M Joint 11 
*the world is accumulated = M root x M Joint1 * M Joint11

So if I have to transform the vertex without considering weights, what I've been trying to do is multiplying the vertices by the world matrix  , but that doesnt show me the correct positions of the vertex and when I apply faces it mess up .  Or doest it have to be : vertex * Inverse(World Matrix of Joint)? .

Before I forget , my respect to fatduck in how he figure out the struct of the file .. thats impressive .
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-05T18:34:14+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

I just assumed fatduck had figured it out when he never replied again, so I never bothered looking at the actual files. I'll have a look at it tonight, if no one else posts and tells me it's already been figured out in the mean time.
## Post #7
- Username: qslash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 28, 2011 7:05 am
- Post datetime: 2011-04-05T23:29:50+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

thanks MrAdults , maybe  this can save you some time checking  , what I have done till now is this : 

from the model : 00s.gmi

- Bone struct is correct
- MeshInfo  has only a small difference from the specified from fatduck, new field bones_used from the log fatduck attached : 

```
  word          MeshType?
  dword         numVerts
  dword         numFaceControl?
  word          padding
  dword         ofsVertCoord
  dword         ofsNormal
  dword         ??              //must be offset of something
  dword         ofsUV
  dword         ofsBoneIndices
  dword         ofsWeight
   byte [12]    bones_used ;       // <-- qslash , array with bone used by the mesh
}
```

- Vertcoord struct is correct , the FaceControl field is equal to 1 , Im assuming is the end of a tri face , if there are 2 consecutives I take the 2 previous vertex before the first FaceControl = 1.
- Struct BoneIndices  is correct , for every vertex the Index1 field is the index position in MeshInfo.bones_used , eg MeshInfo.bone_used[BoneIndices[VertexPosition].index1] is the bone used.

So far  : 
Number of Bones : 46  // Bone[46] 
Number of Meshes : 5 // MeshInfo[5]

Taking as example the Mesh[0] , that I think is the body of the model , we have : 

```
Number of Vertices : 261
Offset Vertices : 5424
Offset Bone Indices : 25104
No weigths .. 
Bones_used [0..11] : 1,3,2,4,7,5,6,8,16,9,18,10
```


Taking only the Bone 3 , that has values , and parentid 1 (Bone 1) , we have 

```
  1.000000 ,   0.000000,   0.000000,   0.000000
  0.000000 ,   1.000000,   0.000000,   0.000000
  0.000000 ,   0.000000,   1.000000,   0.000000
  0.000000 ,   0.000000,   0.000000,   1.000000

[Bone 1 Matrix] Name : h_jnt_waist , parent_id = 0
 -0.000000 ,  -1.000000,  -0.000000,   0.000000
  0.000000 ,  -0.000000,   1.000000,   0.000000
 -1.000000 ,   0.000000,   0.000000,   0.000000
 -0.000000 ,   0.000000,   0.000000,   1.000000

[Bone 3 Matrix] Name : h_jnt_luleg, parent_id = 1 (Local Space Matrix)
  0.998632 ,  -0.052288,  -0.000000,   0.000000
  0.052288 ,   0.998632,   0.000000,   0.000000
 -0.000000 ,  -0.000000,   1.000000,   0.000000
 -0.915000 ,  -0.047500,   0.665000,   1.000000
```


A vertex that uses that bone, Vertex  V[10], 
with BoneIndices[10].bindex1 = 1 , MeshInfo.bones_used[bindex] = 3: 

```

```

The World Space (accumulated) matrix for Bone 3  I have is this : 
 
```
  0.000000  -0.052288   0.998632   0.998632
 -1.000000   0.000000   0.000000   0.000000
 -0.665000   0.915000  -0.047500  -0.047500

```

*Note , Im re-loop-checking again and again if my logic for operations with matrix  is correct .. till now I think is ok .. if not I will shoot myself  .. 

If a multiply the vector with the inverse of the World Space matrix (accumulated), I got the same vector : 
 
```

```

* Edit : I think that is multiplying with a Identity matrix .. mm but thats only if cant be inversed ..weird ..  checking code again .. 
* Edit2 : corrected , fabs(float)  .. but the same the model now looks like a babylon 5 spaceship ..  

if a multiply with the World Space (accumulated) , I got :

```
-0.067392 0.111545 0.945942 
```


But the model with faces , looks wrong : 


So .now Im bleeding from the eyes  I dont know what Im doing wrong ... I just want to get to the same thing that fatduck did , so any help will be appreciated ...
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-06T02:20:38+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

It looks like these verts are meant to be transformed by the modelspace bone matrices. So, multiply the bone matrices down the hierarchy to end up with a fully transformed skeleton, then transform position and normal by the appropriate bone matrix. That will give you the right results for meshes with only 1 weight:
[](http://img59.imageshack.us/i/seiyatest.jpg/)
Unfortunately, though, this still doesn't handle the 2-weight meshes. There is something weird about them. The bone indices all appear correct, but multiplying them against weight matrices does not give you anything resembling the "right" result. This is the problem fatduck had run into. I'll keep messing with it and see what I come up with, but here's my current WIP code. (if you don't recognize some classes/functions, you can reference the Noesis plugin SDK, which is included with Noesis)

```
typedef struct gmiHdr_s
{
	int				id; //0x20040319
	int				size;
	int				unkOfsA;
	int				unkB;
	WORD			numBones;
	WORD			numMeshes;
	int				ofsBones;
	int				ofsMeshes;
	int				unkC;
	int				unkD;
} gmiHdr_t;

typedef struct gmiMesh_s
{
	WORD			unkA;
	int				numVerts;
	int				numUnkB;
	WORD			unkC;
	int				ofsPos;
	int				ofsNrm;
	int				unkD;
	int				ofsUV;
	int				ofsBoneIdx;
	int				ofsBoneWgt;
	BYTE			boneList[12];
} gmiMesh_t;

typedef struct gmiBone_s
{
	RichMat44		mat;
	short			parentIdx;
	short			unkA;
	short			unkB;
	char			name[42];
} gmiBone_t;

typedef struct gmiIntrVert_s
{
	RichVec3		pos;
	RichVec3		nrm;
	float			uv[2];
	int				bi[4];
	float			bw[4];
	int				numWeights;
} gmiIntrVert_t;

noesisModel_t *Model_GMI_Load(BYTE *fileBuffer, int bufferLen, int &numMdl, noeRAPI_t *rapi)
{
	gmiHdr_t *hdr = (gmiHdr_t *)fileBuffer;
	gmiBone_t *srcBones = (hdr->numBones > 0 && hdr->ofsBones > 0) ? (gmiBone_t *)(fileBuffer+hdr->ofsBones) : NULL;
	modelBone_t *bones = NULL;
	int numBones = 0;
	if (srcBones)
	{ //convert bones
		numBones = hdr->numBones;
		bones = rapi->Noesis_AllocBones(numBones);
		for (int i = 0; i < numBones; i++)
		{
			gmiBone_t *srcBone = srcBones+i;
			modelBone_t *dstBone = bones+i;

			dstBone->mat = srcBone->mat.ToMat43().m;
			dstBone->index = i;
			dstBone->eData.parent = (srcBone->parentIdx >= 0) ? bones+srcBone->parentIdx : NULL;
			memcpy(dstBone->name, srcBone->name, sizeof(dstBone->name)-1);
			dstBone->name[sizeof(dstBone->name)-1] = 0;
		}
		rapi->rpgMultiplyBones(bones, numBones);
	}

	void *pgctx = rapi->rpgCreateContext();

	CArrayList<gmiIntrVert_t> verts;

	gmiMesh_t *meshes = (gmiMesh_t *)(fileBuffer + hdr->ofsMeshes);
	for (int i = 0; i < hdr->numMeshes; i++)
	{
		gmiMesh_t *mesh = meshes+i;
		if (mesh->numVerts <= 0 || mesh->ofsPos <= 0 || mesh->ofsPos >= bufferLen)
		{
			continue;
		}

		float *posAr = (float *)(fileBuffer + mesh->ofsPos);
		short *nrmAr = (mesh->ofsNrm > 0 && mesh->ofsNrm < bufferLen) ? (short *)(fileBuffer + mesh->ofsNrm) : NULL;
		float *uvAr = (mesh->ofsUV > 0 && mesh->ofsUV < bufferLen) ? (float *)(fileBuffer + mesh->ofsUV) : NULL;
		BYTE *bidxAr = (mesh->ofsBoneIdx > 0 && mesh->ofsBoneIdx < bufferLen) ? (BYTE *)(fileBuffer + mesh->ofsBoneIdx) : NULL;
		float *bwgtAr = (mesh->ofsBoneWgt > 0 && mesh->ofsBoneWgt < bufferLen) ? (float *)(fileBuffer + mesh->ofsBoneWgt) : NULL;

		int lastDrawIdx = 0;
		for (int j = 0; j < mesh->numVerts; j++)
		{
			gmiIntrVert_t vert;
			memset(&vert, 0, sizeof(vert));
			if (uvAr)
			{
				float *uv = uvAr + j*2;
				vert.uv[0] = uv[0];
				vert.uv[1] = uv[1];
			}

			float *pos = posAr + j*4;

			if (nrmAr)
			{
				short *snrm = nrmAr + j*4;
				vert.nrm[0] = (float)snrm[0] / (float)snrm[3];
				vert.nrm[1] = (float)snrm[1] / (float)snrm[3];
				vert.nrm[2] = (float)snrm[2] / (float)snrm[3];
				vert.nrm.Normalize();
			}

			if (bidxAr)
			{
				BYTE *bidx = bidxAr + j*4;
				float *bwgt = (bwgtAr) ? bwgtAr + j*2 : NULL;
				vert.numWeights = (bwgt) ? 2 : 1;

				RichVec3 tpos;
				RichVec3 tnrm;
				for (int k = 0; k < vert.numWeights; k++)
				{
					if (bidx[k] == 255)
					{
						continue;
					}
					assert(bidx[k] < 12);
					int idx = mesh->boneList[bidx[k]];
					assert(idx < numBones);
					RichVec3 &vpos = *((RichVec3 *)pos);
					float w = (bwgt) ? bwgt[k] : 1.0f;

					RichMat43 *bmat = (RichMat43 *)&bones[idx].mat;
					tpos += bmat->TransformPoint(vpos)*w;
					tnrm += bmat->TransformNormal(vert.nrm)*w;
					vert.bi[k] = idx;
					vert.bw[k] = w;
				}
				vert.pos = tpos;
				vert.nrm = tnrm;
				vert.nrm.Normalize();
			}
			else
			{
				vert.pos = RichVec3(pos);
			}

			verts.Append(vert);

			if (pos[3] == 1.0f)
			{ //draw strip
				assert(lastDrawIdx <= verts.Num());
				rpgeoPrimType_e prim = RPGEO_TRIANGLE_STRIP;
				int vnum = (verts.Num() - lastDrawIdx);
				if (vnum < 3)
				{ //need at least 3 verts to start a strip
					lastDrawIdx -= (3-vnum);
					assert(lastDrawIdx >= 0);
					vnum = 3;
				}
				gmiIntrVert_t *startVert = &verts[lastDrawIdx];
				if (bidxAr)
				{
					rapi->rpgBindBoneIndexBuffer(startVert->bi, RPGEODATA_INT, sizeof(gmiIntrVert_t), 4);
					rapi->rpgBindBoneWeightBuffer(startVert->bw, RPGEODATA_FLOAT, sizeof(gmiIntrVert_t), 4);					
				}
				rapi->rpgBindUV1Buffer(startVert->uv, RPGEODATA_FLOAT, sizeof(gmiIntrVert_t));
				rapi->rpgBindNormalBuffer(startVert->nrm.v, RPGEODATA_FLOAT, sizeof(gmiIntrVert_t));
				rapi->rpgBindPositionBuffer(startVert->pos.v, RPGEODATA_FLOAT, sizeof(gmiIntrVert_t));

				rapi->rpgCommitTriangles(NULL, RPGEODATA_INT, vnum, prim, true);
				rapi->rpgClearBufferBinds();

				lastDrawIdx = verts.Num()+1;
			}
		}
		assert(lastDrawIdx == verts.Num()+1);
		verts.Reset();
	}

	rapi->rpgSetExData_Bones(bones, numBones);
	noesisModel_t *mdl = rapi->rpgConstructModel();
	if (mdl)
	{
		numMdl = 1; //it's important to set this on success! you can set it to > 1 if you have more than 1 contiguous model in memory
		float mdlAngOfs[3] = {0.0f, 90.0f, 270.0f};
		rapi->SetPreviewAngOfs(mdlAngOfs);
	}
	rapi->rpgDestroyContext(pgctx);
	return mdl;
}

```

(note that the adding of transformed pos/normal here is also mathematically equivalent to transforming once against a weighted matrix)
## Post #9
- Username: gustavofarias
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-06T04:50:15+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

Also, I noticed some of the GMI files in this game are compressed too. It was pretty easy to figure out since it's a very simple lzs algorithm:

```
{
	BYTE			id[4]; //"CMPS"
	int				cmpType;
	int				decompSize;
	int				resv;
} gmiCmpHdr_t;

//decompress data
static BYTE *Model_GMI_Decompress(BYTE *src, int &len, noeRAPI_t *rapi)
{
	gmiCmpHdr_t *cmpHdr = (gmiCmpHdr_t *)src;
	int srcLen = len;
	int dstLen = cmpHdr->decompSize;
	BYTE *dst = (BYTE *)rapi->Noesis_PooledAlloc(dstLen);
	int srcPtr = sizeof(gmiCmpHdr_t);
	int dstPtr = 0;

	while (srcPtr < srcLen && dstPtr < dstLen)
	{
		BYTE ctrl = src[srcPtr++];
		for (int i = 0; i < 8 && srcPtr < srcLen; i++)
		{
			if (ctrl & (1<<i))
			{ //literal
				dst[dstPtr++] = src[srcPtr++];
			}
			else
			{ //ofs+len
				WORD ol = *(WORD *)(src+srcPtr);
				srcPtr += sizeof(WORD);
				int len = 3 + ((ol>>8) & 15);
				int relOfs = (ol & 255) | ((ol>>12) << 8);
				int ofs = dstPtr - ((dstPtr-18-relOfs) & 4095);
				for (int j = 0; j < len; j++)
				{
					if (ofs+j < 0 || ofs+j >= dstPtr)
					{
						dst[dstPtr++] = 0;
					}
					else
					{
						dst[dstPtr++] = dst[ofs+j];
					}
				}
			}
		}
	}
	assert(srcPtr == srcLen);
	assert(dstPtr == dstLen);

	len = dstLen;
	return dst;
}

```


PS- unkD in the mesh structure is an offset to vertex colors, typically only used on the compressed stage models.
## Post #10
- Username: qslash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 28, 2011 7:05 am
- Post datetime: 2011-04-06T06:32:02+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

Thanks! I think I just have to add the normals and consider all the meshes to have the correct model, my initial code was ok ... Now I have to undo .

You beat me with the lzss code , I was using the aluigi unlzss of the quickbms but without the init_chr, I saw that in the plugin code of noesis you have also a unlzss , doesnt do the same?
## Post #11
- Username: gustavofarias
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-06T22:43:40+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

I dunno what quickbms does regarding lzs support. I couldn't use Decomp_LZSSGeneric for it though because it expects bits for offset and length to be contiguous, where in this algorithm it's laid out like 8 ofs low, 4 len, 4 ofs high. I could add a Decomp_LZSSGenericEx or some crap to allow for it, but I don't think it's worth it. I have only come across 1 other implementation so far that does not have contiguous bits for offset and length.
## Post #12
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-07T03:29:25+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

The 2-weight thing actually turned out to be really simple. You just don't transform vertices with 2 weights, haha. Just make sure that you do still transform 1-weight verts, even in 2-weight meshes.
[](http://img218.imageshack.us/i/seiyatest2.jpg/)
I'll get a Noesis plugin with code in the next release. I'd put it up now, but I had to add an extension to load the TIM3 textures, so it wouldn't work with the current release.
## Post #13
- Username: qslash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 28, 2011 7:05 am
- Post datetime: 2011-04-07T22:17:25+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

Cool , now that I return from the dentist I will start again doing what you said ..  also Ill try to check which animations belong to each model, maybe, I dont know if I could but I will try .. its a good learning experience this forum.

Thanks again Mr Adults ..
## Post #14
- Username: qslash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 28, 2011 7:05 am
- Post datetime: 2011-04-08T03:06:49+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

Im close ..  .. 


The only problem that I have is when I try to create all the meshes they appear moved to the last vertex drawed of the previous,  ..but when I create 1 by 1 , and imported in blender as layers is ok ...

Mr Adults 3 questions : 
-this lines, is using the mat(matrix) from the file or the one after this function was applied  "rapi->rpgMultiplyBones(bones, numBones);"? : 

RichMat43 *bmat = (RichMat43 *)&bones[idx].mat;
tpos += bmat->TransformPoint(vpos)*w; 

- TransformPoint does a multiply ?? 

- When you say 1 -weight verts .. theat means in your code :
tpos += bmat->TransformPoint(vpos)*(1-w);
## Post #15
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-08T08:08:30+00:00
- Post Title: Need help on PS2 "matrix palette skinning"

Oh, no, not 1 minus weight, haha. Sorry, I just meant verts with only 1 active weight.

Anyway, the plugin is out there now, so you can look at its source in Noesis 3.0. The matrix multiply and transform operations are pretty standard fare (you can find math for that all over the internet), so hopefully you won't have any trouble with it.
## Post #16
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-04-08T22:00:45+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

OMG, OMG, i cant wait to see the plugin released in noesis.
## Post #17
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-05-05T06:47:32+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

Please help, face is missing
File from Saint Seiya Chapter Sanctuary
[delete](delete)
## Post #18
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-05T14:03:28+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

> Reply from dj082502
>
> 
Please help, face is missing
File from Saint Seiya Chapter Sanctuary
http://www.mediafire.com/?zaczir5n278i4r7
it work for me.
## Post #19
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-06-05T22:13:17+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

> Reply from CriticalError
>
> dj082502 wrote:
What Version of Noesis?
## Post #20
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-05T22:40:37+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

> Reply from dj082502
>
> CriticalError wrote:dj082502 wrote:


What Version of Noesis?latest 3.25 and old one 3.19
## Post #21
- Username: matematico666
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 10, 2011 5:34 am
- Post datetime: 2011-06-09T21:55:36+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

> Reply from CriticalError
>
> dj082502 wrote:
Please help, face is missing
File from Saint Seiya Chapter Sanctuary
http://www.mediafire.com/?zaczir5n278i4r7
it work for me.

Pleaseplease could you pass as you worked on this model. Thank you
## Post #22
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-05T12:05:43+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

> Reply from dj082502
>
> 
Please help, face is missing
File from Saint Seiya Chapter Sanctuary
Gmi format for Saint Seiya The Sanctuary PAL PS2 is very similar to Saint Seiya The Hades PAL PS2.
The two title are much alike, but they do have differences.
I can't find a face, too.

It must be PAL version.
## Post #23
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-02-07T23:31:26+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

> Reply from MrAdults
>
> Also, I noticed some of the GMI files in this game are compressed too. It was pretty easy to figure out since it's a very simple lzs algorithm:

MrAdults, could you please tell me which variation of LZS algorithm is used in this Saint Seiya? I'm trying to develop a Java tool to decompress some images (TIM2 and TIM3) from this game. But I'm not sure I can understand the code you posted. If I'm not asking too much (ok, I am), could you please put line comments on the tricky parts of your code?

I could just use Noesis and that great plugin, but I'm not exactly interested in 3D models and their textures, and although Noesis does a great job on .TPL files, there are many other binary files full of TIM images that Noesis can't handle (I think it's because it always expect an FJF header that is missing sometimes).
## Post #24
- Username: gustavofarias
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-08T01:47:51+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

Full source for the plugin is already included with Noesis, see the pluginsource.zip in any recent Noesis distribution. The decompression algorithm is in there too. It's extremely simple, about as standard-fare as you can get with LZ77-based algorithms (8-bit flag with 16-bit offset+length pairs for non-literals), and the function is very small. If you have any idea what LZ77 is then you should understand it at a glance. If you don't, you can always [learn](http://en.wikipedia.org/wiki/LZ77).
## Post #25
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-02-08T01:55:30+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

Thanks.
I saw the plugin source code. I just didn't get everything. You know, those kids playing with Java, they missed the right path   . I was trying to understand LZ77 from Wikipedia but I noticed that there are tens of similar LZ* algorithms. I wanted to make sure I was investing in the right one.
## Post #26
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-08T02:00:56+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

I see. Yeah, there are usually variations in LZ* implementations, and implementations tend to borrow elements from each other (especially common is the addition of op flags so they can combine various other forms of RLE, dictionary lookups, or whatever else)

So at least this one is a good starting point, because of its simplicity. Good luck.
## Post #27
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-02-10T16:56:52+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

I moved the discussion about compression to this topic:
[viewtopic.php?f=21&t=8251](http://forum.xentax.com/viewtopic.php?f=21&t=8251)

I hope you can give me more advices.
## Post #28
- Username: GoFeR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 06, 2012 3:27 am
- Post datetime: 2012-06-05T20:36:00+00:00
- Post Title: Re: Need help on PS2 "matrix palette skinning"

i extract all the meshes and textures from the saint seiya game and make the "constelation" form to put into the sims 2 as objects

























hope this like to you..
