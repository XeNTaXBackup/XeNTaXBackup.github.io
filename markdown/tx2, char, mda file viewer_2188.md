## Post #1
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-11-05T03:39:45+00:00
- Post Title: tx2, char, mda file viewer

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-11-11T15:48:00+00:00
- Post Title: tx2, char, mda file viewer

Anyone can help me?
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-11-11T19:18:20+00:00
- Post Title: tx2, char, mda file viewer

Wich game use this?
## Post #4
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-11-12T14:33:39+00:00
- Post Title: tx2, char, mda file viewer

They from PS2 Nippon Ichi game, like Disgaea, Makai Kingdom
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-13T09:56:18+00:00
- Post Title: tx2, char, mda file viewer

Oh, hi again LustD. ive been busy doing some other things lately, but ive
integrated an TX2 converter/ripper so far into jader.

[http://jaedernaub.ath.cx/jntest.zip](http://jaedernaub.ath.cx/jntest.zip)

ill try too see if i can figure out the rest :X
## Post #6
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-11-13T16:34:15+00:00
- Post Title: tx2, char, mda file viewer

Glad to see you back again Strobe 

I shall wait until you figure the rest, thank you.
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-13T17:19:40+00:00
- Post Title: tx2, char, mda file viewer

Im not even sure the MDA and CHR are containing any graphics, the CHR file is so damn small i cannot find anything usefull in it.

the MDA file have something that looks like a palette data with 4 colors,
and after that chunk i see nothing that resembles gfx data. :/

The DAT file however contains some TX2 files, just similiar to the .TX2 in the zipped package.
## Post #8
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-11-13T18:50:05+00:00
- Post Title: tx2, char, mda file viewer

Hmm i check what you tell me, i found something like this the data that have been ripped have same name but with different like: 
mp07003. dat
mp07003. POS
mp07003. chr
mp07003. mda

Is that posible that this 4 file actually one or connecting each other? 

Also before when using jaeder  i found one character sprite (in attachment)
this more clear if you see it reverse.

Btw Strobe do you need more data? if yes then i will upload it soon
Thanks
[mk_ 24809569_xxxx.rar](https://xentaxbackup.github.io/file/974_mk_ 24809569_xxxx.rar)
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T17:49:26+00:00
- Post Title: tx2, char, mda file viewer

I would most certainly say that the filenames are linked to eachother that way. and maybe some extensions does not even contain any graphic at all,
but i would be glad to have some more files to analyze for that.
## Post #10
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-11-15T04:57:59+00:00
- Post Title: tx2, char, mda file viewer

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-11-29T04:20:50+00:00
- Post Title: tx2, char, mda file viewer

oi :( I guess I missed this topic

The games makai kingdom and disgaea have diferent(althrough similar) file formats, I am getting REALLY confused with these 2 getting mixed up

So far the makai's tx2 format is not much diferent form what I posted before:

Header
int16 Width
int16 Height (needs to be / by 2 in disgaea?)
int16 Depth (in colors, not bits)
int16 Flags - data unknown
int16 unknown, same as depth as far as i know
int16 unknown
int32 padding?

Palette follows
Picture follows

Palette has an odd color space, something like rgb565 + Alpha(8) or something like that Oo.
these files only contain background data

> mp07003. POS
>
> mp07003. chr
>
> mp07003. mda
I have none of these files, are they form disgaea?

Attached is the source of 2 little programs I made to view tx2 and extract files form the main dat file(port form mr mouse script)
[MKsrc.rar](https://xentaxbackup.github.io/file/993_MKsrc.rar)
