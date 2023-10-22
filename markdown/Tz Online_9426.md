## Post #1
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-07T11:55:50+00:00
- Post Title: Tz Online

I know that there is another topic about TZ Online but not about model format.






Files format: EVP (packed)
Model format: EVS
Animation format: EVA
Texture format: DDS

I've read that gameclub's games have the same format as dragon and queens blade....

Someone rescued to import this model into noesis or max?
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-07T17:19:24+00:00
- Post Title: Tz Online

Don't think there is an unpacker for the new EVP format.
If it's the same as queen's blade just try that plugin?

Gameclub is just a publisher I think and don't actually develop games.
## Post #3
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-07T21:26:12+00:00
- Post Title: Tz Online

i've not problem to unpack ^^ 

But the extension of queen's blade is mesh, not eva/evs
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-08T04:42:06+00:00
- Post Title: Tz Online

Send me meshes with textures. I don't think I'll get anywhere close to the animations.
## Post #5
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-08-08T21:33:40+00:00
- Post Title: Tz Online

here the samples

[http://www11.zippyshare.com/v/21763119/file.html](http://www11.zippyshare.com/v/21763119/file.html)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-08T22:32:55+00:00
- Post Title: Tz Online

TZ Online published under a bunch of different names right?

talisman online...
weapons of war online...

etc
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-09T02:04:41+00:00
- Post Title: Tz Online

Ok I got past the materials. I've figured out the pattern for the vertices, but I don't know where the vert Count is. There's an odd integer right before the vertex data, but the number is greater than the largest index reference. For example if I'm supposed to read 919 of something, when in fact there are only like 700 vertices.

Then I tried something like

```
for i in range(numVerts):            
    if total == count - 100
        break
    self.inFile.read('3f')
    count = self.inFile.readUInt()
    total += count
    for j in range(count):
        self.inFile.readByte()
        self.inFile.read('7f')
        
        self.inFile.readByte() # 1
    self.inFile.read('2f')
    self.inFile.readByte() # 1

```


And that actually works. It seems to be 100 off all the time (for the samples) cause I reach the end of the struct.

I don't know the vertex struct though.

Here's an 010 editor template 

```
//--- 010 Editor v4.0.1 Binary Template
//
// File: TZ Online .evs
//--------------------------------------

struct Name {
    int len;
    char str[len];
};

struct Vertex {
    int unk;
};

struct Material {
    char header[21];
    byte delim;
    Name Matname;
    byte delim;
    Name texName;
    int unk;
    Name lightmap;
    byte unks[3];
    float properties[48];
    byte delim;
    byte unks2[19];
    Name name;
    Name name;
    Name name;
    byte delim;
    int unks4[2];
    Name name;
    byte delim;
    int unks5[3];
    Name name;
    Name name;
    byte unks6[18];
    byte delim;
};

struct Mesh {
    
    Name meshName;
    Name matName;
    SetBackColor( cLtRed );
    int numIdx;
    short indices[numIdx];
    byte delim;
} ;

struct MatLibrary {
    char header[21];
    byte delim;
    int numMat;
    Material mat[numMat] <optimize=false, bgcolor = cGreen>;
};

struct File {
    
    short null;
    byte len;
    char chunkName[len];
    int neg1;
    byte delim;
    int len;
    char name[len];
    byte null;
    int numMesh;
    
    Mesh mesh[numMesh] <optimize=false, bgcolor=cLtRed>;
    MatLibrary library;

    int unk;
    int unk;
    byte delim;
    
    //vertex section
    Vertex verts <bgcolor=cLtRed>;
} file <bgcolor=cYellow>;

```
