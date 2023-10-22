## Post #1
- Username: Tenchi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 17, 2023 1:31 am
- Post datetime: 2023-08-16T17:46:53+00:00
- Post Title: Need help decompressing a GameCube game file

Hi everyone

I recently started a translation project for the game Hikaru no Go 3 on GameCube, which was only released in Japan.

I've reached a point where what I need to translate is in compressed textures. Almost all the menu names are textures.

The files I need to edit have a .bpe extension in the file system, and after some research I found an algorithm called Byte Pair Encoding, which not only matches the name of the extensions but also seems like it's really what's used here.

My explanation on why I think this is:

1. At the end of each file (screenshot 2) there is always a list of mangled file names, making me believe it's an archive file containing multiple files, and this archive was compressed using BPE. 

2. In the strings of the executable that I found in Ghidra, I see the paths of these .bpe files, and each BPE file is followed by the same file names but this time unmangled. In screenshot 2, we see cursor.cas,  g07.D4 and g16.D4. In the executable's strings, one of those is indeed cursor.cas, but the other two bbg07.D4 and bbg16.D4. Since BPE works by encoding common byte pairs, it seems that the common byte pair bb has been encoded into a single byte, which kind of confirms my suspicion that it is indeed this algorithm. Which means that these BPE files are archives, with a footer containing a file listing, and the whole archive was itself compressed using BPE.

I tried my best to manually reverse this format, but the furthest I've come is that I noticed that each file begins with at least one 00 byte (screenshot 1 is the beginning of a file), and it looks like it's part of an unsigned int at the beginning of each file. I think this is the uncompressed size of the file. I tried to check this number on a bunch of files and they are always slightly (2x to 4x) bigger than the size of the compressed file, so I think it could be correct.

After a while I decided to try out quickbms (first time) which supports BPE (and apparently a variant called BPE2) but I had no success making it work so far. Here's the script I tried:

```
endian big

get size long

get ZSIZE asize
math ZSIZE -= 4

log "" 4 ZSIZE

```


I tried BPE, BPE2, with or without the size header, and all it does is just spit out the same exact file. I also tried using the original 1994 code implementation of BPE but it also doesn't work (enters an infinite loop trying to make a pair table after the 2nd block)

Anyone willing to help me out? It would be greatly appreciated! 
[image (6).png](https://xentaxbackup.github.io/file/24234_image (6).png)
## Post #2
- Username: Tenchi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 17, 2023 1:31 am
- Post datetime: 2023-08-16T17:47:30+00:00
- Post Title: Need help decompressing a GameCube game file

The 2nd screenshot for the start of the file
[image (5).jpg](https://xentaxbackup.github.io/file/24235_image (5).jpg)
