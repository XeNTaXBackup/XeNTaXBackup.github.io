## Post #1
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-08-05T10:35:05+00:00
- Post Title: Re: Drawing a voxel mesh with multiple materials

not exactly the correct forum section.

minecraft type of rendering? use a general shader with specular enabled and specular textures. it's easier to manage. also, if you use a texture2d array like a stack of same size textures you essentially have a easy way of indexing the textures by material id aka the depth in the stack.

the other way you could do it without the spec texture is if you would preprocess the quads (2 triangle)s and add a specular value into a 'per face' instance buffer while the vertices still have the simple data. that means if that works. usually when using instances (in dx9 it's SetStreamSourceFreq), the same faces are rendered multiple times. that's the other way around.
