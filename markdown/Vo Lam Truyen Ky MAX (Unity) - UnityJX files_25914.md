## Post #1
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-10-18T14:41:23+00:00
- Post Title: Vo Lam Truyen Ky MAX (Unity) - UnityJX files

Hi guys,

I recently found a game called Vo Lam Truyen Ky MAX. It use unity however assetstudio cannot load files. 

I look at the header and it says UNITYJX, I tried to modify it without luck. Do u have any tips ?

, 


Here you could download the installer: [https://img.zing.vn/upload/vltkmax/sour ... -right.png](https://img.zing.vn/upload/vltkmax/source/News/2022/t10/bg-right.png)

Here some samples [https://www.mediafire.com/file/w12in7jl ... e.rar/file](https://www.mediafire.com/file/w12in7jlk0br5xx/samplee.rar/file)

Thanks in advance,

Drawing
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-10-20T10:25:44+00:00
- Post Title: Vo Lam Truyen Ky MAX (Unity) - UnityJX files

This is a normal UnityFS with a modified header.
The file size can be calculated from the file with the headers in place, but I don't know how to get the length of the resource information and the length of the decompressed information.

I have restored several files and it does not appear to be bit-shifted or XOR. I'm sure there must be some sort of rule...
## Post #3
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-10-20T12:52:32+00:00
- Post Title: Vo Lam Truyen Ky MAX (Unity) - UnityJX files

> Reply from einherjar007 ↑Thu Oct 20, 2022 6:25 pm at Thu Oct 20, 2022 6:25 pm
>
> 
This is a normal UnityFS with a modified header.
The file size can be calculated from the file with the headers in place, but I don't know how to get the length of the resource information and the length of the decompressed information.

I have restored several files and it does not appear to be bit-shifted or XOR. I'm sure there must be some sort of rule...

Thanks for taking a look. I assumed it had a modifies header, but had no luck restoring it.
## Post #4
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-10-21T11:20:31+00:00
- Post Title: Vo Lam Truyen Ky MAX (Unity) - UnityJX files

If you are familiar with UnityFS, you will recognize 0x1E as the replacement.

First, the data before this is a custom header. Anything before that should be replaced with a regular UnityFS header: 0x43 followed by 0x00, with 0x1E coming in the 0x40 position.
Then write the file size in the correct location. Next, write the size of the file information, from 0x1E to the end-of-line information(in general 0xF0) after resS and so on. Next, write the file size after lz4 expansion. By following the above steps manually, the file can be opened in AS for the time being.

I assume that the file information and the size of the extracted file are included in the custom header, but I don't know how to make fix that information correct.

BTW, this game seems to be released in Vietnam, but the content is clearly a Chinese game. I think there is probably an underlying Chinese game, just with a different name due to global expansion.
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-27T17:12:19+00:00
- Post Title: Vo Lam Truyen Ky MAX (Unity) - UnityJX files

Not sure if totally correct, but output from provided samples works with AssetStudio 0.15.47. Quickbms should be used with -w option, because the script is modifying files themselves. 



 unityjx_convert.zip
(455 Bytes) Downloaded 40 times
## Post #6
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-10-27T18:02:41+00:00
- Post Title: Vo Lam Truyen Ky MAX (Unity) - UnityJX files

> Reply from Spiritovod ↑Fri Oct 28, 2022 1:12 am at Fri Oct 28, 2022 1:12 am
>
> 
.

Thanks a lot
