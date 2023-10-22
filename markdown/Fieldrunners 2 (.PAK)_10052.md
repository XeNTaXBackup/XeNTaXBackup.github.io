## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-17T15:32:10+00:00
- Post Title: Fieldrunners 2 (*.PAK)

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
- Username: Elayna
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 08, 2014 6:43 am
- Post datetime: 2014-10-08T07:30:53+00:00
- Post Title: Fieldrunners 2 (*.PAK)

Been searhing for this after extracted the file. I am new in this website and i find this website and the people here are SUPER AWESOME!!



> Reply from Ekey
>
> Code: Select allfilexor 0xf8

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
