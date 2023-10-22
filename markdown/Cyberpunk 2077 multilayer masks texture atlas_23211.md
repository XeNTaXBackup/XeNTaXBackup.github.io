## Post #1
- Username: Hitmanhimself
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Aug 08, 2020 12:43 am
- Post datetime: 2020-12-23T13:34:43+00:00
- Post Title: Cyberpunk 2077 multilayer masks texture atlas

need some hand here regarding texture atlases, cyberpunk is using masks in texture atlases to make materials for models like clothes and weapons etc, they are not using diffuse textures directly, in a single atlas texture they have multiple masks however those masks have been packed in such a way that they can't directly be used, there are no 2ndary or tertiary uv layers for the model these textures are being used for. they have done the packing in such a way that they have removed the 16x16 black color tiles to save space(for eg. masks have a lot of portion just black color so somehow they have removed them and possibly using an algorithm based on some input values to reconstruct those black tiles). these masks textures have a cr2w definition file that can be dumped using rfuzzo's cp77tool to get the image information and some other information, then they have the atlas buffer file which has the atlas mask texture itself and lastly they have another buffer which has some tiles data(specified by cr2w json definition file.) the tiles buffer data needs to be figured out, i guess the tiles buffer itself has some information regarding constructing the masks properly which can be used.

If someone has previously worked with these type of textures atlases where image reconstruction is based on tiles data should be able to figure out, or if some know how these things are used in game engine should be able to figure out.

atlas buffer has been exported using raw texture cooker by daemon1 with bc4 compression and with resolution information from the cr2w dumped json file.
sample texture atlas


normal for this model


some sample files with  cr2w def, atlas buffer, tiles buffer and some exported images and some normal for the model for some reference u know.
[https://mega.nz/file/QQ1yUCDa#_DIZdhJv- ... jJ_MxyKrOk](https://mega.nz/file/QQ1yUCDa#_DIZdhJv-_anCgsgrFKzdSXYRV3eN209vjJ_MxyKrOk)
