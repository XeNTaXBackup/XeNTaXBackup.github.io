## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-01-18T16:53:06+00:00
- Post Title: MaxScript alignment function

Since I couldn't find anything like this on the web, I figured I'd write one myself and share it here so others can find it.

```
	align = (alignment - (mod relativeoffset alignment as integer))
	align = fseek fstream align #seek_cur
	return align
)

```


usage eg:

```
AlignOffset f PBChunkSize 0x40

```
