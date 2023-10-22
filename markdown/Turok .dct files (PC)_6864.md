## Post #1
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-28T03:54:55+00:00
- Post Title: Turok *.dct files (PC)

[Solved]


 Turok.7z
(185.05 KiB) Downloaded 77 times
## Post #2
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-08-16T09:34:25+00:00
- Post Title: Turok *.dct files (PC)

I create structure for these files, but I´m not a programmer.

```
int (4096)
int unknown
int seven
int numberofrecords (I'm not sure)
int64 nul1
int64 nul2
{
int HASH (HASH of first record)
int Pos (+ position in file),(Pos of first record)
}
char Zero[40]
for x = 8 < numberofrecords
{
int HASH
int Pos (+ position in file)
}

```


I create a template for 010 Editor. Template is in attachment.
[Turokdct.rar](https://xentaxbackup.github.io/file/4635_Turokdct.rar)
## Post #3
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-08-30T01:02:54+00:00
- Post Title: Turok *.dct files (PC)

[Solved]
