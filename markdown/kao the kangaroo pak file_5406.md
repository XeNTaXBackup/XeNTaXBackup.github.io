## Post #1
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-11-17T10:47:40+00:00
- Post Title: kao the kangaroo pak file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-18T00:14:20+00:00
- Post Title: kao the kangaroo pak file

look how small it is!

```
math pEOCDR -= 12
goto pEOCDR

get CDR_NUM long
get CDR_PTR long
idstring "T8FM"   ## assumed magic

goto CDR_PTR

for i = 1 to CDR_NUM

  getdstring R_NAME 80
  get R_POS long
  get R_SIZE long

  log R_NAME R_POS R_SIZE

next i

```
## Post #3
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-11-18T06:38:52+00:00
- Post Title: kao the kangaroo pak file

ok take a look
## Post #4
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-11-18T07:04:17+00:00
- Post Title: kao the kangaroo pak file

thank you the script works correctly I have one more question
how are you doing this because you know the script for a particular game where you know how?
I do not know
## Post #5
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-11-18T12:53:14+00:00
- Post Title: kao the kangaroo pak file

WRS By the way correct topic because the error is because I noticed that the error had
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-18T23:47:53+00:00
- Post Title: kao the kangaroo pak file

> Reply from Bogus
>
> thank you the script works correctly I have one more question
how are you doing this because you know the script for a particular game where you know how?
I do not know

it takes work..

you posted enough detail for me to want to download the sample - that's the first step.

then i make a note of the filesize, as pointers won't go over this value
then in a hex editor at the end of the file there was clearly ascii code at the end, like you said
i see all these ascii parts were 80 bytes long and contain a filename

between each of these 80 bytes is 8 bytes of data. i dont know what it is yet, but i can make an educated guess -
the minimum needed to find the file is its position and its size. as it happens, this file format does only store these values, so its not complicated - reading unsigned integers (4-bytes) is standard

i notice there are a few more bytes at the end of the file.
again, i could use with a pointer to the start of the filename records i've identified and the number of them.
this time is another value which i can only assume is a magic value used to determine the file format before trusting the pointers.

i hope you can take something from this post!
## Post #7
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2010-11-19T06:54:53+00:00
- Post Title: kao the kangaroo pak file

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-19T15:45:29+00:00
- Post Title: kao the kangaroo pak file

and the following is the script for Kao the Kangaroo round 2:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "TATE"
get DUMMY long
get DUMMY long
get ENTRIES long
getdstring NAME 0x30
for i = 0 < ENTRIES
    getdstring NAME 8
next i
getdstring DUMMY 0x18

get PAK_SIZE asize
savepos OFFSET
for OFFSET = OFFSET < PAK_SIZE
    getdstring DUMMY 4
    get SIZE long
    get DUMMY long
    get DUMMY long
    getdstring NAME 0x70
    savepos OFFSET
    if SIZE != 0
        log NAME OFFSET SIZE
    endif
    math OFFSET += SIZE
    math OFFSET x= 0x80
    goto OFFSET
next
```
