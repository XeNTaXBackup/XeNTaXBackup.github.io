## Post #1
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-06-29T21:12:29+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Hi. 

Did anyone know if there's a wa way to unpack\pack an.oppc archive from Darksiders: Wrath of War?

I think that the archives are the same as the Warhammer 40,000k: Space Marine, but i'm not so sure.

If anyone needs a sample file, just write me PM
## Post #2
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-06-30T15:35:38+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

*bump*
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-01T09:53:37+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Look [here](http://forum.xentax.com/viewtopic.php?f=10&t=5147&hilit=OBPK)
## Post #4
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-07-01T12:19:30+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Ekey, i know this thread but i forgotten to say that i'm talking about the PC version of the game and this thread is useless.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-01T13:11:32+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

the easiest thing you can try is removing the "endian big" command from the script.
if you are lucky it may work
## Post #6
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-07-01T14:16:22+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

> Reply from aluigi
>
> the easiest thing you can try is removing the "endian big" command from the script.
if you are lucky it may work

I have tried now and it's not working.  Maybe there the format is not the same as the PC version (i mean that script for the PS3 version) or the script is not finished. 

So, is there really a way to unpack\repack the .oppc archives or im completely lost
## Post #7
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-07-04T09:29:24+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Is anyone interested in this game or no one knows how to "hack" the .oppc format?

I really need a way to unpack few .oppc archives (and repack them), but im a noobie (i mean that i don't understand from programming and that's why i have created this thread, if there is anyone who can help out)
## Post #8
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2012-07-04T10:58:36+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Hey,
maybe you upload a small samplefile, so that we can take a look at it?
## Post #9
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-07-04T13:37:20+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

pivke, i can't post a link here because the new rules, but anyone who wants to look at the .oppc archives just can PM me so i can send a link.

By the way, pivke, i have send you a link - read your PM
## Post #10
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-07-07T10:58:34+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Did anyone is interested or no?
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-07T12:30:24+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Weekends, relax
## Post #12
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-07-11T11:27:13+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Well, here are one sample file inside the .rar archive in case "someone" want to do something  
[ui_icons_small.rar](https://xentaxbackup.github.io/file/5568_ui_icons_small.rar)
## Post #13
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-07-28T14:24:35+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

So, nothing...

*bump*
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-05-02T12:53:11+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

Hi guys! I want to bump this thread. I really would like to extract content from .oppc archives. Game Warhammer: Space Marine using same format (newer version of it I guess) here's specs for Space Marine .oppc, I'm sure they didn't change much for Darksiders

```
OPPC File Format
================
Version: 0.1.0
Author: Santos
================

------
HEADER
------

CHAR[4] 	signature (OBPK)
UINT8		flag? (0)
UINT32		major version? (10)
UINT32		minor version? (0)
UINT32		num files
UINT32		? (8-53)
UINT32		header size (337)
UINT32		index size
UINT32		data size (uncompressed)
UINT32		? (0)
UINT32		? (0)
UINT32		? (10000)
UINT32		? (50000)
DATA[288]	?

-----
INDEX
-----

// Unknowns

UINT32		num unknowns
FOR (num unknowns) DO
	UINT32	count
	FOR (count) DO
		UINT32 ?
UINT32		num strings


// Strings

FOR (num strings) DO
	STRING	string
UINT32		num types

// Types

FOR (num types) DO
	DATA[8]		type id
	UINT32		num entries

// Entries

FOR (num types) DO
	FOR (type -> num entries) DO
		STRING		name
		STRING  	dir
		UINT32  	size
		FLOAT		? (-1,0,n)
		UINT32  	size
		UINT32  	? (0)
		UINT32  	? (0)
		UINT8		enum (4, 7, 8, 9)
		DATA[enum] 	?
// Padding

DATA[N}		padding (00 up to index size)

----
DATA
----

UINT32		uncompressed data size
DATA[N]		compressed data (to end of file)

```


Here's also sample .opp c+ sorce for the .oppc extraction tool
[https://www.mediafire.com/?riuxx51o61zt476](https://www.mediafire.com/?riuxx51o61zt476)
Thanks in advance for any help
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-06T11:34:48+00:00
- Post Title: PC < Darksiders: Wrath of War .oppc archives

The bms script of WRS which Ekey pointed to is the key.

Guess you don't need it any more but here's the modified script for oppc files:

```

## Header

idstring "OBPK"
getdstring UNKNOWN 14
get NSTRUCTPOINTER long # >= 30
get DATAPOINTER long    # next 4096 block - NSTRUCTPOINTER
print "NSTRUCTPOINTER %NSTRUCTPOINTER%, DATAPOINTER %DATAPOINTER%"

## EStruct ( count may be zero)

get ESTRUCTCOUNT long

for i = 0 < ESTRUCTCOUNT
  getdstring UNKNOWN 8
  get NAMELEN long
  getdstring NAME NAMELEN
  print "%i%: %NAME% (%NAMELEN%)"
next i

## NStruct
# goto NSTRUCTPOINTER
print "***  Nstruct ***"
get NSTRUCTCOUNT long
print "NSTRUCTCOUNT= %NSTRUCTCOUNT%"
for i = 0 < NSTRUCTCOUNT
  getdstring UNKNOWN 8
  get NAMELEN long
  getdstring NAME NAMELEN
  print "%i%: %NAME% (%NAMELEN%)"
next i

print "***  Nstruct 2 ***"
get unk_offs long
get NSTRUCTCOUNT2 long
print "NSTRUCTCOUNT2= %NSTRUCTCOUNT2%"
for i = 0 < NSTRUCTCOUNT2
  getdstring UNKNOWN 8
  get NAMELEN long
  getdstring NAME NAMELEN
  print "%i%: %NAME% (%NAMELEN%)"
next i


## ZLib data chunks

savepos LASTPOS
math DATASTART = DATAPOINTER
math DATASTART += NSTRUCTPOINTER
goto DATASTART
print "DATASTART: %DATASTART%"

get SIZE long
savepos POS
get ZSIZE asize
math ZSIZE -= POS
print "cpr size: %ZSIZE% size %size%"

# the oppc files should be small enough to make this ok
clog MEMORY_FILE POS ZSIZE SIZE

Log "bunchOfFiles.bin" 0 size MEMORY_FILE ;

```

As you may see I didn't bother splitting up the files. Starting points in the extracted .bin should be the (file?) names logged by the script. But for ui_icons_small.oppc there aren't any contained in bunchOfFiles.bin - so splitting it up the  before the 68 "DDS" strings does the trick (see attachment).

I checked these files:
ui_icons_small.oppc
AbyssalHorse01.oppc, cpr size: 775802 size 1019952
angel_fallen.oppc, cpr size: 1430920 -> size 2237271

Here's the first and the last icon from ui_icons_small:



ui_small_icons.JPG (9.36 KiB) Viewed 430 times
