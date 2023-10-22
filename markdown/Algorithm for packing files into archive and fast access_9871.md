## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-14T04:51:11+00:00
- Post Title: Algorithm for packing files into archive and fast access

What's a fast way to pack together a bunch of files with a reasonably fast way to index them? 

```
File Data

```


I can build the table and the data separately, like for each file, create an entry for the file, and put the file data in a buffer. Then, combine the table and data sections together and then increment all offsets in the table to the start of the data sections.

Or perhaps...

```
entry_data 1
entry_header 2
entry_data 2
...

```


Which means I don't have to worry about keeping track of my data I just need to write as I go.
Except I guess the problem is that if you want to find a file you need to loop through every entry...
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2012-11-16T18:02:47+00:00
- Post Title: Algorithm for packing files into archive and fast access

Save file data at the start end the table at the end. Then maybe put CRC32 or some other hash values in the table and sort it by them. Then to locate a file, you hash the passed filename and do a binary search for it. Also need to normalize the path before hashing, so you get the correct hash.
