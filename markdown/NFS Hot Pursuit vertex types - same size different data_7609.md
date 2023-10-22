## Post #1
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-11-01T12:52:25+00:00
- Post Title: NFS Hot Pursuit vertex types - same size different data

Hi, I'm trying to read vertices in models from X360 version of NFSHP2010. X360 vertices differs from PC vertices only in vector compression - it uses [111110](http://msdn.microsoft.com/en-us/library/microsoft.directx_sdk.reference.xmhendn3%28v=VS.85%29.aspx) format.

The problematic vertex types are these:

```
{
    short X,Y,Z,W;
    Vector3 Normal;
    Vector3 Tangent;
    int bones, weights;
    float16 u0, v0;
    float16 u1, v1;
}
Vertex56
{
    short X,Y,Z,W;
    Vector3 Normal;
    Vector3 Tangent1;
    Vector3 Tangent2;
    int bones, weights;
    float16 u0, v0;
}
```

Since X360 version uses vector compression, vertex with size of 32 bytes can map into Vertex48 or Vertex56.

I've checked the mesh header - there's nothing indicating vertex type.

Does anyone have an idea how to determine correct vertex type (possibly without bruteforce data testing)?
