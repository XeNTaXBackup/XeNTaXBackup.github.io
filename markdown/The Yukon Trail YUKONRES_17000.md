## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-09-11T04:20:06+00:00
- Post Title: The Yukon Trail: YUKONRES

More edutainment games!

This one is a bit more complicated. While I have mostly figured out the structure for this file, there are still a few unknowns. Also, the file has no extension, and the header contains no ID string, so... that kind of sucks. Also, the byte order is big-endian. Yaaaaay...

As usual, feel free to follow along at home. Link: [https://www.dropbox.com/s/4wwgcz4kp2pgrwu/YUKONRES?dl=0](https://www.dropbox.com/s/4wwgcz4kp2pgrwu/YUKONRES?dl=0)

I have determined the structure up to this point:

```
uint16 {2}      - starting offset of file type table
uint16 {2}      - pre-data size
char {6}        - "MECC" plus two nulls  // closest thing to an ID string we have
char {12}       - "Yukon Trail" plus null
byte {52}       - padding (all 0s)
char {4}        - version number?  // I assume it's the version number, but I could be mistaken
byte {6}        - more padding (all 0s)
uint16 {2}      - number of file types
uint16 {2}      - total number of files

// begin file type table
   // for each file type
   char {4}        - file type
   uint16 {2}      - number of files of that type
   uint16 {2}      - position number (NOT relative offset) of first file of that type in entry table

// begin entry table
   // for each file
   char {4}        - file type
   uint16 {2}      - unknown
   uint32 {4}      - length
   uint32 {4}      - offset

```


The file type "TREE" seems to refer to dialogue trees. Thankfully, these are mostly plain text, though there are a few hex values mixed in there as well (not sure what they mean). As for the other files... CBMP would imply bitmaps/picture files, but they don't start with a normal bitmap header. PSND would imply sound, but... I've tried importing this file as raw data into Audacity, to no avail. I hear no in-game audio, just noise (yes, there is a difference  ). My guess: The files use some form of compression and/or encoding. I don't want to try decoding or decompressing the files myself, because it seems like a rather daunting task based on my experience level. But hey, I'm still happy I figured out as much as I did.

If anyone can help me figure out anything beyond this, please let me know; I would really appreciate it.

-Johnny
