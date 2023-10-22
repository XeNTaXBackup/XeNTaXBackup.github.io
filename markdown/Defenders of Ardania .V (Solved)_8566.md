## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-16T00:02:30+00:00
- Post Title: Defenders of Ardania *.V (Solved)

Just XOR'ed zip

Here script for unpack 

```
# script for QuickBMS http://quickbms.aluigi.org

filexor 0x55

ComType deflate

for
    idstring "PK\x03\x04"

    get ver         short
    get flag        short
    get method      short
    get timedate    long
    get crc         long
    get comp_size   long
    get uncomp_size long
    get name_len    short
    get extra_len   short
    getdstring name     name_len
    getdstring extra    extra_len

    savepos offset
    if method == 0
    Log name offset uncomp_size
else
    CLog name offset comp_size uncomp_size
endif
    math offset += comp_size
    goto offset
next i
```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-19T10:35:38+00:00
- Post Title: Defenders of Ardania *.V (Solved)

probably you would like to replace:

```
    CLog name offset comp_size uncomp_size
```
with:

```
    Log name offset uncomp_size
else
    CLog name offset comp_size uncomp_size
endif
```
it's useful in case of uncompressed files.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-19T18:38:58+00:00
- Post Title: Defenders of Ardania *.V (Solved)

oy thanks aluigi
