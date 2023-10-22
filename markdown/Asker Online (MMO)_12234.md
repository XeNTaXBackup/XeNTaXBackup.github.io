## Post #1
- Username: jimbojinbo
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-15T01:28:20+00:00
- Post Title: Asker Online (MMO)

Here is an extractor for this game.
Model Script [viewtopic.php?f=16&t=12244](http://forum.xentax.com/viewtopic.php?f=16&t=12244)
Website: [http://asker.pmang.com/](http://asker.pmang.com/)


to Download the game without an account
[https://www.sendspace.com/file/bxkl8l](https://www.sendspace.com/file/bxkl8l)
extract these folders to
C:\Neowiz\Pmang\
then run this from command line

```
"C:\Neowiz\Pmang\Launcher\launchern.exe" GiveMe3dModels QT 0 http://dl.pmang.com/asker/version.ini 368
```



```
# By chrrox
# Script for QuickBMS http://quickbms.aluigi.org

IDSTRING "VARC"
get VERSION short
get FILES long
get NTSIZE long
get UNK1 long
get UNK2 long
for i = 0 < FILES
	get NSIZE short
	get SIZE long
	get ZSIZE long
	get OFFSET long
	putarray 0 i NSIZE
	putarray 1 i SIZE
	putarray 2 i ZSIZE
	putarray 3 i OFFSET
next i
comtype inflate
for j = 0 < FILES
	getarray NSIZE  0 j
	getarray SIZE   1 j
	getarray ZSIZE  2 j
	getarray OFFSET 3 j
	encryption xor "\x35\xC1\xB6\x43\x36\xB0\xE6\x4B\x37\x4A\xC1\xD8\x34\xBC\xAD\x53\x36\x44\xB5\xBF\xBF\xCF\x37\x57\xC3\xD6\x37\xB5\xB5\x43\x35\xB0\xE6\x44\x36\x4B\xBC\xBA\x35\x53\x38\xBA\xB4\x42\xC3\xB6\x31\x43\x35\xC2\xF7\x43\x36\x4A\xC1\xDF\xC8\xC6\x37\x48\xB1\xE8\x37\x4B\x37\xBF\xF8\x57\x35\x4A\xC1\xD6\xC8\xB2\x38\xC0\xCE\x48\x34\x49\x37\xBE\xF7\x55\xBE\xE7\x35\xC3\xA2\x59\x37\x43\x36\x53\xBC\xB1\xB1\xE8\x37\xB0\xED\x4B\x34\x47\x34\xC0"
	filecrypt 1
	getdstring NAME NSIZE
	filecrypt ""
	encryption "" ""
	get NULL byte
	if ZSIZE == SIZE
		log NAME OFFSET SIZE
	else
		math OFFSET + 2
		math ZSIZE - 2
		clog NAME OFFSET ZSIZE SIZE
	endif
next j
```
## Post #2
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2017-02-25T05:16:05+00:00
- Post Title: Asker Online (MMO)

Did anyone download this game's client that they could upload? Apparently it's no longer available and was shut down.
## Post #3
- Username: zex4
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 23, 2019 3:54 am
- Post datetime: 2020-01-27T20:28:47+00:00
- Post Title: Asker Online (MMO)

yea i am searching for the client to 
it would be great if someone could upload it...
## Post #4
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2023-02-25T18:56:07+00:00
- Post Title: Asker Online (MMO)

Guess no one archived this game at all, what a sad way to be forgotten.
