## Post #1
- Username: 3ps3
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 19, 2013 6:38 am
- Post datetime: 2013-07-22T08:51:59+00:00
- Post Title: Bioshock Infinite translate - PS3

Hi
I need text files in Bioshock Infinite
How extract and repack COALESCED_INT.BIN ?
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-07-22T09:48:59+00:00
- Post Title: Bioshock Infinite translate - PS3

You can't it is encrypted.... I could not found anyone who can help at all
## Post #3
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-01-22T20:40:09+00:00
- Post Title: Bioshock Infinite translate - PS3

Too late, but maybe someone will find it useful. Here is my tool to convert coalesced binary (PS3 and maybe X360) to normal INI-files.
[http://www.sendspace.com/file/dsdp3n](http://www.sendspace.com/file/dsdp3n)

The format itself is not encrypted but compressed using Huffman's compression algorithm. Main COALESCED_*.BIN contains a code table for all localization files of the same language. A tool above creates a very useful log file so anyone can see what data are stored there and someone with skills can write an encoder for it.
## Post #4
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-03-24T20:35:55+00:00
- Post Title: Bioshock Infinite translate - PS3

Here is a tool to convert coalesced files to .ini and back:
[http://www.sendspace.com/file/qkb307](http://www.sendspace.com/file/qkb307)
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-03-25T07:14:53+00:00
- Post Title: Bioshock Infinite translate - PS3

> Reply from flatz
>
> Here is a tool to convert coalesced files to .ini and back:
http://www.sendspace.com/file/qkb307

Thank you does it also work for X360?

EDIT : Tested on X360 and so far unpack works ok  thx again i will test pack also in game
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-03-25T07:34:33+00:00
- Post Title: Bioshock Infinite translate - PS3

> Reply from flatz
>
> Here is a tool to convert coalesced files to .ini and back:
http://www.sendspace.com/file/qkb307

Tool work but only for coalesced.bin and how to repack all other files like S_Fink3_P_INT.bin or S_BW_P_INT.bin?

Thank you
## Post #7
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-03-25T08:08:57+00:00
- Post Title: Bioshock Infinite translate - PS3

> Reply from michalss
>
> Tool work but only for coalesced.bin and how to repack all other files like S_Fink3_P_INT.bin or S_BW_P_INT.bin?
It works for all files, just place all .bin files into the same directory and specify this directory as an argument.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-03-25T09:22:41+00:00
- Post Title: Bioshock Infinite translate - PS3

> Reply from flatz
>
> michalss wrote:Tool work but only for coalesced.bin and how to repack all other files like S_Fink3_P_INT.bin or S_BW_P_INT.bin?
It works for all files, just place all .bin files into the same directory and specify this directory as an argument.

Ahh ok thx ill test it
## Post #9
- Username: javurek91
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Feb 09, 2014 9:29 pm
- Post datetime: 2014-04-21T20:45:17+00:00
- Post Title: Bioshock Infinite translate - PS3

Hello, i need advice about pack the files back to *.BIN file. What about the listing file. I don't know what it's meant with that? In which format must be this listing file and what must be in this file? Thanks for any help
## Post #10
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2016-06-09T15:58:16+00:00
- Post Title: Bioshock Infinite translate - PS3

Please reupload flatz tools  
or how i extract coalested_int.bin ?? tnx
