## Post #1
- Username: stumpyhwde
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 15, 2018 11:09 am
- Post datetime: 2018-12-15T23:24:48+00:00
- Post Title: UGX 3d Model Files for the Phoenix Game Engine, Halo Wars

I'm part of a small modding community for an old RTS game (Halo Wars) that has always wanted to use custom models in the game. The problem is that the files are a proprietary format (.ugx). Someone has made a maxscript that allows this proprietary model format to be loaded into 3dsmax, however the opposite would allow us to use any model in the game. I'm asking anyone with an sort of experience with this thing to help out with this as most of us in the community don't even know where to start. Anything is appreciated, thanks.

The models were exported with a 3dsMax tool called Granny3d into the .GR2 format. This is the tool that was used to make the model files in the game, .UGX. The problem is there is no way to convert the .GR2 to .UGX that the games engine expects. Attached is one of the game models, as well as 3 sets of mesh extraction settings, each set in both 86x and 32x big-endian. The reason why I've included 3 sets is because I'm not sure the settings used to make the UGX files. The files should only contain a model, mesh, and a texture location (its external to the model).

There is also a tool that splits the UGX into 5 ecf based files called .ECF_Chunk files. I'm not sure what these files actually contain, but they appear to be parts of the UGX. One of the .ecf_chunks is also a file path for the texture, called .binary_data_tree, and can be dropped into the tool to turn it into a .binary_data_tree_xml that can be viewed with any XML viewer, and contains the paths for the model files. This is only a one way road as they cant be turned back into .ecf_chunks with the program. These are included in the rar, as well as the tool to build and split the files.

Files too big for the site
[https://www.dropbox.com/s/o4v1ywr9bcijm ... X.rar?dl=0](https://www.dropbox.com/s/o4v1ywr9bcijmgc/gr2toUGX.rar?dl=0)
