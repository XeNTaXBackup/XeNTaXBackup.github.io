## Post #1
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-09-28T23:25:48+00:00
- Post Title: "external directory" archive - length of filename

Hi there.   
I work on unpacking some "external directory" archive here..
There is master.dir (little one, with directory listing)
and master.dat (big one with data)

I already know the structure of the directory file. Here it is:

First goes a list of pointers:

401E0000 681E0000 8C1E0000 B01E0000 D81E0000 001F0000 281F0000... [over 1900] ...
They tell us where is each listing entry in the directory file. There are 1935 pointers and exactly the same number of entries.

Then goes directory listing itself:

00000000 E0550000 3E1D0000 data\loading\british.dds....
00200000 E0550000 67050000 data\loading\french.dds.
00280000 E0550000 96010000 data\loading\german.dds.
00300000 E0550000 4B050000 data\loading\swedish.dds....
00380000 E0550000 D1050000 data\loading\italian.dds....
00580000 80000200 52C50100 data\legal.dds..
...

Yup, i even almost understand the format of entries. Here is what i have:

00000000 E0550000 3E1D0000 data\loading\british.dds....
00000000 - offset in master.dat.
E0550000 - no idea. I suspect it somehow refered to length of filename
3E1D0000 - length of a file.
data\loading\british.dds - file name (obvious x))

Ok, i have almost anything to write BMS script. But I stuck on length of filename. O____o If i don't know the length i can't tell parser how many characters to read to get the filename.
(I wonder if there is some way to make parser read only until first 00 value...)

So, here it is - how to get the filename?
any help would be just great.  

P.S. Thanks for reading, hope you didn't get a headache because of my english -_-'''
[master.zip](https://xentaxbackup.github.io/file/2399_master.zip)
## Post #2
- Username: Corwin
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-29T01:05:41+00:00
- Post Title: "external directory" archive - length of filename

Yes there is just use 
getdstring NAME
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-09-29T06:40:17+00:00
- Post Title: "external directory" archive - length of filename

Start from 0x0000, a Dword(4-bytes each) telling you where is individual index/record start!
so, 1st record start @0x1E40, 2nd record @0x1E68

and for BMS, you need to use:
get RESNAME string

getdstring will not work(AFAIK) since the strings are not in fixed length!
