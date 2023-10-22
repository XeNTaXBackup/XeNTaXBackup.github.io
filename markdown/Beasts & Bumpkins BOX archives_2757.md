## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-17T10:37:12+00:00
- Post Title: Beasts & Bumpkins BOX archives

Could someone help me with those B&B archives?
Some example files can be downloaded here: [http://uploaded.to/?id=9zjtw5](http://uploaded.to/?id=9zjtw5)


EDIT:
The format is nearly figured out. There's just one thing left.
Files start with "BOX" followed by a byte that changes from file to file (maybe file count?) and the value 65536.

```
0000h: 42 4F 58 97 00 00 01 00  BOX.....
```

I need to know the meaning of that byte.

This is my binary template:

```
byte uk1;
uint uk2; // 65536
struct Entry {
	string filename;
	byte crap[255-Strlen(filename)];
	string path;
	byte crap2[255-Strlen(path)];
	ushort year; // SYSTEMTIME
	ushort month;
	ushort dayofweek;
	ushort day;
	ushort hour;
	ushort minute;
	ushort second;
	ushort milliseconds;
	uint size;
	char data[size];
}entries[256]<optimize=false>;

```
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-21T08:10:58+00:00
- Post Title: Beasts & Bumpkins BOX archives

Hmm doesn't seem to be the file count. There is a box archive with more than 256 files in it.
