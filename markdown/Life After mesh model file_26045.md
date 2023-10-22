## Post #1
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-11-30T01:43:37+00:00
- Post Title: Life After mesh model file

Hello forum, I have a model file from a mobile game called life after that uses the NeoX engine, I have managed to extract the NPK files into their Mesh and other files. 
I know that they are un encrypted and working model files, but all the tools to open said mesh are out of date and produce corrupted or bad faces. 
thanks to vlad_256 (to give credit where it is due) on the discord and their help I now know the mesh is intact and works. 

I was wondering if someone could make a Noesis or Blender script that could import this file into it.  I know from testing the skeleton and weights are also included in this file. 



b_f_3025.mesh_Tue_Nov_29_15-19-26_2022.png (88.31 KiB) Viewed 257 times


Just to show his work and that it is possible.
here is a link to the model, I wasn't able to attach it cause its over 1 mb. 
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1nGIM2O8FKyi_1LBqdvTAa-H2K1lqncV5?usp=share_link)
## Post #2
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-11-30T02:09:12+00:00
- Post Title: Life After mesh model file

Small update. looking in with model researcher, the skeleton is at the beginning of the file very clearly
## Post #3
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-11-30T03:52:56+00:00
- Post Title: Life After mesh model file

Beginning of Vertices
[https://gyazo.com/182679bd1d93af101956eadfee4e3ebb](https://gyazo.com/182679bd1d93af101956eadfee4e3ebb)

end of vertex data
[https://gyazo.com/5fdcfb23c84feaea39a26cdd86ea4ae0](https://gyazo.com/5fdcfb23c84feaea39a26cdd86ea4ae0)

beginning of face data
[https://gyazo.com/0d3f0c1d93f90c3c9b912fa87dbb88b7](https://gyazo.com/0d3f0c1d93f90c3c9b912fa87dbb88b7)

end of face data beginning of UV data
[https://gyazo.com/ee71bbdb375a782a5a3fe1b0bec1b3b1](https://gyazo.com/ee71bbdb375a782a5a3fe1b0bec1b3b1)

end of UV data
[https://gyazo.com/8156fd793bdddff12af887699b8f2d9e](https://gyazo.com/8156fd793bdddff12af887699b8f2d9e)

All the models follow this same format
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-30T07:40:38+00:00
- Post Title: Life After mesh model file

Hello, I found some inconsistency for the addresses of face index block and the uv block. They don't fit the displayed model.
(Probably belong to another sub mesh.)

For me it's 
address of face indices: 131366 (0x20126)
and
uv address 171086 (0x29c4e)
.



model_b_f_3025-mesh.jpg (168.78 KiB) Viewed 241 times

(Sorry for using a different app.)
btw, the 19860= 6620*3 result from hex2obj using face indices count
## Post #5
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-11-30T07:46:59+00:00
- Post Title: Life After mesh model file

Hey Shakotay thank you for taking the time to reply., you are right I think, you can see the large UV map overlapping the other, i don't think its a submesh but another material face for the model. 
I am noticing inconsistencies in the Face and UV data location as well. 

the vertices are easy to find but I have really struggled to locate UV data, I can find face data easy now.
I can load them pretty reliably. but i have 135 models, I would really like to be able to import them directly to blender or even noesis.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-30T07:57:40+00:00
- Post Title: Life After mesh model file

If the models have one sub mesh only you could write a Noesis script for yourself, I guess. (Check for a template in one of my previous posts.
Here for example, click up arrow:)

> Reply from shakotay2 ↑Fri Jul 02, 2021 4:34 am at Fri Jul 02, 2021 4:34 am
>
> 

You simply need to search for 000001000100 in a .mesh, and 6 bytes after a fitting offset you'll find the vertex count and the face count as DWords (4 bytes each).

btw, for one mesh you don't need a "while loop" as in said example
Getting uv data needs some more lines, because it's separate (not in an FVF block together with vertex data).

well, and it's not big endian...
Maybe use another "template" as a base, from Tuliopilloto:

> Reply from shakotay2 ↑Wed Nov 23, 2022 8:10 pm at Wed Nov 23, 2022 8:10 pm
>
>
## Post #7
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-11-30T08:19:03+00:00
- Post Title: Life After mesh model file

That is pretty awesome, I would like to be able to load its skeleton and weight paint as well, it's at the top of the mesh file, you can see the bone names. but i think the base script will only turn it to an OBJ ?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-30T08:21:21+00:00
- Post Title: Life After mesh model file

Noesis can export to different formats. But said script doesn't care for bones and weights. That requires additional script lines.

(I'd suggest to solve it one step after the other...  )
## Post #9
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-11-30T08:26:54+00:00
- Post Title: Life After mesh model file

thank you, you said search for 000001000100  in the mesh file, is that binary? I'm alittle confused what that is looking for.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-30T08:29:57+00:00
- Post Title: Life After mesh model file

yep, binary (or hexadecimal, as you wish), counts rectangled, sig 000001000100 preceeding:
.



LifeAfter_counts.png (26.41 KiB) Viewed 219 times
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-11-30T14:51:46+00:00
- Post Title: Life After mesh model file

> Reply from shakotay2 ↑Wed Nov 30, 2022 4:29 pm at Wed Nov 30, 2022 4:29 pm
>
> 
counts rectangled
the number of vertices 4518 is also indicated there  

> Reply from Xr79 ↑Wed Nov 30, 2022 9:43 am at Wed Nov 30, 2022 9:43 am
>
> 
thanks to vlad_256
 



also skeleton using skelFinder



b_f_3025.mesh.png (14.5 KiB) Viewed 182 times


*(Thanks to this model, I noticed that I published "skelFinder" with an error, when reading the parent due to checking for EOF, it always returned 0, fixed))
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-30T18:10:00+00:00
- Post Title: Life After mesh model file

> Reply from Durik256 ↑Wed Nov 30, 2022 10:51 pm at Wed Nov 30, 2022 10:51 pm
>
> 
the number of vertices 4518 is also indicated there  
Xr79 wrote: ↑Wed Nov 30, 2022 9:43 am
thanks to vlad_256Dunno, what he did there. Seems he confuses things or models. 
There's model_b_f_3025.mesh that I cared for, "model_"  being part of the name.
Vertex block is here: 2C24 to F524, that is 4288x12 (decimal).

And there's another model sample, b_f_3025.mesh, of bigger size which might be the cause for the confusion.
## Post #13
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-11-30T18:51:08+00:00
- Post Title: Life After mesh model file

> Reply from shakotay2 ↑Thu Dec 01, 2022 2:10 am at Thu Dec 01, 2022 2:10 am
>
> 
And there's another model sample, b_f_3025.mesh, of bigger size which might be the cause for the confusion.
Yes, that is right. I downloaded models from Discord, And you  used the file from the this topic (with 'model_')
## Post #14
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-11-30T22:48:47+00:00
- Post Title: Life After mesh model file

Oh dang it looks like you were able to get more than I did. I can upload more samples if they are needed, but I think all the models follow the same structure.
I uploaded more sample models if they can help.
I'm not sure what the submesh is about either, because no model i have loaded using hex2obj actually used that sub mesh. and it looked fine without it. it was usualy the neck seal area. but the rest of it was always one UV map.
## Post #15
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-12-02T02:05:38+00:00
- Post Title: Life After mesh model file

So Vlad did an awesome job on the script to import them to noesis
I have run into a new problem. 
the NPK extractor i used is out of data and spits out 17 thousand un named files. I have a modified script i used from ages ago to rename HASH files
my question is

I know that they are .mesh files and I know they should have a name. but when extracted they are just HASHes.
is the name of this file stored somewhere in this Hex file?
an example of the mesh name would be
b_f_3165.mesh
but the extractor spits them out as various forms of 
"F8CB5A495EFE23AE" <- file name

here is the script i modified to rename them


 mesh_RENAMER.rar
(204 Bytes) Downloaded 21 times
## Post #16
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-02T15:37:00+00:00
- Post Title: Re: Life After mesh model file

> Reply from Xr79 ↑Fri Dec 02, 2022 10:05 am at Fri Dec 02, 2022 10:05 am
>
> 
i know that they are .mesh files
but there may be textures and other files.  I made a console application that changes the extension depending on the first 4 bytes of 'magic'.  maybe [.mesh, *.dds, *.gis], other files will remain unchanged.
just drop a file or directory on it and it will scan all the files in the folder.
tested on "_Unknow" folder.
source code:

```
using System.IO;
using System.Text;

namespace ConsoleRenamer
{
    internal class Program
    {
        static void Main(string[] args)
        {
            if (args.Length > 0)
            {
                bool flag = File.GetAttributes(args[0]).HasFlag(FileAttributes.Directory);
                string[] files = Directory.GetFiles(flag ? args[0] : Path.GetDirectoryName(args[0]));

                foreach (string file in files)
                {
                    uint magic;

                    using (BinaryReader br = new BinaryReader(File.OpenRead(file), Encoding.UTF8))
                        magic = br.ReadUInt32();

                    switch (magic)
                    {
                        case 1397311314:
                            rename(file, ".gis");
                            break;
                        case 542327876:
                            rename(file, ".dds");
                            break;
                        case 3150479412:
                            rename(file, ".mesh");
                            break;
                    }
                }
            }
            Console.ReadKey();
        }

        static void rename(string name, string ext)
        {
            File.Move(name, Path.ChangeExtension(name, ext));
            Console.WriteLine($"{name} >> {ext}");
        }
    }
}

```

[ConsoleRenamer.zip](https://xentaxbackup.github.io/file/23098_ConsoleRenamer.zip)
