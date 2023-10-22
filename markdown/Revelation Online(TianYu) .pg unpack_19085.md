## Post #1
- Username: vampir9763
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 21, 2018 1:34 pm
- Post datetime: 2018-11-19T04:35:05+00:00
- Post Title: Revelation Online(TianYu) .pg unpack

I apologize in advance for my bad english.
Hello!Found on the Internet ROSPG (Revelation Online pg unpacker), but it does not work for the latest version of the client. Interested in such a question, how to unpack the game archive with the extension .pg? I did not find the source code for the old unpacker on the network. Interested in any suggestions or any information on this issue. Thanks in advance for your help.
## Post #2
- Username: vampir9763
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 21, 2018 1:34 pm
- Post datetime: 2018-11-19T12:53:33+00:00
- Post Title: Revelation Online(TianYu) .pg unpack

I'm only interested in one entities.pg file. If someone managed to unpack it, I will be glad to any information, I am interested in the very contents of this file.
## Post #3
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2022-04-28T05:49:21+00:00
- Post Title: Revelation Online(TianYu) .pg unpack

Without any samples, nobody can help you :/
## Post #4
- Username: vampir9763
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 21, 2018 1:34 pm
- Post datetime: 2022-04-28T06:01:52+00:00
- Post Title: Revelation Online(TianYu) .pg unpack

Hey, decided to revisit the issue.
What I managed to find: the beginning of the files looks like this (highlighted in green is what is common in all files).
As far as I know a modified Lz4 is used: ("It seems to be a modified LZ4 with xor to 0xD7 + 0x1129 + 0x14" - as Ekey said).
I've been trying to make an unpacker for several days, but everything is empty - I can't even calculate the offset. Please help me, I'm a noob
Update files for the game are packed with BZip2
[Снимок.PNG](https://xentaxbackup.github.io/file/22159_Снимок.PNG)
## Post #5
- Username: vampir9763
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 21, 2018 1:34 pm
- Post datetime: 2022-04-28T06:02:57+00:00
- Post Title: Revelation Online(TianYu) .pg unpack

attached one of the resource files for example
[mi.7z](https://xentaxbackup.github.io/file/22160_mi.7z)
## Post #6
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-05-01T09:23:44+00:00
- Post Title: Revelation Online(TianYu) .pg unpack

Go [there](https://aluigi.altervista.org/quickbms.htm) and download QuickBMS with 1gab_2gab_bag.bms script for it.
Modify quickbms.bat as needed and run it ... then Xor every file with 0xd7.
