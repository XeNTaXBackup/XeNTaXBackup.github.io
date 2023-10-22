## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-16T03:40:27+00:00
- Post Title: Fate/Extra pak archives

I extracted the cpk archive using cpk_unpack and among some compressed archives I found some pak archives which were uncompressed (a lot of them had "RIFF WAVE" near the top)

The format is looks simple and should take some people only a couple minutes (just a table at the top followed by the data afterwards) but ya here are some samples:
[pak.7z](https://xentaxbackup.github.io/file/4899_pak.7z)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-12-16T16:56:29+00:00
- Post Title: Fate/Extra pak archives

```
get UNKNOWN short

for f = 0 < FILES
  get TMP long
  putarray 0 f TMP
next f

padding 16

for f = 0 < FILES
  getdstring NAME 64
  savepos POS
  getarray SIZE 0 f

  log NAME POS SIZE

  math POS += SIZE
  goto POS
next f

```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-16T20:55:25+00:00
- Post Title: Fate/Extra pak archives

Now I know how to use arrays lol
## Post #4
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-03-27T10:54:57+00:00
- Post Title: Fate/Extra pak archives

Someone decompressor\compressor or fix WRS script? 
Аll .cmp: [http://www120.zippyshare.com/v/o04JRKjc/file.html](http://www120.zippyshare.com/v/o04JRKjc/file.html)
000001.cmp (original) - [https://zenhax.com/download/file.php?mode=view&id=4339](https://zenhax.com/download/file.php?mode=view&id=4339)
000001.cmp (decompress) - [https://zenhax.com/download/file.php?mode=view&id=4338](https://zenhax.com/download/file.php?mode=view&id=4338)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-27T18:06:02+00:00
- Post Title: Fate/Extra pak archives

> Reply from makcar
>
> 000001.cmp (original) - https://zenhax.com/download/file.php?mode=view&id=4339
this bms script will decompress your sample  

```

comtype lzss0
idstring "IECP"
get ZSIZE asize
get SIZE long
savepos OFFSET
math ZSIZE - OFFSET
get NAME basename
string NAME + _decmp.cmp
clog NAME OFFSET ZSIZE SIZE

```
## Post #6
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-03-27T21:13:37+00:00
- Post Title: Fate/Extra pak archives

Thanks a lot AceWell! How to edit string "bla-bla-bla" for all files compression?

cmp_compressor.bms:
```

comtype lzss0
idstring "bla-bla-bla"
get ZSIZE asize
get SIZE long
savepos OFFSET
math ZSIZE - OFFSET
get NAME basename
string NAME + _decmp.cmp
clog NAME OFFSET ZSIZE SIZE
```
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-27T21:59:34+00:00
- Post Title: Fate/Extra pak archives

if you're sure they all use the same compression you could just replace that line with one of these  

```
get blablabla long
```

or 

```
goto 0x4
```

or 

```
getdstring blablabla 4
```

i hope i'm understanding what you mean
## Post #8
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-03-27T22:55:34+00:00
- Post Title: Fate/Extra pak archives

That's right?
[bat and bms.rar](https://xentaxbackup.github.io/file/14101_bat and bms.rar)
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-27T23:56:43+00:00
- Post Title: Fate/Extra pak archives

> Reply from makcar
>
> That's right?
i guess so, modding is not my area, but it looks okay.
