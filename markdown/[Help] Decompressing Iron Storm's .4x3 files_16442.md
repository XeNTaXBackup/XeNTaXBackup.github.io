## Post #1
- Username: AKMDM
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 23, 2017 11:48 pm
- Post datetime: 2017-06-23T16:26:43+00:00
- Post Title: [Help] Decompressing Iron Storm's .4x3 files

I need help with decompressing the .4x3 files from Iron Storm by 4X Studios. They are the 3D models from the game and they also contain the textures, materials and meshes used by the model.

After looking through the files in a hex editor, as well as searching through the game's executable, I think that the 3D models are using zip deflate compression. Additionally, the .4x3 files are full of "zip!" keywords, so I'm wondering if they could be .zip files too.

The .4x3 files are composed of several or more entries stored one after another. Every entry starts with the "zip!" keyword, followed by 4 bytes indicating the size of the entry in the file. The next 4 bytes indicates the type of file it is. From my understanding, 

TEXU = Textures
MATL = Materials
MESH = Meshes


There's more types than what I listed, but these are bigger ones and are the most common.

Finally, the next 4 bytes could represent the uncompressed size of the file. The compressed data follows, usually ending with "00 00 FF FF" followed by a null byte in case the aforementioned entry size is an odd number.

I tried using Offzip to decompress the deflated data from these files. Actually, the first entries (always textures) in every .4x3 file decompressed perfectly and I could view the image after editing its header afterwards. However, all subsequent entries just won't decompress at all. The only message I keep getting is:

```
zlib Z_DATA_ERROR, the data in this file is not in zip format or uses a different windowsBit value (-z). Try using -z 15
```


I've tried writing a script for QuickBMS that would inflate the compressed data streams and save them into a new file, but it yielded the same results.

I'm really unsure as to why the first entry would always decompress without issues but the rest fail. I want to be able to use these 3D models for editing and other uses, so I'm asking now if anyone has any idea how to solve this. Also, would it be a good idea to try and reverse engineer some .zip file using the decompressed data? There doesn't seem to be any CR-32 checksum values anywhere, which may be problematic.

I've uploaded a couple of .4x3 files taken directly from Iron Storm's Models.ibf archive. You can find them at this [link](http://www.mediafire.com/file/np84t9mk74b8xop/is_3dmodels.zip). If anyone has any idea on what to do, please respond.

Thank you.
