## Post #1
- Username: zjvlqkd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 28, 2012 9:11 am
- Post datetime: 2013-05-19T13:57:35+00:00
- Post Title: How to decompress a new LZS format?

I used  to tool of quickbms but well
and i know my english skill is not good

I was unpacking *.PAC file
*.PAC file was NOT compression
so i writed quickbms code and using code unpacked *pac.file!
used code

```
//.PAC file
idstring "add"
goto 0x10
get FILES long
goto 0x20
for i = 0 < FILES
 get offset long
 get size long
 get dummy long
 get dummy long
 get name_offset long
 savepos break
 goto name_offset
 get name string
 goto break
 getdstring null 0xC
 get name1 filename

 string name1 += "_unpacked/" 
 string name1 += name
 log name1 offset size

next i

```


unpacking file header is LZS
so 
I searched LZS decompress tool and get!! some tools...
but..
I'm not decompressd file

I explain know to LZS header of this file
first 8byte is same as all files of this game
next 4byte unknown
next 4byte is offset
next 4byte maybe decompress SIZE?
next 4byte compress SIZE
next 4byte unnown
next 4byte null
and file name

here attach *.pac file and UNPACKING LZS file
[example files.zip](https://xentaxbackup.github.io/file/6410_example files.zip)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-19T15:27:06+00:00
- Post Title: How to decompress a new LZS format?

please post the tools then i might be able to help.
## Post #3
- Username: zjvlqkd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 28, 2012 9:11 am
- Post datetime: 2013-05-20T00:42:18+00:00
- Post Title: How to decompress a new LZS format?

> Reply from chrrox
>
> please post the tools then i might be able to help.

Quickbms link:[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

thanks you for your help
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-20T01:38:21+00:00
- Post Title: How to decompress a new LZS format?

you will have to ask the Chinese guy
[viewtopic.php?f=10&t=6474](http://forum.xentax.com/viewtopic.php?f=10&t=6474)
