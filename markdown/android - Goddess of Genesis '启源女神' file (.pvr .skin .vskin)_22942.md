## Post #1
- Username: slideblue
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 31, 2016 9:05 am
- Post datetime: 2020-11-02T13:04:58+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

Can someone help ripping models from this games? 
I just extracted from big mp3 file from chinese version,
.pvr files seem to be texture file, and .skin is models file, but i couldnt open these file.
(for pvr MaliTexture,   for .skin blender249 refer to [https://zenhax.com/viewtopic.php?f=5&t= ... 220#p52220](https://zenhax.com/viewtopic.php?f=5&t=12801&p=52220#p52220)
both didn't work) 

I've uploaded sample files.
[https://www.mediafire.com/file/rztxj1hs ... s.zip/file](https://www.mediafire.com/file/rztxj1hs9x3s1np/goddess_of_genesis.zip/file)
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-11-02T14:01:24+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

I have downloaded the Goddess of Genesis_v1.8.0_apkpure.com.xapk file (1.4 GB) to get more sample files.
It contains the main.22.com.zlongame.sea.gog.obb file (1.4 GB), but I don't know how can I unpack it.
## Post #3
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-02T14:53:35+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

[viewtopic.php?f=16&t=21385](https://forum.xentax.com/viewtopic.php?f=16&t=21385)

I asked a question about it before. Bigchillghost kindly created the decompression script.
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-11-02T14:59:28+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

Doesn't seem too complicated in terms of mesh data. I have extracted a few meshes using hex2obj, might need to be scaled using the bbox. I will think  of doing a proper tool for this.



Edit:

Actually nevermind. Szkaradek's blender script will work with a single change . Change line 52 to this

```
r=g.B(12)
```
## Post #5
- Username: slideblue
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 31, 2016 9:05 am
- Post datetime: 2020-11-02T15:30:52+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

I tried Szkaradek's script, but the blender2.49 console said below

Traceback
 File "starter.py", line 128, in Parser
AttlibuteError: 'Sys' object has no attribute 'parseFile' 

blender2.49 python version is 2.6.6, is it not supported?
## Post #6
- Username: slideblue
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 31, 2016 9:05 am
- Post datetime: 2020-11-02T17:15:06+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

I did wrong way, now i could open the model. Thanks for advise.
But there is no bone data or T-pose one?
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-11-02T18:47:26+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

> Reply from einherjar007 ↑Mon Nov 02, 2020 10:53 pm at Mon Nov 02, 2020 10:53 pm
>
> 
viewtopic.php?f=16&t=21385

I asked a question about it before. Bigchillghost kindly created the decompression script.

Thank you for your information.
After read your post, I have realized my program supports the Goddess of Genesis .skin/.vskin files, because the God Summoner game uses these files also.
## Post #8
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-03T02:30:02+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

*EDIT
I've checked a lot files, but skin has 2IKS and 3IKS headers, and it seems that 2IKS can be read.
I also speculate that the skeleton has changed from LEKS to a 2EKS header and that there may be some changes in the file format.
Some can be loaded by changing the header or changing the script, but they are broken.
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-12-26T22:50:25+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

> Reply from einherjar007 ↑Tue Nov 03, 2020 10:30 am at Tue Nov 03, 2020 10:30 am
>
> 
*EDIT
I've checked a lot files, but skin has 2IKS and 3IKS headers, and it seems that 2IKS can be read.
I also speculate that the skeleton has changed from LEKS to a 2EKS header and that there may be some changes in the file format.
Some can be loaded by changing the header or changing the script, but they are broken.

Hello einherjar007! I were checking this filetypes and you are right, the headers have been changing a bit and the script doesn't work I was trying to change simple things into the script but nothing x.x   , Also are some creatures that are divided in two .skin files, I'm not sure if the .skeleton file is the armature only, or it contains the animations. I'm attaching some samples, in case someone could take a look at them, thanks in advance!   

[https://www.mediafire.com/file/3gtue9vp ... sm.7z/file](https://www.mediafire.com/file/3gtue9vpt8cemud/samples_.skin_.skel_.sm.7z/file)
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-27T04:01:15+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

mb35_obj1.skin using meshFinder(Android)
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-12-27T05:09:09+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

> Reply from Durik256 ↑Tue Dec 27, 2022 12:01 pm at Tue Dec 27, 2022 12:01 pm
>
> 
mb35_obj1.skin using meshFinder(Android)

thanks Durik :')
## Post #12
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-12-28T06:47:26+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

all the links to the other samples were broken, so I only had the one sample of that lion to write the script on.


here is a partial code snippet of the script, the codebase gotten a bit large now and its too large to post.
the project can also be found on my [github](https://github.com/coreynguyen/bpy_god_summoner)

```
    Title:        	God Summoner Mesh Importer
    Description:  	Imports models from God Summoner on the PC
    Release:       	December 27 2022 
    Author:       	mariokart64n
    
    Notes:
    # ------------------------------------------------------------------------------ #
        Unknown data between buffers could cause files to crash due reading in the
        the wrong place.
        normals and other data are unknown in the vertex data, therefore it isn't
        really possible to write models back - Dec 27 2022
        
        When I reviewed this topic in relation to the mesh format there was mention
        of the files being compressed by lzo1x.
            https://forum.xentax.com/viewtopic.php?f=16&t=21385
        
        No samples were provided, but I located some source code on lzo1x decoding.
            https://github.com/ARM-software/u-boot/blob/master/lib/lzo/lzo1x_decompress.c
        
        This other game 'Goddess of Genesis' may also have the same formats,
        but I was unable to secure file samples, links were down.
            https://forum.xentax.com/viewtopic.php?t=22942

    
    Change Log:
    # ------------------------------------------------------------------------------ #
    
    [2022-12-27]
        Wrote it!
    

   ----------------------------------------------------------------------------------- '''


class fmtSM2_Skeleton:  # 4 Bytes + n bytes:Bone Data
    '''uint32_t'''
    num_bones = 0,

    '''Bone[n]'''
    bones = []

    # for SKEL file
    '''fmtSKEL'''
    skel = fmtSKEL()

    def size(self, type=0):
        nsize = 4
        if type == 0x00534D32:
            nsize += len(self.bones) * 36
        elif type == 0x534B4932:
            nsize += len(self.bones) * 32
        return nsize

    def read(self, f=fopen(), type=0):
        self.num_bones = readLong(f, unsigned)
        self.bones = []
        if self.num_bones > 0:
            self.bones = [fmtSM2_Bone] * self.num_bones
            for i in range(0, self.num_bones):
                self.bones[i] = fmtSM2_Bone()
                self.bones[i].read(f, type)
        return None

    def write(self, s=fopen()):
        self.num_bones = len(self.bones)
        writeLong(s, self.num_bones, unsigned)
        for i in range(0, self.num_bones):
            self.bones[i].write(s, type)
        return None


class fmtSM2_FaceBuf:  # 4 Bytes + n bytes:faces indices
    '''uint32_t'''
    num_faces = 0,

    '''uint16_t[3]'''
    faces = []

    def size(self):
        nsize = 4 + len(self.faces) * 3 * 2
        return nsize

    def read(self, f=fopen()):
        result = False
        self.num_faces = readLong(f, unsigned)
        self.faces = []
        if self.num_faces > 0:
            self.faces = [[int] * 3] * self.num_faces
            for i in range(0, self.num_faces):
                self.faces[i] = [readShort(f, unsigned), readShort(f, unsigned), readShort(f, unsigned)]
            result = True
        return result

    def write(self, s=fopen()):
        result = False
        self.num_faces = len(self.faces)
        writeLong(s, self.num_faces, unsigned)
        for i in range(0, self.num_faces):
            for v in range(0, 3): writeShort(s, self.faces[i][v], unsigned)
            result = True
        return result


class fmtSM2_Object:
    '''uint32_t'''
    name_len = 0

    '''char[n]'''
    name = ""

    '''uint16_t'''
    unk003 = 0  # ?? padding ??? insufficient samples to determine

    '''uint32_t'''
    max_index = 0  # same as vertex count from header

    '''uint8_t'''
    unk004 = 0  # ?? padding ??? insufficient samples to determine

    '''float[3]'''
    bb_max = [0.0, 0.0, 0.0]  # same as in header

    '''float[3]'''
    bb_min = [0.0, 0.0, 0.0]  # same as in header

    '''FaceBuf[n]'''
    faceBuf = []  # no count? read until end is reached

    '''uint32_t'''
    unk005 = 0  # ?? padding ??? insufficient samples to determine
    '''
        its unknown how this block terminates, and theres not enough samples to
        investigate..
        I assume that when a 4byte null is reached the read is terminated

        however the padding afterwards seems to vary in sample
    '''
    '''uint32_t'''
    padding = 0

    def size(self):
        nsize = 46 + self.padding + len(self.name)
        for i in range(0, len(self.faceBuf)):
            nsize += self.faceBuf[i].size()
        return nsize

    def seekPastWhiteSpace(self, f=fopen(), len=16):
        '''
            this is a hack to skip and 0's or padding after the face buffer
        '''
        p = ftell(f)
        for i in range(0, len):
            b = readByte(f, unsigned)
            if b > 0 or b == None:
                fseek(f, -1, seek_cur)
                break
        # return number of bytes skipped
        return (ftell(f) - p)

    def read(self, f=fopen(), stopAddr=0):
        self.name_len = readLong(f, unsigned)
        self.name = ""
        for i in range(0, self.name_len):
            b = readByte(f, unsigned)
            if b > 0: self.name += bit.IntAsChar(b)

        self.unk003 = readShort(f, unsigned)
        self.max_index = readLong(f, unsigned)
        self.unk004 = readByte(f, unsigned)
        self.bb_max = [readFloat(f), readFloat(f), readFloat(f)]
        self.bb_min = [readFloat(f), readFloat(f), readFloat(f)]
        self.faceBuf = []
        fb = fmtSM2_FaceBuf()
        while ftell(f) < stopAddr:
            fb = fmtSM2_FaceBuf()
            if not fb.read(f): break
            append(self.faceBuf, fb)

        self.unk005 = readLong(f, unsigned)

        # Unsure how the padding in this area works, skip until a none 0 is reached
        padding = self.seekPastWhiteSpace(f)
        format("padding: \t%:@ %\n", (padding, ftell(f)))
        return None

    def write(self, s=fopen()):
        self.name_len = len(self.name) + 1
        writeLong(s, self.name_len, unsigned)
        writeString(s, self.name)
        writeShort(s, self.unk003, unsigned)
        writeLong(s, self.max_index, unsigned)
        writeByte(s, self.unk004, unsigned)
        for i in range(0, 3): writeFloat(s, self.bb_max[i])
        for i in range(0, 3): writeFloat(s, self.bb_min[i])
        for i in range(0, len(self.faceBuf)): self.faceBuf[i].write(s)
        writeLong(s, 0, unsigned)
        writeLong(s, self.unk005, unsigned)
        for i in range(0, self.padding): writeByte(s, 0, unsigned)
        return None


class fmtSM2_Vertex:  # 20 Bytes
    '''
        I'm unable to decode the normals and what could be also be bi-normals
        writing new geometry back to the file is therefore not possible or advise.
    '''

    '''float[3]'''
    position = [0.0, 0.0, 0.0]

    '''float[2]'''
    texcorrd = [0.0, 0.0, 0.0]

    '''float[4]'''
    weight = [1.0, 0.0, 0.0, 0.0]

    '''uint8_t[4]'''
    normal = [0.0, 0.0, 0.0, 0.0]

    '''uint8_t[4]'''
    boneid = [0, -1, -1, -1]

    '''uint8_t[4]'''
    binormal = [0.0, 0.0, 0.0, 0.0]

    def read(self, f=fopen(), type=0):
        self.position = [readHalf(f), readHalf(f), readHalf(f)]
        w = readHalf(f)
        self.position = [self.position[0] + w, self.position[1] + w, self.position[2] + w]
        self.texcorrd = [readHalf(f), readHalf(f), 0.0]
        if type == 0x00534D32:  # 'SM2' 20 Bytes
            self.normal = [readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned),
                           readByte(f, unsigned)]  # normal?
            self.binormal = [readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned),
                             readByte(f, unsigned)]  # tangent?
        elif type == 0x534B4932:  # 'SKI2' 32 Bytes
            self.weight = [readHalf(f), readHalf(f), readHalf(f), readHalf(f)]  # weight
            self.normal = [readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned),
                           readByte(f, unsigned)]  # normal?
            self.boneid = [readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned),
                           readByte(f, unsigned)]  # boneid
            self.binormal = [readByte(f, unsigned), readByte(f, unsigned), readByte(f, unsigned),
                             readByte(f, unsigned)]  # tangent?
            # round off the weights, theres some issues with the half float function
            for i in range(0, len(self.weight)): self.weight[i] = float(int(self.weight[i] * 1000)) / 1000.0
        return None

    def write(self, s=fopen()):
        for i in range(0, 3): writeHalf(s, self.position[i])
        self.texcorrd = [self.texcorrd[1], self.texcorrd[1], 0.0]
        for i in range(0, 2): writeHalf(s, self.texcorrd[i])
        #for i in range(0, 4): writeShort(s, self.unk009[i], unsigned)
        return None


class fmtSM2:  # 60 Bytes + n Bytes:Buffers
    '''uint32_t'''
    type = 0x00534D32  # SM2, SKI2

    '''uint32_t'''
    version = 0x0105011B

    '''uint32_t'''
    num_verts = 0

    '''float[3]'''
    bb_min = [0.0, 0.0, 0.0]

    '''float[3]'''
    bb_max = [0.0, 0.0, 0.0]

    '''float'''
    draw_dist = [0.0, 0.0, 0.0]

    '''uint32_t'''
    unk001 = 0  # Padding?

    '''uint32_t'''
    unk002 = 0  # Padding?

    '''uint32_t'''
    verts_addr = 0

    '''uint32_t'''
    meshs_addr = 0

    '''uint32_t'''
    bones_addr = 0

    '''Vertex'''
    verts = []

    '''Object'''
    meshs = fmtSM2_Object()

    '''Skeleton'''
    bones = fmtSM2_Skeleton()

    def size(self, type=0):
        nsize = 52
        if self.type == 0x00534D32:
            nsize += 8 + len(self.verts) * 20 + self.meshs.size() + self.bones.size()
        else:
            nsize += 8 + len(self.verts) * 32 + self.meshs.size() + self.bones.size(self.type)
        return nsize

    def read(self, f=fopen(), skelfile=""):
        fsize = f.size
        result = False
        if fsize > 52:
            self.type = readLong(f, unsigned)
            if self.type == 0x00534D32 or self.type == 0x534B4932:
                self.version = readLong(f, unsigned)
                if self.type == 0x00534D32:
                    self.num_verts = readLong(f, unsigned)

                elif self.type == 0x534B4932:
                    self.num_verts = readShort(f, unsigned)
                    self.verts_addr = readShort(f, unsigned)

                self.bb_min = [readFloat(f), readFloat(f), readFloat(f)]
                self.bb_max = [readFloat(f), readFloat(f), readFloat(f)]
                self.draw_dist = readFloat(f)
                if self.type == 0x00534D32:
                    self.unk001 = readLong(f, unsigned)
                    self.unk002 = readLong(f, unsigned)
                    self.verts_addr = readLong(f, unsigned)

                self.meshs_addr = readLong(f, unsigned)
                self.bones_addr = readLong(f, unsigned)

                self.verts = []
                if self.verts_addr > 0 and self.num_verts > 0:
                    self.verts = [fmtSM2_Vertex] * self.num_verts
                    fseek(f, self.verts_addr, seek_set)
                    for i in range(0, self.num_verts):
                        self.verts[i] = fmtSM2_Vertex()
                        self.verts[i].read(f, self.type)

                if self.type == 0x534B4932: self.meshs_addr = ftell(f)

                self.meshs = []
                if self.meshs_addr > 0 and self.meshs_addr < fsize:
                    fseek(f, self.meshs_addr, seek_set)
                    self.meshs = fmtSM2_Object()
                    self.meshs.read(f, fsize)

                if self.type == 0x534B4932: self.bones_addr = ftell(f)

                self.bones = []
                if self.bones_addr > 0 and self.bones_addr < fsize:
                    fseek(f, self.bones_addr, seek_set)
                    self.bones = fmtSM2_Skeleton()
                    self.bones.read(f, self.type)

                    if self.type == 0x534B4932 and skelfile != None and skelfile != "" and doesFileExist(
                            skelfile) == True:
                        if not self.bones.skel.open(skelfile):
                            format("Warning: \tFailed to locate SKEL file\n")

                result = True
            else:
                format("Error: \tUnsupported File Type:0x\n", (self.type))
        else:
            format("Error: \tInvalid File Size {%}\n", (fsize))
        return result

    def write(self, s=fopen()):
        ptr = 60  # Vertex Buffer Position, Always 60
        self.num_self.verts = len(self.verts)
        writeLong(s, 0x00534D32, unsigned)  # 'SM2'
        writeLong(s, self.version, unsigned)
        writeLong(s, self.num_self.verts, unsigned)
        for i in range(0, 3): writeFloat(s, self.bb_min[i])
        for i in range(0, 3): writeFloat(s, self.bb_max[i])
        writeFloat(s, self.draw_dist)
        writeLong(s, self.unk001, unsigned)
        writeLong(s, self.unk002, unsigned)
        writeLong(s, ptr, unsigned)  # Vertices Address
        ptr += self.num_self.verts * 20
        writeLong(s, ptr, unsigned)  # Objects Address
        ptr += self.meshs.size()
        writeLong(s, ptr, unsigned)  # Bones Address
        for i in range(0, self.num_self.verts): self.verts[i].write(s)
        self.meshs.write(s)
        self.bones.write(s)
        return None

    def build(self, texName="", mscale=0.00254, clear_scene=False, impSkin=True, skelName = "Skeleton", rotOff=(matrix3([-1, 0, 0, 0], [0, 0, 1, 0], [0, 1, 0, 0], [0, 0, 0, 1]))):

        # ClearScene
        if clear_scene == True: deleteScene(['MESH', 'ARMATURE'])

        # Build Skeleton
        boneNames = []
        boneArray = boneSys(skelName)

        for i in range(0, len(self.bones.bones)):
            bname = self.bones.bones[i].name
            n = self.bones.skel.name(self.bones.bones[i].boneid)
            if n != "": bname = n
            boneArray.createBone(
                bname,
                [self.bones.bones[i].position[0] * mscale, self.bones.bones[i].position[1] * mscale,
                 self.bones.bones[i].position[2] * mscale],
                [self.bones.bones[i].position[0] * mscale, (self.bones.bones[i].position[1] + 60) * mscale,
                 self.bones.bones[i].position[2] * mscale],
                [0, 1, 0]
                )
                
            m = inverse(self.bones.bones[i].asMat4x3())
            m = m.multiply(rotOff)
            k = m.position()
            m.setPosition([-(k[0] * mscale), k[1] * mscale, k[2] * mscale])
            
            
            boneArray.editMode(True)
            # -------------------------- B O N E  E D I T  M O D E  O P E N E D -------------------------- #
            boneArray.setTransform(bname, m.asMat4())
            
            # -------------------------- B O N E  E D I T  M O D E  C L O S E D -------------------------- #
            boneArray.editMode(False)


            append(boneNames, bname)
        
        
        
        boneArray.editMode(True)
        # -------------------------- B O N E  E D I T  M O D E  O P E N E D -------------------------- #
        for i in range(0, len(self.bones.bones)):
            p = self.bones.skel.parent(self.bones.bones[i].boneid)
            if p > -1:
                for j in range(0, len(self.bones.bones)):
                    if self.bones.bones[j].boneid == p:
                        boneArray.setParent(boneNames[i], boneNames[j])
                        break
        
        boneArray.rebuildEndPositions(mscale=mscale)
        
        # -------------------------- B O N E  E D I T  M O D E  C L O S E D -------------------------- #
        boneArray.editMode(False)


        # Build Meshes
        vertArray = []
        tvertArray = []
        
        if len(self.verts) > 0:
            vertArray = [[float] * 3] * self.num_verts
            tvertArray = [[float] * 3] * self.num_verts

            for i in range(0, len(self.verts)):
                vertArray[i] = [self.verts[i].position[0] * mscale, self.verts[i].position[2] * mscale,
                                self.verts[i].position[1] * mscale]
                tvertArray[i] = [self.verts[i].texcorrd[0], self.verts[i].texcorrd[1], 0.0]

        for i in range(0, len(self.meshs.faceBuf)):  # these appear to be Level of Details meshes
            if len(self.meshs.faceBuf[i].faces) == 0: continue
            
            mshName = "Mesh " + str(i)
            if self.meshs.name != "": mshName = self.meshs.name + " (" + str(i) + ")"
            
            mat = StandardMaterial()
            
            if texName != "" and doesFileExist(texName) == True:
                mat.diffuseMap(str(texName))
            
            msh = mesh(
                vertices=vertArray,
                tverts=[tvertArray],
                faces=self.meshs.faceBuf[i].faces,
                obj_name=mshName,
                materials=[mat]
                )
            
            if i > 0: hide(msh)
            
            
            # Import Weights
            if impSkin==True and len(self.bones.bones) > 0:

                weights = []
                boneids = []

                # Create Skin Modifier
                skinMod = skinOps(msh, boneArray.armature)

                # Add self.bones to modifier
                vi = 1
                bu = 0
                for vi in range(0, len(self.bones.bones)):
                    if vi + 1 == len(self.bones.bones): bu = 1
                    skinMod.addbone(boneNames[vi], bu)

                # Get Number of Bones in Skin Modifier
                boneListCount = skinMod.GetNumberBones()

                # Build Bone List Map
                boneMap = []
                nodeName = ""
                if boneListCount > 0:

                    # dimension bone map
                    boneMap = [int] * boneListCount

                    # Search for Bone Id in boneArray:Array with all the self.bones
                    for vi in range(0, boneListCount):
                        # Initialize Bone Map to 1st bone
                        boneMap[vi] = 0

                        # get bone name from skin modifier list
                        nodeName = skinMod.GetBoneName(vi, 0)

                        # search bonearray
                        for fi in range(0, len(self.bones.bones)):
                            # if bone name is found, assign to bone map

                            if boneNames[fi] == nodeName:
                                boneMap[vi] = fi

                # apply weights to skin modifier
                bi = []
                we = []
                for vi in range(0, len(self.verts)):
                    bi = []
                    we = []
                    for fi in range(0, len(self.verts[vi].weight)):
                        if self.verts[vi].weight[fi] > 0.0:
                            x = findItem(boneMap, self.verts[vi].boneid[fi])
                            if x > 0:
                                append(bi, x)
                                append(we, self.verts[vi].weight[fi])
                    if len(we) == 0:
                        we = [1.0]
                        bi = [0]
                    skinMod.ReplaceVertexWeights(vi, bi, we)
        return None


def read (file="", impSkin=True, mscale=0.00254, skelName = ""):
    if file != None and file != "":
        
                
        fext = getFilenameType(file)


        if matchPattern(fext, pattern=".sm") or matchPattern(fext, pattern=".skin"):
            f = fopen(file, "rb")
            if f != None:
                fpath = getFilenamePath(file)
                fname = getFilenameFile(file)
                skel_file = fpath + fname + ".skel"
                mapd_file = fpath + fname + ".dds"
                if not doesFileExist(skel_file):
                    file = ""
                    files = getFiles(fpath + "*.skel")
                    for file in files:
                        skel_file = file
                        break

                if not doesFileExist(mapd_file):
                    file = ""
                    files = getFiles(fpath + "*.dds")
                    for file in files:
                        mapd_file = file
                        break

                sm = fmtSM2()
                sm.read(f, skelfile=skel_file)
                sm.build(mapd_file, impSkin=impSkin, mscale=mscale, skelName=skelName)
                del sm
                fclose(f)
            else:
                format("failed to open file {%}\n", (file))
        else:
            format("file extension not supported {%}\n", (fext))
    return None


def write(sm = fmtSM2(), file=""):
    if file != None and file != "" and sm != None:
        fext = getFilenameType(file)
        if matchPattern(fext, pattern=".sm"):
            s = fopen(file, "wb")
            if s != None:
                sm.write(s)

                fclose(s)
            else: format("failed to save file {%}\n", (file))
        else: format("file extension not supported {%}\n", (fext))
    return None

```


here's a python script that adds import to blender for *.sm and *.skin
download the zip attached and copy the contents of the script into blender's script tab and then press play that will temporarily install the import to the files > import menu until you restart blender.
[bpy_god_summoner.zip](https://xentaxbackup.github.io/file/23215_bpy_god_summoner.zip)
## Post #13
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-12-28T14:08:26+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

> Reply from mariokart64n ↑Wed Dec 28, 2022 2:47 pm at Wed Dec 28, 2022 2:47 pm
>
> 
here's a python script that adds import to blender for *.sm and *.skin
download the zip attached and copy the contents of the script into blender's script tab and then press play that will temporarily install the import to the files > import menu until you restart blender.
Thanks mariokart64n!
## Post #14
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2023-02-06T02:08:52+00:00
- Post Title: android - Goddess of Genesis '启源女神' file (.pvr .skin .vskin)

can i ask what blender version you tested this. BC I test in most of them and I can load the scrip but not the mesh. Blender load go not responding for some min and next nothing change on viewport no new mesh load.
