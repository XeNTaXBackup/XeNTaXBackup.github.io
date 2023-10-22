## Post #1
- Username: supercolin
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 17, 2011 5:49 pm
- Post datetime: 2015-02-04T14:19:56+00:00
- Post Title: Any idea what format is this?

OFFSET:
0 - 2: RAW
3 - 8: unknown
9 - C: file size
D - 0x14: unknown

Start from offset 0x15, it looks like a JPEG file. If remove the first 0x14 bytes, and be opened as JPEG file, however, suppose it should PNG file, but it lost alpha chanel.
[texture.7z.001.7z](https://xentaxbackup.github.io/file/8599_texture.7z.001.7z)
## Post #2
- Username: supercolin
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 17, 2011 5:49 pm
- Post datetime: 2015-02-04T14:21:07+00:00
- Post Title: Any idea what format is this?

7z file part 2.
Rename and unzip to get the original file and header-removed file.

> Reply from supercolin
>
> OFFSET:
0 - 2: RAW
3 - 8: unknown
9 - C: file size
D - 0x14: unknown

Start from offset 0x15, it looks like a JPEG file. If remove the first 0x14 bytes, and be opened as JPEG file, however, suppose it should PNG file, but it lost alpha chanel.
[texture.7z.002.7z](https://xentaxbackup.github.io/file/8600_texture.7z.002.7z)
## Post #3
- Username: supercolin
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 17, 2011 5:49 pm
- Post datetime: 2015-02-05T08:00:35+00:00
- Post Title: Any idea what format is this?

OK there are some updates, I know most part of the header structure and how to combine the image..

OFFSET:
0 - 2: RAW
3 - 8: unknown
9 - C: total size of embedded pictures.
D - 0x10: size of picture w/ RGB channel, JPG format.
0x11 - 0x13: size of picture of alpha channel, 8bit, JPEG format.

Combine the RGB with A, you got the PNG.



> Reply from supercolin
>
> 7z file part 2.
Rename and unzip to get the original file and header-removed file.
supercolin wrote:OFFSET:
0 - 2: RAW
3 - 8: unknown
9 - C: file size
D - 0x14: unknown

Start from offset 0x15, it looks like a JPEG file. If remove the first 0x14 bytes, and be opened as JPEG file, however, suppose it should PNG file, but it lost alpha chanel.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-02-07T21:27:13+00:00
- Post Title: Any idea what format is this?

That's all very interesting, but what game is this ?
