## Post #1
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-08-24T16:33:41+00:00
- Post Title: Fallen Earth IFS/CCH

(Modified repost)

I've been working on deciphering the graf for FE (think Fallout, but online), but so far have only been able to decode a few of the fields. 

Attached: A zip file containing two ~100K cuttings from both files using Watto's Archive Cutter.

OR see the next post for a text file with URLs to the entire resource archive and directory file.

Will post more as I try a couple different things, it seems to be an external directory archive so I'm working on copying and pasting the contents of the index to the tail of the resource archive.  So far no luck, but I'm particularly interested in extracting the, "actors.db" and "static.dat" files to see what kind of data it might contain.  I'm also just mainly curious about what other data might be in there, since a lot of research on available skills and such has to be done by manually collecting the data in-game right now.

*Feel free to PM me for any questions, or if you have trouble with the DL.
[FE_DATA_cuttings.zip](https://xentaxbackup.github.io/file/2312_FE_DATA_cuttings.zip)
## Post #2
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-08-26T12:56:03+00:00
- Post Title: Fallen Earth IFS/CCH

The contents of this post was deleted because of possible forum rules violation.
[2009-08-26-FE_DATA.zip](https://xentaxbackup.github.io/file/2320_2009-08-26-FE_DATA.zip)
## Post #3
- Username: verkho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 24, 2009 9:40 pm
- Post datetime: 2009-09-24T13:51:27+00:00
- Post Title: Fallen Earth IFS/CCH

I've been dabbling abit with this one as well. So far I've managed to find some kind of structure to the cch file.
I've created a ruby script which does this.
An extraction looks like this:

# FILE INFO - Offset 2152231 ###################################################
File header (20 bytes)
00 00 00 00   90 f2 93 09   a7 25 02 00   7a 00 00 00   
25 00 00 00   
Filename: /actors/crits/hlb/anim/hlb_umwsr.v3b
2f 61 63 74   6f 72 73 2f   63 72 69 74   73 2f 68 6c   
62 2f 61 6e   69 6d 2f 68   6c 62 5f 75   6d 77 73 72   
2e 76 33 62   00 

Do you have any info on what the first 20 (or sometimes 24) bytes mean ?
In most cases I've found that byte 17 tells you how many bytes the filename has but in some cases this is not true.

I'm guessing that the first 20 (or 24) bytes could name the location and size of the object in the .ifs but i'm not there yet.


Anything new on you front ?


- Verkho
## Post #4
- Username: ShayneCranston
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 04, 2009 9:09 am
- Post datetime: 2009-10-04T14:23:49+00:00
- Post Title: Fallen Earth IFS/CCH

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-10-04T15:41:21+00:00
- Post Title: Fallen Earth IFS/CCH

The contents of this post was deleted because of possible forum rules violation.
