## Post #1
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-10-21T22:09:48+00:00
- Post Title: Hatsune Miku: Dreamy Vocal

game site
[http://miku.qq.com/](http://miku.qq.com/)
quickbms script to extract all unity files from game without names.
They load fine in unity studio.
File table looks xored.


```
math i = 0
endian big
for OFFSET = 0 != ARCHIVE_SIZE
    findloc OFFSET binary "\x55\x6E\x69\x74\x79\x46\x53\x00"
    goto OFFSET
    getdstring NULL 0x1E
    get ZSIZE long
    string NAME p "%08x.unity3d" i
    log NAME OFFSET ZSIZE
    math OFFSET + ZSIZE
    goto OFFSET
next i

```
## Post #2
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2018-10-29T05:15:05+00:00
- Post Title: Hatsune Miku: Dreamy Vocal

Thanks so much!
I hope it has better name than random number for file name
It's really hard to sort thing
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-10-29T11:23:37+00:00
- Post Title: Hatsune Miku: Dreamy Vocal

Use the load folder option in unity studio that will show model names.
you can then right click on the model and say show original file to find the files you want.
## Post #4
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2018-10-29T17:56:03+00:00
- Post Title: Hatsune Miku: Dreamy Vocal

Yeah that's wut i'm doing from the start
But it's take to long to read the whole folder 
Even though u just looking for few mesh

I just stick to this method if there none other method
