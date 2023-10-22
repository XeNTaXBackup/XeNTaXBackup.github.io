## Post #1
- Username: PROXY ZER0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 07, 2023 10:18 pm
- Post datetime: 2023-07-21T13:59:58+00:00
- Post Title: Extract textures from game Odin sphere ps2

Would anyone know how to extract the textures from the LOGO.BMP file?
by my tests this is a texture file, but I think it is compressed.
I've used tools like texture find, but no results.
[test.zip](https://xentaxbackup.github.io/file/24090_test.zip)
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-07-28T10:30:45+00:00
- Post Title: Extract textures from game Odin sphere ps2

Given the file directory in the header and the shared FCMP block found in all 3 files, at least there's hope that once you figure out one, you figure out them all, likely a general compression shared across each. It appears [someone](https://www.vg-resource.com/thread-38430-post-668969.html#pid668969) has already done a lot of investigation on Vanillaware games like Odin Sphere and [Muramasa](https://github.com/rufaswan/Web2D_Games/blob/master/tools/psxtools/wii_mura_FCMP_decode.php#L28) with some PHP utility scripts. rufaswan states that you should look for .FTP files to find texture data, as .MBP files are quad coordinates.
## Post #3
- Username: PROXY ZER0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 07, 2023 10:18 pm
- Post datetime: 2023-07-29T12:43:38+00:00
- Post Title: Extract textures from game Odin sphere ps2

Thank!
I'm a layman in this reverse engineering business
