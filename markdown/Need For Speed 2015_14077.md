## Post #1
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2016-03-11T13:32:37+00:00
- Post Title: Need For Speed 2015

Hey guys,


I really need some help on the need for speed 2015 files, i've tried to use Frenkenstein's BF4 frostbite extracter,

I've extracted some files, but when i get to genesis01.toc i get this error


> genesis01.toc
>
> D:\NFS 2015 Extraction\Dump/bundles/res/levels/genesis01/worldassets/architecture/residential/bldn_residential_independentgarage01_7x3x5/bldn_residential_independentgarage01_7x3x5_mesh_occludermesh 100dca33c8c6a225 ffffffffffffffffffffffffffffffff.occludermesh
>
> 
>
> Traceback (most recent call last):
>
>   File "D:\NFS 2015 Extraction\BF_Four_Python_Scripts\bf4dumper.py", line 257, in <module>
>
>     if "tocRoot" in locals():  dumpRoot(tocRoot)
>
>   File "D:\NFS 2015 Extraction\BF_Four_Python_Scripts\bf4dumper.py", line 248, in dumpRoot
>
>     dump(fname,targetDirectory)
>
>   File "D:\NFS 2015 Extraction\BF_Four_Python_Scripts\bf4dumper.py", line 179, in dump
>
>     writePayload(entry, targetPath, sourcePath)
>
>   File "D:\NFS 2015 Extraction\BF_Four_Python_Scripts\bf4dumper.py", line 224, in casPatchedPayload
>
>     casPayload(bundleEntry, targetPath, sourcePath) #if casPatchType is not 2, use the unpatched function.
>
>   File "D:\NFS 2015 Extraction\BF_Four_Python_Scripts\bf4dumper.py", line 213, in casPayload
>
>     LZ77.decompress(catEntry.path,catEntry.offset,catEntry.size, bundleEntry.originalSize,targetPath)
>
> WindowsError: [Error -529697949] Windows Error 0xE06D7363
>
> >>>

looks more like the problem is with "occludermesh" or the "LZ77"


EDIT: after some edits i figured it out.

but all extracted .mesh files are 0kb...
anyone can help me?
