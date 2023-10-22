## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-18T03:39:08+00:00
- Post Title: How does quickbms re-pack work?

Been wondering for awhile now: why does the size of the modified file have to be no greater than the original?

I mean, when you consider a fairly simplistic archive format (which is not too uncommon I think.)

```
get FILES long
for i = 0 < FILES
   get SIZE long
   get OFFSET long
   getdstring NAME 32
   log NAME OFFSET SIZE
next i

```


it doesn't seem too difficult to figure out how to pack a set of files given the structure of the archive, even if you have completely new files.

If I had some archive format like the above, would I be able to just toss in new files and have quickbms pack them all up?

EDIT: on second thought, it doesn't actually say "repack" but instead "re-import", so maybe it is a different concept.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-18T09:00:33+00:00
- Post Title: How does quickbms re-pack work?

you "EDIT" answers your question.
it's not a repacking feature.

in reimporting you take the original archive and simply replaces the original files with the modified one:

```
|       |      |
|       |      other data
|       file
other data

so the new file can be OOOOOOO long or less
```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-18T17:32:57+00:00
- Post Title: How does quickbms re-pack work?

I think of mex script as some sort of functional language: you just specify some commands that outline the format and then the interpreter goes ahead and does whatever it needs.

Or am I misunderstanding mex script? Lol
Is it possible to write re-packers if you're given a bms script?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-19T06:11:16+00:00
- Post Title: How does quickbms re-pack work?

the original mexscript is most command oriented.
in quickbms I have added a sort of compatibility with structure definitions where things like "char test[10]" get automatically interpreted as "getdstring test 10" leaving only the non-Get commands necessary to be specified completely.

for writing a real rebuilder/repacker you must know all the fields of the archive while in extraction you can just ignore them and it makes the difference when you must calculate a crc or adding fields with unkonwn values.
it can be easy for simple archives but for most of them it's a good wasting of time, for sure more than the seconds or minutes necessary for writing a script.

in short:
- extraction and reinjection is a joke to do with a script language like bms
- rebuilding/repacking is another story and usually needs the writing of a stand-alone tool
