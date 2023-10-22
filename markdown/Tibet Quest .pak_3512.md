## Post #1
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-27T07:54:34+00:00
- Post Title: Tibet Quest .pak

Hi ! 

again i have a problem with a .pak file of a Casual Game

Here you can download.

[http://www.fenomen-games.com/tibet-quest.htm](http://www.fenomen-games.com/tibet-quest.htm)

there is only one tibetquest.pak with signature FPAK

I found that Sig on some other games too in the past.

No Generic Extractor Works. (

So maybe someone can help me with extracting the tibetquest.pak

Thx !
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-27T12:22:09+00:00
- Post Title: Tibet Quest .pak

job done but at the moment the function used in the script is implemented only in the beta that I will release in these days.
so for the moment I show the script (which is enough slow unfortunately) and when the new version of quickbms will be out you will be able to use it:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

quickbmsver 0.2.1   # needed for the "binary" type used for MEMORY_FILE2

idstring FPAK
get DUMMY long
get DUMMY long
get FILES long
set INFO_SIZE long FILES
math INFO_SIZE *= 73
savepos INFO_OFFSET

log MEMORY_FILE INFO_OFFSET INFO_SIZE

set VAR_A long INFO_SIZE
math VAR_A -= 0x27
set VAR_C long 0xad
set VAR_D long 0x6f
for i = 0 < INFO_SIZE
    math VAR_A += VAR_C
    math VAR_C += VAR_A
    math VAR_D += VAR_C
    math VAR_D ^= VAR_A
    math VAR_A &= 0xff  # not needed
    math VAR_C &= 0xff  # not needed
    math VAR_D &= 0xff  # not needed
    getvarchr BYTE MEMORY_FILE i
    math BYTE ^= VAR_D
    putvarchr MEMORY_FILE i BYTE
next i

set MEMORY_FILE2 binary "\x7B\x47\x85\xF0\x91\x8B\x2C\x94\xA7\x55\x3A\xF6\x17\xB1\xC2\x06\x6B\x64\x28\x8A\x86\x09\xCE\xA2\x9F\x58\xDE\x46\xAE\x24\x63\x74\x69\x9D\xFB\xFD\x6E\x50\xE0\x12\x57\x1C\x08\xBC\x1B\xD0\xD9\x81\x01\xE4\xC7\x07\x88\x16\x76\x49\x23\x05\xAD\x51\x38\x78\x45\x89\x5D\xCF\x2E\x20\x26\xB6\x3B\xC3\xEB\xEF\x22\xA0\x19\xC6\x6A\xBB\xA1\x41\xF5\xCB\x73\xED\xEA\x9B\x90\xA9\x2D\xAA\x15\x27\xDA\x37\xF9\x40\xA4\xE8\x67\xBF\x1E\xB8\xAC\x60\x53\xD2\x54\x1D\x68\xF7\x4F\x00\xC4\x5E\x33\x29\x14\x0C\x3F\x62\xFC\x93\xC1\xB0\xB4\x9C\x1F\x72\xAB\x11\x18\x87\xB5\xE9\xF1\x59\xF8\x36\x5C\xA3\xE3\x79\x8C\x2F\x0A\xBA\x44\xD8\xC8\xA6\x2A\x03\xCA\x1A\x10\x35\xF3\x77\xD7\x31\xB9\x97\x43\xF2\x3D\xDF\x21\x52\x65\xB2\x34\x6F\x7F\xD3\x2B\xC0\xCC\x6D\x75\xDD\x0D\x13\xDB\xE5\x02\xEE\xB3\xF4\xC9\xFE\x66\x5B\xEC\x7D\x83\x5F\xCD\x8E\xE6\x84\xD4\xBE\x32\xD1\xA5\x56\xC5\x70\x9E\x0B\x9A\x80\x6C\x5A\xE7\x7A\x7C\xB7\x7E\xFA\xDC\x0F\xE1\x4B\x4C\x8F\x4A\x04\x4E\xA8\xFF\x3C\xD6\x0E\x95\x39\x82\x42\x3E\x61\x96\x48\x8D\xAF\x30\xE2\x71\x4D\xD5\x25\x92\xBD\x99\x98"

for i = 0 < FILES
    getdstring NAME 0x41 MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE

    log MEMORY_FILE3 OFFSET SIZE

    for j = 0 < SIZE
        getvarchr BYTE MEMORY_FILE3 j
        getvarchr BYTE MEMORY_FILE2 BYTE
        putvarchr MEMORY_FILE3 j BYTE
    next j

    log NAME 0 SIZE MEMORY_FILE3
next i
```
## Post #3
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-27T12:37:05+00:00
- Post Title: Tibet Quest .pak

Hi bugtest !

Thanx !!!

That doesnt look easy 

And i will wait for the new quickbms Version
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-27T12:43:46+00:00
- Post Title: Tibet Quest .pak

in reality it's more easy than how much it looks.
practically the info table (name table or how you want to call it) is obfuscated with a simple algorithm which uses the length of the table as key, in C it looks like:

```
    int     i;
    unsigned char   a, c, d;

    a = datalen - 0x27;
    c = 0xad;
    d = 0x6f;
    for(i = 0; i < datalen; i++) {
        a += c;
        c += a;
        d = (c + d) ^ a;
        data[i] ^= d;
    }
}
```
while in each file is used a "substitution byte", for example if you have the byte 0x00 you must substituite it with 0x7b, 0x01 with 0x47 and so on.
so it's very basic :)

for the new version of quickbms I can say that it's practically ready, I need only to see if I want to add a couple of new things (which are absolutely not important) so it's not excluded that I can release it even in the next hours
## Post #5
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-27T12:53:51+00:00
- Post Title: Tibet Quest .pak

For you it seems to be easy, but for me it looks like mandarine-chinese with a sort of special dialect. 

And the other point is, how fast you can analyze the algo.. very impressive.

Dont hurry with the new version, maybe i need the extracted data on Friday or so, didnt know what my boss said.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-27T20:56:05+00:00
- Post Title: Tibet Quest .pak

[new version](http://aluigi.org/papers.htm#quickbms) out :)
## Post #7
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-28T09:44:55+00:00
- Post Title: Tibet Quest .pak

THX !! Works great
