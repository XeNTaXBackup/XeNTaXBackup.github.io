## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-02-04T12:32:03+00:00
- Post Title: ASTONISHIA ONLINE

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-04T14:25:19+00:00
- Post Title: ASTONISHIA ONLINE

it's necessary to know the exact size of the archive in bytes
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-04T14:34:26+00:00
- Post Title: ASTONISHIA ONLINE

ok doesn't seem necessary :)

```

get MYOFF long
get FILES long
goto MYOFF
for i = 0 < FILES
    get TYPE byte
    get ZSIZE long
    get NAMESZ short
    getdstring NAME NAMESZ
    get OFFSET long
    get SIZE long
    if TYPE == 1
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-02-04T15:55:20+00:00
- Post Title: ASTONISHIA ONLINE

thanks, will try it when I get home. It seems to be quite an easy archive, would you mind describing the process of the script? I really want to learn to at least be able to extract some archives alone before I die, don't want to give you gray hair aluigi
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-04T17:12:46+00:00
- Post Title: ASTONISHIA ONLINE

I hope this one is enough :)
anyway remember that all the supported commands are listed inside [quickbms.txt](http://aluigi.org/papers/quickbms.txt).

get MYOFF long
take the offset where is located the table with all the file information this field is a "long", so it's a 32bit value
default endianess is the intel one so 44 33 22 11 is read as 0x11223344
example: 3e 54 1f 0c
get FILES long
take the number of files stored in the archive, still a 32bit long value
example: 01 03 00 00
goto MYOFF
go to the offset where are located the informations about the files
so the current offset (where we are in the input file) changes from 8 to 0x0c1f543e
for i = 0 < FILES
classical loop, 'i' is a counter so we will execute the following cycle for each file
    get TYPE byte
8bit value, this is ever 1 in the file you provided so I don't know what it is
    get ZSIZE long
32 bit value but I don't know what it is because it's ever zero, I have decided to give it the name of ZSIZE for saying that it's compressed but this is NOT TRUE or VERIFIED!
    get NAMESZ short
size of the string that follows, it's a 16 bit value
example: 46 00
    getdstring NAME NAMESZ
get the name of the file (NAME) reading the number of bytes specified in the previous value
example: Data\Character\Resource\Morphing\BON\FaceMotion_A_EM_BON_Hello1_W0.nif
    get OFFSET long
offset of where is located the file
example: 05 86 ab 0b
    get SIZE long
size of the archived file
example: 9c d8 02 00
    log NAME OFFSET SIZE
this commands means that we want to dump the a certain amount of bytes (SIZE) starting from that offset (OFFSET) in a file with the name NAME
next i
    this command is part of the "For" command and means that we want to increment the 'i' counter

note that I have not commented the part of code referred to clog and the "if" because it's not part of the format, was only something I added in case there are other archives in that game and in case they use that particular format but it's something done by me and not verified.

this game has a simple format and at the same time uses various commands and fields with different sizes (8, 16 and 32 bit) so it's good to learn the bms language
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-02-04T18:13:47+00:00
- Post Title: ASTONISHIA ONLINE

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-04T18:23:38+00:00
- Post Title: ASTONISHIA ONLINE

if the archive says that at offset 8 there is a dds of 0xac8e byte while in reality it's a nif, it's its problem:

```
61 63 74 65 72 5c 52 65 73 6f 75 72 63 65 5c 50   acter\Resource\P
61 72 74 73 5c 44 46 4d 5c 57 5f 50 5f 44 46 4d   arts\DFM\W_P_DFM
5f 57 50 54 5f 57 38 5f 30 33 31 31 2e 64 64 73   _WPT_W8_0311.dds
08 00 00 00 8e ac 00 00                           ........
```
## Post #8
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-02-04T18:49:07+00:00
- Post Title: ASTONISHIA ONLINE

yeah reading about DIVINE DIVINITY now and seems to be like that there also. its a new gamebryo embedded texture thingy

yes, just found that if you rename to .nif and open in niftools and choose export you actually get a real .dds

Thanks aluigi
## Post #9
- Username: Daimyo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 07, 2010 4:27 am
- Post datetime: 2010-02-07T16:47:43+00:00
- Post Title: ASTONISHIA ONLINE

Hello,
@ Aluigi :
There is something that I don't understand about your script.
Its start with :"get MYOFF long" ,so its mean that bms will start at 0*00 and will take an long used as offset later, but the file(start.apk) start with "3E541F0C"which is an Id string.
Can you tell me what I missed?
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-07T19:17:57+00:00
- Post Title: ASTONISHIA ONLINE

"3E541F0C" would be a string if the sequence of bytes was "33 45 35 34 31 46 30 43", while in this case there are 4 bytes (32bits long): "3E 54 1F 0C".
verify it with the hex editor
## Post #11
- Username: Daimyo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 07, 2010 4:27 am
- Post datetime: 2010-02-07T21:34:17+00:00
- Post Title: ASTONISHIA ONLINE

Thanks for the help but I still don't understand how it can be an offset since it's too big(little or big endian).

I can't  reach that point :0C 1F 54 3E when (start+end.apk)=01 08 E3 07.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-08T08:57:18+00:00
- Post Title: ASTONISHIA ONLINE

because start and end are only the limits of the file that was uploaded.
there is a "middle" part too
## Post #13
- Username: Daimyo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 07, 2010 4:27 am
- Post datetime: 2010-02-08T16:59:31+00:00
- Post Title: ASTONISHIA ONLINE

Thanks a lot, I understand now.
