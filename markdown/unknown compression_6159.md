## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-03-01T16:19:19+00:00
- Post Title: unknown compression

Hi there
Could you assist me?
how to decompress this file?
Thank you in advance.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T16:43:20+00:00
- Post Title: unknown compression

the file is simply xored with the following 4 bytes:
34 76 12 95

script for quickbms:

```
get NAME basename
get EXT extension
string NAME += "_decrypted."
string NAME += EXT
get SIZE asize
log NAME 0 SIZE
```


it's probably a mesh file or similar stuff

anyway what's the game?
you must write ever the game from which you took the file!
## Post #3
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-03-01T16:55:06+00:00
- Post Title: unknown compression

Thank you very, very much.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T16:57:17+00:00
- Post Title: unknown compression

I repeat: what's the name of game?
