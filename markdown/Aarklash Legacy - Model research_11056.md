## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-18T22:39:31+00:00
- Post Title: Aarklash Legacy - Model research

Hi guys, been a while, so I got this new game from Steam and looked at the model files (.cef)

I used C# to render it using DirectX but I got this problem   



and here is the code:

```
            using (BinaryReader br = new BinaryReader(new FileStream(fileName, FileMode.Open, FileAccess.Read)))
            {
                char[] cef = br.ReadChars(3);
                br.Seek(99);

                string modelName = br.ReadStringZeroEnded();
                br.ReadBytes(133);

                string position = br.ReadStringZeroEnded();
                br.ReadBytes(35);

                long pos = br.BaseStream.Position;

                string blendWeight = br.ReadStringZeroEnded();

                if (blendWeight == "BLENDWEIGHT")
                    return null; // todo --> followed by BLENDINDICES
                else
                    br.Seek(pos);

                // pos 296 7944 bytes 1986 floats 662 vertices
                int vertSize = br.ReadUInt16();
                br.ReadBytes(16);
                List<Vector3> vertices = new List<Vector3>();
                for (int i = 0; i < vertSize / 12; i++)
                {
                    var x = br.ReadFloat();
                    var y = br.ReadFloat();
                    var z = br.ReadFloat();
                    vertices.Add(new Vector3(x, z, y));
                }
                cMesh.Vertices = vertices;
                
                // pos 8326 3768 bytes 1884 ints 628 faces
                br.ReadBytes(24);
                string indice = br.ReadStringZeroEnded();
                br.ReadBytes(37);
                int indexSize = br.ReadUInt16();
                br.ReadBytes(16);
                int[] indices = new int[indexSize / 2];
                for (int i = 0; i < indices.Length; i++)
                {
                    indices[i] = br.ReadUInt16();
                }
                cMesh.Indices = indices;
                br.Close();
            }
            return cMesh;

```


any help is more than welcome

T.
[issue01.PNG](https://xentaxbackup.github.io/file/6849_issue01.PNG)
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-18T22:41:05+00:00
- Post Title: Aarklash Legacy - Model research

Here is the actual file
[AcheronGolem_weapon_00_306b1411.zip](https://xentaxbackup.github.io/file/6850_AcheronGolem_weapon_00_306b1411.zip)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-18T23:00:37+00:00
- Post Title: Aarklash Legacy - Model research

what is the problem? The shape? Or the texturing?

I loaded your sample in hex2obj:
[](http://www.pic-upload.de/view-21668110/AG_weapon.jpg.html)

This is the H2O file:
0x2098 1884
VB0
0x0
0x13A 662
0200

(Didn't look for uv data.)
## Post #4
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-18T23:01:26+00:00
- Post Title: Aarklash Legacy - Model research

Found the problem when I was doing some refactoring..

DirectX doesn't like the indices of the format int[], so it needs to be short[], then it works 

so in the code you need to change this line:

```
int[] indices = new int[indexSize / 2];
```


with

```
short[] indices = new short[indexSize / 2];
```


and this one:

```
indices[i] = br.ReadUInt16();
```


with:

```
indices[i] = br.ReadInt16();
```


T.
[issue_solved.PNG](https://xentaxbackup.github.io/file/6851_issue_solved.PNG)
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-21T10:16:27+00:00
- Post Title: Aarklash Legacy - Model research

Darn, 2 days and I don't seem to be able to figure out these texture coordinates..

some more help plz ?

T.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-21T16:57:04+00:00
- Post Title: Aarklash Legacy - Model research

strange -
these were my nearest hits:
[](http://www.pic-upload.de/view-21692799/Mace_tex.jpg.html)

How does the texture file look like?
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-22T12:28:02+00:00
- Post Title: Aarklash Legacy - Model research

I needed to reduce the size of the texture, normally it is a dds file of 2.7MB

I believe the weapon is unwrapped in the upper right corner, so I think your unwrapping is not correct, yet :p

Don't worry I'm still looking at it as well,  no luck either, thanks for the help already

T.
[golem_dff_3d403ec7.jpg](https://xentaxbackup.github.io/file/6870_golem_dff_3d403ec7.jpg)
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-01-17T07:51:01+00:00
- Post Title: Aarklash Legacy - Model research

TaylorMouse,

I did find the UV datas in the .cef file. See the attached .obj file.
[AcheronGolem_weapon_00_306b1411.zip](https://xentaxbackup.github.io/file/6924_AcheronGolem_weapon_00_306b1411.zip)
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-01-17T07:59:45+00:00
- Post Title: Aarklash Legacy - Model research

How to get the UV datas?

File offset:  $2FEC
Data block: TEXCOORD

- read the 'TEXCOORD'
- skip the next 36 bytes
- UV Vertex Size = Read Long / Vertices
- skip the next 14 bytes

UV vertex size of the your sample file: $28

UV data block:
- 20 bytes unknown
- U: 4 bytes Float
- V: 4 bytes Float
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-01-17T08:11:47+00:00
- Post Title: Aarklash Legacy - Model research

I added the .cef loader module to the 3D Object Converter and I will upload it to my web page from my home.

I don't understand why has the .cef file invalid texture file name.
bad:  Golem_DFF.tga
valid: golem_dff_3d403ec7.dds
## Post #11
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-01-21T08:15:37+00:00
- Post Title: Aarklash Legacy - Model research

I uploaded this (Aarklash Legacy support) version to my web page:
[http://3doc.i3dconverter.com/downloads/ ... rtable.zip](http://3doc.i3dconverter.com/downloads/3doc_v5.307_portable.zip)
## Post #12
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2014-01-21T10:16:41+00:00
- Post Title: Aarklash Legacy - Model research

Karpati
it would be nice to see your activity a part of us out here
## Post #13
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-21T19:17:54+00:00
- Post Title: Aarklash Legacy - Model research

interesting, need to check this at home!!

Thnx
T.
