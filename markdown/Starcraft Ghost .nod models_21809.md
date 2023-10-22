## Post #1
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2020-02-26T00:51:02+00:00
- Post Title: Starcraft Ghost .nod models

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("Starcraft Ghost model", ".nod")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG

    #noesis.logPopup()
    return 1


#check if it's this type based on the data
def noepyCheckType(data):
    bs = NoeBitStream(data)
    idt = bs.readUInt()
    if (idt != 0x0000000A):
        noesis.logOutput('bad ID tag {:08X}\r\n'.format(idt))
        return 0
    return 1

#load the model
def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    
    bs.readUInt()
    hdr = []
    hdr.append(bs.readByte()) #Materials
    hdr.append(bs.readByte()) #Bone Matrices
    hdr.append(bs.readByte()) #Number of Vert pools
    hdr.append(bs.readByte()) #Number of CC entries? seems to line up.
    
    bs.seek(0x24,NOESEEK_ABS)
    vtype = bs.readInt() #Number of bone weights per vertex; This can be 3 4 or 5 and still means 0,1,2... See Lurker.nod
    vcnt = bs.readInt() #Vertices count
    noesis.logOutput('Vert Count 1 {:08X}\r\n'.format(vcnt))
    
    #bs.seek(0x30,NOESEEK_ABS)
    utype = bs.readInt() #Number of bone weights per vertex
    unkcnt = bs.readInt() #Vertices count, second pool
    noesis.logOutput('Vert Count 2 {:08X}\r\n'.format(unkcnt))
    
    #bs.seek(0x38,NOESEEK_ABS)
    utype2 = bs.readInt() #Number of bone weights per vertex
    unkcnt2 = bs.readInt() #Vertices count, third pool
    noesis.logOutput('Vert Count 3 {:08X}\r\n'.format(unkcnt2))
    
    bs.seek(0x44,NOESEEK_ABS)
    tcnt = bs.readInt() #This represents the number of Int16 shorts in the triangle block
    noesis.logOutput('Tri Count {:08X}\r\n'.format(tcnt))
    
    texlist = []
    matlist = []
    bonelist = []
    vertices = []
    unk = []
    unk2 = []
    faces = []
    tris = []
    submeshconfigs = []
    
    
    posbuff = bytearray()
    normbuff = bytearray()
    uvbuff = bytearray()
    bwtbuff = bytearray() #bone weight buffer
    bidbuff = bytearray() #Bone ID buffer
    
    
    bs.seek(0x5C,NOESEEK_ABS) #End of header
    for i in range(0, hdr[0]):
        matlist.append(bs.readBytes(0x20).decode('utf-8').strip('\x00')) #String materials
        noesis.logOutput('  {}\r\n'.format(matlist[i]))
    #noesis.logOutput('Materials complete  Location:{:08X}\r\n'.format(bs.tell()))
    
    bonelist.append(bs.readBytes(0x40 * hdr[1])) #Bone matrices, 4x4 floats?
    #noesis.logOutput('Matrices complete  Location:{:08X}\r\n'.format(bs.tell()))
    
    #noesis.logOutput('Vertex pool 1 complete\tLocation:{0:08X}; Count:{2:04X}; Bones:{1:02X}\r\n'.format(bs.tell(),vtype,vcnt))
    readVertex(bs,vcnt,vtype,posbuff,normbuff,uvbuff,bwtbuff,bidbuff)
    
    #noesis.logOutput('VertExtra pool 1 complete\tLocation:{0:08X}; Count:{2:04X}; Bones:{1:02X}\r\n'.format(bs.tell(),vtype,vcnt))
    readVertExtra(bs,vcnt,vtype,posbuff,normbuff,uvbuff,bwtbuff,bidbuff)
    
    #noesis.logOutput('Vertex pool 2 complete\tLocation:{0:08X}; Count:{2:04X}; Bones:{1:02X}\r\n'.format(bs.tell(),utype,unkcnt))
    readVertex(bs,unkcnt,utype,posbuff,normbuff,uvbuff,bwtbuff,bidbuff)
    
    #noesis.logOutput('VertExtra pool 2 complete\tLocation:{0:08X}; Count:{2:04X}; Bones:{1:02X}\r\n'.format(bs.tell(),utype,unkcnt))
    readVertExtra(bs,unkcnt,utype,posbuff,normbuff,uvbuff,bwtbuff,bidbuff)
    
    #noesis.logOutput('Vertex pool 3 complete\tLocation:{0:08X}; Count:{2:04X}; Bones:{1:02X}\r\n'.format(bs.tell(),utype2,unkcnt2))
    readVertex(bs,unkcnt2,utype2,posbuff,normbuff,uvbuff,bwtbuff,bidbuff)
    
    #noesis.logOutput('VertExtra pool 3 complete\tLocation:{0:08X}; Count:{2:04X}; Bones:{1:02X}\r\n'.format(bs.tell(),utype2,unkcnt2))
    readVertExtra(bs,unkcnt2,utype2,posbuff,normbuff,uvbuff,bwtbuff,bidbuff)
    
    #noesis.logOutput('  Total vertices: {0}  0x{0:04X}  Location:{0:08X}\r\n'.format(vcnt+unkcnt+unkcnt2,bs.tell()))
    
    faces.append(bs.readBytes(0x02 * tcnt))
    #noesis.logOutput('Tridata complete  Location:{:08X}\r\n'.format(bs.tell()))
    
    rapi.rpgSetPosScaleBias((1.00,1.00,1.00),(0,0,0))
    #rapi.rpgSetUVScaleBias((0.9900,0.9900,0.9900),(0.005,0.005,0.005))


    for i in range(hdr[3]):
        submeshconfigs.append(SubMeshConfig(bs))
    
    noesis.logOutput('Submesh configs complete  Location:{:08X}\r\n'.format(bs.tell()))
    
    
    
    #rapi.rpgBindPositionBuffer(posbuff, noesis.RPGEODATA_FLOAT, 0x0C)
    #rapi.rpgBindNormalBuffer(normbuff, noesis.RPGEODATA_FLOAT, 0x0C) 
    #rapi.rpgBindUV1Buffer(uvbuff, noesis.RPGEODATA_FLOAT, 0x08)

    #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, len(posbuff)//0x0C, noesis.RPGEO_POINTS, 1)
    reportHighestTri(faces[0])

    index = 0
    firstvert = 0


    #for i in range(1):
    for i in range(hdr[3]):
        rapi.rpgSetName("Mesh{}".format(submeshconfigs[i].MeshID))
        ##########TEST###########

        rapi.rpgBindPositionBuffer(posbuff[firstvert*0xC:(firstvert*0xC)+((submeshconfigs[i].totalverts+2)*0xC)], noesis.RPGEODATA_FLOAT, 0x0C)
        rapi.rpgBindNormalBuffer(normbuff[firstvert*0xC:(firstvert*0xC)+((submeshconfigs[i].totalverts+2)*0xC)], noesis.RPGEODATA_FLOAT, 0x0C) 
        rapi.rpgBindUV1Buffer(uvbuff[firstvert*0x8:(firstvert*0x8)+((submeshconfigs[i].totalverts+2)*0x8)], noesis.RPGEODATA_FLOAT, 0x08)

        ##########TEST###########
        
        stripcount = submeshconfigs[i].lod0strip
        tricount   = submeshconfigs[i].lod0tri
        noesis.logOutput('Submesh strips:{:04X} Index:{:04X}\r\n'.format(stripcount,int(index/2)))
        #if(stripcount > 0):
        rapi.rpgCommitTriangles(faces[0][index:], noesis.RPGEODATA_USHORT, stripcount, noesis.RPGEO_TRIANGLE_STRIP, 1)
        index += (2*stripcount                 )
        
        noesis.logOutput('Submesh tris:{:04X} Index:{:04X}\r\n'.format(tricount,int(index/2)))
        #if(tricount > 0):
        rapi.rpgCommitTriangles(faces[0][index:], noesis.RPGEODATA_USHORT, tricount, noesis.RPGEO_TRIANGLE, 1)
        index += (2*tricount                 )
        
        index += (2*submeshconfigs[i].lod1strip)
        index += (2*submeshconfigs[i].lod2strip)
        index += (2*submeshconfigs[i].lod3strip)
        
        index += (2*submeshconfigs[i].lod1tri)                                                                 
        index += (2*submeshconfigs[i].lod2tri)                                                                 
        index += (2*submeshconfigs[i].lod3tri)
        
        ##########TEST###########
        rapi.rpgBindBoneIndexBuffer(bidbuff[firstvert*0x8:], noesis.RPGEODATA_INT, 0x08, 2)
        rapi.rpgBindBoneWeightBuffer(bwtbuff[firstvert*0x8:], noesis.RPGEODATA_FLOAT, 0x08, 2)
        firstvert += (submeshconfigs[i].totalverts-0)
        
        ##########TEST###########
        
    # Assign Bone weights and indices
    #rapi.rpgBindBoneIndexBuffer(bidbuff, noesis.RPGEODATA_INT, 0x08, 2)
    #rapi.rpgBindBoneWeightBuffer(bwtbuff, noesis.RPGEODATA_FLOAT, 0x08, 2)

    
    mdl = rapi.rpgConstructModel()
    
    
    mdlList.append(mdl)
    
    #rapi.rpgClearBufferBinds() 
    return 1
    
def readVertex(bs,count,bones,posbuff,normbuff,uvbuff,bwtbuff,bidbuff):
    if bones == 2 or bones == 5:#hdr[2] == 3: # 0x30 sized vertices
        for i in range(count):
            posbuff += bs.readBytes(0x0C)
            normbuff += bs.readBytes(0x0C)
            uvbuff += bs.readBytes(0x08)
            #bs.readBytes(0x10)
            bwtbuff += bs.readBytes(0x04) #float weight
            bidbuff += bs.readBytes(0x04) #int ID
            bwtbuff += bs.readBytes(0x04) #float weight
            bidbuff += bs.readBytes(0x04) #int ID
            
    if bones == 1 or bones == 4:#hdr[2] == 3: # 0x30 sized vertices
        for i in range(count):
            posbuff += bs.readBytes(0x0C)
            normbuff += bs.readBytes(0x0C)
            uvbuff += bs.readBytes(0x08)
            #bs.readBytes(0x04)
            bwtbuff += struct.pack('f',1) #Assume 1 since no weight is given?
            bidbuff += bs.readBytes(0x04) #Bone ID
            bwtbuff += struct.pack('f',0) #Assumed values since no bone is specified
            bidbuff += struct.pack('i',0) #Assumed values since no bone is specified
            
    if bones == 0 or bones == 3:#hdr[2] == 1 or hdr[2] == 2 : # 0x20 sized vertices
        for i in range(count):
            posbuff += bs.readBytes(0x0C)
            normbuff += bs.readBytes(0x0C)
            uvbuff += bs.readBytes(0x08)
            bwtbuff += struct.pack('f',1) #Assumed values since no bone is specified
            bidbuff += struct.pack('i',0) #Assumed values since no bone is specified
            bwtbuff += struct.pack('f',0) #Assumed values since no bone is specified
            bidbuff += struct.pack('i',0) #Assumed values since no bone is specified
    
    #I HAVE NO IDEA WHAT THIS IS
    #Its a bunch of floats with no index values. Looks like a matrix 3x3 but what would that even be for?
    
def readVertExtra(bs,count,bones,posbuff,normbuff,uvbuff,bwtbuff,bidbuff):
    if bones == 3:
        for i in range(count):
            bs.readBytes(0x24)
    if bones == 4:
        for i in range(count):
            bs.readBytes(0x24)
    if bones == 5:
        for i in range(count):
            bs.readBytes(0x24)
    
def reportHighestTri(input):
    tmp = struct.unpack("H"*(len(input)//2),input)
    output = 0
    idx = -1
    for i in range(len(tmp)):
        old = output
        output = max(output,tmp[i])
        if old != output: idx = i
    noesis.logOutput("  Highest vertex ID in triangle list:{:04X} ; Index:{:04X}\r\n".format(output,idx))
    
    
    
class SubMeshConfig:
    def __init__(self, bs):
        self.MeshID     = bs.readInt()
        self.lod0strip  = bs.readShort()
        self.lod0tri    = bs.readShort()
        self.lod0verts  = bs.readShort()
        
        self.lod1strip  = bs.readShort()
        self.lod1tri    = bs.readShort()
        self.lod1verts  = bs.readShort()
        
        self.lod2strip  = bs.readShort()
        self.lod2tri    = bs.readShort()
        self.lod2verts  = bs.readShort()
        
        self.lod3strip  = bs.readShort()
        self.lod3tri    = bs.readShort()
        self.lod3verts  = bs.readShort()
        
        self.totalverts = bs.readShort()
        
        self.tv2        = bs.readShort()
        self.unknown    = bs.readBytes(0x18)
        #noesis.logOutput("  TotalVerts:{:04X}\tMeshID:{:04X}\r\n".format(self.totalverts,self.MeshID))
```


EDIT:
A suggestion I got on discord led me to finding some of the information regarding the missing triangles and strip termination codes. I've not updated the script yet as its still a mess.
Will update further once I have something anyone other than me could read.

EDIT2:
[https://i.imgur.com/eozCM7k.png](https://i.imgur.com/eozCM7k.png)
I have updated the script such that it now decodes the triangles of... most models correctly Nova.nod is still completely screwed up, but NovaCinematic and other variants are perfectly fine.
If anyone has suggestions, I'm open to hearing them.
I'm also still not entirely certain how to handle the skeletal construction (I've only ever tried that twice, and only succeeded once, with noesis) but I believe I've read in the pertinent bone IDs and weights...

I discovered some particularly uncommon extra data related to vertices in the file Lurker.nod
If anyone can give me an idea what it is, I've labeled the read function for it readVertExtra, and included several commented out logging functions to report where in a file is being read to the noesis log.
## Post #2
- Username: feber13
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 28, 2017 4:54 am
- Post datetime: 2020-04-16T23:26:51+00:00
- Post Title: Starcraft Ghost .nod models

hmm how did you get the game?
