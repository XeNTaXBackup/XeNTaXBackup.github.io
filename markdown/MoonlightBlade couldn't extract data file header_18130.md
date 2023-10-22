## Post #1
- Username: duanduan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 08, 2018 5:57 pm
- Post datetime: 2018-05-23T06:50:31+00:00
- Post Title: "MoonlightBlade" couldn't extract data file header

Dear friends, this could be an easy task. I could even get some from the exe file, but I cannot do it in a systematic way.

---
The following sfc file in game "Moonlight Blade" contains table-like data of the game.
[https://mega.nz/#!IV4yHAZB!u4zdnBV5i8YM ... efWTU2QnU4](https://mega.nz/#!IV4yHAZB!u4zdnBV5i8YM8Pb9GGlAQg68Sb262_hFyefWTU2QnU4)

Using this quickbms [script](http://aluigi.altervista.org/bms/qq_sfc.bms) can extract the tablebin.sfc file into many single table files.
one sample I've extracted:
[https://mega.nz/#!UJJSlQAA!vZGSaabC-PXP ... RR81paPya8](https://mega.nz/#!UJJSlQAA!vZGSaabC-PXPLzK-029pQ2MydtXEuWVIyRR81paPya8)

I've written a simple python script to extract the bin file, the structure is quite simple so I could guess out it, just a bunch of binary data. Strings are start with one or two bytes that is the length in binary.
What I'm wondering is, how to extract the header of these tables instead of just columns of numbers and strings. I've found the headers are in the main exe file, and I could manually search and guess each header.
the following is the exe file.
[https://mega.nz/#!8V5xDLib!g7Qjg98OTNDW ... hviJbIVxlM](https://mega.nz/#!8V5xDLib!g7Qjg98OTNDWXkxfo1c7XivpUMdFfu7ZmhviJbIVxlM)

For example, We can use  'grep' command find out the table file contains "ItemTable", and search the string in the exe, I could get a bunch of header names in "Hungarian notation", such as szName, mSize etc.
So what I need is to extract the headers with datatype from the exe, it seems many tables have nested structure which is not so easy guessing. A script would be better!
Sorry for my bad english if I didn't represent my need well.
## Post #2
- Username: duanduan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 08, 2018 5:57 pm
- Post datetime: 2018-10-01T10:23:49+00:00
- Post Title: "MoonlightBlade" couldn't extract data file header

Could anyone help me please, it could be easy. I could even guess some from the exe file, but no systematic way to do it.
