## Post #1
- Username: Lezard
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 23, 2016 9:31 pm
- Post datetime: 2016-04-23T15:36:24+00:00
- Post Title: [PC] Sangokushi 11 with PUK - Dialog Compression

Hi there, I'm working on the translation of this game and need help figuring out the compression used.

This game dialogs are stored in four ".s11" files and I'm attaching one of them here, whose header is as follows:
16 bytes = 4C 53 31 31 00 00 00 00 00 00 00 00 00 00 00 00 | LS11
256 bytes = ???
16 bytes = 00 08 0B 2D 00 08 0B 2D 00 00 01 20 00 00 00 00 | Compressed / Uncompressed sizes and unknown 01 20

I have a program that decompresses these files and it uses Zlib, but for some odd reason few last messages of the file won't show properly after decompression. I wonder if something is wrong with the decompression or if I should re-compress the files (the program I'm using doesn't have this feature). I'm attaching the decompressed file too.

I don't think this is of any help to you, but this is what the decompressed data looks like:
2 bytes = # of messages
4 bytes = reference to 1st message (note if a message is added all references must be increased by 4)
4 bytes = reference to 2nd message (= to previous reference + the length of previous message)
...
the messages themselves each ending with 05 05 05

Forget the attachment, use this link instead:
[http://ulozto.net/xQaYSpUi/msg-7z](http://ulozto.net/xQaYSpUi/msg-7z)

Hopefully one of you experts can help me out.
