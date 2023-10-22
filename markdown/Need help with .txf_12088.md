## Post #1
- Username: Harime Nui
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 11, 2014 7:32 am
- Post datetime: 2014-10-11T00:33:41+00:00
- Post Title: Need help with .txf

Hi everyone,

I am trying to open a .txf image file form the game Disgaea D2.
Sadly I got stuck, because the image seems to be compressed somehow.

I tried to read every column into a separate image and got some strange results.
Only the image 9 and 11 are recognizable. The rest is very fuzzy, but you still can kinda recognize the shapes.
Also 0-7 look like alpha channels, but there are 8 of them which is strange.

I hope someone can help me, how I can open the file properly and solve this puzzle.  

It's maybe hard to see on this JPG image, but every image is different, even if the differences sometimes is very small:
[txf.jpg](https://xentaxbackup.github.io/file/7916_txf.jpg)
## Post #2
- Username: Harime Nui
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 11, 2014 7:32 am
- Post datetime: 2014-10-13T21:42:25+00:00
- Post Title: Need help with .txf

I found out!
I compared the file to the Half Life 2 textures and noticed it was the same (you could copy the header and it would open in HL2).
So the compression is DXT.
[http://de.wikipedia.org/wiki/S3_Texture_Compression](http://de.wikipedia.org/wiki/S3_Texture_Compression)
