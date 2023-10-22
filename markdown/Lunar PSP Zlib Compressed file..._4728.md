## Post #1
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-07-08T00:42:31+00:00
- Post Title: Lunar PSP Zlib Compressed file...

Well, this file is compressed with zlib, it starts at 16 but the header seems to be cuted out.

Can anyone help me out??

Thanks.!
[8.rar](https://xentaxbackup.github.io/file/3217_8.rar)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-08T01:12:11+00:00
- Post Title: Lunar PSP Zlib Compressed file...

here you go 
quickbms script

```
goto 0xA
get name string
savepos offset
goto -4
get size long
get zsize asize
math zsize - offset
math zsize - 8
comtype inflate
clog name offset zsize size
next i

```
## Post #3
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-07-08T13:40:42+00:00
- Post Title: Lunar PSP Zlib Compressed file...

> Reply from chrrox
>
> here you go 
quickbms script
Code: Select allfor i = 1 < 2
goto 0xA
get name string
savepos offset
goto -4
get size long
get zsize asize
math zsize - offset
math zsize - 8
comtype inflate
clog name offset zsize size
next i

Hey man, thanks, you are the man.

But i'm trying to add the function to one of my tools. Can you explain it in words?? thanks again.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-08T23:34:08+00:00
- Post Title: Lunar PSP Zlib Compressed file...

I just read the null terminated string that started at 0xA
then i save the position where the name ended as the start offset.
the last 8 bytes are not part of the compressed file.
the last 4 of those 8 bytes are the uncompressed file size.
so that gives us what we need to extract offset size and zip size
the size is the total size of the file - the start offset of the compressed block - 8 bytes at the end.
and the compression is lib with -15 window bit or inflate.
## Post #5
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-07-09T00:37:06+00:00
- Post Title: Lunar PSP Zlib Compressed file...

> Reply from chrrox
>
> I just read the null terminated string that started at 0xA
then i save the position where the name ended as the start offset.
the last 8 bytes are not part of the compressed file.
the last 4 of those 8 bytes are the uncompressed file size.
so that gives us what we need to extract offset size and zip size
the size is the total size of the file - the start offset of the compressed block - 8 bytes at the end.
and the compression is lib with -15 window bit or inflate.

Hey man, thanks.

Now i can translate the texts that were compressed.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-09T00:44:38+00:00
- Post Title: Lunar PSP Zlib Compressed file...

do you have a site where you release your tools / translations?
## Post #7
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-07-09T12:27:25+00:00
- Post Title: Lunar PSP Zlib Compressed file...

> Reply from chrrox
>
> do you have a site where you release your tools / translations?

Mainly i release them in the romhacking.trd.net , but some people puts them in the romhackers.org and romhacking.net.
[http://www.romhackers.org/modules/news/](http://www.romhackers.org/modules/news/)
[http://www.romhacking.trd.br/index.php?topic=7060.0](http://www.romhacking.trd.br/index.php?topic=7060.0)
Ps:They're in portuguese so guess you will need google translate.!
The lunar is still just a project, i'm not going to translate it, just creating the tools so the people in my team will be able to do so..(man 1.5 mb of texts is just too much for me...)
I think that only the 5 bytes at the end arent part of the compressed file...

Now i'm going to research the decompressed file... container i think...
