## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-14T22:21:56+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

Find the way to unpack the dat files here: 
[viewtopic.php?f=10&t=9387&p=77136#p77136](http://forum.xentax.com/viewtopic.php?f=10&t=9387&p=77136#p77136)

What I found so far 

```
4 bytes 		-> always 0A D7 83 3F
4 bytes 		-> nbr of Submeshes
4 bytes			-> unk ??
FF FF FF FF 	-> delimiter ??

6 * 4 bytes		-> always 00 00 00 00
4 * 4 bytes		-> always 00 00 80 3F ??
FF FF FF FF 	-> delimiter ??


4 bytes 		-> nbr of submeshes

4 bytes			-> length of the name of the submesh
chars[]			-> name of the submesh

4 bytes			-> nbr of submesh
4 bytes			-> always 00 00 00 00
4 bytes			-> nbr Indices  -> chunk size => * 2
4 bytes			-> nbr Vertices -> chunk size => * 4 * 3 

read the indices [i1, i2, i3]

4 bytes			-> unk
4 bytes			-> unk
4 bytes			-> size of the next chunk

read the vertices [f1, f2, f3]

4 bytes			-> unk
4 bytes			-> unk
4 bytes			-> size of the next chunk

-> zero delimited... ?? every fourth float = 0?

4 bytes			-> unk
4 bytes			-> unk
4 bytes			-> size of the next chunk

-> another weird chunk.. every first 2 bytes of 4 bytes is FF ??

```


T.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T22:46:51+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

Samples?
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-15T09:38:44+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

Here are some samples

T.
[KungFuStrikeSamples.rar](https://xentaxbackup.github.io/file/5663_KungFuStrikeSamples.rar)
## Post #4
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-15T21:41:42+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

Attempt on a single mesh file:




here is the c# class:

```
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Diagnostics;
using System.Threading;
using System.Globalization;

namespace ModelToObj
{
    public static class KungFuStrike
    {
        public static void Convert(string fileIn, string fileOut)
        {
            string decimalChar = Thread.CurrentThread.CurrentCulture.NumberFormat.CurrencyDecimalSeparator;

            if (decimalChar == ",")
            {
                Thread.CurrentThread.CurrentCulture = CultureInfo.GetCultureInfo("en-us");
                decimalChar = Thread.CurrentThread.CurrentCulture.NumberFormat.CurrencyDecimalSeparator;
            }

            List<Vector3> vertices = new List<Vector3>();
            List<Indices> faces = new List<Indices>();
            uint nVerts = 0;
            uint chunkFaces = 0;

            using (BinaryReader br = new BinaryReader(new FileStream(fileIn, FileMode.Open, FileAccess.Read)))
            {
                char[] header = br.ReadChars(4); // A3D.
                br.ReadUInt32();
                int nbrMeshes = (int)br.ReadUInt32();

                if (nbrMeshes == 1)
                    br.BaseStream.Seek(72, SeekOrigin.Begin);
                if (nbrMeshes == 2)
                    br.BaseStream.Seek(132, SeekOrigin.Begin);

                nbrMeshes = (int)br.ReadUInt32(); // again ?

                for (int i = 0; i < nbrMeshes; i++)
                {
                    int len = (int)br.ReadUInt32();
                    string meshName = Helper.CharToString(br.ReadChars(len));
                    Debug.WriteLine(meshName);
                }
                br.ReadUInt32(); // 2 or 1
                br.ReadUInt32(); // 00 00 00 00

                nVerts = br.ReadUInt32();
                chunkFaces = br.ReadUInt32() * 2;
                uint nFaces = chunkFaces / 6;
                
                for (int i = 0; i < nFaces; i++)
                {
                    faces.Add(new Indices()
                    {
                        a = (int)br.ReadUInt16(),
                        b = (int)br.ReadUInt16(),
                        c = (int)br.ReadUInt16()
                    });
                }
                br.ReadUInt32();
                br.ReadUInt32();
                br.ReadUInt32();
                br.ReadUInt32();
                
                for (int i = 0; i < nVerts; i++)
                {
                    vertices.Add(new Vector3()
                    {
                        X = br.ReadSingle(),
                        Y = br.ReadSingle(),
                        Z = br.ReadSingle()
                    });
                }

                // TEST
                StringBuilder vertexLis = new StringBuilder();
                StringBuilder faceList = new StringBuilder();

                Debug.Write(nVerts);
                Debug.Write(",");
                Debug.WriteLine(nFaces);
                foreach (Vector3 v in vertices)
                {
                    vertexLis.Append(String.Format("[{0},{1},{2}],", v.X, v.Y, v.Z));
                }
                Debug.WriteLine(vertexLis.ToString());

                foreach (Indices f in faces)
                {
                    faceList.Append(String.Format("[{0},{1},{2}],", f.a + 1, f.b + 1, f.c + 1));
                }
                Debug.WriteLine(faceList.ToString());


                br.Close();
            }

        }
    }
}


```

no uvw mapping yet.

T.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-15T22:08:50+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

```
numSections = self.inFile.readUInt()
for i in range(numSections):
    chunkType, unk2 = self.inFile.read('2L')
    size = self.inFile.readUInt()

    if chunkType == 2:
        vertBuff = self.parse_vertices(numVerts)
    elif chunkType == 3:
        self.inFile.seek(size, 1)
    elif chunkType == 4:
        self.inFile.seek(size, 1)
    elif chunkType == 1:
        self.inFile.seek(size, 1)

self.inFile.readInt() # delimiter ?

```


After the faces you get a section count, followed by structs that look like

```
   int32 ?
   int32 ?
   int32 size
   byte[size] data
}

```
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-16T07:31:37+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

I haven't looked any further yet, but I think the next chunk will probably have the uv mappings, then it switches to the next submesh
or first vertex normals or something else..

I'll look at it later this evening.

T.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-16T16:58:27+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

I couldn't figure out how it handles multiple meshes. It just seemed like something completely different afterwards.
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-16T19:02:45+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

Alright after some plumbing, I found the uv texture coordinates

still only works with one submesh

I needed to jump 2 chunks over... don't know what is in there, a lot of.... bull

here is the sample:



lets see how to find multiple meshes....

T.
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-04T07:16:59+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

still not found this piece of j(ch)unk... 

anyone any idea ?

T.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-04T07:36:21+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

It's just a sequence of mesh structs.

After the section with the different chunks there are some more structs

```
    int[2] nulls
    int numVerts
    int numIdx
    # index buffer
    
    int numSections
    # vertex, normal, uv buffers, other buffers

    int count1
    Unk1[count1] unks

    int count2
    Unk2[count2] ...
   
    int count3
    Unk3[count3]
}

```


```
   68 bytes
}

struct Unk2 {
   8 bytes
}

struct Unk3 {
   1 byte
}

```
## Post #11
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-04T07:42:35+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

Did you (finale00) include in you py script?

T.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-04T07:59:26+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

I did now.
## Post #13
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-04T08:24:47+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

Alright !!!

I check it out this evening 

T.
## Post #14
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2012-09-05T00:20:54+00:00
- Post Title: Kung Fu Strike: The Warriors Rise (*.a3d)

The game is written in some .NET language. Use .NET reflector on it and you will find the complete spec for the model format.
