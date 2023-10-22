## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2012-03-05T01:21:13+00:00
- Post Title: VVVVVV Music Archive

I wanted some new music for my MP3 player, and I remembered that the music from VVVVVV was cool. The file format looked weird, and the extractors found through Google looked crappy, so I decided to properly research the format.

C-struct-like representation (more like i.Hex visualization syntax):

```
{
    char name[48];
    int reserved;
    int length;
    int hasContent;
};    

struct VvvArch
{
    Entry entries[128];
    char data[];
};
```


Parsing:
The format has a fixed entry table size of 7680 bytes. Since each entry is 48+3*4=60 bytes, that makes up 128 entries. The names are in ASCII, length 48 bytes, with excess characters being null (0x00). The reserved int is not used by the game, and looks more or less like junk. hasContent is actually only 1 byte, but allocated as 4 bytes. If the byte is 0, then the entry does not have a file, and is ignored. Otherwise, the game malloc()s some space and adds it in some list. The remainder 3 bytes of hasContent is junk. Actual data is consecutive, so you must sum up the lengths of all files before the one you want and add the file table size to get the offset of the file.

Here is the extractor I wrote, striving to parse the format properly. Different from other code you find on the Internet, it actually reads hasContent, and does not base the data start offset on a constant, but at the end of the file table. The file table entries count is overrideable, so if that changes in the future I don't need to rewrite stuff. [http://www.mediafire.com/file/en5mumnuj ... ractor.zip](http://www.mediafire.com/file/en5mumnujwngg0f/VVVVVVMusicExtractor.zip)

Have fun doing it right. That's what file format research is about. You don't just get the data out - you also figure out what various structures actually represent.
## Post #2
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2012-03-06T16:50:33+00:00
- Post Title: VVVVVV Music Archive

is not this just a flash game and the audio inside are mp3s?
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2012-03-08T23:35:09+00:00
- Post Title: VVVVVV Music Archive

This applies to version 2.0, which is a port for Windows/Mac/Linux, written with SDL. The music are in a separate archive, while most of the other data are loose files.
