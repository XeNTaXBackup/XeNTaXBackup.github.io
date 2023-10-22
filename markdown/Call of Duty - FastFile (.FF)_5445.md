## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-11-23T10:45:47+00:00
- Post Title: Call of Duty - FastFile (.FF)

[out]
## Post #2
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-11-24T17:23:52+00:00
- Post Title: Call of Duty - FastFile (.FF)

Yeah, all i could find out so far was 2 size-related and one number of index. It looks like there aren't any pointers but anyway i migth be wrong. We need tomake a joint effort on this one...
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-11-25T00:28:59+00:00
- Post Title: Call of Duty - FastFile (.FF)

[out]
## Post #4
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-11-25T01:21:53+00:00
- Post Title: Call of Duty - FastFile (.FF)

> Reply from Wobble
>
> The problem I'm having is that the datafile entry headers don't seem to be consistent.  For example, there are different types of
datafiles, .text, .wav, etc..., and they all seem to have a different header based on its type?

Which means if you don't know how to read a certain type, you can't advance to the next datafile?  Crappy format.

I was expecting it to be simple, as if you could treat them all as raw data types.  I was hoping for this format, as it is the most logical:
0xFFFFFFFF
DWORD raw_file_size1
0xFFFFFFFF
char raw_filename1[asciiz]

raw data1 follows

0xFFFFFFFF
DWORD raw_file_size2
0xFFFFFFFF
char raw_filename2[asciiz]

raw data2 follows

But, it looks like only text files follow this format?  

They always use a special entryId of 0xFFFFFFFF to signify the start of something, whether it be a filesize, a filename,
a filetype, or something else.

Pretty much. I've tried mapping every asset structure. It took WAY too long and I never finished.
## Post #5
- Username: dogkarl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 10, 2010 2:56 pm
- Post datetime: 2010-11-25T03:53:35+00:00
- Post Title: Call of Duty - FastFile (.FF)

> Reply from Wobble
>
> 
Which means if you don't know how to read a certain type, you can't advance to the next datafile?  Crappy format.

That is true. I've researched it for a week, now i've able to load the texts and font. So there's some info I can share.
The 0xFFFFFFFF is actually a pointer place holder. The FF loading system replaced the tradition "new" with their own memory loading mechanism and object construction system for "Fast Loading".(Don't understand? Read C++ Primer)

There's three types of value for the placeholder. 0xFFFFFFFF stands for "Allocate new space from the pool and create object". 0xFFFFFFFE happens much rare, stands for "Allocate four bytes for a Pointer then Allocate new space from the pool and create object". Sometimes it's a value for example "0x80005cdc", this value is actually two parts. High 3 bits stands for the object memory type. Here is "0x4", type 4 memory type. Low 29 bits stands for the object offset it refers to.
Here is some object at "0x5cdc" in type 4 memory.

So in general, it's a very complexed system filled with data reference, different memory type and data alignment. It's a true hell. Maybe after I finally go through this hell, I will write more..

Good luck..this format is a real pain in the ass.
## Post #6
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-11-25T06:01:38+00:00
- Post Title: Call of Duty - FastFile (.FF)

[out]
