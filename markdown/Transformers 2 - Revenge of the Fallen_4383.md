## Post #1
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2010-04-25T16:50:41+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

Hey Guys,

Hope you are all well,

Ive done a search but cant seem to find anything, also looked through google.

Im wondering if anybody has had a go at modding transformers 2 revenge of the fallen?!

Or if there is any other tool apart from 3d ripper x that will extract textures and models?

Any help or a pointer would be great!

Cheers in advance
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-25T16:55:12+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

if it's developed by the same people of Transformer 1 then this script should do the job:
[http://aluigi.org/papers/bms/ttgames.bms](http://aluigi.org/papers/bms/ttgames.bms)

otherwise you must upload an archive or a part of it
## Post #3
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2010-04-25T18:02:04+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

thanks aluigi,

forgive me for asking but what do I do with this script
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-25T19:53:36+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

that one is a script for [quickbms](http://aluigi.org/quickbms) that extracts all the files contained in the DAT archives used in the first Transformer game,
## Post #5
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-05-05T16:36:14+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-05T18:35:05+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-05-06T19:44:36+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

I tried to unpack it with offzip just like you've said savage, and tried sir luigis ttgames script, but it says that it's still invalid

thanks for the info though sir savage
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-07T08:02:39+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

But transformers 1 uses lz2k compression, and transformers 2 uses zlib..it's a different script, someone must to make a new one.
My knowledge making progrmas it's close to 0..(is not my area) but i'm trying to make a stupid and silly zlib unpacker for tihs but i get errors, sure the script it's at 99% wrong but...

```
get unkown long
get SIZE long
set NAME fname.str
get ZSIZE asize
math ZSIZE -= 0x14
goto 0x14
savepos OFFSET
comtype inflate
clog NAME OFFSET ZSIZE SIZE

```

And i get:

> Error: the compressed zlib/deflate input is wrong or incomplete (-3)
>
> Error: there is an error with the decompression
>
>        the returned output size is negative (-1)
But with offzip worked perfect.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-07T17:27:40+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

quickbms returns that error because that script is not correct, the second field is ZSIZE and not unknown
anyway due to the lack of the SIZE field and the presence of only one compressed block is without doubts better to use offzip for this job:
offzip soldiermale.str output.str 0x14
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-07T22:30:07+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

Thanks for the correction aluigi (and for the tip) anyway..the game check for compressed data and don't works.

But it's the 1rst script (kiddy and silly..but i'm starting)
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-08T14:41:26+00:00
- Post Title: Transformers 2 - Revenge of the Fallen

for the recompression the job is easy.
copy the header (the first 0x14 bytes) in a new file called, for example, new.str and then use packzip to compress the data you have modified:
offzip -o 0x14 edited.str new.str

then open new.str with a hex editor, go at its end, take note of the reported offset (attention that you need to add 1, for example if in xvi32 you see 2E9ABD then the total size is 2E9ABE), go at offset 4 and place that value there in little endian.

well, it's more easy to do than explaining :)
