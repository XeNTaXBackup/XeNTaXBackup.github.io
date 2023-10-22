## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-07-18T16:07:30+00:00
- Post Title: Metropolis Software *.texture files

[https://mega.nz/folder/0SBwQQYK#8TMg5IEGkYFjL42OP7L1pw](https://mega.nz/folder/0SBwQQYK#8TMg5IEGkYFjL42OP7L1pw)

So, are textures in Metropolis Software games (such as Infernal) encrypted/compressed with S3TCDXT1?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-19T21:19:01+00:00
- Post Title: Metropolis Software *.texture files

Here is the file format [http://wiki.xentax.com/index.php/Metrop ... re_TEXTURE](http://wiki.xentax.com/index.php/Metropolis_Software_TEXTURE)
There is 33 bytes header and then there is DXT1/DXT5 compressed image data.

You can use raw texture cooker to export:
[https://imgur.com/a/ROQguIs](https://imgur.com/a/ROQguIs)
[https://imgur.com/a/r7xe6rG](https://imgur.com/a/r7xe6rG)

But for some reason you have to use offset 31 instead 33 to decompress...
