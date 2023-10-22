## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-03-14T21:27:18+00:00
- Post Title: Order of Magic Online

Hey guys   Need help with PAK file's.. Example file attached.

Thanks advance 
[db.rar](https://xentaxbackup.github.io/file/4066_db.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-15T11:23:04+00:00
- Post Title: Order of Magic Online

the initial part is simple, the rest instead looks like a sequence of compressed chunks of an unknown algorithm or encrypted+zlib
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-03T17:38:41+00:00
- Post Title: Order of Magic Online

Oh T_T necroposting   

here algo

```

void Decrypt(int a1, int a2, int a3)
{
  int v4;
  unsigned __int8 i;
  int v6; 
  char v7;

  v4 = 0;
  for ( i = 115; v4 < a2; *(_BYTE *)v6 = i ^ v7 )
  {
    v6 = v4 + a3;
    i = (i >> 7) + 2 * i;
    v7 = *(_BYTE *)(v4 + a3 + a1 - a3) ^ (v4 + v4 / 0xFFu);
    ++v4;
  }
}
```


a1 - buffer
a2 - size
a3 - destbuffer

attached source for testing 
[OMPak_Test_Decrypting.rar](https://xentaxbackup.github.io/file/5536_OMPak_Test_Decrypting.rar)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-03T18:15:44+00:00
- Post Title: Order of Magic Online

*full script available in the next posts*
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-03T18:26:41+00:00
- Post Title: Order of Magic Online

Yep cuted chunks for test from pak file.

db.pak

```
- open input file D:\Order of Magic\Data\db.pak
- open script D:\OM.bms
- set output folder D:\EXTTEST\

  offset   filesize   filename
------------------------------

Error: incomplete input file number 0, can't read 423487 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted

Press RETURN to quit
```


for all other paks

```
- select the input archives/files to extract, type "" for whole folder and subfo
lders
- select the output folder where extracting the files
- open input file D:\Order of Magic\Data\shaders.pak
- open script D:\OM.bms
- set output folder D:\EXTTEST\

  offset   filesize   filename
------------------------------

- the script has requested to load a function from the dll
  MEMORY_FILE3
  do you want to continue (y/N)? y
- library MEMORY_FILE3 loaded at address 042D0000
- function found at offset 042D0000
```


crashed and VS tiggered JIT Debugger.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-04T11:30:42+00:00
- Post Title: Order of Magic Online

I have rechecked db.pak but the index table doesn't leave doubts: OFFSET followed by SIZE.
so my only hypothesis at the moment is that the content of the archive is a divided in compressed chunks (so just the archive and not the single files as I thought).
I'm trying to make some tests.

oh I forgot "putvarchr MEMORY_FILE2 SIZE 0" in my script
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-04T12:02:19+00:00
- Post Title: Order of Magic Online

job done:
[http://aluigi.org/papers/bms/order_magic_online.bms](http://aluigi.org/papers/bms/order_magic_online.bms)
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-04T14:47:39+00:00
- Post Title: Order of Magic Online

Hehe good job 

for db work fine. for all other ->

```
  MEMORY_FILE3
  do you want to continue (y/N)? y
- library MEMORY_FILE3 loaded at address 0B6E0000
- function found at offset 0B6E0000

Error: the compressed LZO input is wrong or incomplete (-6)

Error: there is an error with the decompression
       the returned output size is negative (-1)
```
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-04T15:21:51+00:00
- Post Title: Order of Magic Online

can you send me one of these files?
I guess I swapped the ZIP field with another or maybe there is something else to do
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-04T18:20:48+00:00
- Post Title: Order of Magic Online

fixed, was exactly that thing: ZIP field and DUMMY
oh well, I had 50/50 of success :)
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-04T18:35:33+00:00
- Post Title: Order of Magic Online

So new script for all pak's work fine. Thanks
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-04T20:44:16+00:00
- Post Title: Order of Magic Online

this is the game?
[http://play.ordenmagii.ru/index.html](http://play.ordenmagii.ru/index.html)
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-04T22:16:03+00:00
- Post Title: Order of Magic Online

Yep
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-04T23:24:10+00:00
- Post Title: Order of Magic Online

can you make this file not use a memory file luigi?
it wants over 1gb of free memory to work with on one file.
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-05T07:17:48+00:00
- Post Title: Order of Magic Online

I have fixed the original script so that now it's a lot faster and uses less resources (I forgot the classical "putvarchr MEMORY_FILE4 TMP 0").

if you want the temporary file solution:
[http://aluigi.org/papers/bms/order_magi ... _noram.bms](http://aluigi.org/papers/bms/order_magic_online_noram.bms)
