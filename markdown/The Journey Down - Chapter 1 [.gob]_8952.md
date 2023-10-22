## Post #1
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2012-05-19T14:42:16+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

All resources in one file - data.gob (615mb)


What format is this and how to unpack it?

Thanks in advance.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-05-19T19:42:25+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

```
get FILE_OFF long
do
  get NAMESIZE short
  getdstring FILE_NAME NAMESIZE
  get START_POS long
  get FILE_SIZE long
  get UNK byte
  set FNX string FILE_NAME
  string FNX += "."
  string FNX += UNK
  log FNX START_POS FILE_SIZE
  savepos INFO_OFF
while INFO_OFF < FILE_OFF

```
## Post #3
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2012-05-20T05:49:29+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

bacter, Thanks!
## Post #4
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2012-06-07T22:52:19+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

Hi thanx for bms script, but there are no real extension and some files seem unreadable, looks on attachement.
[Nouveau dossier.rar](https://xentaxbackup.github.io/file/5485_Nouveau dossier.rar)
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-06-09T05:05:15+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

The files are compressed with zlib. Here's a simple QuickBMS script for decompressing:

```
goto 0 0 SEEK_END
savepos FILESIZE 0
clog "outfile" 0 FILESIZE 10000000

```
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-09T07:59:35+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

when you want to decompress a raw zlib/deflate for which you don't know the uncompressed size you would prefer to use unzip_dynamic:

```
get SIZE asize
clog "output.dat" 0 SIZE SIZE
```
it's easier and works at 100% automatically recognizing zlib or deflated data :)
## Post #7
- Username: gyeben
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 19, 2011 10:43 pm
- Post datetime: 2013-01-17T22:47:14+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

Hi!
I could successfully extract all files from data.gob, but reimporting doesn't work for me.
Is it possible to reimport modified files into the data.gob file?
## Post #8
- Username: Pakolmo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 25, 2017 10:35 am
- Post datetime: 2017-05-17T17:42:25+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

Hi!

Since the last update of the game from march. If I reimport the gob file, the game doesn't start.

Can someone check the script?

Thanks!
## Post #9
- Username: cacarasa
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Oct 04, 2017 12:08 am
- Post datetime: 2019-01-09T20:48:18+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

> Reply from aluigi
>
> when you want to decompress a raw zlib/deflate for which you don't know the uncompressed size you would prefer to use unzip_dynamic:
Code: Select allcomtype unzip_dynamic
get SIZE asize
clog "output.dat" 0 SIZE SIZEit's easier and works at 100% automatically recognizing zlib or deflated data

Thank you it worked, but how do I compress the file again?
## Post #10
- Username: walas74
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 10, 2019 7:41 am
- Post datetime: 2019-01-09T23:45:24+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

Hi cacarasa. 

We intend to translate The Journey Down at Guias Pat & Asperet as it was the winner of our annual poll for adventure game to be translated. 

Beginning of translation's estimate date: July 2019.
## Post #11
- Username: cacarasa
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Oct 04, 2017 12:08 am
- Post datetime: 2019-01-10T20:23:32+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

ok walas74... but how do you compress the texts again?

thanks in advance
## Post #12
- Username: walas74
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 10, 2019 7:41 am
- Post datetime: 2019-01-10T20:58:48+00:00
- Post Title: The Journey Down - Chapter 1 [.gob]

I don't know yet, but my friend ghylard from Planete Aventure has translated the game into French so he will assist me when I begin the translation.
