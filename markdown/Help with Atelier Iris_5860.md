## Post #1
- Username: VincentValentine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 16, 2011 10:27 am
- Post datetime: 2011-01-21T00:00:42+00:00
- Post Title: Help with Atelier Iris

Hello.
I'm trying to extract all files are in RPK.BIN of Atelier Iris game to translate this game to Spanish language. I using rpkextract.rb of Ar Tonelico 2, but i didn't extract any file. The problem are the offset of the RPK.BIN, because i dont find the offset of the files to extract. I need help for this.

PD: Sorry for my english, I undertand very well, but i dont write correctly in english.
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2011-01-23T06:09:43+00:00
- Post Title: Help with Atelier Iris

From RPK files I have seen, the offset records are in the PS2 executable file.  Each record is 0xC bytes in length with a format like:
0x00 - 0x03: Unknown
0x04 - 0x07: Offset/0x800
0x08 - 0x0B: Size

So find some known file types and search by offset or length values to find the table.
## Post #3
- Username: VincentValentine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 16, 2011 10:27 am
- Post datetime: 2011-01-23T22:52:19+00:00
- Post Title: Help with Atelier Iris

When you are saying to find the table, the table is the list of files are in the RPK.BIN?. Because I find in SLUS_211.13 directory of al files are in RPK.BIN (see image)[http://img546.imageshack.us/i/atelieriris.jpg](http://img546.imageshack.us/i/atelieriris.jpg). But the rpkextract.rb have 2 variables:
names_a
entries_a
In "names_a" I write 00B528D0, the offset is the are mark on the image post before, but in the entries_a i dont have idea where write. I have Ar Tonelico 2, and I see the numbers they have in the original rpkextract.rb, but i dont see anything. Sorry for everething, but I'm a noob in this world, and I'm learning slowly with practice and reading many information.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-06-20T15:27:43+00:00
- Post Title: Help with Atelier Iris

> I using rpkextract.rb of Ar Tonelico 2

@VincentValentine, can you upload rpkextract.rb file? I need it for someone.
