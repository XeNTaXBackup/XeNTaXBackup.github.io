## Post #1
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-02-26T10:18:39+00:00
- Post Title: Far Cry 3 Xbox360 extracted files

Hi
This is some files extracted with gibbed Dunia2 tools from Far Cry 3 Xbox360.
[http://www.mediafire.com/download/wj054 ... box360.rar](http://www.mediafire.com/download/wj054f5xst7v3vd/FC3_Xbox360.rar)
They are compressed and I couldn't find the compression.
Does anybody know what is the compression?
Thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-03-01T10:17:55+00:00
- Post Title: Far Cry 3 Xbox360 extracted files

```
comtype lzma_dynamic
savepos OFFSET
get SIZE asize
math SIZE -= OFFSET
get NAME basename
get EXT extension
string NAME p= "%s_unpack.%s" NAME EXT
clog NAME OFFSET SIZE SIZE
```
