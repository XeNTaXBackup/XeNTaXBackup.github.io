## Post #1
- Username: NVtom
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 09, 2019 3:00 am
- Post datetime: 2020-06-22T00:44:28+00:00
- Post Title: how can i recompress this file

i started like they did in this post:
[viewtopic.php?f=16&t=13462&p=129719&hilit=zig#p129719](https://forum.xentax.com/viewtopic.php?f=16&t=13462&p=129719&hilit=zig#p129719)

with this quickbms script:
comtype zlib_noerror
get SIZE asize
get NAME basename
get EXT extension
string NAME p "%s_dec.%s" NAME EXT
clog NAME 0 SIZE SIZE

now how can i make my decompressed file compressed again so i can merge it into the bigger game files
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-06-22T08:42:09+00:00
- Post Title: how can i recompress this file

Did you try to use reimport mode?
Read more here --> [https://aluigi.altervista.org/papers/quickbms.txt](https://aluigi.altervista.org/papers/quickbms.txt)
in section "Reimporting the extracted files"
