## Post #1
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2019-03-19T05:11:38+00:00
- Post Title: [Fantasy Tennis] Need Help on item's icon

Hi everyone,

I suddenly missed the game called "Fantasy Tennis" which was closed for a long time.

What I want to do is to extract the game item's icon, but I have many problems with it.

First, I can extract until I found many .tex and .dat files in MESH or ITEM.res folder. (the example is below)

[](http://picture.in.th/id/aecac029152088a7704cb7f0e5439d7e)

For .tex file, I tried using specific program posted in one webboard that can convert .tex to .bmp, but what I got is this

[](http://picture.in.th/id/506cd8af8d2ac1a2a207cbb92c12950c)

It's kind of like an icon that I want but extended and full of unwanted line.


and for .dat files, I can't even open them. (When I opened with notepad, it showed me alien wording)

Can anyone help me with this?

------------------------------------------------------------------------------
PS. Here is the link to download the file and program that I used.
[https://drive.google.com/open?id=1gdnge ... XXgxwff5YN](https://drive.google.com/open?id=1gdnge1EteGBWVYvUhR1pbTXXgxwff5YN)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-19T06:23:36+00:00
- Post Title: [Fantasy Tennis] Need Help on item's icon

we'll need to see some samples for examination.   
but i'll assume this game is "Fantasy Tennis by Alaplaya"
if so, the tex files are dds with tex extension but with xored header.
this bms script will fix those tex files right up and make them dds.  

```

idstring "\xBB\xBB\xAC\xDF"
get SIZE asize
math SIZE - 0x80
get NAME basename
string NAME + .dds
append
filexor "0xff"
log NAME 0x0 0x80
filexor ""
log NAME 0x80 SIZE
append
```
## Post #3
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2019-03-19T08:59:12+00:00
- Post Title: [Fantasy Tennis] Need Help on item's icon

> Reply from Acewell ↑Tue Mar 19, 2019 2:23 pm at Tue Mar 19, 2019 2:23 pm
>
> 
we'll need to see some samples for examination.   
but i'll assume this game is "Fantasy Tennis by Alaplaya"
if so, the tex files are dds with tex extension but with xored header.
this bms script will fix those tex files right up and make them dds.  
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

idstring "\xBB\xBB\xAC\xDF"
get SIZE asize
math SIZE - 0x80
get NAME basename
string NAME + .dds
append
filexor "0xff"
log NAME 0x0 0x80
filexor ""
log NAME 0x80 SIZE
append

Yes it is, I also just upload the file examples.
So I have to download Quickbms right?
## Post #4
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2019-03-19T09:11:52+00:00
- Post Title: [Fantasy Tennis] Need Help on item's icon

Thank you very much, I can finally made it!
