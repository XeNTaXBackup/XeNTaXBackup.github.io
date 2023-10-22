## Post #1
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2012-11-20T02:26:27+00:00
- Post Title: need help for  convert

hello
need help how to convert

17B7513C6B2B66BF4260253E3EE8593C
764F6EBFF38E133EDAAC7A3C931864BF

to 

v 0.012800 -0.899100 0.161500
v 0.013300 -0.930900 0.144100



Converted.png (36.89 KiB) Viewed 157 times



any help is appreciated thanks
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-20T02:42:36+00:00
- Post Title: need help for  convert

How do you know what it represents?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-20T02:43:48+00:00
- Post Title: need help for  convert

need more information.
#1 what game is it?
#2 what are you trying to convert it with?
#3 what have you done so far?
## Post #4
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2012-11-20T03:29:04+00:00
- Post Title: need help for  convert

How do you know what it represents?



convert2.png (19.3 KiB) Viewed 151 times



need more information.
#1 what game is it?
#2 what are you trying to convert it with?
#3 what have you done so far?

#1 Game is Tales Of Pirate  .lgo Format
#2 I draw the vertices and face
#3 very little just what helped me
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-20T16:06:08+00:00
- Post Title: need help for  convert

I made a converter lgo to obj: [http://www.uploadmb.com/dw.php?id=1353426997](http://www.uploadmb.com/dw.php?id=1353426997)

Only tested with items: 0092990019.lgo and 0092990022.lgo

I also tried to code a bms script but didn't find a simple IEEE754 to float conversion for it.

(And I'm not very motivated to translate my I3E750_to_float() function to quickbms.)
## Post #6
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2012-11-20T17:15:52+00:00
- Post Title: need help for  convert

> Reply from shakotay2
>
> I made a converter lgo to obj: http://www.uploadmb.com/dw.php?id=1353426997

Only tested with items: 0092990019.lgo and 0092990022.lgo

I also tried to code a bms script but didn't find a simple IEEE754 to float conversion for it.

(And I'm not very motivated to translate my I3E750_to_float() function to quickbms.)

good job shakotay
but not all begin 0X8fc some begin 0X518

common to all the schemes comes before this code



1234.png (3.5 KiB) Viewed 139 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-20T20:13:51+00:00
- Post Title: need help for  convert

> Reply from wolfen
>
> common to all the schemes comes before this codeNope; imho the pattern FF 7x 00 does not help; or can you assure that it's the 93 th finding in the "0x518 files"?

edit: you're partially right. The pattern is 01 00 05 00 FF (7x 00).

obsolete:
I modified the converter: [http://www.uploadmb.com/dw.php?id=1353441774](http://www.uploadmb.com/dw.php?id=1353441774)

You can enter now the verts start address  (if it doesn't work with the 0x518 files, you might send me a sample via PM).
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-20T22:53:10+00:00
- Post Title: need help for  convert

I think someone doing a private server or something sent me source code for the engine some time ago...
[TalesOfPirates_LGO raw.7z](https://xentaxbackup.github.io/file/6016_TalesOfPirates_LGO raw.7z)
## Post #9
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2012-11-21T00:49:56+00:00
- Post Title: need help for  convert

> Reply from finale00
>
> I think someone doing a private server or something sent me source code for the engine some time ago...
finale how use this codes
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-21T03:05:05+00:00
- Post Title: need help for  convert

Reference only.
## Post #11
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2012-11-21T03:16:39+00:00
- Post Title: need help for  convert

but what is its use
TalesOfPirates_LGO raw

These codes are from user kLabMouse
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-22T03:16:35+00:00
- Post Title: need help for  convert

I don't know what it's used for. I'm assuming it's reversed from the engine or something.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-22T09:48:16+00:00
- Post Title: need help for  convert

> Reply from wolfen
>
> but what is its useAs finale00 said it can be used as a guidance. Knowing the structure you can progam an exporter assumed you are capable in some programming language.

Here's my last approach I hope: should work with most lgos:
[http://www.uploadmb.com/dw.php?id=1353576988](http://www.uploadmb.com/dw.php?id=1353576988)
## Post #14
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2012-11-22T15:57:36+00:00
- Post Title: need help for  convert

Tanks Master
