## Post #1
- Username: dijotp
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 20, 2009 9:47 pm
- Post datetime: 2014-06-01T12:56:05+00:00
- Post Title: Tropico 2 Texts File

Hi everyone.

I would like to translate Tropico 2 but I can not edit the texts.

I have been analyzing the file with a hex editor, but I could not understand much.

I would appreciate if you could help me.

The only thing I noticed was:

Header contains 16 bytes.
First 4 bytes is the file ID (75 B1 C0 BA).
Third 4 bytes is pointer with data in file.
Fourth 4 bytes is size file.

RAR file with file in multiple languages: [https://mega.co.nz/#!44YXHCQZ!B0_iW7ID_ ... KqLbqWnZe4](https://mega.co.nz/#!44YXHCQZ!B0_iW7ID_PsQg8QcaExYxrixcpajLHAlKKqLbqWnZe4)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-11-08T19:49:00+00:00
- Post Title: Tropico 2 Texts File

hello

i have spent time looking at this format. i can parse the entire thing but haven't finished writing up the code for unpacking to a format you could edit for translations.

overview;

16 byte header (magic, unknown, footer block, size)
backwards recursive resource structures - starting from the footer block) - offsets are signed
strings are stored in 2 ways; the blob after the header, and inlined (if < 4 characters)
also this format includes more than 1 language for special "nati" entries

pm me if you want to continue my work (c# source)

edit

i've dumped the languages here:
[https://mega.co.nz/#!F9Yn0ACB!kglwD7jev ... qhqTX5WILQ](https://mega.co.nz/#!F9Yn0ACB!kglwD7jevW8hesyO9mey1deh3ZNCjWoiDqhqTX5WILQ)

beware the encoding of the output and string data is different (utf8)
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-09T19:18:53+00:00
- Post Title: Tropico 2 Texts File

hmm i was thinking abut there is something allrady.... Just cannot remeber where i have seen it
