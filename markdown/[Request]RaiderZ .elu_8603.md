## Post #1
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-21T12:40:06+00:00
- Post Title: [Request]RaiderZ .elu

Hi guys , i'm a your italian fun and i follow this forum since a long time.
I'm trying to open models from RaiderZ :  i have extracted models from the client but i cant open them. I have the noesis plugins to open .elu raiderZ but when i put the plugin in plugins folder , noesis doesn't work.


I'm sorry if i 'm wrong section and if my english is not very well


this is the noesis plugin : 

#Binary parser template

import os, sys
from Sanae3D.lib.StructReader import StructReader
from Sanae3D.lib.ModelObject import Model3D

class RaiderZ_elu(Model3D):

    def __init__(self, obj3D=None, outFile=None, inFile=None):

        super(RaiderZ_elu,self).__init__("ELU")
        self.obj3D = obj3D
        self.inFile = inFile
        self.outFile = outFile
        self.normals = []
        self.uvs = []

    def parse_faces(self, meshName):

        numFaces = self.inFile.read_long()
        print "%d faces" %numFaces
        self.inFile.seek(8, 1)
        for i in xrange(numFaces):
            vertCount = self.inFile.read_long()
            info = self.inFile.read_short(18)
            v1, v2, v3 = info[0], info[6], info[12]
            self.inFile.seek(2, 1) #unk

            self.create_face(meshName, i)
            self.add_face_verts(meshName, i, [v1, v2, v3])

    def parse_vertices(self, meshName):

        numVerts = self.inFile.read_long()
        for i in xrange(numVerts):
            vx, vz, vy = self.inFile.read_float(3)

            self.create_vertex(meshName, i)
            self.add_coords(meshName, i, [vx, vy, vz])

        numNorm = self.inFile.read_long()
        for i in xrange(numNorm):
            nx, ny, nz = self.inFile.read_float(3)
            self.normals.append([nx, ny, nz])

        unk3 = self.inFile.read_long()
        for i in xrange(unk3):
            self.inFile.read_float(4)

        unk4 = self.inFile.read_long()
        for i in xrange(unk4):
            self.inFile.read_float(3)

        numUV = self.inFile.read_long()
        for i in xrange(numUV):
            self.inFile.read_float(3)

        unk5 = self.inFile.read_long()
        self.inFile.seek(unk5 * 12, 1)

    def parse_mesh(self, numMesh):

        charLen = self.inFile.read_long()
        meshName = self.inFile.read_string(charLen).strip("\x00")
        index = self.inFile.read_long()

        self.create_object(meshName)
        print meshName

        self.inFile.seek(5, 1)
        unk1 = self.inFile.read_long()
        if unk1 in [0x0, 0x2000]:
            self.inFile.seek(72, 1)
        else:
            print "unknown unk1", unk1

        self.parse_vertices(meshName)
        self.parse_faces(meshName)

    def parse_file(self):
        '''Main parser method. Can be replaced'''

        magic = self.inFile.read_string(4)
        version, numMat, numMesh = self.inFile.read_long(3)
        self.parse_mesh(numMesh)


def read_file(path):
    '''Read the file'''

    openFile = StructReader(open(path, 'rb'))
    obj = RaiderZ_elu(inFile=openFile)
    obj.parse_file()
    openFile.close()
    return obj

def write_file(path):

    pass

def definitions():
    '''Return the header, extension, and a description of the format'''

    return "\x60\xF0\x07\x01", "ELU", "RaiderZ ELU"

if __name__ == '__main__':

    file1 = "frog.elu"
    file2 = "npc_drum01.elu"
    file3 = "temple_of_renas_arch_a_01.elu"
    file4 = "npc-obj_anvil01.elu"
    obj = read_file(file2)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-21T13:12:16+00:00
- Post Title: [Request]RaiderZ .elu

This is a Sanae3d plugin.
## Post #3
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-21T13:20:03+00:00
- Post Title: [Request]RaiderZ .elu

> Reply from finale00
>
> This is a Sanae3d plugin.
how can i download it ?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-21T13:39:46+00:00
- Post Title: [Request]RaiderZ .elu

[viewtopic.php?f=29&t=6932](http://forum.xentax.com/viewtopic.php?f=29&t=6932)
## Post #5
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-21T16:05:55+00:00
- Post Title: [Request]RaiderZ .elu

> Reply from finale00
>
> viewtopic.php?f=29&t=6932

i have done everythink but it doesn't work . Maybe i don't understand very well the english ç_ç so can you give me blender folder with sanae3D working ? Please ç_ç
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-21T16:47:52+00:00
- Post Title: [Request]RaiderZ .elu

Just download [http://www.mediafire.com/download.php?ye67dkt02ds5cs5](http://www.mediafire.com/download.php?ye67dkt02ds5cs5)
Install Python 2.7

And it should work on command-line.
If you want to use blender...it works for blender 2.49.
## Post #7
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-21T17:33:34+00:00
- Post Title: [Request]RaiderZ .elu

> Reply from finale00
>
> Just download http://www.mediafire.com/download.php?ye67dkt02ds5cs5
Install Python 2.7

And it should work on command-line.
If you want to use blender...it works for blender 2.49.
i followed the ReadMe but it doesn't work , probably i erred somethink...... ç_ç can you give me blender folder with all plugins installed ?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-21T20:20:50+00:00
- Post Title: [Request]RaiderZ .elu

Just use it as command-line tool.
Blender was some project I tried to get at but never completed.
## Post #9
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-21T21:30:57+00:00
- Post Title: [Request]RaiderZ .elu

> Reply from finale00
>
> Just use it as command-line tool.
Blender was some project I tried to get at but never completed.
i'm not very good to use blender but i think that i've almost understood.
I have only 2 questions : command-line is the prompt of blender or cmd of pc ? What i have to write in this command line ? I'm sorry for the inconvenience
