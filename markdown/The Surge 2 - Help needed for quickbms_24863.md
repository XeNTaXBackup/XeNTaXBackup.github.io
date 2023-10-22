## Post #1
- Username: Belghen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 25, 2021 6:44 am
- Post datetime: 2021-12-19T18:09:20+00:00
- Post Title: The Surge 2 - Help needed for quickbms

I am trying to extract the models from The Surge 2 using quickbms, but I just get an error "invalid command or argument 1, line 11. 
Could anyone help me? Thanks.
## Post #2
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2021-12-19T21:55:40+00:00
- Post Title: The Surge 2 - Help needed for quickbms

> Reply from Belghen ↑Mon Dec 20, 2021 2:09 am at Mon Dec 20, 2021 2:09 am
>
> 
I am trying to extract the models from The Surge 2 using quickbms, but I just get an error "invalid command or argument 1, line 11. 
Could anyone help me? Thanks.

can you supply a sample file?
## Post #3
- Username: Belghen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 25, 2021 6:44 am
- Post datetime: 2021-12-19T23:49:04+00:00
- Post Title: The Surge 2 - Help needed for quickbms

What do you mean?
## Post #4
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2021-12-20T03:17:40+00:00
- Post Title: The Surge 2 - Help needed for quickbms

> Reply from Belghen ↑Mon Dec 20, 2021 7:49 am at Mon Dec 20, 2021 7:49 am
>
> 
What do you mean?

Supply a sample file so someone can look into your said issue.
## Post #5
- Username: Belghen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 25, 2021 6:44 am
- Post datetime: 2021-12-21T03:01:09+00:00
- Post Title: The Surge 2 - Help needed for quickbms

Thanks for the reply; I was able (I think) to unpack the files, but now I have hundreds of files with no extension and .bin files that I can't handle. Some of these files (without extension) are textures and I can just rename them adding .jpg/tga etc, but I can't find the models/meshes. 
Anyone have some tips?
The .dat files are too large to post.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-21T07:53:47+00:00
- Post Title: The Surge 2 - Help needed for quickbms

> Reply from Belghen ↑Tue Dec 21, 2021 11:01 am at Tue Dec 21, 2021 11:01 am
>
> , but I can't find the models/meshes. 
Anyone have some tips?
The .dat files are too large to post.Without some basic knowledge of 3D formats it's not easy to check hex data.

(The following example e3m was NOT taken from The Surge 2, btw.)

A simple check would be the one for existing unsorted alphabets such like:
.



unsortedAlphabet.png (41.13 KiB) Viewed 87 times


If you find something like this then there's a good chance that it  is accompanied by mesh data (vertices as floats, half floats or integers).
(But that's not 100% reliable.)

Even simpler you could do a search for 000001000200 (sufficient but not necessary condition).
(For big endian you'd search 000000010002.)

remark: in former post I wrote "scrambled" which doesn't have the meaning I thought of (not being a native speaker).
So "unsorted" should name it better.
