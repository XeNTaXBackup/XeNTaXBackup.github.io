## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-06-24T18:19:05+00:00
- Post Title: Problem with Stray Vertex Cleanup Algorithm

Hey guys,

In games, models can use vertex buffers that are shared among multiple input layouts. However, in Blender, you can only have one vertex buffer per mesh object, which kind of sucks because in games there may be only one vertex buffer with 50,000 vertices, but many input layouts that reference only 5,000 vertices or so at a time. So to get models into Blender I have to create new vertex buffers (based on what vertices are referenced by the index buffers), one per mesh object; otherwise, I would get a lot of stray points.

So this is my algorithm (example):

vertex buffer  (6 vertices)
 v0
 v1
 v2
 v3
 v4
 v5

index buffer (6 indices)
 0, 2, 5, 1, 3, 4

input layout #1 (mesh #1)
 index buffer start: 0
 index buffer elem: 3

input layout #2 (mesh #2)
 index buffer start: 3
 index buffer elem: 3

To get the model in Blender, without stray points, I mark used indices

input layout #1: vertices 0, 2, 5 used
input layout #2: vertices 1, 3, 4 used

Then I remap the indices:

input layout #1: vertices 0, 2, 5 used -> remapped to 0, 1, 2
input layout #2: vertices 1, 3, 4 used -> remapped to 0, 1, 2

And in Blender we are left with:

Mesh Object #1
Vertex Buffer: v0, v2, v5
Index Buffer: 0, 1, 2

Mesh Object #2
Vertex Buffer: v1, v3, v4
Index Buffer: 0, 1, 2

However, this is my problem:

Model looks great.
Weights are great.
UV DATA BECOMES SHIT THOUGH. Some UV end up being rotated. How bad it depends on the mesh. Overall I say 90% of UVs are correct. Some meshes have 0 bad UVs. Some meshes have only 1 or 2 bad UVs. Then there are some meshes where almost all UVs are shit.

I have looked at my algorithm and it looks great, but this rotate UV problem is driving me fucking bonkers ! Is there anything I'm forgetting about the remapping of vertex and index buffers that would cause rotated UVs?

This is a my index buffer remapping code. It takes an index buffer, and returns a map that maps old indices to a new indices.

```
{
 typedef std::set<uint16> set_type;
 typedef std::map<uint32, uint32> map_type;
 typedef std::map<uint32, uint32>::value_type value_type;

 // mark used vertex indices
 std::set<uint16> used;
 for(uint32 i = 0; i < elem; i++)
     if(data[start + i] != 0xFFFF) used.insert(data[start + i]);

 // map old vertex index to new vertex index
 uint32 curr_index = 0;
 map_type retval;
 for(set_type::iterator iter = used.begin(); iter != used.end(); iter++)
     retval.insert(value_type(*iter, curr_index++));

 return retval;
}

```


Then the only thing needed to be done is save out new vertex buffers, which is pretty straightforward.

```
         for(auto iter = imap.begin(); iter != imap.end(); iter++)
            {
             // get indices
             uint32 old_index = reference.vb_start + iter->first;
             uint32 new_index = iter->second;

             // copy position
             vbnew.data[new_index].vx = vbuffer.data[old_index].vx;
             vbnew.data[new_index].vy = vbuffer.data[old_index].vy;
             vbnew.data[new_index].vz = vbuffer.data[old_index].vz;

             // copy normal
             vbnew.data[new_index].nx = vbuffer.data[old_index].nx;
             vbnew.data[new_index].ny = vbuffer.data[old_index].ny;
             vbnew.data[new_index].nz = vbuffer.data[old_index].nz;

             // copy tangent
             vbnew.data[new_index].tx = vbuffer.data[old_index].tx;
             vbnew.data[new_index].ty = vbuffer.data[old_index].ty;
             vbnew.data[new_index].tz = vbuffer.data[old_index].tz;

             // copy binormal
             vbnew.data[new_index].bx = vbuffer.data[old_index].bx;
             vbnew.data[new_index].by = vbuffer.data[old_index].by;
             vbnew.data[new_index].bz = vbuffer.data[old_index].bz;

             // copy blend weights
             vbnew.data[new_index].wv[0] = vbuffer.data[old_index].wv[0];
             vbnew.data[new_index].wv[1] = vbuffer.data[old_index].wv[1];
             vbnew.data[new_index].wv[2] = vbuffer.data[old_index].wv[2];
             vbnew.data[new_index].wv[3] = vbuffer.data[old_index].wv[3];
             vbnew.data[new_index].wv[4] = vbuffer.data[old_index].wv[4];
             vbnew.data[new_index].wv[5] = vbuffer.data[old_index].wv[5];
             vbnew.data[new_index].wv[6] = vbuffer.data[old_index].wv[6];
             vbnew.data[new_index].wv[7] = vbuffer.data[old_index].wv[7];

             // copy blend indices
             vbnew.data[new_index].wi[0] = vbuffer.data[old_index].wi[0];
             vbnew.data[new_index].wi[1] = vbuffer.data[old_index].wi[1];
             vbnew.data[new_index].wi[2] = vbuffer.data[old_index].wi[2];
             vbnew.data[new_index].wi[3] = vbuffer.data[old_index].wi[3];
             vbnew.data[new_index].wi[4] = vbuffer.data[old_index].wi[4];
             vbnew.data[new_index].wi[5] = vbuffer.data[old_index].wi[5];
             vbnew.data[new_index].wi[6] = vbuffer.data[old_index].wi[6];
             vbnew.data[new_index].wi[7] = vbuffer.data[old_index].wi[7];

             // copy texture coordinates
             for(uint32 i = 0; i < 8; i++) {
                 vbnew.data[new_index].uv[i][0] = vbuffer.data[old_index].uv[i][0];
                 vbnew.data[new_index].uv[i][1] = vbuffer.data[old_index].uv[i][1];
                }

             // copy vertex colors
             for(uint32 i = 0; i < 8; i++) {
                 vbnew.data[new_index].color[i][0] = vbuffer.data[old_index].color[i][0];
                 vbnew.data[new_index].color[i][1] = vbuffer.data[old_index].color[i][1];
                 vbnew.data[new_index].color[i][2] = vbuffer.data[old_index].color[i][2];
                 vbnew.data[new_index].color[i][3] = vbuffer.data[old_index].color[i][3];
                }
            }

```
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-27T00:46:54+00:00
- Post Title: Problem with Stray Vertex Cleanup Algorithm

The solution is...don't use blender.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-27T05:51:19+00:00
- Post Title: Problem with Stray Vertex Cleanup Algorithm

Indeed. Don't you have a modeler preference though or can you do everything through Noesis? There was actually nothing wrong with my C++ code to convert mesh objects where vertex buffer data is shared to ones where they aren't. My lack of knowledge of Python and the Blender API was the culprit. Looking at Mariusz's code really helped me out and with his help I was able to solve the problem. But at least the Blender API has documentation . I'm just kidding; I've been meaning to write a Noesis plugin for quite some time but I don't like bugging you or Chris when I have too many questions (like can I view vertex colors in Noesis, can I view UV maps in Noesis, can I view morphs in Noesis, does it support multiple UV channels, position channels, etc. etc.).
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-28T00:47:30+00:00
- Post Title: Problem with Stray Vertex Cleanup Algorithm

Max makes me wanna kill myself 200% less for actual modeling/UV'ing/animating/skinning/etc. For everything that involves any kind of automated or custom processing, though, I use Noesis.

The answer to all of your questions is yes. You would have to deal with multiple position channels with morph frames as well. But you'd also find the answers to all of those questions pretty much immediately with a glance through __NPReadMe.txt or the shared native plugin header. The basics are pretty obvious. Things only start getting obscure and onto the topic of knowledge that exists only in my head when you want to start doing weird and obscure things. There's also the fact that I don't think anyone has ever actually tested the morph stuff in Python, myself included. I just wrote it and pretend that it all works. It is used in native plugin land for Quake 2 support, so at least I know it functions that far.
