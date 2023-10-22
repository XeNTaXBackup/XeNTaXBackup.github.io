## Post #1
- Username: Yukimura
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 27, 2019 5:36 pm
- Post datetime: 2019-10-06T12:15:59+00:00
- Post Title: [Help] Analyze LZP2 compress file

Hello you guys.

I'm try hacking Toukiden Kiwami (PSP)

And need some helping.

Some file I need edit already compressed with header LZP2.

And due i'm still only a newbie, so I dont sure I can perform some high programing for this.

I read some document from Gbatemp, some guys talk that it compressed with method LZSS, but I dont sure about this.

So, I need you guys, if can let's help me analyze it, example like it use what method? (Or further a tool for it   )

I also cut a file dump (from memory view of ppsspp) in case you want compare the original file of it. Hope it useful for progress analyze.

Thank so much.
[LZP2 COMPRESS.rar](https://xentaxbackup.github.io/file/16868_LZP2 COMPRESS.rar)
## Post #2
- Username: Yukimura
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 27, 2019 5:36 pm
- Post datetime: 2019-11-06T13:09:08+00:00
- Post Title: [Help] Analyze LZP2 compress file

Hello everyone, it has been a while since I posted this theard, and I had an in-depth look at this compress file. Please download new file below. 

[http://www.mediafire.com/file/zd0ay23iw ... E.rar/file](http://www.mediafire.com/file/zd0ay23iwozhn09/LZP2_UPDATE.rar/file)

The first 8 bytes are always the same, so I don't mind it.

The next 2 bytes are the size of the compressed original file, from the LZP2 file I uploaded it is E0D1, this seems to be little edian size (sorry, I don't know much about Hacking term), so the exact size of the original file is D1E0 (53,728 bytes)

From that clue I dug into the dump file from the game's ram, and tried to find and locate the exact original file.

And luckily, I was able to locate it exactly the same size in the LZP2 file, I could also read the file information, table, text etc ... and it was complete exactly. 

From 2 bytes (little edian size) to the rest is the content of the file is compressed.

Now I have got its original file from dump ram. The next step I want to compress its original file, and replace it back to the rom with the LZP2 header. 

The problem is that I still do not know what algorithm it uses to compress, from the information I gathered, it seem uses LZSS compress.

So I tried with some LZ compress series, and surprisingly it had the same E0D1 header as in the original LZP2 file, the compressed text looks quite similar, but not completely.

To make sure which algorithm it uses is correct, I will compress the original file and compare it with the contents of the LZP2 file.

But unfortunately, I tried with LZ10, LZ11, LZ77 and LZSS (Most tools picked from romhacking), but without any algorithm that produced the same results as the LZP2 file, they just same like at few points. 

I also tried replacing them back to the rom, but none of them worked.

I wonder if it needs another algorithm? Or does the LZ compression algorithm have some level of compression like Zlib? Maybe some of the tools I used to compress are not the same type as the original file.

Can anyone help me analyze this? I think I am very close to the goal of progress analyzing it. Just a little bit more, hoping someone can help me Enlighten this, omg my head is about to explode haha. )
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-10T10:32:06+00:00
- Post Title: [Help] Analyze LZP2 compress file

You can always take a shot at comtype scan.
[https://zenhax.com/viewtopic.php?f=4&t=23](https://zenhax.com/viewtopic.php?f=4&t=23)
