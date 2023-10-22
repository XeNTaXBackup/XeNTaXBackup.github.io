## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-19T23:58:40+00:00
- Post Title: Waren Story

Waren History files samples in the repository. I shure finale see this format before and its a head paint to he. jejejeje.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-20T03:41:45+00:00
- Post Title: Waren Story

img files are compressed.
Don't know about sobject.
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-20T04:39:40+00:00
- Post Title: Waren Story

game its from aeria games, sobject its same format of twelve sky 2
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-20T05:19:26+00:00
- Post Title: Waren Story

No, it is slightly different. About half of the file is something else, followed by the compressed data that you can decompress with the existing twelve sky unpacker.

How the data is stored is also not the same. It is the same compression format, but a new script will need to be written.

It is possible that the model data is uncompressed, and all of the compressed data is just textures.

EDIT: Ok from the samples there are two types of sobjects. If you look at the header, it starts with SOBJECT2 (so it's not the same SOBJECT format as before), followed by two integers. If the first integer is a 1, then it's a model. If it's an 0x28, I don't know what it is but it doesn't look like a model. If you see something else then you should upload that as well.

I would like some decently large files (600-700 KB) and maybe some monsters/weapons (even if they load, for reference)

Plugin: [http://db.tt/ryDE45s9](http://db.tt/ryDE45s9)
Loads meshes and textures from the file. Don't bother extracting the textures I don't bother checking.



The compressed data is just the textures.
If you run it through offzip you'll get them fine



It would be a lot easier to just load the textures directly without bothering to extract them, but I'll have to figure out where it's getting the sizes from.

The img files are also compressed. You can use offzip to get them out. They're just DDS files with some extra stuff before it
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-20T10:28:06+00:00
- Post Title: Waren Story

I would like some decently large files (600-700 KB) and maybe some monsters/weapons (even if they load, for reference)

In repository, More Folders

Coz the names i cant see wath its weapons or armors, i start search and upload lather.

Wath its the diference betwen this .SOBJECT and 12 sky 2 .SOBJECT?

BTW .SOBJECT and i see .MOBJECT from twelve sky 2 in the repository now.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-20T17:39:00+00:00
- Post Title: Waren Story

Everything in twelvesky is compressed (models, textures, ...)
This one just has textures compressed.

I've removed the "limiter" on the plugin so that it doesn't bother checking that first integer I mentioned.
Each model comes in pairs; one that contains the model information, the other containing...I don't know.

It looks like all of the files whose names end with a 2 are models, while the ones that end with a 1 comes with it but doesn't contain mesh/texture info. So I changed it to check the filename instead.

I don't really understand why the same copy of the model is stored multiple times in the file (LOD maybe?), but it looks like you only need to load the first one to get the full model.

I've provided an option to load just the first mesh at the top of the script.



I have no idea where the normals are stored in the vertices (maybe it's not just 3 floats)
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-20T20:13:28+00:00
- Post Title: Waren Story

Lol, this its nice, impresive see how u can find how the models are stored, thanks finale
