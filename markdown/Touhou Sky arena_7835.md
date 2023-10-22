## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-10T17:42:50+00:00
- Post Title: Touhou Sky arena

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-10T18:44:57+00:00
- Post Title: Touhou Sky arena

jut post the executable of the game and i am sure someone can figure it out in a few seconds.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-17T04:35:43+00:00
- Post Title: Touhou Sky arena

The contents of this post was deleted because of possible forum rules violation.
[Touhou Sky Arena.7z](https://xentaxbackup.github.io/file/4903_Touhou Sky Arena.7z)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-06T02:12:41+00:00
- Post Title: Touhou Sky arena

Wow ok I just realized the format is is chunk based. I was wondering how to determine how many bones I'm supposed to read.

Now to try to add the bones/weights.

Chunk 0 is the start of the mesh, although the chunk size seems wrong. I would just read the mesh name and move on.

Chunk 1 is the vertex section.

Chunk 2 is the faces.

chunk 3 is the start of the material section, which gives the matCount. The chunk size also seems wrong.

Chunk 4 is a material

chunk 5 is a texture associated with the current material

Chunk 7 is a bone

Chunk 8, 9, 10 I imagine are related to animations, morphs, and stuff.

At the end of each section there's a -1.

```
   read chunk
   if chunk != -1:
       read chunkSize
       if chunk == 0
           ...
       elif chunk == 1
          ...
       ...

```
## Post #5
- Username: Tamao
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 16, 2011 4:29 am
- Post datetime: 2012-01-06T18:54:51+00:00
- Post Title: Touhou Sky arena

Is a pity that the guy doesn't want make public the GPK tool, i was looking for it D: BTW good work =) I was looking for the models (or the tools) as i played with Touhou Sky Arena *-*  

BTW: how i can extract the bones? I hate make them by myself xD It's a looong way T_T Is the first time that i use noesis for that O.O 

I red that: If anyone knows how bones work, it's stored in the mdl file located right after the materials. <-- but where exactly? D:
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-06T20:23:58+00:00
- Post Title: Touhou Sky arena

I got in touch with the guy that made it and he gave me the scripts and doesn't mind if I release them.

So I posted them here [viewtopic.php?p=64718#p64718](http://forum.xentax.com/viewtopic.php?p=64718#p64718)
If someone can write it in C++ or something that would be great, cause it's kind of slow with python (and I think even slower since it's using insani rather than directly reading bytes but I don't know)

It works for the hayate patch, but he isn't sure whether it'll still be the same key when kurenai comes out (they might change it if they realize that it's been cracked)

The model format is huge cause it stores absolutely everything.
The geometry is like 10% of the file.

Chunk 7 has a bunch of bone names and parent bone names, so I'm assuming that's defining all the bones.
There are a bunch of floats in some of the bone structs so that might be where the vertex weights are defined.

I still haven't actually written a plugin to load bones with proper weighting (nor do I know how to check), so haven't done anything.
## Post #7
- Username: Tamao
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 16, 2011 4:29 am
- Post datetime: 2012-01-24T10:58:18+00:00
- Post Title: Touhou Sky arena

Mhh do u know where i can find Aya and Sanae too? The package that u posted is of the prepatch game °^° BTW, i'm boning them by myself ^^ (For MMD)
I'm getting fun XD
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-24T16:17:33+00:00
- Post Title: Touhou Sky arena

Just extract from Hayate patch.

If I get around to it I'll write an exe for it rather than rely on the python. But the python scripts work just fine and pack/repack as well.
## Post #9
- Username: Tamao
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 16, 2011 4:29 am
- Post datetime: 2012-01-24T20:00:45+00:00
- Post Title: Touhou Sky arena

extract them from the gpk file  right? But i dunno how to do that D: 
If u can tell me it will be nice :3 is the first time that i do a similar thing so... but it's a good deal to learn something of new
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-25T01:32:34+00:00
- Post Title: Touhou Sky arena

Just download the python extract scripts and insani and drag/drop gpk over it.
## Post #11
- Username: Tamao
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 16, 2011 4:29 am
- Post datetime: 2012-01-26T15:59:47+00:00
- Post Title: Touhou Sky arena

> Reply from finale00
>
> Just download the python extract scripts and insani and drag/drop gpk over it.

roftl o.o nice xD thnx for your patience =)
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-10T02:59:35+00:00
- Post Title: Touhou Sky arena

Here's something I wrote while figuring out C#
[http://pastebin.com/HZLX74bM](http://pastebin.com/HZLX74bM)

To use, just drag and drop a bunch of gpk files onto it and let it do its work.

All it does is extract the file. I've dumped the value that's used to determine the xor key into a file called "keys.txt" which will be automatically updated everytime a gpk archive is extracted, and will be used when re-packing.

The keys file is created in the same directory as the executable, so you can call the exe from wherever and ignore the keys file completely.

My assumption is that you can't re-pack unless you have actually unpacked, so as long as you unpack the archive first, an entry for the key will exist for you to re-pack it.

It works for the original release and somewhat for the Hayate patch. I don't have the decrypt keys for other hayate files/any of the kurenai models

Can anyone look over the code and point out where I could make optimizations? It seems kind of slow.
[TSAExtract.7z](https://xentaxbackup.github.io/file/5489_TSAExtract.7z)
## Post #13
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2013-11-18T12:44:41+00:00
- Post Title: Touhou Sky arena

> Reply from finale00
>
> Here's something I wrote while figuring out C#
http://pastebin.com/HZLX74bM

To use, just drag and drop a bunch of gpk files onto it and let it do its work.

All it does is extract the file. I've dumped the value that's used to determine the xor key into a file called "keys.txt" which will be automatically updated everytime a gpk archive is extracted, and will be used when re-packing.

The keys file is created in the same directory as the executable, so you can call the exe from wherever and ignore the keys file completely.

My assumption is that you can't re-pack unless you have actually unpacked, so as long as you unpack the archive first, an entry for the key will exist for you to re-pack it.

It works for the original release and somewhat for the Hayate patch. I don't have the decrypt keys for other hayate files/any of the kurenai models

Can anyone look over the code and point out where I could make optimizations? It seems kind of slow.
I tried to rip Reisen Udongein Inaba with the tool but it keeps crashing.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-11-22T04:26:31+00:00
- Post Title: Touhou Sky arena

Needs the key for the new archives.
## Post #15
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2013-11-22T16:53:55+00:00
- Post Title: Touhou Sky arena

> Reply from finale00
>
> Needs the key for the new archives.
What kind of new archives?
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-11-27T03:31:29+00:00
- Post Title: Re: Touhou Sky arena

The expansion packs (scarlet, the other one) use a different encryption key from the original.
## Post #17
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2013-12-13T13:38:25+00:00
- Post Title: Re: Touhou Sky arena

> Reply from finale00
>
> The expansion packs (scarlet, the other one) use a different encryption key from the original.
OK. Do you think you can do it?
