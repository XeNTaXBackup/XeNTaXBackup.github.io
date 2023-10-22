## Post #1
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-07-15T16:23:15+00:00
- Post Title: S.W.I.N.E pak file

ok, so here's the deal:
im trying to find an exporter for the game S.W.I.N.E
the file header tells me its a pack file(which it is...a .pak, i just wanted to make sure so i checked, maybe there are different versions of pak)
it goes like that: 
```
53 72 1A 1B 0D 0A 87 0A 50 41 43 4B AC C8 03
```
 which means 
```
Sr....‡.PACK¬ָ.
```

i dont know alot about those things, but i can see a lot of filenames, so i dont think it has a complex compression...truth is i can see every filename in this archive...
the problem is, all the gamefiles are located in that pak, which makes it a 850MB file, i can try and upload it at night, but i doubt anyone will download a 500MB file(compressed)
the game is made by stormregion and fishtank studios, and i cant find a record on its engine, maybe its custom-made
i'd appreciate if you can tell me more about that file, but i dont think the header is enough to know...
here is something i found about the file, but it doesnt tell me anything, maybe it could help you lot...

```
Header is first, then library and then data. Untested !
Offset is from Data start, so real file offset is 16 + lib size + offset

Header:	 offset	 length	 contents
ident1 0 4 53 72 1A 1B 'Sr'
?	 4	 4
ident2	 8	 4	 'PACK'
lib size	 12	 4	 long

Lib record:
?	 0	 1
name length	 1	 1	 0..255
name	 2	 namelen
offset	 2+namelen	 4	 ulong
size	 6+namelen	 4	 ulong
?	 10+namelen	 5
```
## Post #2
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-07-16T20:06:30+00:00
- Post Title: S.W.I.N.E pak file

anyone? please?
you have the structure of the file above...
if you need me to upload it i can...
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-16T21:43:57+00:00
- Post Title: S.W.I.N.E pak file

you need to upload the first and last 10mb of the file.
## Post #4
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-07-17T08:13:23+00:00
- Post Title: S.W.I.N.E pak file

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-07-18T14:19:08+00:00
- Post Title: S.W.I.N.E pak file

can anyone please please give it a try?
## Post #6
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-07-20T17:19:16+00:00
- Post Title: S.W.I.N.E pak file

please? anyone?
## Post #7
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-06T19:58:35+00:00
- Post Title: S.W.I.N.E pak file

*up*
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-07T19:06:24+00:00
- Post Title: S.W.I.N.E pak file

> Reply from chrrox
>
> you need to upload the first and last 10mb of the file.

> Reply from yair1221
>
> er...how do i know what are the first 10MB, you mean the first 10 million bytes? oh...i have a lot of counting ahead
 

PACK section runs over the TEXT section, so could you run this script:

```
  idstring "Sr\x1a\x1b\xd\xa\x87\xa"
  getdstring TYPE 4
  get SIZE long
  savepos POS

  if TYPE == "PACK"  

  elif TYPE == "TEXT"

  elif TPYE == "SCEN"

  else
    print "Not sure how to hanlde "%TYPE""
    cleanexit
  endif

  math POS += SIZE
  goto POS  

next

```
## Post #9
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-15T12:37:15+00:00
- Post Title: S.W.I.N.E pak file

it tells me this:

```
this one: "; Effect
expected: "Sr><
c
"
```


the SR>< simply has arrows instead of ><, that was the closest thing so i wrote it...
## Post #10
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-23T22:54:09+00:00
- Post Title: S.W.I.N.E pak file

please?
i just love this game's models, and i want to extract them
## Post #11
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-26T20:09:58+00:00
- Post Title: S.W.I.N.E pak file

bump
im not giving up on this thread 
i just love the models from this game 
i think what i gave in the thread's open is the bloody struct, can anyone give it a try?
## Post #12
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-08-29T12:59:16+00:00
- Post Title: S.W.I.N.E pak file

humpty dumpty bump
## Post #13
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-09-01T12:10:43+00:00
- Post Title: S.W.I.N.E pak file

unbelievabe, 12 posts, only 2 made by others XD
## Post #14
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-09-29T11:55:14+00:00
- Post Title: S.W.I.N.E pak file

bummmmmmp
