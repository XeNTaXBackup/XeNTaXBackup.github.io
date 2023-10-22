## Post #1
- Username: christorrella
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 13, 2020 1:30 am
- Post datetime: 2020-10-12T18:43:49+00:00
- Post Title: Test Drive Unlimited (help!)(MHPF .PCK format)(PSP/PS2)

1. Introduction
I've mostly deciphered the structure of a pack file format for a game called Test Drive Unlimited. I even wrote a script to unpack and repack these files, and I verified that the game is still playable after modifying the order of resources; [check out the script here.](https://github.com/christorrella/mhpf-tools/blob/main/mhpf-tools.py) There's just one part of one table left that I need to understand before I can mod the game and repack it without "cheating" to do so. So, I have a challenge for you, if you're willing to take it!   Skip down to section 5 to see my big question.

The purpose of this post is to firstly ask for help discovering what a specific number in an archive's table means, and to secondly spill my knowledge on how this pack file's format works.

2. Background information
Test Drive Unlimited (TDU's) game resource files are pretty similar across platforms (PC, PS2, PSP, maybe XBOX too), but in the case of the Playstation platforms, the bulk of the resources are packed away in files ending in .PCK (TDUPSP.PCK, TDUPS2A.PCK, TDUPS2B.PCK). These files are all under 2gb in size and might be split in two files for PS2's particular case for DVD disk format limitation reasons (not sure on that).

3. Header/signature
All three .PCK's are structured in the same way. See attached screenshot of a hex editor for reference.


All offsets, sizes, etc all appear to be 4 bytes long and little-endian unsigned (but I don't really know, because this is the first file format I've ever reverse-engineered.) 

In those sets of four bytes, the header appears to be structured this way:

1. file's "magic"(?), always being ascii characters "MHPF" which I assume means "Melbourne House Pack File" (Melbourne House being the gaming studio that developed the Playstation versions of this game)
2. unknown; maybe the version of the file or packing program; in all three cases this is a decimal 1
3. total archive file size; matches the size of the .pck file you're looking at, in this case it's decimal 1161251806 bytes in size
4. number of resources contained in the file; in TDUPSP.PCK's case, it's decimal 4682 resources
5. unknown; always decimal 31 for all three archives

6. start offset of Table 1 (explanation of each table below)
7. size of Table 1
8. start offset of Table 2
9. size of Table 2
10. start offset of Table 3
11. size of Table 3
12. start offset of Table 4
13. size of table 4

4. Structure

It should be noted that some tables and resource files are fit inside of N-chunks of 2 Kibibytes (yes, 2 'Kibibytes', or 2048 bytes) of data. For example, if a game resource contained in Table 2 is just 3 kibibytes in size, then you should expect another 1 kibibyte of zeros/padding before the next resource file starts.

The above is important to note because the sizes that are given in the header refer to the length of the data contained in that table and NOT always the length of the chunk that the table takes up. For example, in TDUPSP.PCK, the header stipulates that Table 1 is only 56184 bytes long, but the chunk that Table 1 sits in is actually 28 kibibytes in size (57,344 bytes). This is particularly important when re-packing the resource files into a new .PCK file.

With that out of the way, each .PCK is split in the following way:
1. 2 Kibibytes chunk for header: contains the 'MHPF' magic, total filesize,  table offsets/sizes, etc
2. N-kibibytes chunk for Table 1: contains resource offsets, sizes, and the unknown value I'm asking for help with in this post
3. M-kibibytes for Table 2: contains the actual game resource files that are referenced to in Table 1
3. a. note that each resource file is also sitting in R * 2-kibibyte chunk, with padding if necessary, until the next 2-kibibyte chunk starts
4. X-bytes (not a 2-kib chunk) for Table 3: contains starting offsets of filename strings located in Table 4
5. Y-bytes for Table 4: contains filename strings for each resource file

Note that the ordering of resource files in Table 1 matches the ordering of resource files in Table 2 and the ordering of destination names in Tables 3 and 4.

5. The "unknown" value in Table 2
Table 2 consists of N records that are 12 bytes long, and each record contains information for one resource file. If the .PCK contains N resource files, then Table 2 has N records that are 12 bytes each. The size of this table's data is therefore N * 12.

These 12 bytes represent three values; the second value is the resource's offset, the third value is the resource's size (actual size of the resource, not the 2-kibibyte chunk size, remember.) The first value is what I can't figure out for the life of me!

In TDUPSP.PCK, these twelve bytes are:

```
B0F01800 00F0AC2D C1840000
```

(unknown, offset, size)

Some things I've found about this data:

1. The ordering of all resource information (Tables 1,2,3 and 4) is dictated by this unknown value. It might be split up, but it's mighty interesting to me that this value only increases as you go through Table 2. [See this Google Sheets doc](https://docs.google.com/spreadsheets/d/12Isv8Wxpv5tmFre_3fNC9LHGJytzqIDD4Kk-E4Kc79s/edit?usp=sharing) to see the number increase pretty much linearly as you go through Table 2.

2. If I change the ordering of the resources, but I keep the order of resources consistent across all of the tables, the game still runs fine. If I change the "unknown" value at all, the game does not boot.

3. If you look closely, the ordering seems closely related to filetype of the resources. For example, a lot of .tla, .tlb and .tlc files are ordered closely together. Also, the difference in "unknown" values between adjacent resource listings (column D of that google spreadsheet) is sometimes consistent; for example, for any two adjacent .tla and .tlb files that are in the same directory is always decimal 2, and between .tlb and .tlc files, this "unknown" value has a difference of decimal 1582. The same applies to some .bnk files that are next to each other.

4. The number probably isn't a 32-bit integer referencing any kind of offset. The last "unknown" value in TDUPSP.PCK is well over decimal 4.2 billion, and the file is only 1.1 bil bytes in size. Maybe this "unknown" value is split into 2 or 1 bytes instead?

Any and all advice is appreciated. Thank you for reading & I look forward to any pointers (  ) you can give!
[Screen Shot 2020-10-12 at 1.44.16 PM.png](https://xentaxbackup.github.io/file/18812_Screen Shot 2020-10-12 at 1.44.16 PM.png)
## Post #2
- Username: christorrella
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-12T19:56:34+00:00
- Post Title: Test Drive Unlimited (help!)(MHPF .PCK format)(PSP/PS2)

Great work with researching this file format. 
I'm just guessing here, but maybe this unkown is CRC value or hash value?
## Post #3
- Username: christorrella
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 13, 2020 1:30 am
- Post datetime: 2020-10-12T20:01:50+00:00
- Post Title: Test Drive Unlimited (help!)(MHPF .PCK format)(PSP/PS2)

> Reply from ikskoks ↑Tue Oct 13, 2020 3:56 am at Tue Oct 13, 2020 3:56 am
>
> 
Great work with researching this file format. 
I'm just guessing here, but maybe this unkown is CRC value or hash value?

Thanks! It's been about 7 years in progress   

If it is a "check" or "hash" number, would that mean that resources can't be changed in size, otherwise the game won't boot? I can increase the size of a resource or modify it somehow without an issue, but I haven't extensively tested this (i.e. deleting files completely by giving them a size of 0 in Table 1 or significantly increasing their size to a new 2-kibibyte chunk). Thoughts?

Thanks again!
## Post #4
- Username: christorrella
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-12T20:22:00+00:00
- Post Title: Test Drive Unlimited (help!)(MHPF .PCK format)(PSP/PS2)

> otherwise the game won't boot?
To be honest, I'm not sure. I suppose it depends on the game   
I can imagine situation when game have custom CRC checking procedure etc.etc.

I can also imagine some custom packing procedure like this:

```
   unk_val = make_hash(res_offset + res_type)
   file.write(unk_val)
   return
```


That's may be reason why your value is still increasing for some file types.
But I'm not sure any of this. I'm still guessing.
