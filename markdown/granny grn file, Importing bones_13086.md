## Post #1
- Username: Ryder25
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 01, 2011 6:43 am
- Post datetime: 2015-07-22T04:13:42+00:00
- Post Title: granny grn file, Importing bones

Hey guys, I've been working on being able to import, and export .grn files from the Age of Mythology game to 3ds Max, and I was wondering how I can create a proper bone system. 

I have position, and quaternion data, but I notice most other scripts I've found online are for formats that have the entire transformation directly. Right now I'm just creating each bone as a dummy.

Here is an example bone data that I extracted in xml format. These values are local to the bone, so they would have to be multiplied by the parent's transform matrix.

```
  <parentIndex>5</parentIndex>
  <position>{X:0.08962885 Y:-1.721544E-09 Z:2.114075E-15}</position>
  <rotation>{W:1 X:5.108084E-15 Y:1.104274E-09 Z:-0.0003988306}</rotation>
  <scale>{[A1:0.9999999 A2:-5.772494E-12 A3:-3.124496E-16] [B1:-5.772494E-12 B2:0.9999999 B3:-1.176143E-14] [C1:0 C2:-1.176132E-14 C3:0.9999999]}</scale>
</boneData>
```


Also, I know that in maxscript you can set an objects scale to a point3 value, but here I'm given a 3x3 matrix. What do I do in this case? I'm thinking I can just multiply the entire transform by this matrix, after applying position, and rotation.

Thanks!
## Post #2
- Username: Ryder25
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 01, 2011 6:43 am
- Post datetime: 2015-07-29T09:16:25+00:00
- Post Title: granny grn file, Importing bones

I've managed to create a proper transform. It seems obvious now, I don't know why I was having problems earlier.

I do have another question though. Grn files contain bone bindings, which tell which bones from the skeleton apply to a certain mesh.  What I don't understand is the OBB, and this unknown value:

```
<fMeshBone>
  <boneIndex>6</boneIndex>
  <unknown>0.267601848</unknown>
  <obbMin>{X:0.006540398 Y:-0.05598566 Z:-0.1125851}</obbMin>
  <obbMax>{X:0.236042 Y:0.1820828 Z:0.111452}</obbMax>
</fMeshBone>
```


I understand that obb stands for object (oriented?) aligned bounding box, but what does the unknown value mean? I'm not quite sure exactly how OBBs are calculated and stored.

Anyone have experience with this?
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-08-03T14:27:44+00:00
- Post Title: granny grn file, Importing bones

If I had to guess,
obbMin = vertex with the least amount of distance between itself and [0,0,0]
obbMax = vertex with the most amount of distance between itself and [0,0,0]
unknown = radius of the bounding sphere

To get the min and max values, you just need to calculate the biggest and smallest vertex
To get the radius, you'd have to calculate the bounding sphere and then calculate the radius from that.
I do have some C# code that calculated these values

```
        {
            Vector3 minExtent = new Vector3();
            Vector3 maxExtent = new Vector3();
            foreach (Vector3 vertex in vertices)
            {
                minExtent.X = Math.Min(minExtent.X, vertex.X);
                minExtent.Y = Math.Min(minExtent.Y, vertex.Y);
                minExtent.Z = Math.Min(minExtent.Z, vertex.Z);

                maxExtent.X = Math.Max(maxExtent.X, vertex.X);
                maxExtent.Y = Math.Max(maxExtent.Y, vertex.Y);
                maxExtent.Z = Math.Max(maxExtent.Z, vertex.Z);
            }

            Vector3 sphereCentre = new Vector3(
                (float)0.5 * (minExtent.X + maxExtent.X),
                (float)0.5 * (minExtent.Y + maxExtent.Y),
                (float)0.5 * (minExtent.Z + maxExtent.Z));

            float maxDistSq = new float();
            foreach (Vector3 vertex in vertices)
            {
                Vector3 fromCentre = vertex - sphereCentre;
                maxDistSq = Math.Max(maxDistSq, fromCentre.LengthSq());
            }

            float sphereRadius = (float)Math.Sqrt(maxDistSq);

            return new BoundingInfo(sphereCentre, sphereRadius);
        }

```
