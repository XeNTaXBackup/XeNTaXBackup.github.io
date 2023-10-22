## Post #1
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2016-12-10T20:55:55+00:00
- Post Title: Trying to extract Mafia II sounds files.

We used an Extractor to extract the sounds from their default .sds main archive, but now they're just .sound files. Any help is appreciated! Here is a sample: [https://www.mediafire.com/?z5gnli46zo4d23u](https://www.mediafire.com/?z5gnli46zo4d23u) Thanks in advanced!
## Post #2
- Username: Pepper26
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 14, 2017 11:06 pm
- Post datetime: 2017-02-14T15:08:53+00:00
- Post Title: Trying to extract Mafia II sounds files.

IIRC, They use FMOD audio FSB.  you may have to open the file with a hex editor and delete everything leading up to the fsb header (FSB4 or FSB5).

for example, spdrvjoe.sds has some animation data at the start (probably for when he says things) and then at offset of 4295 the first FSB4 header starts.  there is more than one fsb header inside, so keep an eye on that.
