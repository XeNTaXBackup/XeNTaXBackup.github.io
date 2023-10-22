## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-12T15:20:32+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

The game developer is "THQ"
Textures: *.jpg
Mesh: *.cmfh
I was wondering if someone could create a Noesis plugin to import these files


Thanks in advance!
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T17:09:10+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

It's a simple format (parsing-wise), except in big endian........but I don't seem to be able to bind the buffers correctly.
Anyone have ideas?

[http://db.tt/VkHl0r2Q](http://db.tt/VkHl0r2Q)

```
struct Vertex {
   float[3] vx, vy, vz
   dword[12] ?
   float[3] nx, ny, nz
   float[2] tu, tv
}

struct Face {
   int16[3] v1, v2, v3
}

char[4] idstring
int32 ?
int32 numVerts
int32 numFaces

numVerts Vertex
numFaces Face

#a bunch of 4-byte integers afterwards

```
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-02-12T20:26:44+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

Vertex structure:
  3 floats (X,Y,Z)
15 floats unknown
 2 floats (U,V)

I did try on all sample files with my program, but I can't load the desmodus.cmfh and the zarkon.cmfh files correctly.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-02-12T20:31:39+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

Is the full name of the game Voltron: Defender of the Universe ?
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-12T21:40:37+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

Yes.
The title of the game is 'Voltron: Defender of the Universe'
I uploaded some more sample files
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T18:37:26+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

Cool, all I had to do was set BIG_ENDIAN option in noesis and it worked.

```

```


Right now I'm just assuming texName = {filename}, but that's not true. The material library is stored in {filename}_mat.txt, but I haven't bothered to look at it. If someone tells me the exact format I can just add a parser quickly.

There's also a second mesh format which I guess is for static meshes (you can see those in vehicles, rvm format)

Which is also pretty straightforward.
## Post #7
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-17T06:44:40+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

Thank you for your support.
Do you know how to fix this model?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T07:02:13+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

Nope. Not sure why some of the models are different. Not sure what the issue might be either.
## Post #9
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-18T02:50:35+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

desmodus.cmfh(zarkon.cmfh, voltron_synthoid.cmfh, voltron.cmfh) was different from any other cmfh.
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-02-19T09:47:28+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

> Reply from finale00
>
> Nope. Not sure why some of the models are different. Not sure what the issue might be either.

You wrote: #a bunch of 4-byte integers afterwards

I think (hope) this format stores the model in the following format like this:

Vertexbuffer
Face buffer

Part Counter (4 bytes LongInt)

Parts: 
Vertex_index_from  (4 bytes LongInt)
Vertex_count         (4 bytes LongInt)
Face_index_from    (4 bytes LongInt)
Face_count           (4 bytes LongInt)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T19:15:56+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

Ya, you're right.

```

numGroups {
    int32 offset into vertex buffer
    int32 numVerts
    int32 offset into index buffer
    int32 numFaces
    int32 unk
    int32 count
    int32[count] ?
}
byte[2] 01 01

```



I don't know what all those other integers could mean though.

Btw, the material info is not really stored in the .mat file.
Unless it's incomplete.

I actually have no idea where the material info is.
But script is updated to load the meshes properly.
## Post #12
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-02-19T19:39:36+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

> Btw, the material info is not really stored in the .mat file.
>
> Unless it's incomplete.
>
> I actually have no idea where the material info is.

npc_arus.mat.txt file:

ch/human/npc/arus/arus_npc
endmats

arus_npc is the texture filename without file extension I think.
The real filename is arus_npc.jpg
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T19:44:54+00:00
- Post Title: [request]Voltron xbox360 cmfh to obj

For desmodus, it has _d and _a and _nm for the different types of texture maps.
Its mat.txt file only has that one line also.

There doesn't seem to be consistency either. If you look at zarkon it says _dm instead of _d lol
