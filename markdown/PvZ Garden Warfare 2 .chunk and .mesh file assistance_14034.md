## Post #1
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2016-02-28T18:47:16+00:00
- Post Title: PvZ Garden Warfare 2 .chunk and .mesh file assistance

I've already dumped the archive of Garden Warfare 2, but I need assistance in getting the BF4 Chunk and Mesh management tool, Skeleton and Mesh importer MaxScripts, and EBX to txt converter to work with it. It uses Frostbite 3 engine and I've managed to rip from PvZ Garden Warfare 1 before, but it seems that the tools for ripping models from it need to be updated of the sort.

I have provided a sample with a .mesh and .chunk file from Garden Warfare 2 if anyone needs it. Either the tools need to be updated, or I'm doing something wrong, here.

Thanks!
[GW2Sample.zip](https://xentaxbackup.github.io/file/10538_GW2Sample.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-28T21:20:39+00:00
- Post Title: PvZ Garden Warfare 2 .chunk and .mesh file assistance

Dunno about the tools but the mesh format (in .chunk) is rather simple:



face.jpg (166.34 KiB) Viewed 208 times
## Post #3
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2016-02-28T23:13:23+00:00
- Post Title: PvZ Garden Warfare 2 .chunk and .mesh file assistance

Well that's good to know that the mesh files are rippable, though I'd still prefer to figure things out with the tools. Either I'm doing something wrong, or the tools need updating. Whichever comes first, I suppose.
## Post #4
- Username: thanhhieu02
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 20, 2015 3:19 pm
- Post datetime: 2016-03-01T15:03:46+00:00
- Post Title: PvZ Garden Warfare 2 .chunk and .mesh file assistance

Can you up more file plants ?
and shakotay2 you can unpack file obj ?
## Post #5
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2016-05-12T05:22:38+00:00
- Post Title: PvZ Garden Warfare 2 .chunk and .mesh file assistance

Good news, Everyone! -Farnsworth

I've managed to import the mesh into 3DS Max, finally, using an updated Chunk and mesh management tool and the NFS 16 mesh importer found here: [https://forum.xentax.com/viewtopic.php? ... 8&start=15](https://forum.xentax.com/viewtopic.php?f=16&t=14108&start=15)

Now I just gotta figure out how to get the Skinning to import on the bones, like the previous script did before. Anyone have any ideas?
## Post #6
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2016-11-06T23:58:01+00:00
- Post Title: PvZ Garden Warfare 2 .chunk and .mesh file assistance

I apologize for necro-bumping this thread, but since it's my thread anyway, I thought I'd might as well. So I revisited this ripping project and am trying to get a new dump of the .cas archive using a newer dumper, but now it gives me this message:

```
  File "C:\Users\owner\Documents\ChunkAndMeshTools\swbf\swbf_dump\sw_dumper.py", line 315, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Users\owner\Documents\ChunkAndMeshTools\swbf\swbf_dump\sw_dumper.py", line 287, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\owner\Documents\ChunkAndMeshTools\swbf\swbf_dump\sw_dumper.py", line 118, in dump
    toc=cas.readToc(tocPath)
  File "C:\Users\owner\Documents\ChunkAndMeshTools\swbf\swbf_dump\cas.py", line 95, in readToc
    return Entry(unXor(tocPath))
  File "C:\Users\owner\Documents\ChunkAndMeshTools\swbf\swbf_dump\cas.py", line 37, in __init__
    raise Exception("Entry does not start with \\x82 or (rare) \\x87 byte. Position: "+str(f.tell()))
Exception: Entry does not start with \x82 or (rare) \x87 byte. Position: 1
>>> 

```


Any ideas on how to go about this would be VERY appreciated. Thanks!
