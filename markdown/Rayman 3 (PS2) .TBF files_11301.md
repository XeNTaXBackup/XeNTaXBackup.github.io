## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2014-03-10T22:19:59+00:00
- Post Title: Rayman 3 (PS2) *.TBF files

Hi guys, 

I have ventured into graphics file formats before, but I know absolutely zero about PS2 graphics formats. If you do, I could definitely use your help with these files!

```
https://app.box.com/s/irky7011bmvwmbgbob22
```

They're from an early demo of Rayman 3 and I think there might be some interesting stuff in it.

Thanks,
Droolie.
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-03-11T07:27:06+00:00
- Post Title: Rayman 3 (PS2) *.TBF files

Here's what I found :

```
{
    DWORD Header         //0x0AB9FC72
    DWORD palletteType //????
    DWORD Width
    DWORD Height
    BYTE* Pallette
    BYTE* ImageData
}
```


this structure repeats till eof.
Edit : ImageData could be swizzled.
## Post #3
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2015-08-29T21:53:49+00:00
- Post Title: Rayman 3 (PS2) *.TBF files

Bumping this, does anyone knows anything?
## Post #4
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-09-28T20:20:21+00:00
- Post Title: Rayman 3 (PS2) *.TBF files

[http://www.mediafire.com/download/1x41a ... tbftool.7z](http://www.mediafire.com/download/1x41ad0f379d21o/tbftool.7z)
Just drag a TBF file into the executable and it'll extract png files from the file.
4-bit textures don't convert properly for some reason, but I included the source code in case anyone wants to look at it.
## Post #5
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2015-11-21T15:12:38+00:00
- Post Title: Rayman 3 (PS2) *.TBF files

> Reply from TGE
>
> http://www.mediafire.com/download/1x41a ... tbftool.7z
Just drag a TBF file into the executable and it'll extract png files from the file.
4-bit textures don't convert properly for some reason, but I included the source code in case anyone wants to look at it.
Thanks a lot! It works kinda nicely!
