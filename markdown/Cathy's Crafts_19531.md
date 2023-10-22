## Post #1
- Username: chphat11
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 03, 2018 12:45 am
- Post datetime: 2019-02-20T15:16:05+00:00
- Post Title: Cathy's Crafts

Can anyone help me make tool for export/import this language file.
And unpack/repack data,arc
[https://www.mediafire.com/file/tpqmxkwgo4cgaxj/data.rar](https://www.mediafire.com/file/tpqmxkwgo4cgaxj/data.rar)
Sorry my bad english 
[english.rar](https://xentaxbackup.github.io/file/15758_english.rar)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2019-06-13T22:15:37+00:00
- Post Title: Cathy's Crafts

did you solve this? the format is very simple

```

then key-values are:

4 bytes - key name size
wchar_t * size - key name
4 bytes - text size
wchar_t * size - text

```
