## Post #1
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2011-06-19T16:56:35+00:00
- Post Title: [NGC] F-Zero GX Unpacker and Packer (LZ and ARC)

Here's a command line tool that will take a F-Zero GX directory and unpack all LZ and ARC files, or take an unpacked directory and pack it again.

USAGE: 
Easy if you know how to use the command line.

```
OR
./gxpand pack input output
```


input and output SHOULD be directories, and MUST not be the same one. (There's a way to make it work with files, but it's so weird and useless that it isn't worth explaining). Usually you would want to pack or unpack the whole game, I guess...

---

IMPORTANT!, I have not tested if the repacked ARCs work in the game, because I have nothing to edit them and test! But they will most likely work... maybe   

There are no plans to support more formats in this tool! This tool will just support compression and archive formats which can be repacked lossless, and I think I got them all. This tool is designed to make possible to look at the game resources easily.

ALSO, I have already figured out the .TPL format (textures) completely, and a huge chunk of the .GMA format (models). This means that I'll post tools to convert or edit them in a few days   .
[gxpand.zip](https://xentaxbackup.github.io/file/4357_gxpand.zip)
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2011-06-20T17:23:14+00:00
- Post Title: [NGC] F-Zero GX Unpacker and Packer (LZ and ARC)

Well I have some good news. I figured out how are materials stored and I have been able to export fully texturized models   There are still some problems to solve (vertex normals, texture extraction, some unknown fields in the models that I'd like to figure out), but it's pretty good until now.

Here's a render to create hype   

[](http://img215.imageshack.us/i/st342.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)
## Post #3
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-06-21T14:00:17+00:00
- Post Title: [NGC] F-Zero GX Unpacker and Packer (LZ and ARC)

Thanks a lot for the info bro
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-07-29T09:39:33+00:00
- Post Title: [NGC] F-Zero GX Unpacker and Packer (LZ and ARC)

This tool is now also on the blog. [blog](http://forum.xentax.com/blog)
## Post #5
- Username: CosmoCortney
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 19, 2012 11:13 am
- Post datetime: 2012-02-19T03:19:54+00:00
- Post Title: [NGC] F-Zero GX Unpacker and Packer (LZ and ARC)

hi,
sorry, but can someone give me an explicite instruction how to use these codes? i tryed it for many times, but no success..
thanks
## Post #6
- Username: StarkNebula
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 24, 2013 12:06 pm
- Post datetime: 2013-01-24T16:14:46+00:00
- Post Title: [NGC] F-Zero GX Unpacker and Packer (LZ and ARC)

@GameZelda: Thanks a lot for the tools! I've been rummaging through F-Zero GX's ROM and  found a couple of cool things. The next step was to explore F-Zero AX's ROM (content is extractable with GameCube Explorer). 'gxpand' can unarchive AX's .ARC files but not any of the .LZ files. What I get is this: 

C:\Users\…\gxpand unpack input output
UnLZ output\st87.gma.lz
std.stream.ReadException@std\stream.d<46>: not enough data in stream
----------------
47EA54
47E8CB
----------------

C:\Users\…\gxpand>save
'save' is not recognized as an internal or external command, operable program or batch file.

C:\Users\…\gxpand>close
'close' is not recognized as an internal or external command, operable program or batch file.

I had to screen cap to see this because the prompt closes so quickly. Anyway, I was wondering if you or anyone else here could find a way to unpack AX's .LZ files. The ROM I'm working from for AX was (re)dumped on October 14, 2009. *The ROM is under-dumped, according to DiscEx0.8(a). This is particularly important to me because I've undertaken the task of writing the the F-Zero pages on tcrf.net, and would love to complete an F-Zero AX page. 

What will this accomplish? Well, going through what I could of AX, there are 19 new stages within AX's 'stg' folder that were not present in GX's ROM. Stages numbered 77-110, missing a bunch in between. These could either be test stages, or unused/beta stages. It would be crazy if we could extract that content. Not to mention that while looking at AX's 'bmp>stg', the folder containing the background images on course select, there is a file called, 'bmp_stg_aur' that is not present in GX, insisting there was 1 more venue that didn't make the cut in GX. *It is an .ARC file and can be extracted, but it's image is a placeholder (Port Town's BG with 'DUMMY' written over it.) Perhaps one of those stages at least contains 'aur' textures. 

Please let me know either what I can do to get the .LZ's unpacked or help me out if you're as curious about those files as I am. C:
