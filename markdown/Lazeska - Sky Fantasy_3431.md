## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-10T12:52:34+00:00
- Post Title: Lazeska - Sky Fantasy

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-13T17:16:00+00:00
- Post Title: Lazeska - Sky Fantasy

I have figured out the archive format for this game but I am not very good at programming so it might take me a while to write an extractor.
the format is as follows.
1. Xor the file table with 0xAC (in the file Character.pak this is the first 0X1282E8 bytes) don't xor the first 0x20 bytes
2.the total files in the archive is 4 bytes located at 0x08 (in this case it is 0xD141 wich we then reverse to make 0x41D1 = 16,849 files)
"I think the total size of the archive is stored at 0x19 - 0x1B"
3.When you see 0xFFFFFFFF this is the creation of a folder followed by the folder name
4. Take this as a file example.

```
........~À.B....Ë<..CF001D023M001.nif
```


```
CB 3C 00 00 43 46 30 30 31 44 30 32 33 4D 30 30
31 2E 6E 69 66
```

The files always start out with 0x01
Then they skip 0x3 bytes
the next 4 bytes are the file size (0x16040100 then we reverse this 0x00010416 = 66582)
the next 4 bytes are the position in the archive from the first file stored in it (0x7EC08F42 reverse this 0x428FC07E + 1400020 'start of first archive" = 0x43CFC09E
Then it skips 0x4 bytes and ends up a the next 0x4 bytes which is the file number in the archive (0xCB3C reversed 0x3CCB = file 15,563)
This is the format for these archives.
if anyone wants a particular model from this game i used jaedernaub to extract the images from this game and their offset so I choose a picture then convert its offset from the binary output into hex reverse the order then just search for the name of the file in the file table then extract everything related to that picture and your done 
psycho girl lol
[](http://xs.to/xs.php?h=xs538&d=09161&f=psychogirl861.jpg)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-06T22:25:50+00:00
- Post Title: Lazeska - Sky Fantasy

Does anyone still have this client? I can't seem to find a copy.
