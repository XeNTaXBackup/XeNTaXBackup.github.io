## Post #1
- Username: x5254725
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 22, 2011 4:41 am
- Post datetime: 2011-02-09T12:44:25+00:00
- Post Title: Extract iex file (The Tuttles - Madcap Misadventures)?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-17T02:12:34+00:00
- Post Title: Extract iex file (The Tuttles - Madcap Misadventures)?

sorry to reply so late (missed this thread)

right approach with the signature thing   
you can't have math doing more than one thing

```
math SIZE = 0

for COUNT = 0

  math START += SIZE
  goto START

  findloc START string "\xff\xd8\xff\xe0"
  findloc END string "\xff\xd9"

  if START == ""
     # no signature found
    cleanexit
  endif

  if END == ""
     # no signature found
    cleanexit
  endif

  if END < START
    # bad size
    cleanexit
  endif

  math END += 2
  math SIZE = END
  math SIZE -= START

  set NAME string COUNT
  string NAME += ".jpeg"
   
  log NAME START SIZE

next COUNT

```


compare versions, and you should understand what i'm doing different
