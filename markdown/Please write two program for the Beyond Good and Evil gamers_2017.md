## Post #1
- Username: DJviolin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 01, 2006 5:50 pm
- Post datetime: 2006-08-01T10:14:49+00:00
- Post Title: Please write two program for the Beyond Good and Evil gamers

Hi,

I want to ask a big favor from you. Pls, write for me two Beyond Good & Evil editors - one which can extract and make or edit *.bf files, and one which can extract or make / edit the files with dialogs.
Pls, help us to make a translation and also the hungarian gamers can enjoy this gorgeous game.
Please help us!

Bye:
DJviolin
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-01T10:17:38+00:00
- Post Title: Please write two program for the Beyond Good and Evil gamers

In principle, you should be able to do this in the next release of MultiEx Commander with Rahly's BF plugin. Hey may also have a standalone tool already.
## Post #3
- Username: DJviolin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 01, 2006 5:50 pm
- Post datetime: 2006-08-01T10:33:58+00:00
- Post Title: Please write two program for the Beyond Good and Evil gamers

Thanks for the help.
## Post #4
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2006-08-20T15:34:15+00:00
- Post Title: Please write two program for the Beyond Good and Evil gamers

> In principle, you should be able to do this in the next release of MultiEx Commander with Rahly's BF plugin. Hey may also have a standalone tool already.

 Maybe I'm wrong but I tried something he had made that only extracted sound and music from the BF file.
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-08-21T19:07:38+00:00
- Post Title: Please write two program for the Beyond Good and Evil gamers

you are wrong, that program extracted anything from the archive file, i made special mods to convert the wav files into a standard PCM format that any player could read, IF you selected the option.  This is because most people wanted the soundtrack ripped out of it.  As to the other files in there, like Close Captions and Models, I leave that up to other programmers.  Mexcom is generally an extractor, MAYBE creater, not a modifier, unless its a compression of some sort.

```
bfextractor -l <bffile>
```


would allow a complete listing of any file in there.
## Post #6
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2006-08-23T02:52:08+00:00
- Post Title: Please write two program for the Beyond Good and Evil gamers

As to the other files in there, like Close Captions and Models, I leave that up to other programmers. Mexcom is generally an extractor, MAYBE creater, not a modifier, unless its a compression of some sort. 


> you are wrong, that program extracted anything from the archive file

My apologies for the error.

> As to the other files in there, like Close Captions and Models, I leave that up to other programmers. Mexcom is generally an extractor, MAYBE creater, not a modifier, unless its a compression of some sort.

Not quite sure what you are saying here... but I didn't see any texture files as least none viewable. I'm thinking maybe archives within archives like maybe in the .bin files
## Post #7
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-08-23T11:46:31+00:00
- Post Title: Please write two program for the Beyond Good and Evil gamers

BG&E uses the first(?) version of the JADE Engine (also used in the Prince of Persia games, for example), and its bin files are in a slightly different format than what I'm used to, but if enough people are interested, I can write a texture/model extractor for it (hoping the formats haven't evolved too much).
I don't see a reimporter happening, since the unknowns for the format are way too big.
