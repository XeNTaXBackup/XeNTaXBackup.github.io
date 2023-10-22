## Post #1
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-12T11:29:09+00:00
- Post Title: Help with project IGI textures and models

I've managed to extract the models and textures via an extractor i found on this site
But the models i got were *.mef, and the textures were *.tex
Has anyone ever found a converter?
If not, Can you please work on it a bit? Shouldn't take long, It's a very old game...And i don't think it's a very complex structure...
Attached is a rar with 2 files, A texture and a model, I'm not sure they're related, They might just have the same name because they are indexed inside the archive
[Desktop.rar](https://xentaxbackup.github.io/file/4618_Desktop.rar)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-12T12:45:04+00:00
- Post Title: Help with project IGI textures and models

Model file is chunk based format, but there aren't any chunk sizes so I guess you'd end up scanning the file for all the chunks and then figure out what they are, no convenient "skip chunk section" methods for testing.

There seems to be a lot of indexing going on, so skimming over the file doesn't really give me any ideas.
Maybe someone will try it out.
## Post #3
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-13T12:59:15+00:00
- Post Title: Help with project IGI textures and models

thanks, but i'm really not the expert in these things, so...i'll just hope someone could figure something out
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-13T16:17:26+00:00
- Post Title: Help with project IGI textures and models

Post more model samples. Preferably a dozen small ones of increasing size and maybe a few large ones.
That is mainly for comparison to find patterns.
## Post #5
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-15T12:45:28+00:00
- Post Title: Help with project IGI textures and models

there you go, 6 of the smallest, and 6 of the largest, same for the textures, so you have 24 files here...just choose the ones you want, i had to split it because it is more than 256 KB(WTF? its a small attachment)
so it will come in 3 posts...
[IGI.part1.rar](https://xentaxbackup.github.io/file/4628_IGI.part1.rar)
## Post #6
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-15T12:46:17+00:00
- Post Title: Help with project IGI textures and models

here is the second part
[IGI.part2.rar](https://xentaxbackup.github.io/file/4629_IGI.part2.rar)
## Post #7
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-15T12:46:56+00:00
- Post Title: Help with project IGI textures and models

third part, good riddance  
[IGI.part3.rar](https://xentaxbackup.github.io/file/4630_IGI.part3.rar)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-15T13:21:59+00:00
- Post Title: Help with project IGI textures and models

lol ya, 256 KB attachment limit
## Post #9
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-23T22:58:04+00:00
- Post Title: Help with project IGI textures and models

got anywhere with it?
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-23T23:08:31+00:00
- Post Title: Help with project IGI textures and models

Well I found some pattern, but still a lot of unknowns.

Some outline I wrote out:

```

#header
dword chunk "ILFF"
dword filesize
dword 4
dword unk
dword chunk "OCEM"

#chunk starts
char_4 chunk
dword chunkSize - 16
dword 4
dword chunkSize

chunkSize Chunk {
   data
}

```


The face section is all weird.
I found this forum which talks about IGI2, and they appear to HAVE TOOLS for it, but there's absolutely no information on the format. You might have better luck there, though if they're anal about things they might just keep everything private private.
## Post #11
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-24T22:56:19+00:00
- Post Title: Help with project IGI textures and models

what forum was it?
and as for the script:
i get this:
invalid command "dword" or arguments 2 at line 14
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-24T23:06:24+00:00
- Post Title: Help with project IGI textures and models

It's not a script, just an outline.

[http://community.codemasters.com/forum/ ... f-126.html](http://community.codemasters.com/forum/archive/index.php/f-126.html)
## Post #13
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-29T13:00:24+00:00
- Post Title: Help with project IGI textures and models

well, they deal with IGI 2
which i think had an entirely different engine and not even made by the same company...
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-29T13:02:06+00:00
- Post Title: Help with project IGI textures and models

I see.

Well, aside from the fact that it's chunk-based, I don't really know enough common patterns to be able to figure out the structures.
## Post #15
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-29T13:31:14+00:00
- Post Title: Help with project IGI textures and models

ok, never mind, thanks for the try

*lockable*
## Post #16
- Username: agaur6562
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 26, 2020 2:37 pm
- Post datetime: 2021-01-10T15:55:07+00:00
- Post Title: Re: Help with project IGI textures and models

Hi everyone we part of the community have created .mef importer for u all however it has some drawbacks 
Not supported glow 
Not supported magic vertex idk about this

Video link : [https://youtu.be/wjhYPw7btkM](https://youtu.be/wjhYPw7btkM)
Any suggestions greatly supported 

Now how to convert tex 
Very complicated method HE can tell u
[https://youtube.com/channel/UClRsoqWve12YK0PGfFt_1uw](https://youtube.com/channel/UClRsoqWve12YK0PGfFt_1uw)
## Post #17
- Username: agaur6562
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 26, 2020 2:37 pm
- Post datetime: 2021-01-10T15:56:50+00:00
- Post Title: Re: Help with project IGI textures and models

> Reply from yair1221 ↑Mon Aug 29, 2011 9:31 pm at Mon Aug 29, 2011 9:31 pm
>
> 
ok, never mind, thanks for the try

*lockable*

View next post to get your answers
## Post #18
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-05-03T11:45:32+00:00
- Post Title: Re: Help with project IGI textures and models

I found a proper mesh in .mef file.
[bandicam 2021-05-03 04-44-25-475.jpg](https://xentaxbackup.github.io/file/20030_bandicam 2021-05-03 04-44-25-475.jpg)
## Post #19
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-05-03T11:49:44+00:00
- Post Title: Re: Help with project IGI textures and models

Sorry for bumping an old thread.
[100_01_2.7z](https://xentaxbackup.github.io/file/20032_100_01_2.7z)
