## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-03-11T08:58:22+00:00
- Post Title: Corvette (2003) data.sma

[https://mega.nz/file/IK4T1A6a#QO7JLX5M6 ... WeEwtYd-uE](https://mega.nz/file/IK4T1A6a#QO7JLX5M6XrkbSuHuPeVe-0LbjDIaoFoDWeEwtYd-uE)

I'm reading that data.sma (Steel Monkeys Archive) from Corvette (2003) has filenames ending with UT.
Anyone found a QuickBMS script to extract files from data.sma?
## Post #2
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-05-02T19:31:02+00:00
- Post Title: Corvette (2003) data.sma

Bump
## Post #3
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-05-09T11:45:11+00:00
- Post Title: Corvette (2003) data.sma

This is actually a zip archive that has been slightly modified to prevent the use of normal tools. The modifications that are made are:

1. The ZipDirEntry signature 0x02014B50 is swapped for 0x9AB3C729
2. The ZipEntry signature 0x04034B50 is swapped for 0xB3850CAC
3. The compressed_size and offset_curfile fields are XOR'd with a magic value of 0xCC6B9A57 i.e. 
```
header.compressed_size ^= 0xCC6B9A57
```


The game loads the file, creates a copy of each header in memory, XORs the fields (if required) and then remaps the pointers to the local file so that it can use unzip to process it like a normal zip file. By replicating this you end up with a normal archive.

I've never used QuickBMS but the C# code I used for this is available [here](https://gist.github.com/barncastle/153a48f4941327674275de7567a219fc) - it should be pretty trivial to convert.

Interestingly, it looks like the game actually supports reading a normal zip file provided it is named 'data.sma' as it checks for the custom signatures before XOR'ing the fields.
