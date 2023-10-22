## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T17:15:36+00:00
- Post Title: Dumped functions

yesterday I wrote a simple and small tool which takes a dumped function as input (practically the functions exported from an executable into a raw file) and produces a C source code with all the fixed/static references converted into local variables allocated through an init function.

it's the same identical job I did with unlz2k a couple of days ago but it's all automatic so that the user needs only to clean the resulted source code and adding the initialization of some pieces of memory or the NOPing of some parts of the dumped function "if" needed.

I have already tested it with the same lz2k dumped function and works perfectly but I would like to test some other "real" examples so if someone has a pre-compiled custom compression/encryption function (x86 32bit) which uses static addresses (otherwise there is no need of the tool) I can test it.

yeah I know that I could do the tests with other known functions and examples but then where is the fun if the result is not really useful and necessary? :)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-20T20:56:10+00:00
- Post Title: Dumped functions

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T21:47:37+00:00
- Post Title: Dumped functions

uhmmm I guess you are off-topic because I referred to something completely different :)

anyway I have given a look at this HFS archives and they are just ZIP files with a different "magic" (HF\1\2 instead of PK\3\4) and with encrypted filenames and files.
so the files are first encrypted and then compressed which means that you can extract and decompress the files without problems but their content is encrypted (no xor, no rot).

that's an unusual and senseless thing because when you encrypt a file before its compression you increase the differences in the bytes with the result of an unoptimized compression.

I have already tried to use the md5 hash of some passwords ("csm...") with the rc4 algorithm (the Crypt* functions) without success.

if you want to make a quick test disable the update in some way (for example try it offline) and put the byte 0xcc at offset 0x4C4E39 of engine.dll, when the debugger will popup you will see the password in the stack window.

*edit* I have attached a simple script in case you are curious of the content of the extracted files
[hfs.zip](https://xentaxbackup.github.io/file/2469_hfs.zip)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T22:28:48+00:00
- Post Title: Dumped functions

I have also tried using the ICE encryption with both the hexadecimal keys "\xbf\x01\x00\xde\x55\x27\x9a\x01" and "\x36\xaf\xa5\x05\x4c\xfb\x1d\x71" but still no success.

anyway a bad thing of the ice encryption is the setting of the key and its level... really chaotic
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-21T01:04:07+00:00
- Post Title: Dumped functions

Were you looking more along the lines of a game like devil may cry 4 that uses an unkown compression?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-21T10:04:51+00:00
- Post Title: Dumped functions

I thought that everything about dm4 was finished.
if the decompression algorithm is still not known it could be a good candidate for the testing of my tool.

P.S.: has someone checked if it was XMemDecompress?
exist a raw decompressed block somewhere to test? (only the compressed data without headers)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-21T12:38:07+00:00
- Post Title: Dumped functions

confirmed, it's XMemDecompress
## Post #8
- Username: brycechen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 28, 2010 8:19 pm
- Post datetime: 2010-01-28T12:30:42+00:00
- Post Title: Dumped functions

umm since i was looking for the mabinogi heros's dumping files, hope you don't mind i could post a reply and ask some question.

are there any bms files i could have for dumping  mabinogi heros ?
## Post #9
- Username: Chessman
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 23, 2009 12:47 am
- Post datetime: 2010-02-23T08:00:08+00:00
- Post Title: Dumped functions

> Reply from aluigi
>
> confirmed, it's XMemDecompress

how to find XMemDecompress functions? 
in one dll of the dlls in the bin directory?
## Post #10
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-05-20T01:52:27+00:00
- Post Title: Dumped functions

Here is a sample of mobinogi hero's hfs file.

[http://www.sendspace.com/file/8tk710](http://www.sendspace.com/file/8tk710)
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-25T10:56:50+00:00
- Post Title: Dumped functions

don't go off-topic
