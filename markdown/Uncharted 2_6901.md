## Post #1
- Username: fadi002
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-02T22:46:24+00:00
- Post Title: Uncharted 2

Here is a script i made to extract dds textures from uncharted 2 pac files.
It may mess up weather its a dxt1 or 5 if its green and fuzzy looking just change it to dxt5 and your all set.

quickbms script

```
print "%START%"
goto START
savepos BASEOFF
print "%BASEOFF%"
goto 0
for
ENDIAN BIG
FindLoc START string "z:/"
math start - 0x54
goto start
get unk01 long
get unk02 long
get unk03 long
get unk04 long
get unk05 long
get unk06 long
get unk07 long
get unk08 long
get unk09 long
get OFFSET long
math OFFSET + BASEOFF
get SIZE long
get unk12 long
get TYPE long
get unk14 long
get unk15 long
get MIPS long
get WIDTH long
get HEIGHT long
get unk19 long
get unk20 long
get unk21 long
getdstring null 0x3
get name string
string name - 24
string name + .dds
if unk19 == 0x1
print "%name%"
callfunction addDDSheader
math size + 0x80
log NAME 0 size MEMORY_FILE
endif
next


startfunction addDDSheader
endian little
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0xC HEIGHT long
putVarChr MEMORY_FILE 0x1C MIPS long
if type == 0x1
putVarChr MEMORY_FILE 0x57 0x31
endif
if type == 0x2
putVarChr MEMORY_FILE 0x57 0x35
endif
endian big
   append
   log MEMORY_FILE OFFSET SIZE
   append
endfunction

```

[elena-skin-main-color..png](https://xentaxbackup.github.io/file/4421_elena-skin-main-color..png)
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-07-03T07:02:37+00:00
- Post Title: Uncharted 2

wow, very unexpected, thanks chrrox.
## Post #3
- Username: lahbibnabil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 02, 2010 3:08 am
- Post datetime: 2011-07-06T07:01:15+00:00
- Post Title: Uncharted 2

(thanks) this script do not extract 3d model
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-07-06T07:04:13+00:00
- Post Title: Uncharted 2

> Reply from lahbibnabil
>
> (thanks) this script do not extract 3d model
you right, and it shouldn't.
## Post #5
- Username: RAWTalent
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 08, 2011 8:39 pm
- Post datetime: 2011-07-10T15:32:49+00:00
- Post Title: Uncharted 2

Wow, now if only extracting models too we'd be all set!
## Post #6
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2011-11-26T16:29:42+00:00
- Post Title: Uncharted 2

Thanks for the great script! But unfortunately it does not support Uncharted 3, is it possible to support and Uncharted 3 too?
[http://www.multiupload.com/4KXDC2RZYM](http://www.multiupload.com/4KXDC2RZYM)
## Post #7
- Username: Strelok
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 13, 2012 3:37 am
- Post datetime: 2012-07-02T23:52:06+00:00
- Post Title: Uncharted 2

What about models? Why you did not support them?
## Post #8
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-07-04T21:03:07+00:00
- Post Title: Uncharted 2

Wow, thank you! I'm going to try this with Uncharted 3 later, hopefully it will work...
If it doesn't, you should make a new code that works with Uncharted 3 and hopefully extracts everything from the files.

I'm so glad you did this!     

Edit: Doesn't work for Uncharted 3.
## Post #9
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-07-08T16:30:38+00:00
- Post Title: Uncharted 2

I was able to make this script work for Uncharted 3 PAK files by changing the beginning of the script to this:

```
print "%START%"
```

But, unfortunately, it only works ~30% of the time and the dds textures come up messed up all the time. At least it's something... (The original script finds 0 textures 100% of the time if a U3 pak is being used with it)

If anyone with more experience with BMS scripts can help me out, I would really appreciate it.     It doesn't seem like it would need too much work (I could be totally wrong though).

If a U3 pak file sample is needed, go to Skykila's post. He has a link of one.
## Post #10
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-07-19T01:03:54+00:00
- Post Title: Uncharted 2

Well, I used the U3 script edit for some more paks and I was able to get some things to be extracted and actually show some of the file clearly, but it still needs fixes (that I have no idea how to do) to be as good as the U2 one. 

Anyways, I've also figured out the edit needed for it to work with UDF Pak files, but the dds textures come up even more messed up than the U3 ones.

Here it is: (for UDF)

```
print "%START%"
```


UDF= Uncharted: Drake's Fortune
## Post #11
- Username: modz2014
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 30, 2021 10:42 pm
- Post datetime: 2021-12-30T14:44:01+00:00
- Post Title: Uncharted 2

how do i run this script please
