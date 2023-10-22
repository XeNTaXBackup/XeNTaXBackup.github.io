## Post #1
- Username: 0xdeadbeef
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 01, 2016 7:34 am
- Post datetime: 2017-11-05T02:31:35+00:00
- Post Title: Star Control 3 - compressed strings file SC3STR.DAT

Hi all

I've been working on the compressed strings file for the old game Star Control 3.  I've temporarily uploaded the 310kB file here:

[http://s000.tinyupload.com/?file_id=364 ... 3621255427](http://s000.tinyupload.com/?file_id=36462496773621255427)

Here is the file format:

```
int16_t unknown; // == 1
int16_t table_size; // == 0x1869
int16_t last_section_size; // == 0x497c8

// Values range from 0x07 to 0xfc. Meaning unknown. Do these all refer to
// the array uvalues below?
int16_t table[table_size];

int16_t count; // == 510
// Ordered values -256..1 then all even numbers 0..510. LZ dictionary related?
int16_t uvalues[count];

int16_t stringcount; // == 256
int16_t stringoffsets[stringcount]; // into stringtable below

int16_t stringtablesize;
char stringtable[stringtablesize]; // null-terminated strings

char last_section[last_section_size]; // unknown compressed data


```


Here is a look at the first eight lines of data in last_section:

```
FB CE F8 57 E8 82 FF FC CE 3B 63 8E D9 98 56 B1
00 76 A9 CB A6 84 86 DF 2F 2D D2 77 3E C2 4B 2F
78 59 46 27 FE E7 28 F0 3F 2D C4 C2 A6 0B 28 5D
6F D8 77 CC 8F 69 15 97 5A 75 94 33 9E 97 5E 74
66 AD E1 D0 0B 4E E0 F7 DF 59 37 5D F5 ED 75 C3
EE 97 5E 95 BB 7D E0 D4 39 4A 2F 16 06 7B 87 A6
54 7E 20 84 CF 3D E2 DE 79 1F 9E AE 7B EE 80 E2

```


Compressing this section with zlib only knocks it down from about 300k to about 250k, which is why I think it's lightly compressed.  The sections of size 256 and ~512 make me think this might be LZ-style compression with an embedded dictionary, but I haven't had any success applying that yet.  I'd welcome any tips, or indeed code if someone with lots of LZ experience manages to figure it out.
