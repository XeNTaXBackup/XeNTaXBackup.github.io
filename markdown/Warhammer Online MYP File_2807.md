## Post #1
- Username: Daegalus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 07, 2007 3:56 pm
- Post datetime: 2007-10-07T20:10:32+00:00
- Post Title: Warhammer Online MYP File

What I'm looking for is help to unpack or read whats inside a Warhammer Online MYP file. Ive been looking for something for a while now with no luck.

I found another forum with this information on it about the file that may be helpful:

```
Byte(12) -> Containing general file headers (Version etc.)
WORD -> General Format Header Length (in warhammer-myp's 0x0200)
Byte(6) -> unknown1 (0x00 in all myp's I've seen so far)
WORD -> unknown2 0x0064 ... except in warhammer-mft.myp (0x03E8)
WORD -> unknown3
DWORD? -> Amount of contained files/indexes
byte(remaining format header) -> Unknown4 gibberish

```


```
   QWORD 0x34 -> Offset to start of Data Block of this file
   DWORD 0x3c -> Length of Data Block header (usually 0x0C)
   DWORD 0x40 -> Lenght of compressed data
   DWORD 0x44 -> Size of decompressed file
   DWORD 0x48 -> some hash(filename? extension?)
   DWORD 0x52 -> some hash (filename? extension?)
   DWORD 0x56 -> some hash (folder? because in warhammers-mft.myp this is 0x00 and in all other myp's this is ~ 0x00) 
   WORD  0x5a -> Compressed flag (0x0001 = compressed; 0x0000 = uncompressed)

```


```
   WORD 0xd7c -> some flag (0x0003 in uokr-myp's, 0x0004 in warhammer-myp's)
   WORD       -> offset to file data from this position (in warhammer-myp's 
                  this is 133 and sometimes 132. so the data block header
                  has no fixed size)
   QWORD      -> UNKNOWN, possibly a CRC
                 (don't think so because this value isn't unique for every data
                 block header. if this is a crc it has to be unique unless there are
                 to equal files inside a myp ... or not?)
   BYTE(Lenght) 0xd88 -> compressed data

```


Dunno how much tht will help. Ive attached 2 files in a rar to help you guys.
[files.rar](https://xentaxbackup.github.io/file/1350_files.rar)
## Post #2
- Username: Lliane
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 19, 2008 3:29 pm
- Post datetime: 2008-08-19T12:59:32+00:00
- Post Title: Warhammer Online MYP File

With the end of the NDA over Warhammer Online, mmo-tools.com is proud to announce you the launch of [http://www.wardev.org/](http://www.wardev.org/) his wiki for addon developpers on this new MMO !!!!!!!

You'll find for his launch, as a world exclusive :
- a MYP Archive extractor : [http://www.mmo-tools.com/wardev/doku.ph ... _extractor](http://www.mmo-tools.com/wardev/doku.php?id=myp_extractor)
- the whole game API, ready to be documented : [http://www.mmo-tools.com/wardev/doku.ph ... ce_content](http://www.mmo-tools.com/wardev/doku.php?id=myp_interface_content)

You are invited to contribute, and check out 
- our portal : [http://www.mmo-tools.com/](http://www.mmo-tools.com/)
- our forum : [http://www.mmo-tools.com/forum/](http://www.mmo-tools.com/forum/)
- our bugtracker : [http://www.mmo-tools.com/bugs/](http://www.mmo-tools.com/bugs/)

I hope we'll see you soon on our wiki
