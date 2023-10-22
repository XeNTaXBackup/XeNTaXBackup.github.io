## Post #1
- Username: Racial
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 20, 2015 11:51 pm
- Post datetime: 2016-05-05T13:03:45+00:00
- Post Title: BPE Compression (Needed)

Hi everyone, i discovered this type of compression on some games. I go to readable section of process of windows, and found the uncompressed file. So ive got an example of compressed and uncompressed file.

Before the readable section i found a header of 38h bytes that can help to recognise format maybe i will upload here. In this header i see a dh..TBHS and maybe here its the key. Here a picture of this header.



For that i know, compressed files start with
Sng Int of Uncompressed Size (swaped data)
Sng Int of Compressed Size (swaped data)
Type of compression (in all archives got FE 7F on start of it)

I attached the 2 files, compressed and uncompressed one (maybe it can take some bytes changed for be readable, but the size and 99.9% of bytes are ok)


 Files C-U .zip
Compressed and uncompressed one (105.89 KiB) Downloaded 16 times
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2016-05-05T14:32:33+00:00
- Post Title: BPE Compression (Needed)

The compression is byte pair encoding.
quickbms already supports it.
comp_bpe

And I tested it and it could decompress the example file.
## Post #3
- Username: Racial
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 20, 2015 11:51 pm
- Post datetime: 2016-05-05T14:49:24+00:00
- Post Title: BPE Compression (Needed)

Have you got the scripts for uncompress/compress?

If you cand send me ill be grateful

Thanks
## Post #4
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2016-05-05T18:52:56+00:00
- Post Title: BPE Compression (Needed)

[https://github.com/vteromero/byte-pair-encoding](https://github.com/vteromero/byte-pair-encoding)
## Post #5
- Username: Racial
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 20, 2015 11:51 pm
- Post datetime: 2016-05-05T19:09:26+00:00
- Post Title: BPE Compression (Needed)

Good, thanks again. And sorry if im disturbing
But can you explain to me how you do it to uncompress the example?
I dont know how to use QuickBMS with those files that you give me in the link

What i need to do to uncompress the example and compress the other?
## Post #6
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2016-05-05T19:20:13+00:00
- Post Title: BPE Compression (Needed)

```

get size long
get ZSIZE long

set NAME string "dump"
string NAME += ".dmp"
clog NAME 8 ZSIZE size

```


I think this should decompress it.
save this code on a txt file.
open quickbms.
select the txt file.
select the compressed data.
select output folder.
done
## Post #7
- Username: Racial
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 20, 2015 11:51 pm
- Post datetime: 2016-05-05T19:44:55+00:00
- Post Title: BPE Compression (Needed)

Perfect, it descompressed the file good. Thanks a lot.  

What i need to do for compress it again?

I used reimport and put the edited file and the script that you give me, but it doesn't make a new file and tolds me and error in console
