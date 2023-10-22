## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-01-10T15:34:35+00:00
- Post Title: ZXML files

I found some xml with ZXML tag in the head in Emerald City Confidential.
For exmple strings_shared.xml.

I think the file format is simple like this:
XML 4byts
compressed sie 4bytes
not compressed sie 4bytes

but ,i can't use offzip.exe -a strings_shared.xml out 0 to uncompress it.
So i need someone's help.

The attach file is a sample
[strings_shared.rar](https://xentaxbackup.github.io/file/2707_strings_shared.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-10T15:53:52+00:00
- Post Title: ZXML files

right.

```
string NAME += "_unpacked.xml"
idstring ZXML
get ZSIZE long
get SIZE long
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE
```
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-01-10T16:05:11+00:00
- Post Title: ZXML files

Very thanks!
The offzip works too,Becuse i found i created a 0 size strings_shared.xml in the before tests.
