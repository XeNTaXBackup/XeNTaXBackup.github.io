## Post #1
- Username: nooie
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 27, 2020 9:21 am
- Post datetime: 2021-01-17T17:24:44+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

Hi all,

Does anyone know how to view .tx or .jng files? They are game textures for Beyond Ynth. I have opened .jng with XNViewMP but the file is only black&white or its alpha. I think the .tx file houses the real textures, but I have never heard of it before.

Any ideas anyone?
Many thanks
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-17T20:46:20+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

Can you upload some samples?
## Post #3
- Username: nooie
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 27, 2020 9:21 am
- Post datetime: 2021-01-18T16:53:55+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

[https://drive.google.com/file/d/1njzNeB ... sp=sharing](https://drive.google.com/file/d/1njzNeBu2OajCkkzTpsmv4OlRj6A-sUk5/view?usp=sharing)
[https://drive.google.com/file/d/1x7Rv3c ... sp=sharing](https://drive.google.com/file/d/1x7Rv3cIrJKdaEHMQDPC2jSxuAzcvs1AI/view?usp=sharing)

Hope these work for you
thanks
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-18T20:37:13+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

Ok, so as for jng, it is a normal image with colors,
you can open it with IrfanView [https://i.imgur.com/04xZdFY.png](https://i.imgur.com/04xZdFY.png)

You can also easily convert it to png
[https://www.google.com/search?client=fi ... jng+to+png](https://www.google.com/search?client=firefox-b-d&q=jng+to+png)



As for TX sample, this contains data compressed with ZLIB,
you can use offzip to extract files
[https://i.imgur.com/lnwk0X5.png](https://i.imgur.com/lnwk0X5.png)

```
offzip.exe -a texture_file.tx
```


Download here [https://aluigi.altervista.org/mytoolz/offzip.zip](https://aluigi.altervista.org/mytoolz/offzip.zip)

I was able to get "some" imge with texture cooker, but I'm not sure if it is wnywhere near correct,
so probably need some more samples to compare.
## Post #5
- Username: nooie
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 27, 2020 9:21 am
- Post datetime: 2021-01-19T17:43:41+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

Thanks very much for this. I was able to access the .jng files as you say.

For the .tx, I converted it with offzip to .dat. Like you said, with the texture cooker the image was just coloured static.

Do you think anything can be done to clear up the image? It should look like an ordinary texture file in the end.
Thanks
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-19T19:22:12+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

> Do you think anything can be done to clear up the image?

You can upload more samples and maybe me or someone else
will be able to get it working. "Desert" is not a good example
as you have probably only sand on those images, right? ;p

So try to pick something colorful and detailed.
## Post #7
- Username: nooie
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 27, 2020 9:21 am
- Post datetime: 2021-01-19T21:53:33+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

Thanks   ,
here are some more files:

[https://drive.google.com/file/d/1aYHjGC ... sp=sharing](https://drive.google.com/file/d/1aYHjGCXUscxYRCZH_3CpGc2fJmEL1_xs/view?usp=sharing)
## Post #8
- Username: HealzWat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 03, 2021 7:09 pm
- Post datetime: 2021-11-03T11:10:24+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

Hi all,

Does anyone know how to view .tx or .jng files? They are game textures for Beyond Ynth. I have opened .jng with XNViewMP but the file is only black&white or its alpha. I think the .tx file houses the real textures, but I have never heard of it before.

Any ideas anyone?
Many thanks
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-03T14:49:19+00:00
- Post Title: Beyond Ynth '.tx' and '.jng' files

@HealzWat, you didn't use search function [search.php](https://forum.xentax.com/search.php) and I had to move your post to the original topic.
Please use "search" next time.
