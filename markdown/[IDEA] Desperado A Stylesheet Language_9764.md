## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-20T02:41:10+00:00
- Post Title: [IDEA] Desperado: A Stylesheet Language

So I've been toying with the idea of a stylesheet-like language to describe 3D documents. Tool will have 2 - 4 panes. First pane will be a text editor to type in stylesheet code. Other panes will be perspective pane (to preview model), UV pane (to preview UV), and texture pane (to preview textures). Use would be for people who can't program but can learn to spot data in files. This would be for games that don't have extractors (for people who are desperate lol).

For example, a game file that contains two vertex buffers can be specified like so:

```
identifier: 0
name: vb1_positions_normals_blend
offset: 0x8000
buffer-size: 0x7C00

<vertex-buffer>
identifier: 1
name: vb2_uv
offset: 0x10000
buffer-size: 0x7C00

```


Now that you have your vertex buffers, you have to describe what the vertex format is. In Direct3D 11 this is called the input layout.

```
identifier: 0
slot: 0
name: Position, Normals and Blending
stride: 32
default-endian: little
position-offset: 0
position-format: vector3f
normal-offset: 12
normal-format: vector3h
blendweight-offset: 18
blendweight-format: vector4h
blendindex-offset: 26
blendindex-format: vector4ub
blendindex-type: bone-index

<input-layout>
identifier: 0
slot: 1
name: UV Channel
default-endian: little
stride: 8
texcoord-offset: 0
texcoord-format: vector2f

```


OK, now that you have vertex buffers and input layouts defined, you need to associate one or more vertex buffers with a single input layout. This is where you also specify how you want the data to be rendered. In Direct3D 11, this is part of what is called the input assembly. There would also be stylesheet styles and properties for index buffers, skeleton data, and so on. For those who don't know what slots are, those are Direct3D equivalents to non-interleaved vertex buffers (position, normals, UVs are separate buffers). Positions may be in slot 0, normal in slot 1, etc.

```
input-layout-reference: 0
vertex-buffer-start-slot: 0
vertex-buffers: 2
vertex-buffer-reference[0]: 0
vertex-buffer-reference[1]: 1
topology: points

```


At this point there is enough information to at least render points and vertex normals in perspective pane and UVs in the UV pane.

Think it's a good idea? Currently, the language is based on input supported by Direct3D 11. Any suggestions as to what else should be present in the language? I'll post more of the language that I have so far and a demo program soon if you guys want to test it out lol.
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-10-20T07:43:42+00:00
- Post Title: [IDEA] Desperado: A Stylesheet Language

Seems good enough, but what about for other platforms, like PS2, GameCube or NDS?
## Post #3
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-23T11:08:24+00:00
- Post Title: [IDEA] Desperado: A Stylesheet Language

This is an amazing idea, I hope something comes of it.
