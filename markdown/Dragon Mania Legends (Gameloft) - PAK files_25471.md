## Post #1
- Username: fengyexiye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 31, 2022 7:31 pm
- Post datetime: 2022-05-31T11:42:30+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

Almost all game resources have been compressed into DAT files. I tried many methods but could not unzip them.
Here are some sample files:
[https://drive.google.com/file/d/1-WvCvk ... p=drivesdk](https://drive.google.com/file/d/1-WvCvk9y7zslomgbvABWhu9-5iQi8S9C/view?usp=drivesdk)
If you know something about these contents, please give me some ideas or tell me how to decompress them. Thank you
## Post #2
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-09T15:43:51+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

I've had a quick look at this and the format is using [Zstandard](https://github.com/facebook/zstd) for compression. 

There is an uncompressed header, followed by a compressed file table containing FileTableEntry structures, followed by each file's compressed data in order of the FileTable. Using the header you read FileTableCompressedSize bytes and Zstd decompress to get the FileTable, then iterating each FileTableEntry you read entry.CompressedSize bytes and Zstd decompress to get the raw file.

FYI it looks like some files are actually PKZip archives despite their file extension e.g. "ancient_divine_wind_eyes.tga" is a PKZip archive containing two ktx files.

```
{
   char Magic[4];                  // "BUD\0"
   uint FileTableCompressedSize;
   uint FileTableDecompressedSize;
   
   byte CompressedFileTable[FileTableCompressedSize];
   
   byte CompressedFileDatas[x][y]; // x = num of FileTable entries, y = entry.CompressedSize
}

struct FileTableEntry
{
   uint NameLen;
   char Name[NameLen];
   uint CompressedSize;
   uint DecompressedSize;
}

```
## Post #3
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2022-08-12T04:11:49+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

Thank you very much for your reply.
I tried the method you provided, but there seems to be an error.

```

Last script line before the error or that produced the error:
  14  char Name[NameLen]
  coverage file 0     0%   1437       6333033    . offset 0000059d
```

Is it that I lack any dependence? Or I made some mistakes.
Finally, thank you very much
## Post #4
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-12T16:35:33+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

[Here](https://gist.github.com/barncastle/02eb58226ae5cc7cb699806ddde85793) is some sample code in C# which might help provide reference for your script. I've run this through all of your sample files again and everything is parsing correctly for me. 

Based on the error I would assume your decompression isn't right as the first 4 bytes should be an integer below 256 e.g. "?? 00 00 00" so cannot be negative. You might also want to double check everything is in Little Endian.

If you can share your script someone might be able to pinpoint the issue (I'm not knowledgably of BMS unfortunately but will have a go).
## Post #5
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2022-08-13T08:18:09+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

> Reply from barncastle ↑Sat Aug 13, 2022 12:35 am at Sat Aug 13, 2022 12:35 am
>
> 
Here is some sample code in C# which might help provide reference for your script. I've run this through all of your sample files again and everything is parsing correctly for me. 

Based on the error I would assume your decompression isn't right as the first 4 bytes should be an integer below 256 e.g. "?? 00 00 00" so cannot be negative. You might also want to double check everything is in Little Endian.

If you can share your script someone might be able to pinpoint the issue (I'm not knowledgably of BMS unfortunately but will have a go).

really thanks for your detailed explanation,this is very usefulI.And I found the mistake I made.Thankd again
## Post #6
- Username: fengye
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-13T11:11:02+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

And here's the article for reference:
[http://wiki.xentax.com/index.php/Dragon ... egends_PAK](http://wiki.xentax.com/index.php/Dragon_Mania_Legends_PAK)

Thanks for sharing, barncastle
## Post #7
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2022-08-13T13:43:18+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

> Reply from barncastle ↑Sat Aug 13, 2022 12:35 am at Sat Aug 13, 2022 12:35 am
>
> 
Here is some sample code in C# which might help provide reference for your script. I've run this through all of your sample files again and everything is parsing correctly for me. 

Based on the error I would assume your decompression isn't right as the first 4 bytes should be an integer below 256 e.g. "?? 00 00 00" so cannot be negative. You might also want to double check everything is in Little Endian.

If you can share your script someone might be able to pinpoint the issue (I'm not knowledgably of BMS unfortunately but will have a go).

Sorry to bother you again, I also want to try the C # code you provided, but I can't find the correct assembly containing the "zstdsharp. Decompressor()" function    
It seems that there is no such function in the commonly used datasets on GitHub. If you can, please share the datasets you use. Thank you
## Post #8
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-15T10:36:08+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

> Reply from fengye ↑Sat Aug 13, 2022 9:43 pm at Sat Aug 13, 2022 9:43 pm
>
> 
I can't find the correct assembly containing the "zstdsharp. Decompressor()" function

Sorry yeah I forgot to link the library I used - its [oleg-st's ZstdSharp](https://github.com/oleg-st/ZstdSharp).
## Post #9
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2022-08-19T01:22:09+00:00
- Post Title: Dragon Mania Legends (Gameloft) - PAK files

> Reply from barncastle ↑Mon Aug 15, 2022 6:36 pm at Mon Aug 15, 2022 6:36 pm
>
> 
fengye wrote: ↑Sat Aug 13, 2022 9:43 pm
I can't find the correct assembly containing the "zstdsharp. Decompressor()" function   


Sorry yeah I forgot to link the library I used - its oleg-st's ZstdSharp.
Thank you very much.
