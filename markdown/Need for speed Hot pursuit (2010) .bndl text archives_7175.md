## Post #1
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-08-13T19:13:54+00:00
- Post Title: Need for speed Hot pursuit (2010) .bndl text archives

Can someone create for me pack/unpack tools for this text archive I create structure. Archives are in Little Endian.

zlibbed archive

```
int unknown1 (same in all languages)
int unknown2 (same in all languages)
int sizeoffile1
int one (same in all languages)
int fortyeight (same in all languages)
int sizeofheader (same in all languages)
int sizeoffile2
int sizeoffile3
int sizeoffile4
int one2 (same in all languages)
int zero1 (same in all languages)
int unknown3 (editing is not required)
int64 zero2 (same in all languages)
int zero3 (same in all languages)
int unknown4 (editing is not required)
int64 zero4 (same in all languages)
int zero5 (same in all languages)
int zlibdatasize
char zero[44] (same in all languages)
char zlibdata[zlibdatasize]

```


structure of unzlibbed data

```
int numberofrecords (same in all languages)
int unknown (same in all languages)
int positionoffirstvariable (same in all languages)
for i = 0 < numberofrecords
{
  int id (same in all languages)
}
for x = 0 < numberofrecords
{
  int positionofstrings
  int stringlenght (stringlenght*2)
}

```


links to archives 

```
http://www.multiupload.com/C1UAKQ8VG4
```

or

```
http://www.multiload.cz/stahnout/474148/packed_unpacked_bndl-rar/
```
## Post #2
- Username: XpucmoBG
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Apr 30, 2011 3:27 am
- Post datetime: 2012-02-18T23:22:14+00:00
- Post Title: Need for speed Hot pursuit (2010) .bndl text archives

Have you found a way to edit these files?
