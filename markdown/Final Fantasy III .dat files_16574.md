## Post #1
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-07-20T22:24:00+00:00
- Post Title: Final Fantasy III .dat files

Hi,

I want to translation this game. But I cannot find the localization files. 
I think the language files are in this strings.dat file
Can you help me? 
files: [http://www.mediafire.com/file/kt0j6388b ... trings.rar](http://www.mediafire.com/file/kt0j6388bqjbbs9/strings.rar)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-08-29T10:59:16+00:00
- Post Title: Final Fantasy III .dat files

All strings are encoded into file
First text entry starts at: 0x1867. Values are Big Endian
One entry is:

```
char[] - text (may be Unicode and ASCII!!!)
byte - Settings
varies - varied by Settings
```


Settings:

```
-unknown byte
-unknown uint
-next string

When 7:
-next string

When 1:
-unknown byte
-Next string


```


Anyway, why is there Balamb Garden places names in Final Fantasy III? Along with VIII G.Fs names and FF8Launcher inside? What the hell, that whole file is about strings from Final Fantasy VIII not III

Edit: I didn't break the header yet, but it looks like it's divided to many languages and sections and before every section there's header with probably positions of this text. (pointers are rising)
