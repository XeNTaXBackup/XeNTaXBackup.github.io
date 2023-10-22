## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-22T12:46:00+00:00
- Post Title: Nokia N-Gage *.pkg - unknown compression

Hi there!

I want to extract the files from a Nokia N-Gage game. I'm having problems extracting the files. Here's the file: [http://www.sendspace.com/file/cha1o1](http://www.sendspace.com/file/cha1o1)

And this is the BMS script I wrote:

```
get DUMMY long # always zero
get FILES long
goto 0x2C # skip some unknown variables

for i = 0 < FILES
   get DUMMY long
   getDstring NAME 0x18 # zeros are skipped when writing file
   get UNKNOWN long
   get ZSIZE long
   get SIZE long
   get OFFSET long
   if SIZE == ZSIZE
      log NAME OFFSET SIZE
   else  # unknown compression method
   endif
next i
```

In the attached bms script I confused ZSIZE and SIZE, so just delete the file and take the above script. Something is wrong even with the uncompressed files because the *.txt files are just gibberish.

Thanks for your help!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-22T20:09:40+00:00
- Post Title: Nokia N-Gage *.pkg - unknown compression

comtype gzip
and
clog NAME OFFSET ZSIZE SIZE
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-23T11:42:45+00:00
- Post Title: Nokia N-Gage *.pkg - unknown compression

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-23T13:33:19+00:00
- Post Title: Nokia N-Gage *.pkg - unknown compression

eh eh eh you forgot comtype gzip in the script :)
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-23T13:59:25+00:00
- Post Title: Nokia N-Gage *.pkg - unknown compression

> Reply from aluigi
>
> eh eh eh you forgot comtype gzip in the script
Whoops - corrected. 

Any idea about the swb files?
