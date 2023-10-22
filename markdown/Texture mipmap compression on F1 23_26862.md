## Post #1
- Username: zhenya4342
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 14, 2018 4:57 am
- Post datetime: 2023-06-15T12:46:29+00:00
- Post Title: Texture mipmap compression on F1 23

Hello,

I am working on bringing a certain modding tool for F1 series of games by Codemasters back to life. Recently, a new game was released which is F1 23, and it added some new type of compression for texture mipmaps. The game has its own archive format that stores textures and other files, but mipmaps are stored as separate files unique to each texture in the game folder. All textures and mipmaps are BC-compressed, but mipmaps have an additional layer of compression on them, which gets decompressed first, then the output gets decompressed as BC. Known layers are ZStandard and LZ4, but with the new game we have something new that we cannot yet figure out.

What I figured out is:
- first 4 bytes are the size of the compressed mipmap file;
- bytes 5 and 6 represent "BD" in ASCII;
and that's about it

I am attaching an archive with example files, which include uncompressed mipmap, LZ4-compressed mipmap and the unknowingly-compressed mipmap that we cannot figure out yet. The texture in example has size of 1024x1024 with this mipmap being 2048x2048. Uncompressed and LZ4 compressed examples are just for reference and are not related to the same texture.

The example file's uncompressed size should be 2097152 bytes, that we know from the original texture that references this mipmap file.

Below are screenshots of how the original texture looks (1024x1024) and its mipmap (2048x2048), when treated as no additional compression (it then gets decompressed as BC1) respectively.




Thanks!
[mipmap.rar](https://xentaxbackup.github.io/file/23941_mipmap.rar)
