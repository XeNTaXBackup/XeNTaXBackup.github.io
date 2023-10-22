## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2018-02-12T15:10:30+00:00
- Post Title: Mr. Potato Head Activity Pack: .SND and .PIC

Hi again. Another edutainment game here, this one from Hasbro Interactive.

Feel free to follow along, as always. Link: [https://www.dropbox.com/s/4whtaoy8mnt32 ... O.zip?dl=0](https://www.dropbox.com/s/4whtaoy8mnt322n/POTATO.zip?dl=0)

Byte order is big-endian. Here is the structure:

```
char{16}       - ID string: "MMFW [types]" // [types] can be "Sounds" or "Pictures"
char{2}        - "MM" // don't know why
byte{82}       - padding? (all 0s)
uint16{2}      - unknown // I've seen 0, 0x4000, and 0x8000
uint16{2}      - number of files

// begin offset table
   // for each file
   uint32{4}      - file offset

uint32{4}      - archive size

// begin table 2 [unknowns]
   // for each file
   uint32{4}      - unknown

// begin table 3 [unknowns]
   // for each file
   uint16{2}      - unknown // seems to always be 0012 for sounds, but alternates for pictures

// begin name table
   // for each file
   char{32}       - file name

// begin table 5 [unknowns]
   // for each file
   uint32{4}      - unknown

// the rest is all the raw data

```


I don't know how I can view the raw picture data; UFRaw doesn't seem to recognize it, and I don't know of any other programs that can do the same sort of thing. Anyway, this is what I've got so far; if anyone can help me with the unknowns (and extracting the files), I'd appreciate it.

-Johnny
## Post #2
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2018-02-13T16:28:21+00:00
- Post Title: Mr. Potato Head Activity Pack: .SND and .PIC

Hmm... Taking a closer look at this, I think the .PIC files have a slightly different structure than the .SND files. That last table of "unknowns" seems to be preceded by null padding for the .PIC files.
## Post #3
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2018-02-13T16:33:58+00:00
- Post Title: Mr. Potato Head Activity Pack: .SND and .PIC

...Okay, sorry, I just now realized that the .PIC files are the same format as [MMP MMFW](http://wiki.xentax.com/index.php?title=MMP MMFW), but with a different extension. Still, the .SND files are different too, and such file does not appear to be on the wiki. Also, Game Extractor doesn't support these files.
