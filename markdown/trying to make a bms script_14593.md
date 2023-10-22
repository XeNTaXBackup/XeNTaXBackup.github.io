## Post #1
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-07-03T05:27:51+00:00
- Post Title: trying to make a bms script

sorry for the noob question, I was trying to learn how to make my own bms script but having difficulty if I'm getting the right value or offset. I little guidance is appreciated so I could get started.


```
00 09 93 F0 00 00 00 00 00 00 01 5D 00 00 00 00
```


so I was trying to get the 00 00 00 20 

so how would I do this?

like this

```

goto 0c
get unknown long
```


or like this

```

get unknown1 THREEBYTE
get unknown2 long
```


can I also display the values saved for example on  unknown1 and  unknown2? just to make sure i'm getting the right values

maybe like this

```
print "%unknown1%"
```

[001.jpg](https://xentaxbackup.github.io/file/11230_001.jpg)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-03T18:19:32+00:00
- Post Title: trying to make a bms script

The snippets of BMS script your provided should work. Are you having any syntax errors?

I would personally:

```
goto 0xC
get unknown long
```


QuickBMS probably wants the hex offset prefixed by "0x". And yes, you can always print variables to ensure you are reading the correct data.
## Post #3
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-07-04T10:09:35+00:00
- Post Title: trying to make a bms script

I revised my script to this and it seems to be working but there are some problems with it

```
goto 0xc
get TMP1 long
get TMP2 long
get null long
xmath archiveSize "TMP2 - TMP1"
get FILENUM long
get null long
get null long
get unknown1 long
get null long
get unknown1 long
get unknown2 long
for i = 0 < FILENUM
  get OFFSET1 long
  get OFFSET2 long
  Math OFFSET1 + TMP1
  Math OFFSET2 + TMP1
  xmath SIZE "OFFSET2 - OFFSET1"
  log "" OFFSET1 SIZE
next I
```


```
00 09 93 F0 00 00 00 00 00 00 01 5D 00 00 00 00
00 00 00 00 00 00 01 5D 00 00 00 00 00 00 00 10
00 00 00 00 00 00 0B 00 00 00 24 40 00 00 33 B0
00 00 4B E0 00 00 5C D0 00 00 6B 60 00 00 7E 70
```


it only extract haft of the file mentioned on 00 00 01 5D...
it was supposed to extract from 00 00 00 0B 00 to 00 00 24 40 then from 00 00 24 40 to 00 00 33 B0.
but it extract from  00 00 00 0B 00 to 00 00 24 40 then from  00 00 33 B0 to 00 00 4B E0

but I was wrong and the size of the individual files are located at the end after all the offsets location of the individual files

```
goto 0xc
get TMP1 long
get TMP2 long
get null long
xmath archiveSize "TMP2 - TMP1"
get FILENUM long
get null long
get null long
get SIZENUM long
get null long
get unknown1 long
get unknown2 long
xMath sizepad "FILENUM * 4 + TMP1"
for i = 0 < FILENUM
	get OFFSET long
	Math OFFSET + TMP1
	Padding sizepad
	get SIZE long
	goto OFFSET
	Print %SIZE%
	Print %OFFSET%
next ii
```


so my problem is how to I go to offset of the location to get the size then back to the next offset location of the second file then back to the offset of the second file
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-07-04T12:06:19+00:00
- Post Title: trying to make a bms script

just keep your current position in the file table and use the log command for files.
example
goto 0xC - my position is 0xC
get offset long
get size long
my position in the file is 0x14
but i can store the data from anywhere in the file now
log name offset size
offset can be anywhere in the file and size is the amount of data to read from the offset.
my position ill remain at 0x14.
## Post #5
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-07-04T14:20:02+00:00
- Post Title: trying to make a bms script

my problem is the offset of the files are located from  0x34 to 0x5A4 and the  sizes of the files are located on 0x5A8 to 0xB18

I think I managed to get the files with my messy unsure noob script

```
goto 0xc
get TMP1 long
get TMP2 long
get null long
xmath archiveSize "TMP2 - TMP1"
get FILENUM long
get null long
get null long
get SIZENUM long
get null long
get unknown1 long
get unknown2 long
for i = 0 < FILENUM
	get OFFSET long
	Math OFFSET + TMP1
	Math OFFSETloc = OFFSET
	SavePos OFFSETloc
	xMath sizepad "FILENUM * 4"
	Math sizepad + OFFSETloc
	Math sizepad - 4
	Padding sizepad
	Get SIZE long
	log "" OFFSET SIZE
	Goto OFFSETloc	
next i
```


is this fine? while the extracted files are nameless, can I change the automatically generated names be decimal numbers and not hexadecimal? and would it code also work for reimport/reinject?
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-07-04T22:12:54+00:00
- Post Title: trying to make a bms script

you can loop through saving the pos in each file table like this

set filetbloff 0x50
set sizetbloff 0x80

for i = 0 < files
goto  filetbloff
get fileoff long
savepos  filetbloff
goto sizetbloff
get filesize long
savepos sizetbloff
log "' offset size
next i

or you can use arrays in quickbms
goto  filetbloff

for i = 0 < files
get off long
putarray 0 i off
next i

goto  sizetbloff
for i = 0 < files
get size long
putarray 1 i size
next i

then you can do one mor eloop and grab the variables
example

    for i = 0 < FILES
        getarray FULLNAME 10 i
        getarray OFFSET 2 i
        getarray ZSIZE  3 i
        getarray SIZE   4 i
        getarray PACKED 5 i

        log file here
    next i
## Post #7
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-07-05T17:35:15+00:00
- Post Title: trying to make a bms script

thanks will try using that code and see if I can get it to work

*edit*

```
goto 0xc
get headerpad long
goto 0x18
get FILENUM long
Padding 9
get SIZENUM long
xMath sizeoff "SIZENUM * 4 + 52"
set filetbloff 0x34
set sizetbloff "sizeoff"
for i = 0 < FILENUM
	goto filetbloff
	get OFFSET long
	math OFFSET + headerpad
	savepos filetbloff
	goto sizetbloff
	get SIZE long
	savepos sizetbloff
	xmath HEXNAME "OFFSET - headerpad"
	string NAME p= "%08x.bin" HEXNAME
	log "NAME" OFFSET SIZE	
next i

```


I tried the 1st code you've provided since it's the one I barely understand and it works great.I think i'm beginning to understand it a bit thanks!!

one last question, what to do with no IDstring files? they got same file extentions and the one obvious difference the whole 0x0 to 0x10, cant seem to understand if using the "findloc OFFSET string" would work

```
findloc HEADER string "\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x20"
```
