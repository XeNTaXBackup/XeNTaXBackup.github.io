## Post #1
- Username: anako126n
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 13, 2011 5:13 pm
- Post datetime: 2011-10-25T17:44:59+00:00
- Post Title: File format - help request.

Hi everyone,

I'm complete beginner in archives extracting, quickbms and all the rest, and there is a file I have to extract. Unfortunatelly I stuck and I'm coming here asking others, more experienced people to help if they could.

I can extract the files, however they are partially corrupted, I really hope that someone will help me in this case.

For me it looks like the orange area represents the filename, red states either is compressed or not, and green as follows: offset,size,zsize. 

But what does the 2 bytes just before compression mean? Are they causing the files to be corrupted after extraction?



Thats the file itself [http://www.zshare.net/download/95165767b312bc7a/](http://www.zshare.net/download/95165767b312bc7a/)

Thank you in advance.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-26T21:05:37+00:00
- Post Title: File format - help request.

partially corrupted?? if they have a compressed size field then they're compressed

not sure how you decided the red part was the compression flag. if zsize != size then it's compressed

no idea on algorithm. there are 8 bytes before data which may need ignoring

```

goto 8
get FILES long

for f = 0 < FILES
  getdstring FNAME 52
  get OFFSET long
  get SIZE long
  get ZSIZE long

  # prepended 8 bytes may be part of method
  #clog FNAME OFFSET ZSIZE SIZE

next f


```
## Post #3
- Username: anako126n
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 13, 2011 5:13 pm
- Post datetime: 2011-10-27T00:46:13+00:00
- Post Title: File format - help request.

The compression seems to be lzma_86 dec. 

What do I mean by partially corrupted? All text files are completely readable, but all other files such as: jpg is either missing part of image at the end/beginning or elelment somewhere in the middle. swf files are damaged in the same way,  missing elements etc.
