## Post #1
- Username: Northstar2
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 14, 2016 6:42 pm
- Post datetime: 2016-04-24T14:54:59+00:00
- Post Title: Toy Soldiers Complete .sacb file

Since the Toy Soldiers bms script returned 0 files found error, I ask here again.
I am pulling my hair out, what's wrong with this script?

```
get FILES long
math OFF = 0x60
for i = 0 < FILES
goto OFF
get NAMEOFF THREEBYTE
math NAMEOFF -= 4
get DUMMY byte
get NAMESIZE long
get UNK1 long
get UNK2 long
get OFFSET long
get ZSIZE long
get SIZE long
getdstring DUMMY 0x1c
savepos OFF
goto NAMEOFF
getdstring NAME NAMESIZE
if SIZE == ZSIZE
log NAME OFFSET SIZE
else
clog NAME OFFSET ZSIZE SIZE
endif
next i
```


When run, it spews this and stops:

```
  quickbms.exe
  -l
  -v
  -d
  -w
  sacb.bms
  res.sacb
READLINE 1   goto 0x54
             >set 0x54 (0) to 0x00000054
  ARG0  "goto"
  ARG1  "0x54"

READLINE 2   get FILES long
             >set FILES (1) to "FILES"
  ARG0  "get"
  ARG1  "FILES"
  ARG2  "long"

READLINE 3   math OFF = 0x60
             >set OFF (2) to "OFF"
             >set 0x60 (3) to 0x00000060
  ARG0  "math"
  ARG1  "OFF"
  ARG2  "="
  ARG3  "0x60"

READLINE 4   for i = 0 < FILES
             >set i (4) to "i"
             >set 0 (5) to 0x00000000
             >set i (4) to "i"
             >set FILES (1) to "FILES"
  ARG0  "for"
  ARG1  "i"
  ARG2  "="
  ARG3  "0"
  ARG4  "<"
  ARG5  "FILES"

READLINE 5   goto OFF
             >set OFF (2) to "OFF"
  ARG0  "goto"
  ARG1  "OFF"

READLINE 6   get NAMEOFF THREEBYTE
             >set NAMEOFF (6) to "NAMEOFF"
  ARG0  "get"
  ARG1  "NAMEOFF"
  ARG2  "THREEBYTE"

READLINE 7   math NAMEOFF -= 4
             >set NAMEOFF (6) to "NAMEOFF"
             >set 4 (7) to 0x00000004
  ARG0  "math"
  ARG1  "NAMEOFF"
  ARG2  "-="
  ARG3  "4"

READLINE 8   get DUMMY byte
             >set DUMMY (8) to "DUMMY"
  ARG0  "get"
  ARG1  "DUMMY"
  ARG2  "byte"

READLINE 9   get NAMESIZE long
             >set NAMESIZE (9) to "NAMESIZE"
  ARG0  "get"
  ARG1  "NAMESIZE"
  ARG2  "long"

READLINE 10  get UNK1 long
             >set UNK1 (10) to "UNK1"
  ARG0  "get"
  ARG1  "UNK1"
  ARG2  "long"

READLINE 11  get UNK2 long
             >set UNK2 (11) to "UNK2"
  ARG0  "get"
  ARG1  "UNK2"
  ARG2  "long"

READLINE 12  get OFFSET long
             >set OFFSET (12) to "OFFSET"
  ARG0  "get"
  ARG1  "OFFSET"
  ARG2  "long"

READLINE 13  get ZSIZE long
             >set ZSIZE (13) to "ZSIZE"
  ARG0  "get"
  ARG1  "ZSIZE"
  ARG2  "long"

READLINE 14  get SIZE long
             >set SIZE (14) to "SIZE"
  ARG0  "get"
  ARG1  "SIZE"
  ARG2  "long"

READLINE 15  getdstring DUMMY 0x1c
             >set DUMMY (8) to "DUMMY"
             >set 0x1c (15) to 0x0000001c
  ARG0  "getdstring"
  ARG1  "DUMMY"
  ARG2  "0x1c"

READLINE 16  savepos OFF
             >set OFF (2) to "OFF"
  ARG0  "savepos"
  ARG1  "OFF"

READLINE 17  goto NAMEOFF
             >set NAMEOFF (6) to "NAMEOFF"
  ARG0  "goto"
  ARG1  "NAMEOFF"

READLINE 18  getdstring NAME NAMESIZE
             >set NAME (16) to "NAME"
             >set NAMESIZE (9) to "NAMESIZE"
  ARG0  "getdstring"
  ARG1  "NAME"
  ARG2  "NAMESIZE"

READLINE 19  if SIZE == ZSIZE
             >set SIZE (14) to "SIZE"
             >set ZSIZE (13) to "ZSIZE"
  ARG0  "if"
  ARG1  "SIZE"
  ARG2  "=="
  ARG3  "ZSIZE"

READLINE 20  log NAME OFFSET SIZE
             >set NAME (16) to "NAME"
             >set OFFSET (12) to "OFFSET"
             >set SIZE (14) to "SIZE"
  ARG0  "log"
  ARG1  "NAME"
  ARG2  "OFFSET"
  ARG3  "SIZE"

READLINE 21  else
  ARG0  "else"

READLINE 22  clog NAME OFFSET ZSIZE SIZE
             >set NAME (16) to "NAME"
             >set OFFSET (12) to "OFFSET"
             >set ZSIZE (13) to "ZSIZE"
             >set SIZE (14) to "SIZE"
  ARG0  "clog"
  ARG1  "NAME"
  ARG2  "OFFSET"
  ARG3  "ZSIZE"
  ARG4  "SIZE"

READLINE 23  endif
  ARG0  "endif"

READLINE 24  next i
             >set i (4) to "i"
  ARG0  "next"
  ARG1  "i"

             .start_bms start: -1 0 0

00000000 08  1   goto 0x54
             <get 0x54 (0) 0x00000054
             <get 0x54 (0) 0x00000054

00000054 06  2   get FILES long
             >set FILES (1) to 0x00000000

00000058 0c  3   math OFF = 0x60
- variable "OFF" seems uninitialized, I use its name
             <get OFF (2) "OFF"
             <get 0x60 (3) 0x00000060
             >set OFF (2) to 0x00000060

00000058 0c  4   for i = 0 < FILES
- variable "i" seems uninitialized, I use its name
             <get i (4) "i"
             <get 0 (5) 0x00000000
             >set i (4) to 0x00000000
             .start_bms start: 5 0 0
             <get i (4) 0x00000000
             <get FILES (1) 0x00000000
             condition < is not met
- variable "SIZE" seems uninitialized, I use its name
             <get SIZE (14) "SIZE"
- variable "ZSIZE" seems uninitialized, I use its name
             <get ZSIZE (13) "ZSIZE"
             condition == is not met
             .start_bms start: 21 1 0
             .start_bms end: 21 1 0 (ret 22)
             .start_bms start: 23 1 0
             .start_bms end: 23 1 0 (ret 24)
             .start_bms end: 5 1 0 (ret 25)[/size]
```


I super-suck at programming and I don't know what's wrong with this thing!
Blame my head if you want, but I really need some help!
## Post #2
- Username: Northstar2
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 14, 2016 6:42 pm
- Post datetime: 2016-06-26T15:02:03+00:00
- Post Title: Toy Soldiers Complete .sacb file

Okay, I figured it out.
I was just using the incorrectly written version.

Silly me
