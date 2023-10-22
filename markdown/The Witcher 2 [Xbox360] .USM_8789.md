## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-04-18T19:42:02+00:00
- Post Title: The Witcher 2 [Xbox360] .USM

Hello. 

So The Witcher 2 uses .usm format, and I thought it should be easy to demux it into M2V + ADX with VGMToolbox, convert ADX to wav, and then mux it all together into MKV container with the help of Mkvmerge. It always worked before. 

But this time when ever I drop .m2v video file from Intro movie into mkvmerge it gives an error:

```

"C:\Program Files (x86)\MKVToolNix\mkvmerge.exe" --output-charset UTF-8 --identify-for-mmg "C:\[CG]\witcher 2 [xbox360]\intro_40534656.m2v"

Output:

Error end of file error

Error: File C:\[CG]\witcher 2 [xbox360]\intro_40534656.m2v has unknown type. Please have a look at the supported file types ('mkvmerge --list-types') and contact the author Moritz Bunkus <moritz@bunkus.org> if your file type is supported but not recognized properly.
```

Some other .usm files from the same game do not have this problem, and .m2v stream from (for example) alchemy.usm is properly recognized by mkvmerge.

I'm not sure whether it's VGMToolbox not extracting this particular .m2v the right way or it's a slightly different encode of Mpeg stream inside the .usm, which results in Mkvmerge not being able to identify it accordingly. 

By the way this intro's .m2v file is supported by VLC and other media players. So it must be just a header or something that prevents it from being loaded into mkvmerge.

Please have a look at the sample uploaded and any help would be much appreciated. 

Also, VGMToolbox is the only software that I am aware of which is capable of demuxing USM files, so if there are others it would be good to try them as well.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-26T19:14:18+00:00
- Post Title: The Witcher 2 [Xbox360] .USM

Read the rules? NO ORIGINAL GAME FILES.
