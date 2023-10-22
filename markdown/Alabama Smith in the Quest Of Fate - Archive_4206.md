## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-03-12T16:25:03+00:00
- Post Title: Alabama Smith in the Quest Of Fate - Archive

I'll appreciate any help or guidance to unpack the "images.pak" archive (hex start: 90400100) from "Alabama Smith in the Quest Of Fate". 
The head.bin and tail.bin may be downloaded here: [http://www.motionpress.com/uploads/alab ... il_pak.rar](http://www.motionpress.com/uploads/alabama_head_tail_pak.rar)

Thanks in advance!
## Post #2
- Username: ubrax
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-12T16:46:35+00:00
- Post Title: Alabama Smith in the Quest Of Fate - Archive

quickbms script.

> get filestart long
>
> get files long
>
> for i = 1 to files
>
> get offset long
>
> get size long
>
> get nsize long
>
> getdstring UNAME nsize
>
> set NAME unicode UNAME
>
> math offset += filestart
>
> math offset += 4
>
> log name offset size
>
> next i
