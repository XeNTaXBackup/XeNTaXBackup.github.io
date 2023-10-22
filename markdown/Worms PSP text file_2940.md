## Post #1
- Username: zakos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 15, 2008 3:59 am
- Post datetime: 2008-02-17T23:23:56+00:00
- Post Title: Worms PSP text file

[http://uploaded.to/?id=mvx6ge](http://uploaded.to/?id=mvx6ge)

Any idea how can I edit this file?
I want to translate it to my language.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-02-19T22:57:48+00:00
- Post Title: Worms PSP text file

The structure looks more or less simple:

```

uint32	Version ?
uint32	Total Size of next block (Filesize - 8)


// Block 1 

uint32	Number of text strings?
uint32	Relative Offset of information of first text string?
uint32	0 (unknown)
uint32	Total size of current block (Filesize - 8)
uint34	Unknown

// Block 1.1 (String info, presumably Number of text string-times)

uint32	Relative offset of text string (Add header size (8) to this value)
uint32	Unknown (could be identifier in the game for this string)

// Strings (null-terminated, with additional codes inbetween for mark-up.)


```
