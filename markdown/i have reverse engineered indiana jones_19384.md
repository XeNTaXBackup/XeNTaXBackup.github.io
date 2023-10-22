## Post #1
- Username: bahstrike
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 26, 2019 7:45 am
- Post datetime: 2019-01-25T23:54:20+00:00
- Post Title: i have reverse engineered indiana jones

can someone create me a wiki login so i can update the following page:
[http://wiki.xentax.com/index.php/Indian ... achine_CND](http://wiki.xentax.com/index.php/Indiana_Jones_And_The_Infernal_Machine_CND)


in case u need proof

```
        public class CNDHeader
        {
            public int size;
            [MarshalAs(UnmanagedType.ByValArray, SizeConst = 1216)]
            public byte[] logo;
            [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 64)]
            public string srcpath;
            [MarshalAs(UnmanagedType.ByValArray, SizeConst = 2)]
            public int[] dunno1a;
            [MarshalAs(UnmanagedType.ByValArray, SizeConst = 11)]
            public float[] dunno1b;
            public int dunno1c;
            [MarshalAs(UnmanagedType.ByValArray, SizeConst = 6)]
            public float[] dunno1d;
            public int numSoundFiles;
            public int numMatFiles;
            public int maxMatFiles;
            [MarshalAs(UnmanagedType.ByValArray, SizeConst = 2)]
            public int[] dunno2a;
            public int numVerts;
            [MarshalAs(UnmanagedType.ByValArray, SizeConst = 3)]
            public int[] dunno2b;
            public int numTexVerts;
            [MarshalAs(UnmanagedType.ByValArray, SizeConst = 3)]
            public int[] dunno2c;
            public int numAdoins;
            public int dunno2d;
            public int numSurfaces;
            public int dummy0;
            public int numSectors;
            public int dummy1;
            public int numAIFiles;
            public int maxAIFiles;
            public int dummy2;
            public int numModelFiles;
            public int maxModelFiles;
. . . . .
```


```
me.numMaterials = zip.ReadInt();
me.numMipmaps = zip.ReadInt();
me.unknown2 = zip.ReadInt();
me.colorBits = zip.ReadInt();
me.redBits = zip.ReadInt();
me.greenBits = zip.ReadInt();
me.blueBits = zip.ReadInt();
me.redShift = zip.ReadInt();
```


```
List<SurfaceVertEntry> surfVerts = new List<SurfaceVertEntry>();
for (int x = 0; x < totalSurfVerts; x++)
{
    SurfaceVertEntry sv = new SurfaceVertEntry();
    surfVerts.Add(sv);

    sv.vertIndex = zip.ReadInt();
    sv.texVertIndex = zip.ReadInt();
    sv.lightR = zip.ReadFloat();
    sv.lightG = zip.ReadFloat();
    sv.lightB = zip.ReadFloat();
    sv.dunno = zip.ReadFloat();

}
```
