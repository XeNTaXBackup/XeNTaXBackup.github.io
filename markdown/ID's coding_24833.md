## Post #1
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-12-10T19:36:15+00:00
- Post Title: ID's coding

Anyone know how you could take a Name and encode it like below into an ID.
NBB_Bismark  
ID is 0x6c18c175e43bdb39
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-10T20:55:44+00:00
- Post Title: ID's coding

You can do it with hash function [https://en.wikipedia.org/wiki/Cryptogra ... h_function](https://en.wikipedia.org/wiki/Cryptographic_hash_function)

Some examples [https://hashcat.net/wiki/doku.php?id=example_hashes](https://hashcat.net/wiki/doku.php?id=example_hashes)
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2021-12-11T19:47:45+00:00
- Post Title: ID's coding

You'll have to figure out the correct hash function to use, though. But you have at least one sample (and I'm assuming there are others you didn't bother posting), so at least you can just find some tool that implements a collection of hash functions, and pass in one of your sample strings, to see if any of the output hashes match the string's hash that you already have. You also get a clue from the hashes you have now: the one you posted is 8 bytes/64 bits, so any function that generates hashes of a different length can be immediately ignored.
## Post #4
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-12-14T00:18:12+00:00
- Post Title: ID's coding

Yes. I have more examples to work with. I tried Hashcat but my system won't run it. Will try earlier versions.
I MIGHT be able to capture the process that does the Hash and get clues from that.
Thanks Mates!
