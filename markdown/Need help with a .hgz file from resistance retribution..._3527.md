## Post #1
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-08T19:05:58+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

So, i'm translating this game, and i have to edit some files that are inside others that have this structure... i need help, please, it would be great if anyone coul help me, thx. i attached on file as a example. thx for the attention..  
[UNFREED.rar](https://xentaxbackup.github.io/file/2086_UNFREED.rar)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-08T20:08:23+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

Indeed compressed.
The question is, which algorithm. LZH?

```
uint compressedSize;
uint decompressedSize;
```
## Post #3
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-08T20:25:57+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-08T20:42:22+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

Good idea, but didn't help very much. This just seems to be some debug information referencing the hgz.cc source file.
Can't imagine what HGZ should stand for, Huffman Gzip doesn't make any sense since Gzip already incorporates Huffman due to zlib.
Maybe the executable would help.
## Post #5
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-08T20:46:13+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

> Reply from Rheini
>
> Good idea, but didn't help very much. This just seems to be some debug information referencing the hgz.cc source file.
Can't imagine what HGZ should stand for, Huffman Gzip doesn't make any sense since Gzip already incorporates Huffman due to zlib.
Maybe the executable would help.

What do u mean by executable? the pbp? prx?
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-08T20:52:07+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

Dunno, not familiar with consoles. The main file containing the program code.
## Post #7
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-08T20:57:21+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

> Reply from Rheini
>
> Dunno, not familiar with consoles. The main file containing the program code.

hmm, basically on the consoles there is no executable, he prx is like a plugin (there is two of'em in the game) an there is the pbp that's like the executable, but the only pbp that i can get is the one that update the firmware (this one has no affect in the game)... in the end all i got is the two prx (plugins)..
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-08T21:07:18+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

You might try to search the files for some strings like gzip, zlib, lib, lzh, or whatever. Maybe this gives an indication.
## Post #9
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-08T21:25:11+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

> Reply from Rheini
>
> You might try to search the files for some strings like gzip, zlib, lib, lzh, or whatever. Maybe this gives an indication.

Already tried... no sucess, i even opened the full iso file, but could't get anything, i've uploaded many files in a pack... here is the link:

[http://rapidshare.de/files/47465570/ROTER_C1.rar.html](http://rapidshare.de/files/47465570/ROTER_C1.rar.html)
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-08T22:07:14+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

the file uses the zlib compression, that's clear.
what is not clear is why it's composed by 2 zipped blocks that don't have much sense if you look at their size because the size specified in the two 32bit values at the beginning is the total size (so the total compressed and uncompressed size without references to each single block).
example:

```
offzip -a -1 UNFREED.HGZ c:\ 0
```
then is possible to start with the analysis of the obtained 00000014.dat
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-08T22:38:17+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

the following is the bms script for extracting the files from these HOG archives:

```
# for generating the HOG file from an HGZ one:
#   use "offzip -a -1 UNFREED.HGZ c:\ 0x14"
#   rename c:\00000014.dat to UNFREED.HOG
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

#get DUMMY69 long
idstring "iiii"
get FILES long
get DUMMY long
get NAMES_OFF long
get FILES_OFF long
get OFFSET long
savepos OFFSETS_OFF

for i = 0 < FILES
    goto OFFSETS_OFF
    get NEXT_OFFSET long
    savepos OFFSETS_OFF

    goto NAMES_OFF
    get NAME string
    savepos NAMES_OFF

    set SIZE long NEXT_OFFSET
    math SIZE -= OFFSET
    math OFFSET += FILES_OFF

    log NAME OFFSET SIZE

    set OFFSET long NEXT_OFFSET
next i
```
I have checked the new files and seems that the compressed blocks have a size of 0x17ff8 bytes except the first one of 0x17fec bytes, anyway [offzip](http://aluigi.org/mytoolz.htm#offzip) does the job correctly so it's not much important
## Post #12
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-08T22:46:41+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

> Reply from Bugtest
>
> the following is the bms script for extracting the files from these HOG archives:
Code: Select all# Resistance Retribution (HOG extractor)
# for generating the HOG file from an HGZ one:
#   use "offzip -a -1 UNFREED.HGZ c:\ 0x14"
#   rename c:\00000014.dat to UNFREED.HOG
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

#get DUMMY69 long
idstring "iiii"
get FILES long
get DUMMY long
get NAMES_OFF long
get FILES_OFF long
get OFFSET long
savepos OFFSETS_OFF

for i = 0 < FILES
    goto OFFSETS_OFF
    get NEXT_OFFSET long
    savepos OFFSETS_OFF

    goto NAMES_OFF
    get NAME string
    savepos NAMES_OFF

    set SIZE long NEXT_OFFSET
    math SIZE -= OFFSET
    math OFFSET += FILES_OFF

    log NAME OFFSET SIZE

    set OFFSET long NEXT_OFFSET
next iI have checked the new files and seems that the compressed blocks have a size of 0x8000 bytes except the first one of 0x17ff4 bytes, anyway offzip does the job correctly so it's not much important

yes, thx man, i managed to unpack the data, but, can i repack it? An thx for the HOG script.


eidt: Already figured out, if u delete the first 20bytes (14 in hex) this files turns out into a zlib compressed, then i can compress and decompress with any zlib p\zcker\unpaker. thx for all the efforts a big thanks man..
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T10:48:26+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

remember that thing I said about the size of the compressed blocks, so you can't just compress the whole HOG file and then adding a new header.
anyway I guess that the game could work also with the HOG files without recompressing them
## Post #14
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T10:59:28+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

> Reply from Bugtest
>
> the file uses the zlib compression, that's clear.
lol I refused to be believe it's zlib since it seemed too obvious.
## Post #15
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-09T15:30:29+00:00
- Post Title: Need help with a .hgz file from resistance retribution...

> Reply from Bugtest
>
> remember that thing I said about the size of the compressed blocks, so you can't just compress the whole HOG file and then adding a new header.
anyway I guess that the game could work also with the HOG files without recompressing them

Really? i will try recompressing the hog back and insert it on the game, if this doesnt work i will try to put it back whitout compression.
## Post #16
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-11T13:18:50+00:00
- Post Title: Re: Need help with a .hgz file from resistance retribution...

It's not working, i 
Tried repacking the hog back and reinsert the original header: Not worked.
Tried to use the original file: Not worked.

Any ideas? I already don't know what to do anymore. Help...  

Edit2: A friend told me this:

0x0000[4 bytes] is HGZ id HZ2
0X0004[4 bytes] zlib compress size(+ 8 bytes check)
0x0008[4 bytes] decompress size
0x000c[8 bytes] unknow check
0x0014 zlib start - using default level compression

just in case it helps..
## Post #17
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-14T22:29:53+00:00
- Post Title: Re: Need help with a .hgz file from resistance retribution...

Up.
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-15T19:28:55+00:00
- Post Title: Re: Need help with a .hgz file from resistance retribution...

well, having created the extractor probably I need to reply.
in this period the max I do is writing the extractors on the fly for quickbms so any other project (moreover rebuilding which is something that I don't like because it's boring) is out
## Post #19
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2009-06-15T23:48:10+00:00
- Post Title: Re: Need help with a .hgz file from resistance retribution...

> Reply from Bugtest
>
> well, having created the extractor probably I need to reply.
in this period the max I do is writing the extractors on the fly for quickbms so any other project (moreover rebuilding which is something that I don't like because it's boring) is out
  , but thx anyway.
