## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-20T00:05:42+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

Another archive, and I am not sure how to do some things

Actually, I found an extractor for it written in C++
[http://asmodean.reverse.net/pages/exlac.html](http://asmodean.reverse.net/pages/exlac.html)

So that tells me what the fields are, but I still can't get the script to work lol

```
get files long
for i = 0 < files
   filexor "0xFF"
   getdstring name 0x1C
   #get compressFlag (from the source code, don't know how to check this later)
   get size long 
   get offset long
   #some more stuff
   log name offset [don't know how to get size]
next i

```


Ok so some problems I have with syntax:

1: The filename is encrypted. They are XOR'd by FF (so I use the filexor command). However, this means that the entire string is XOR'd, so the actual string is not null-terminated anymore and I get some really weird filename with lots of 0xFF in the end.

The string length is variable, I want to XOR the string, but I want to preserve all the nullbytes as well. How to do this?

2: Here is a picture of the problem



I have inverted the string to get the filename, and you can see the start of the data block has a DDS, but there is a "DF" and a long before that.

That long is what I think is the size, because it has a "good" value for an image file.
So I will need to jump to this offset, record the size, skip a single byte to skip that DF, and then after that the rest is just saving the file normally.

The data might be encrypted, seeing how it doesn't look like a correct DDS.

I have attached a sample.
[DATA.7z](https://xentaxbackup.github.io/file/4517_DATA.7z)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-04T00:04:28+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

if you're still looking for help,
as the filename is only xor'd up until a 0x00 byte you have to iterate through the string - so log the entire file to memory and use a combination of getvarchr/setvarchr to unscramble the filename
the compression flag is just an unsigned char treated as a boolean - if it's 0, it false, anything else, true (but it should 1)
the data is compressed with lszz .. and you use quickbms's comtype/clog functions to set that up
