## Post #1
- Username: uppfinnarn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 10, 2016 2:36 pm
- Post datetime: 2016-01-10T07:29:46+00:00
- Post Title: Need help decompressing LZSS

I've almost managed to figure out the PAK format used in the PSP game Mahou Shoujo Lyrical Nanoha A's: The Gears of Destiny, but the compression algorithm is giving me trouble.
It's LZSS or something derived therefrom, but I don't understand the algorithm well enough to tell all the parameters used, much less successfully extract it.

One of the archives contains two PNG images, which gives me about 18 bytes of known plaintext (8-byte PNG header + a 0-size IHDR chunk) for each file. A normal PNG always starts with:

```
.  P  N  G  .  .  .  .  .  .  .  .  I  H  D  R  .  .

```


Both compressed PNGs start with:

```
.  P  N  G  .  .  .  .  .  .  I  H  D  R  .  P  .  .  y  Ì  k  [  .  p  H  Y  s

```


Which indicates a PNG with the obligatory IHDR chunk followed by a pHYs (Physical Pixel Dimensions) chunk. After this, they diverge, either due to the compression or differing values.

Now, I'm hoping this will be enough for someone to tell me more if I tell you that the dictionaries for both files start with:

```
FF 7D 20 00 01 01 DD FB 81 01 41 02 21 03 F6 7D 20 04 82 00
```


First file: system_data.png
Compressed size: 24758 byte
Expanded size: 27422 byte
Dictionary size: 5884 byte

Second file: icon0.png
Compressed size: 15650 byte
Expanded size: 16988 byte
Dictionary size: 3364 byte

Compressed payloads (.lzs) and complete dictionaries (.dat) are attached. I can provide more information if needed.
[Archive.zip](https://xentaxbackup.github.io/file/10285_Archive.zip)
