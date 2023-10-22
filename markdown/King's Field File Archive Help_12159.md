## Post #1
- Username: TheStolenBattenberg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 26, 2014 6:52 am
- Post datetime: 2014-10-25T23:05:54+00:00
- Post Title: King's Field File Archive Help

Hey,

I found the forum here a while ago while I was looking for an explanation of Darkstone's (PS1 game) archive format. I decided I might try here for help on understanding this particular format used in early From Software games.

I've had a go at doing this myself, several times. But I'm not very good with understanding anything other than image formats, and that's only a basic understanding.

Edit 01: I figured this out.

```
{
	short {1} T_HeaderEntries;
	short {1} T_HeaderTag;
	
	short {T_HeaderEntries}; Misc Header.
	
	//There's a bunch of padding, here. No clue how the size is worked out.
	//After the padding, files are aligned next to each other.
}
```
## Post #2
- Username: TheStolenBattenberg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 26, 2014 6:52 am
- Post datetime: 2014-10-27T10:24:08+00:00
- Post Title: King's Field File Archive Help

After looking more into the files myself, I figured out some common ground between all the archives on the disk, and in other early from software games.

If you look at this hex:

```

```


You'll notice that each byte is followed by a second, and that the second byte appears to be some sort of ID system. I've observed this to go up to hex of 19.

I also noticed by looking in the other formats, that the third byte, is always '01'. Possible header tag?.. Why wouldn't this be the first byte, though?
