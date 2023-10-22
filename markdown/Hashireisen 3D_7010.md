## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T01:42:57+00:00
- Post Title: Hashireisen 3D

Here is another archive.
Everything is packed into it (100 MB), but it looks like all of the filenames and offsets/sizes are the beginning so I just took the first 1 MB of data and cut everything after so you can probably still get one or two files.

Anyways I'm not looking for a script this time but just some idea what I am looking at.

Data starts at 0x10B20, which is exactly where the list of names finishes, so I know the number of files is correct and each entry occupies that many bytes.

Since I know where the data starts, one file probably starts at that offset, so I searched for "20 0B 01" and found a couple matches, but one of them was one of the unknowns (unk3), so that one's probably the offset.

I went and recorded the other unknowns cause one of them is probably the size (and if it's compressed then I guess the compressed size), and whatever other stuff. checksum etc I don't really have any clue.

(in decimal)
filepath = FONT\02.SFF
unk1 = 3516018830 (0x8E3092D1)
unk2 = 547315384 (0xB85E9F20)
offset
unk4 = 19308
unk5 = 1

unk1 can't be the size cause it's 3 GB
unk2 doesn't seem to mean much either cause this is a fonts file so it probably shouldn't be 500 MB
unk5 is 1 for everything, so unk4 is probably the size.

I skipped that many number of bytes and recorded the next offset, then ran a search for it and found another file with it as the 3rd unknown, so it looks like size and offset are found.

So I get this in the end

```
get files long
for i = 0 < files
   getdstring name 0x40
   get unk1 long
   get unk2 long
   get offset long
   get size long
   get one long
   log name offset size
next i

```


Ok so I went and extracted, but the files were just garbled lol 

So maybe there's something special about the first two unknowns? Can't think of what they could be.
[data_cut.7z](https://xentaxbackup.github.io/file/4507_data_cut.7z)
