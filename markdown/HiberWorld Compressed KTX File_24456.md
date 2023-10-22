## Post #1
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-09-05T13:53:58+00:00
- Post Title: HiberWorld Compressed KTX File

i decided to rip models of hiberworld, while i can download .glb and .ply files correctly, i need to find out how do open those compressed files, i tried pvrtextool and it failed
## Post #2
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-09-05T13:56:53+00:00
- Post Title: HiberWorld Compressed KTX File

for anyone who wants to try decompress this texture, i will leave a link here: [https://www.mediafire.com/file/khxtn40e ... t.ktx/file](https://www.mediafire.com/file/khxtn40e9qrk9rq/CH_PL_astronaut_01_albedo.512-dxt.ktx/file)
## Post #3
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-09-05T13:58:18+00:00
- Post Title: HiberWorld Compressed KTX File

mali texture tool doesn't work
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-05T19:52:06+00:00
- Post Title: HiberWorld Compressed KTX File

It is a standard KTX file [http://wiki.xentax.com/index.php/KTX_Image](http://wiki.xentax.com/index.php/KTX_Image)

Image data is compressed with DXT1, but the file itself is not compressed,
so you can use crunch to convert this to PNG [https://i.imgur.com/GiDJWx4.png](https://i.imgur.com/GiDJWx4.png)

Here is the correct crunch command:

```
crunch.exe -file <KTX_FILE>
```


and here is the source code [https://github.com/BinomialLLC/crunch](https://github.com/BinomialLLC/crunch)
## Post #5
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-09-05T20:00:55+00:00
- Post Title: HiberWorld Compressed KTX File

oh, i thought it would be impossible, i was getting the 256 x 256 versions
