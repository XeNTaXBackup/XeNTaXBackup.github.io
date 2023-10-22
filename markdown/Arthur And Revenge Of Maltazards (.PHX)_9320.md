## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-20T23:11:36+00:00
- Post Title: Arthur And Revenge Of Maltazards (*.PHX)

Just XORed ZIP 

```

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
- Post datetime: 2012-07-20T23:22:37+00:00
- Post Title: Arthur And Revenge Of Maltazards (*.PHX)

the usual zip xored with 0x55, it's used in various games but I have not seen a common developer/publisher since they look all different (paradox, ubi, a german one and others).
for the other games google "filexor 0x55" :)
