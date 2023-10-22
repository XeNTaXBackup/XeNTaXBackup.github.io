## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-10-22T15:07:24+00:00
- Post Title: How reliable is python's parameterless zlib.decompress?

I decompressed a bunch of text files from Backbreaker and there are some strange artifacts like duplicated strings or fragmented.
Basically, it works 90% of the time and then fails catastrophically. I dont know if it is because of my call conventions

```
outData = zlib.decompress(bReader.read(sz))

```

PS would it matter if I used a file larger than Compressed (AKA i added extra bits to the compressed data)
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-10-22T23:07:33+00:00
- Post Title: How reliable is python's parameterless zlib.decompress?

Zlib was not the problem
