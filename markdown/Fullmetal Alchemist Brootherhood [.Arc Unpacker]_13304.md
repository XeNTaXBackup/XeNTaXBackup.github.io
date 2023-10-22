## Post #1
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2015-09-10T05:37:30+00:00
- Post Title: Fullmetal Alchemist Brootherhood [.Arc Unpacker]

The game has the most easy way for extract models, as the models are on the same Root of the game, in the folder named "Unites".
But, they're on .ARC, which is an special version, compared with others.

I did search in many pages, even here (which the unpacker was deleted too), and in one link, but was death to.

The only program which I've read for unpack the models, its one named "FMAB Parser-Decompressor"


Just asking if someone can post it around
## Post #2
- Username: Nodea
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 25, 2017 3:14 am
- Post datetime: 2017-07-24T19:20:32+00:00
- Post Title: Fullmetal Alchemist Brootherhood [.Arc Unpacker]

I figured necro'ing this would be a better idea than just posting the same thing. Edit, the original user who created it gave me it and can be found as an attachment to this post.
[fmab parser-decompressor.zip](https://xentaxbackup.github.io/file/13146_fmab parser-decompressor.zip)
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-24T21:28:11+00:00
- Post Title: Fullmetal Alchemist Brootherhood [.Arc Unpacker]

post a sample file.
## Post #4
- Username: Nodea
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 25, 2017 3:14 am
- Post datetime: 2017-07-25T01:21:16+00:00
- Post Title: Fullmetal Alchemist Brootherhood [.Arc Unpacker]

Here's two.
[https://mega.nz/#!1NBXHYDD!RpRC5k4__lBt ... 7rc1r6MZvk](https://mega.nz/#!1NBXHYDD!RpRC5k4__lBtC4haaJKRIfcY82bLiYa2p7rc1r6MZvk)
[https://mega.nz/#!QBojyLra!_-BiNj8ReslN ... dXzBVWymXM](https://mega.nz/#!QBojyLra!_-BiNj8ReslNryBWaFrW88A0-mXrZ9kxudXzBVWymXM)
Both were found in USR_DIR\Units\
which another user stated on vg-resource was the characters. There's about 16 .arcs in each folder, with about 18 folders all together.
## Post #5
- Username: Nodea
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-25T01:38:22+00:00
- Post Title: Fullmetal Alchemist Brootherhood [.Arc Unpacker]

quickbms script
all files you sent only contained 1 file so can't do much more on multiple file archives without examples.

```
idstring BARC
get unk01 short
get unk02 short
get namestart long
get fsize long
get unk03 long
get unk04 long
get fileTBL long
get null long
get unk05 long
get NAME string
set offset namestart
math offset += unk04
goto fileTBL
get size long
get zsize long
get base long
clog NAME offset zsize size

```


you can also just run offzip on these files
offzip -1 -a -z -15 c:\mfile.arc c:\export_folder 0x0
## Post #6
- Username: Nodea
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 25, 2017 3:14 am
- Post datetime: 2017-07-25T21:19:52+00:00
- Post Title: Fullmetal Alchemist Brootherhood [.Arc Unpacker]

[https://mega.nz/#!sYglhAxa!EJGxuWY-fQZZ ... n9aRdLs9Kw](https://mega.nz/#!sYglhAxa!EJGxuWY-fQZZldMZFWjpUJdlnAZ7EiFz3n9aRdLs9Kw)
Try this, it has all the contents of a single folder.
What's interesting is that UALFa through UALFa3 seem to have the same file in it and the same is true with UALFb.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-25T23:25:54+00:00
- Post Title: Fullmetal Alchemist Brootherhood [.Arc Unpacker]

looks like they all only contain one file so those are the games files.
they might load some other files for those duplicate models to change colors or something not played the game.
