## Post #1
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-11-13T00:21:35+00:00
- Post Title: [360] Dead Rising - Compressed Files(Inside .arc)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-11-15T03:21:13+00:00
- Post Title: [360] Dead Rising - Compressed Files(Inside .arc)

Got some info on textures. Here is a basic layout:

```

0 - Magic - Chars(6) //TEX - Texture
6 - Unknown - Int16
8 - Width - Int32
12 - Height - Int32
16 - Unknown - Int32
20 - Unknown - Int16?
22 - Unknown - Int16?
```


The rest is bitmap data, but I can't figure out how it works.
## Post #3
- Username: saintone
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 17, 2009 8:57 pm
- Post datetime: 2009-12-17T14:20:45+00:00
- Post Title: [360] Dead Rising - Compressed Files(Inside .arc)

Can you reupload the files?
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-21T05:19:37+00:00
- Post Title: [360] Dead Rising - Compressed Files(Inside .arc)

Files are very similar to those that the devil may cry 4 or in the lost planet, but the same tools will not open.

[Download sample](http://www.sendspace.com/file/4gnym2)

Very interesting to extract the models and textures ... and may convert them into what is more understandable.
## Post #5
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-12-21T07:52:53+00:00
- Post Title: [360] Dead Rising - Compressed Files(Inside .arc)

Format appears to be the same from just an initial glance, but all the current tools are based on the PC versions which are Little Endian, these files are from the 360 which is Big Endian, thus all the data values are reversed compared to the PC format.  As such you are correct none of the current tools will support these as is.  Thanks for the samples, i should be able to compare these abit closer now to ensure whether the endian difference is the only change.

EDIT:
Ok there are a few differences.  This format omits some things found in the other formats as well.  i am attempting to map out the changes, but still need to verify a few things.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-04-18T16:35:44+00:00
- Post Title: [360] Dead Rising - Compressed Files(Inside .arc)

> Reply from revelation
>
> Format appears to be the same from just an initial glance, but all the current tools are based on the PC versions which are Little Endian, these files are from the 360 which is Big Endian, thus all the data values are reversed compared to the PC format.  As such you are correct none of the current tools will support these as is.  Thanks for the samples, i should be able to compare these abit closer now to ensure whether the endian difference is the only change.

EDIT:
Ok there are a few differences.  This format omits some things found in the other formats as well.  i am attempting to map out the changes, but still need to verify a few things.

Hi there!
Any progress on extractor/converter?
