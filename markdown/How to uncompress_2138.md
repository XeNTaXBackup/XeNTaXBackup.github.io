## Post #1
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-10-09T12:48:08+00:00
- Post Title: How to uncompress?

How to uncompress?
[files.rar](https://xentaxbackup.github.io/file/897_files.rar)
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-09T18:17:11+00:00
- Post Title: How to uncompress?

The files are compressed with a pretty standard LZSS variation. Try the attached program with the following command line:

```
delzss in.txt out.txt
```

It works on the files you presented, but might fail on others. Just come back if that happens ...
[DeLZSS.zip](https://xentaxbackup.github.io/file/898_DeLZSS.zip)
## Post #3
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-10-10T09:02:58+00:00
- Post Title: How to uncompress?

It works 100%   

but i need to uncompress more than 2000 files  
i need source in visual C#

pls help
## Post #4
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-10T10:03:53+00:00
- Post Title: How to uncompress?

> Reply from astro
>
> but i need to uncompress more than 2000 files
Well, in that case try the attached file. The first parameter should be the file specification (wildcards allowed), the second one should be an output directory. Example:

```
DeLZSS c:\compressed\*.* c:\decompressed
```


> Reply from astro
>
> i need source in visual C#
I am sure that would be quite easy to do, but I have neither the C# experience nor the development environment necessary to do that.

You will have to ask somebody else to translate the code. If you know how to program in C#, you should even be able to do that yourself. Delphi code is usually quite easy to read; in this case you only need to understand the procedure DecompressBlock.

Hope that helps ...
[DeLZSS.zip](https://xentaxbackup.github.io/file/901_DeLZSS.zip)
## Post #5
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-10-11T12:50:04+00:00
- Post Title: How to uncompress?

TY
Can you give source of this
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-11T13:05:51+00:00
- Post Title: How to uncompress?

It's in the file! DPR, Delphi code! 

By the way, Deniz, Good Job! Can I interest you in taking a crack at that RA compression? See the TAW Total Air War thread. That looks like a similar way, but with a dictionary saved before the compressed text. Would be really cool if you could figure that one out?

[viewtopic.php?p=17481#17481](http://forum.xentax.com/viewtopic.php?p=17481#17481)
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-11T15:19:27+00:00
- Post Title: How to uncompress?

> Reply from Mr.Mouse
>
> It's in the file! DPR, Delphi code!
Now that you mention it, I see that I should have written that ... 

> Reply from Mr.Mouse
>
> Can I interest you in taking a crack at that RA compression? See the TAW Total Air War thread.
Sure, I can try. I can't promise anything, however, since the winter term of my studies starts in a few days. But let's see ...
## Post #8
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-10-11T17:03:54+00:00
- Post Title: How to uncompress?

i've translated lzss decompressor code to C# but only half of file is decompressing correctly
maby i need to change this: 
```
  const byte FBits     = 4;
  const byte Threshold = 3;
```

[Progr.rar](https://xentaxbackup.github.io/file/909_Progr.rar)
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-11T18:09:27+00:00
- Post Title: How to uncompress?

> Reply from astro
>
> i've translated lzss decompressor code to C# but only half of file is decompressing correctly
maby i need to change this: Code: Select all  const byte NBits     = 12;
  const byte FBits     = 4;
  const byte Threshold = 3;
No, the constants are correct that way. If you change them, the decompression will fail. (The deal is this: All references into the history buffer [also called "sliding window"] are 16 bits [i. e. two bytes] wide. NBits and FBits specify how many bits of those 16 are used for the length and offset values. The Threshold value tells you the minimum length of a compressed sequence -- since a buffer reference takes up two bytes, only longer sequences are compressed, thus the value of three.)

By the way, I just noticed a bug in my code. Remove the lines

```
  Exit;
```

That's actually complete nonsense ... though it's not critical, since it will never be invoked.

On the first look, I cannot see any problem with your code. We could try some checks, though: Output the values of "Len" and "Offset" to the console right after they have been computed. In the case of the files you posted earlier, they should look like this:

```

(3, 4078)
(4, 2)
(18, 10)
(18, 28)
(4, 4084)
(10, 114)
(6, 124)


match_compressed.txt:

(10, 4078)
(5, 4089)
(4, 7)
(5, 15)
(7, 21)
(3, 29)
(14, 37)
(5, 4089)
(3, 112)
(9, 65)
(3, 8)
(9, 39)
(7, 108)
(4, 127)
(4, 123)
(10, 4078)
(11, 108)
(18, 168)
(12, 186)
(12, 138)
(17, 151)
(12, 198)
(13, 149)
(12, 228)
(5, 274)
(12, 244)
(10, 291)
(6, 198)
```


[Edit: Too stupid to fix my own code ...  ]
## Post #10
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-10-11T19:27:51+00:00
- Post Title: How to uncompress?

my numbers are bad
## Post #11
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-11T20:28:59+00:00
- Post Title: How to uncompress?

> Reply from astro
>
> my numbers are bad
Okay; you should first start by checking the most basic things. Have you verified that  the input file has been read to memory correctly? (Examples: Is the first character of the input buffer within the DecompressBlock routine #255? Are the following characters correct? Does the buffer have the correct size?)
## Post #12
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-10-12T13:07:54+00:00
- Post Title: How to uncompress?

[extractor.rar](https://xentaxbackup.github.io/file/913_extractor.rar)
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-12T17:55:26+00:00
- Post Title: How to uncompress?

May I guess that your code is working now?
## Post #14
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2006-10-12T19:00:07+00:00
- Post Title: How to uncompress?

yes

```
myprogram in.txt out.txt
```
## Post #15
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-12T21:16:34+00:00
- Post Title: How to uncompress?

Sorry; I cannot try it right now, since I currently do not have the required .NET framework installed.

Nevertheless: Congratulations.
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-19T07:37:06+00:00
- Post Title: 

What game or program do these files come from by the way??
## Post #17
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-10-24T17:10:31+00:00
- Post Title: 

>>Deniz Oezmen: Delphi Rulez!!! 
thumbs up, keep up the good work
## Post #18
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2007-04-05T13:22:51+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> What game or program do these files come from by the way??

Yu-Gi-Oh games
