## Post #1
- Username: Dreyar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 29, 2013 11:23 pm
- Post datetime: 2021-06-30T17:24:13+00:00
- Post Title: New World .datasheet file format

Hi !

I have troubles understanding these files containing tables of data. So far I understood this :

```
@offset 0x38	4B	header size
@offset 0x44	4B	number of columns
@offset 0x48	4B	number of lines
@offset 0x5c	start of the header data

```

The header data contains offsets relative to the beginning of the data block (@offset 0x3c + header size).

```
4B	offset of what I believe is the name of the table

Then the columns' title are represented on 12B as follow :
4B	1 or 2, I believe that 2 means that the column is not used
4B	some kind of ID
4B	offset of the end of text, the beginning is the previous offset

The last entry is only on 8B because there's no ID :
4B	1 or 2
4B	last offset

```

Directly after are the offsets of the actual cell data and that's what I don't understand.
On a very easy file where all the columns are used (1) the data is indicated as follows :
4B	start offset
4B	end offset

But things get more complicated when some columns are unset. I give you some of the smallest files if you're interested in making sense of these.  

[https://mega.nz/file/4XxijCTJ#za049-ZPh ... Kpl0X4pI7M](https://mega.nz/file/4XxijCTJ#za049-ZPhni5UHjuJrAbFob3eiDWPeyNCKpl0X4pI7M)
## Post #2
- Username: periwins
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 26, 2021 6:13 pm
- Post datetime: 2021-07-26T10:18:57+00:00
- Post Title: New World .datasheet file format

I found .datasheet files but I don't know how to interpret or read them, could you tell me how you did it, thanks
