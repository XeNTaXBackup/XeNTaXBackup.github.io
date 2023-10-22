## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-15T12:20:13+00:00
- Post Title: Asobo DPC DPS - unknown compression

So I have been working for few days on Asobo games formats.
First I have created a tool and documentation on my github [https://github.com/bartlomiejduda/Tools ... 20Research](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Asobo%20Studio%20DPC%20DPS%20Research)

Then I have copied all informations to Xentax wiki [https://wiki.xentax.com/index.php/Asobo_Studio_DPC_DPS](https://wiki.xentax.com/index.php/Asobo_Studio_DPC_DPS)

And now I'm struggling with figuring out compression method.
Any help would be appreciated. 

Of course, I can provide samples if needed.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-10-15T12:45:36+00:00
- Post Title: Asobo DPC DPS - unknown compression

A Plague Tale: Innocence uses LZ4.

Previous games had custom compression afaik. I was working on a Hololens game by Asobo called Fragments. I got great help from a data compression community and the compression method was solved: [https://encode.su/threads/3147-Reverse- ... LZ-Variant](https://encode.su/threads/3147-Reverse-Engineering-Custom-LZ-Variant)

It was LZ with custom flags. This worked perfectly for Fragments, but I don't know if it applies to other games too. I suppose it should though, or at least something similar.
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-15T14:05:13+00:00
- Post Title: Asobo DPC DPS - unknown compression

> A Plague Tale: Innocence uses LZ4.
Thanks. I'll update wiki article then. 

> It was LZ with custom flags.
That's awesome. I will definitely check this.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-22T11:53:01+00:00
- Post Title: Asobo DPC DPS - unknown compression

Ok, I have tested it and it seems to be working for samples from CT Special Forces: Fire for effect (PC version).
[https://imgur.com/a/pLLWV4e](https://imgur.com/a/pLLWV4e)


Edit: Leaving decompression tool source in the attachment for preservation
[unLZ_rhys_v1.zip](https://xentaxbackup.github.io/file/18876_unLZ_rhys_v1.zip)
