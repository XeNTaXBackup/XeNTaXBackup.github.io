## Post #1
- Username: drsiu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 19, 2011 4:41 pm
- Post datetime: 2016-06-25T17:20:06+00:00
- Post Title: The Secret World  -  RDB HashIndex.bin

Is there anyway to grab all the resources from RDB HashIndex.bin?

When looking at the Game Patcher Log:
[HTTPManager] Downloaded 'C:\TSW\RDB\RDBHashIndex.bin'
[LocalRDBSource] New resources: 694630   31477.12 MB
[RDBManager] Enabled bundles: 1000, 1100, 1200, 1300 .......
[RDBManager] Downloading new:   562315    20521.06 MB

It said there were 31477.12 MB and 694630 total resources in the RDBHashIndex, but the patcher only downloaded 20521.06 MB with 562315 resources. I wonder what the other files are about. Is there any way to grab all the bundles name inside the RDBHashIndex.bin, and possibly get all the hash inside the RDBHashIndex.bin in order to download all the remaining files?

This is the file Structure of the RDBHashIndex.bin:  (Reference from [https://github.com/joakibj/tswrdb/blob/ ... NTATION.md](https://github.com/joakibj/tswrdb/blob/develop/docs/DOCUMENTATION.md) )


File part:	      Length:
Header	              4
Hash Data	       NumTypes * x


Header	:
Offset	Length	          Contents
0	           4	                  Magic (0x52 0x44 0x48 0x49 = RDHI)
4	           4	                  Version (7)
8	           4	                  NumEntries
12	           4	                  NumTypes


Hash Data:
Offset	Length	               Contents
0	           4                     	RDB Type
4	           4             	     NumEntries
8	     NumEntries * 47	     Hash Entries


Sample of a RDBHashIndex.bin: [http://www.filedropper.com/rdbhashindex](http://www.filedropper.com/rdbhashindex)
