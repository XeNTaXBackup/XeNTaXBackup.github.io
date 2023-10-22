## Post #1
- Username: BudWalker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 09, 2016 1:38 am
- Post datetime: 2016-11-08T17:54:35+00:00
- Post Title: NewBe attempting to decompress

Can someone help me determine how to decompress some files that I have? I have examples of input files and the compressed file for each of those files. I also have the app that did the compression. I'm trying to write an app that will decompress the compressed version.

I used signsrch on the app and came up with this

Signsrch 0.2.4
by Luigi Auriemma
......
   offset   num  description [bits.endian.size]
   --------------------------------------------
   00006e1e 2545 anti-debug: IsDebuggerPresent [..17]
   0001bd39 3050 compression algorithm seen in the game DreamKiller 
[32.le.12&]

I searched around and it seems that DreamKiller uses q3huff
compression? I'm a Java coder and can translate non-Java q3huff code
to Java. Am I on the right track?

Here is a Dropbox link of a .zip containing an input file and it's compressed file.
[https://www.dropbox.com/s/b68bgn76464ks ... e.zip?dl=0](https://www.dropbox.com/s/b68bgn76464ksfn/example.zip?dl=0)
## Post #2
- Username: BudWalker
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-11-09T11:02:44+00:00
- Post Title: NewBe attempting to decompress

Data is zlib compressed.
