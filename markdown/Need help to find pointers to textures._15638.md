## Post #1
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-12-24T08:36:02+00:00
- Post Title: Need help to find pointers to textures.

Hi, i have managed to successfully export the mesh and also managed to inject edits back to this format. Could someone help me to find the offsets of different mesh which points to their corresponding textures? For example both the arm mesh point to the same texture,so if i want a tattoo texture on one arm and if i add a tattoo texture on the arm texture,the tattoo texture appears on both the arms. So i want to change the offset of one of the arm mesh so that it points to a different separate texture.

 I'm attaching the model file below.
[https://www.sendspace.com/file/rb6ca0](https://www.sendspace.com/file/rb6ca0)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-24T16:24:04+00:00
- Post Title: Need help to find pointers to textures.

> Reply from eri619
>
> Could you please help me to find the offsets of different mesh which points to their corresponding textures?Is using offsets the way how it works for this game?
Iirc multiple textures are assigned using vertex groups for example.
## Post #3
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-12-27T02:49:53+00:00
- Post Title: Need help to find pointers to textures.

i think it uses offsets because different body parts have separate mesh for example arm,body and legs are all separate objects unlike in svr for example i think it uses vertex groups because vertices of different body parts are mixed together to form an object.
## Post #4
- Username: eatrawmeat391
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Dec 06, 2016 5:51 pm
- Post datetime: 2016-12-27T13:16:13+00:00
- Post Title: Need help to find pointers to textures.

Here is the FML file structure:
- Offset 0x0E: Number of bones (2 bytes)
* Bone data starts from 0x14 with a 16 bytes string per bone name
- Offset 0x0A: Number of materials (2 bytes)
* Material data starts after the bone data,which is 0x14+number_of_bones*0x10.
Material data block size is not constant,you can tell where the next material comes when their name appears
- Offset 0x0C: Number of textures (2 bytes)
* Texture data starts after the material data,from the first valid string
Each texture names is 16 bytes long
* After the texture data there is an unknown section which seems to have some of the bones name at the beginning
Their block size is 0x44,but their total count is not known
* After that here comes the mesh data
* Each mesh's structure:
- Unknown bytes at the beginning (can be absent)
Some mesh has them,but some doesn't
- Unknown value 1 (1 byte)
- Unknown value 2 (2 bytes)
- Number of Vertex Block (2 bytes)
** Vertex Block has variable sizes depending on the mesh,the known sizes are 43, 49, 55,so far they are the working size
** Vertex Block Structure:
- Offset 0x00: Vertex X, Vertex Y, Vertex Z (3*4 bytes)
- Offset 0x1C: UV X, UV Y (2*4 bytes)
** After that there is the face data,its structure is:
- Face Count (2 bytes)
- Face Data, 2 bytes per face value
- 01 00 (2 bytes)
- Face Count (2 bytes)

Attached below is my 2.7 python scripts to deal with this kind of file if anyone is interested.You run this one from a commandline,not as a Blender script.
[WWF_RAW_FML_python_script.7z](https://xentaxbackup.github.io/file/12135_WWF_RAW_FML_python_script.7z)
## Post #5
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-12-28T05:06:05+00:00
- Post Title: Need help to find pointers to textures.

could someone help us find the value of the mesh which points to the corresponding texture?
