## Post #1
- Username: SiPlus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 05, 2011 6:30 pm
- Post datetime: 2012-07-20T10:37:00+00:00
- Post Title: NovaLogic .sbf (Delta Force, Joint Ops, Tachyon, simulators)

I'm trying to extract .sbf files from NovaLogic games.

I found that the files inside are split into 4096-byte segments, all starting with similar 8-byte header. I posted some info about the segments on the wiki, [here](http://wiki.xentax.com/index.php/SBF0).

When I remove segment header, the sound becomes much more clear, but some volume jumps are still there, but this is not a big issue, I think it's just difference introduced by DFX2.

However, I have a much bigger problem. I don't know how to find the last segment in a file. readbytes<filesize doesn't work, and there is no number of segments in the SBF header.

Can anybody help me?

EDIT: found a solution, filesize/segmentsize.
## Post #2
- Username: srcs34k
- Rank: n00b
- Number of posts: 14
- Joined date: Wed May 23, 2012 11:45 pm
- Post datetime: 2016-08-05T20:53:42+00:00
- Post Title: NovaLogic .sbf (Delta Force, Joint Ops, Tachyon, simulators)

[http://www.novahq.net/files.php?ID=325](http://www.novahq.net/files.php?ID=325)
Supported Games: DFX, DFX2, DFBHD, DFBHDTS, JOTR, JOE

> Decompress
>
> - Wave
>
> - TGA
>
> - DDS files
>
> - and more...
>
> 
>
> For NovaLogic Games.
>
> 
>
> Includes:
>
> BDC1Dumper.exe
>
> BFC1Extractor.exe
>
> CPT_PLYDumper.exe
>
> CTP_CDEP_Stripper.exe
[DecompressionTools.zip](https://xentaxbackup.github.io/file/11488_DecompressionTools.zip)
## Post #3
- Username: pleadabot
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 18, 2023 12:05 am
- Post datetime: 2023-10-17T16:08:44+00:00
- Post Title: NovaLogic .sbf (Delta Force, Joint Ops, Tachyon, simulators)

[https://amokfa.github.io/posts/dfbhd_sbf.html](https://amokfa.github.io/posts/dfbhd_sbf.html)
