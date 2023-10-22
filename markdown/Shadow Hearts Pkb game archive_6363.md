## Post #1
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-04-05T16:07:10+00:00
- Post Title: Shadow Hearts Pkb game archive

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: swosho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-05T16:40:09+00:00
- Post Title: Shadow Hearts Pkb game archive

this will extract the models pkb files.
quickbms script

```
for i
set name name1
string name + _
string name + i
string name + .
savepos offset
get type long
get size long
string name + pack
log name offset size
math offset + size
goto offset
padding 0x800
next i

```
## Post #3
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-04-05T18:25:55+00:00
- Post Title: Shadow Hearts Pkb game archive

Thank you but i get many dff file but still can't open it, already used Zmodeler but don't know why can't see anything, and how about TEXTURE.PKB? Still use same scrip?
## Post #4
- Username: swosho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-14T14:47:49+00:00
- Post Title: Shadow Hearts Pkb game archive

Mr adults has added support for shadow hearts 1 to noesis.
[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)
## Post #5
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-04-15T06:27:30+00:00
- Post Title: Shadow Hearts Pkb game archive

Thanks for reply but may be i'm noob or something, cause still can open it  , can't open .pkb file and .diff too, and i see they're not in support list.
## Post #6
- Username: swosho
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-15T08:28:08+00:00
- Post Title: Shadow Hearts Pkb game archive

You need to use chrrox's bms script to extract .pack files from models.pkb. Noesis opens the .pack files and not the .dff directly. (since the pack files contain dff and anm, it reads both) Also keep in mind that you need Noesis 3.14 to open those .pack files.
## Post #7
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2011-04-15T09:42:50+00:00
- Post Title: Shadow Hearts Pkb game archive

Plz mr Chrrox can you give me your script? Thank you.
