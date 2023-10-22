## Post #1
- Username: gaolon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 21, 2010 2:15 am
- Post datetime: 2011-08-02T17:37:39+00:00
- Post Title: Pirates of Black Cove

Hello,

I wanna translate Pirates of Black Cove badly,its fonts and subtitles are easy to find,but now I run into a stone wall...

Take 'Start the Game' as an example ,I tanslate it into Chinese while I keep English words firstly,i.e '开始游戏Start the Game',

both Chinese and English words can be displayed perfectly in the game with the new fonts files I made; But when I delete the

English words,just left the Chinese words,it becomes 'n/a'...so do the dialog subtitles.

I tried to add 'space' after the last chinese word of the sentence,but failed...

Can anyone tell me why it comes this way?  It seems every sentence must contain English words...
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-08-03T05:52:34+00:00
- Post Title: Pirates of Black Cove

Sample file!
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-23T18:14:56+00:00
- Post Title: Pirates of Black Cove

Script for unpack.

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
