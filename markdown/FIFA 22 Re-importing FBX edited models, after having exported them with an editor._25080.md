## Post #1
- Username: NobodyinParticular
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 22, 2022 2:11 pm
- Post datetime: 2022-02-22T06:18:54+00:00
- Post Title: FIFA 22: Re-importing FBX edited models, after having exported them with an editor.

Hi all,

By using a tool called "Fifa Editor" I have managed to export the fbx files which make up a stadium.



I can open these files in Blender, edit them and save them normally.



However, the same editor will not allow re-importing the file. The error message clearly states that "Only Rigid and Skinned Meshes can be imported." The mesh asset in question is a "Composite mesh" asset, not a skinned or rigid mesh asset.



I understand that these files are present in containers with the "cas" extension, and that these are containers used by Frostbite engine. The containers are encrypted and the contents indexed by a "cat" file. This is to my limited knowledge, but I will probably have it wrong.

I have attempted to export/import the file with a different editor, such as Paul's "FMT" Editor, which exports the mesh file as bin. But the size is considerably smaller, and re-importing the edited file with a change of header in HxD bin editor does nothing.

I humbly ask for help. How is it possible to re-import these edited "Composite asset" meshes? Is there a magic way? I hope you can help me, thanks for reading.
