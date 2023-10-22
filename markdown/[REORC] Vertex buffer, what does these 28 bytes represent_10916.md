## Post #1
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-10-31T00:21:12+00:00
- Post Title: [REORC] Vertex buffer, what does these 28 bytes represent?

In the egemodel format (RE:ORC), the vertex buffer have a stride of 52 in most models. 
However, there are 28 bytes of unknown data to me. I searched direct3d reference but didn't find anything useful.

It seems they are all valid floats. I attach ingame screenshots of the behavior when that data is replaced with zeros. 
The vertices extend to an arbitrary point. Any ideas of what the bytes represent? or what to try to find out? can send samples by PM.

float[3] position
float[3] normal
half float[2] uvs
float[7] ???
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-31T07:44:24+00:00
- Post Title: [REORC] Vertex buffer, what does these 28 bytes represent?

what direct3d reference? vertex semantics? if so, the info is there. nomal mapped models typically contain tangent and binormal semantics. re game models also usually contain color and secondary uv semantics (for lightmaps, effects, etc).
## Post #3
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-11-01T17:00:27+00:00
- Post Title: [REORC] Vertex buffer, what does these 28 bytes represent?

> Reply from howfie
>
> tangent and binormal

I think that's what those represent, since tangent is 4 floats, and binormal is 3 floats.
Now I need to find a way to calculate them for a export, since blender doesn't officially provide access to those 
(there's a patch though, I might try when I learn to build blender)

I found good info here:
[http://answers.unity3d.com/questions/77 ... ctor4.html](http://answers.unity3d.com/questions/7789/calculating-tangents-vector4.html)

But if anyone has any example (specially blender) of an exporter, it will be appreciated!

Thanks howfie.
