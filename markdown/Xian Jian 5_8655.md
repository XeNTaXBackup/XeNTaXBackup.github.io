## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-28T22:09:16+00:00
- Post Title: Xian Jian 5

仙剑奇侠传5
"Chinese Paladin 5"

Unpacker for this game. Filenames and all. I'm impressed since I don't see any obvious filenames or directory structure at all,

Just click the first button on the top panel to open a file, and click the second button to read it.
Then select the stuff you want and click the first button in the right panel.

[http://www.mediafire.com/?grtwp1t7qa2cj7b](http://www.mediafire.com/?grtwp1t7qa2cj7b)

Found at: ttp://mayafei263.gotoip2.com/archives/181
He's written several other tools for other games as well. You can find them at ttp://mayafei263.ys168.com/

I am not sure, but maybe the file table is just compressed.

```
int32 unk
int32 unk
int32 unk
int32 table_ofs?
...

```


When you seek to table_ofs you read an integer, followed by some nonsensical data.
I would like to imagine that is the file table.

Sample attached.
[flash.7z](https://xentaxbackup.github.io/file/5240_flash.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-28T23:03:36+00:00
- Post Title: Xian Jian 5

its a pretty easy format.
its just a compressed and encrypted file table at the end of the file the offset at 0x10 tells you where it starts then you just read that long there and its the uncompressed file table size.
no point in trying to find the encryption as this tool works but most likely its zlib data that is xored or something.
[filetable.rar](https://xentaxbackup.github.io/file/5242_filetable.rar)
