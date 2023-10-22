## Post #1
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-09-25T13:17:35+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

I'd love if somebody could work out the decompression, really interested to see what's out there.  They have a *SK_ASC* header.  Attached sample.
[cr0003.zip](https://xentaxbackup.github.io/file/9784_cr0003.zip)
## Post #2
- Username: starkiller
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 10:55 am
- Post datetime: 2015-10-06T23:47:30+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

> Reply from SubDrag
>
> I'd love if somebody could work out the decompression, really interested to see what's out there.  They have a *SK_ASC* header.  Attached sample.

I've been posted related article several month ago, but nothing to help me.

I can conclude that this is slightly modified hi-rate compression algorithms. (That is even better than gzip/deflate level 9, in 2002)
If you are good at reverse-engineering I can give you my own research data.
## Post #3
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-10-06T23:50:45+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

It's almost surely some kind of proprietary compression that needs reverse engineering from ida pro, or I'm not sure if you can step in Dolphin, that would be helpful (is that possible?).
## Post #4
- Username: starkiller
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 10:55 am
- Post datetime: 2015-10-06T23:57:36+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

> Reply from SubDrag
>
> It's almost surely some kind of proprietary compression that needs reverse engineering from ida pro, or I'm not sure if you can step in Dolphin, that would be helpful (is that possible?).

I already dump decompression algorithm subroutine from dol using a IDA pro. 

But If you don't have any advanced knowledge about disassembly, It's... a ton of waste time, without expert's help, I think.
## Post #5
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-10-07T00:07:28+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

So the assembly routine is isolated?  Can you dump the section from ida pro to a text file for me to look at, of this assembly code, and any notes of inputs you have to that function?   And if you can provide a sample file, that is compressed, and decompressed perfectly (use the ingame decompression and save off the exact decompression).  It's been a while since I looked at powerpc but it is not impossible.  You may have done this, but not seeing raw ida pro disassembly, and just identify for me compressed vs uncompressed file in there (not sure what I'm looking at with those files).
## Post #6
- Username: starkiller
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 10:55 am
- Post datetime: 2015-10-07T00:14:10+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

> Reply from SubDrag
>
> So the assembly routine is isolated?  Can you dump the section from ida pro to a text file for me to look at, of this assembly code, and any notes of inputs you have to that function?   And if you can provide a sample file, that is compressed, and decompressed perfectly (use the ingame decompression and save off the exact decompression).  It's been a while since I looked at powerpc but it is not impossible.

Check inside the folder (Using a decompiler to get code)
I've used a japanese version and english version both to analysis, so some of data would be different with english version's offset.  (e.g  8013FC58  /  8014191C)

all cmp/bin file is compreesed data, and dmp/dec is decompressed data from memory dump.


(As I know, all decompressed data has a 4 byte of original-file-size value before the data start, (0x00-0x03), but some files I cut the 4 byte data because I DIDN'T GET WHAT IS THAT before, so careful that   )

I'm not good at assembly, or compiling, So this IS what I got only. I cannot help you much expected.
I hope you find more information. If you get anything to do better we know, please let me know.
## Post #7
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-10-07T00:43:55+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

Oh I don't want a decompiler, I want the original disassembled powerpc code from ida pro.  Can you give me that, dumped to text or something?  And your ida project, but really just the text dump of the entire decompression routine and all subroutines it calls.    The sample files should be helpful, though I guess I'll beware of the size, should be obvious though in decompression code.
## Post #8
- Username: starkiller
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 10:55 am
- Post datetime: 2015-10-07T00:49:54+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

> Reply from SubDrag
>
> Oh I don't want a decompiler, I want the original disassembled powerpc code from ida pro.  Can you give me that, dumped to text or something?  And your ida project, but really just the text dump of the entire decompression routine and all subroutines it calls.    The sample files should be helpful, though I guess I'll beware of the size, should be obvious though in decompression code.

You mean like this?   [https://drive.google.com/uc?id=0B7toBwm ... t=download](https://drive.google.com/uc?id=0B7toBwm7dUDiSEZDb0hLU2NxZk0&export=download)

or Like this? [https://drive.google.com/uc?id=0B7toBwm ... t=download](https://drive.google.com/uc?id=0B7toBwm7dUDibXJqZEhwVVEtZkU&export=download)


I'm not sure it's entire code or not (but I'm sure it's the main-core of decompression related method), 
So I linked decompression-header-seems-like code below

[https://drive.google.com/uc?id=0B7toBwm ... t=download](https://drive.google.com/uc?id=0B7toBwm7dUDiNzd0b2VLXzc2UnM&export=download)
## Post #9
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-10-07T00:57:53+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

Yep thanks.  The text file representation.   I mean hopefully a powerpc expert can go through it and sort it out, but I will look.
## Post #10
- Username: starkiller
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 10:55 am
- Post datetime: 2015-10-07T01:03:11+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

> Reply from SubDrag
>
> Yep thanks.  The text file representation.   I mean hopefully a powerpc expert can go through it and sort it out, but I will look.

I hope you find good result.  Cheer!

* All of file I mention or linked is inside of PPC Decompresion folder (with sub folder)
so anything you need another data, check inside the folder.
## Post #11
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-10-07T01:28:19+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

Looks like you're missing some key asm functions disassembled, can you disassemble those to text (or maybe just dump the whole chunk of disassembly from like 80130000 to 80150000 in ida, if you can in case this calls more):
8013FB14
8013FA24
8013F2BC
8013FA9C

I guess you can decompile those for fun too, though probably disassembly is more usable, maybe if they're simple enough it can tell.

Did the 800F3B34 function in header do anything interesting?  I guess you've concluded the 8013FC58 is the main decompression routine?
## Post #12
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2021-05-23T14:27:52+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

Is there anyone willing to tackle this?  Or at least point me in the right direction on how I could do this nowadays with Ghydra and better tools.
## Post #13
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2021-09-24T15:29:15+00:00
- Post Title: Decompress Eternal Darkness Gamecube?

Like most things in life, you have to do it yourself, if you want things done 

[https://github.com/jombo23/N64-Tools/tr ... alDarkness](https://github.com/jombo23/N64-Tools/tree/master/DecompressEternalDarkness)

The text is encoded kind of weird, if someone wants to look into it.  Characters like 0xFD/0xFC instead of th, e, etc, but different per file (maybe a table inside the Room files?)
