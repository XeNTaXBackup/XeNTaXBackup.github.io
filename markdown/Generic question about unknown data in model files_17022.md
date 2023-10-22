## Post #1
- Username: 0xdeadbeef
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 01, 2016 7:34 am
- Post datetime: 2017-09-14T12:31:36+00:00
- Post Title: Generic question about unknown data in model files

Hi, my first post on this forum, but hopefully not the last!

I'm in the early stages of extracting models from a crusty 10-year-old game that has no tools available yet.  I'm experienced in reverse engineering but this is my first time working with 3d models.  My question is generic so hopefully other beginners can get something from the answers even if they're working on something else.

The game's model files can contain multiple meshes each of which has the expected raw vertex arrays, and element arrays defining triangles.  The following data is what has me puzzled.  There is one set of this data per model, not per mesh.

```
TypeA type_a_array[];
TypeB type_b_array[];
TypeC type_c_array[];

struct TypeA {
    // Which mesh are we referring to?
    int mesh_index;
    // Index into that mesh's vertex array:
    int vertex_index;
};

struct TypeB {
    // Three pairs of indices into the arrays of TypeAs and TypeCs:
    int TypeAIndex1;
    int TypeCIndex1;

    int TypeAIndex2;
    int TypeCIndex2;

    int TypeAIndex3;
    int TypeCIndex3;
};

struct TypeC {
    // Two pairs of indices into the arrays of TypeA and TypeB:
    int TypeAIndex1;
    int TypeBIndex1; // never -1

    int TypeAIndex2;
    int TypeBIndex2; // can be -1
};


```


The names for each element were chosen by comparing max values with array sizes across a large number of model files, and they're certainly correct formally.

Here's what I've understood and what I need help with:

TypeA picks out vertices from the various component meshes. Understood.

TypeB defines a triangle with those vertices and associates each vertex of the triangle with a struct TypeC.

TypeC: What's happening? That TypeBIndex2 can be -1 makes me wonder whether this defining a tree structure, and -1 means a nonexistent child.  Am I looking at something like a BSP for collision detection?

Thanks for any suggestions or answers from the gurus here.  For all I know, this might be a very simple and well-known structure.
