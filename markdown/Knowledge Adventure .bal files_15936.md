## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-03-01T20:30:27+00:00
- Post Title: Knowledge Adventure .bal files

These are *.bal files, used in games from Knowledge Adventure. These particular ones are from JumpStart 1st Grade Math. Looking at them, I think they contain sound, but they're either encrypted or compressed. They also don't have a signature in the header.

MEGA link: [https://mega.nz/#!DkgViIIY!RI2QuxhKl5gl ... T0zQ7URy_Q](https://mega.nz/#!DkgViIIY!RI2QuxhKl5glLwO3dMIBKGKzTP-IiXuKKT0zQ7URy_Q)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-03-03T21:04:47+00:00
- Post Title: Knowledge Adventure .bal files

very rusty at the moment. heres a start:

```
//--- 010 Editor v5.0 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------

uint num;
uint stub;

enum <int>EntryType
{
  Invalid = -1,
  Unknown = 0,
  File = 0xb0,
};

struct File
{
  EntryType a;
  int b,c,d;
  uint nameoff;
};

File f[num];

local int POOL_POS = FTell();
struct pool
{
string i;
} strs[1+num] <optimize=false>;

local int i;

for(i=0;i<num;++i)
{
  Printf("%s == %s\n", EnumToString(f[i].a), ReadString(POOL_POS+f[i].nameoff) );

}

```
## Post #3
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2018-02-16T15:09:44+00:00
- Post Title: Knowledge Adventure .bal files

Took me long enough, but here's what I've figured out so far:

```
byte {8}    - padding
uint32 {4}  - archive size (-4)
uint32 {4}  - unknown (0x8000)
byte {4}    - padding
uint32 {4}  - unknown (2)
byte {8}    - padding (if divided into two ints, -1 followed by 0)
uint32 {4}  - unknown (0x8000 again)
byte {4}    - padding

// offsets table
// for each file
   uint32 {4}  - unknown
   uint32 {4}  - file offset
   uint32 {4}  - file size
   byte {8}    - padding

// name table - names vary in length; table goes until first offset

```


The offset for the first file repeats three times in many of these, leading me to believe that those "files" are just empty. I still can't figure out how to get any sound out of the .SND files, though...
## Post #4
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-05-22T22:22:38+00:00
- Post Title: Knowledge Adventure .bal files

> Reply from HeadsetGuy
>
> Took me long enough, but here's what I've figured out so far:
Code: Select alluint32 {4}  - number of files (+2)
byte {8}    - padding
uint32 {4}  - archive size (-4)
uint32 {4}  - unknown (0x8000)
byte {4}    - padding
uint32 {4}  - unknown (2)
byte {8}    - padding (if divided into two ints, -1 followed by 0)
uint32 {4}  - unknown (0x8000 again)
byte {4}    - padding

// offsets table
// for each file
   uint32 {4}  - unknown
   uint32 {4}  - file offset
   uint32 {4}  - file size
   byte {8}    - padding

// name table - names vary in length; table goes until first offset


The offset for the first file repeats three times in many of these, leading me to believe that those "files" are just empty. I still can't figure out how to get any sound out of the .SND files, though...

Did you try Audacity for the .SND files?
## Post #5
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2018-05-23T14:51:43+00:00
- Post Title: Knowledge Adventure .bal files

> Reply from Puterboy1
>
> Did you try Audacity for the .SND files?
Yes I did. It doesn't sound like anything. Clearly it's supposed to be a sound file (the header is "KA Sound File", for crying out loud), so I'm guessing it's some kind of encoding/compression.
## Post #6
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2018-12-22T19:43:20+00:00
- Post Title: Knowledge Adventure .bal files

Hi all. It's been a long time, but I've figured out the structure.

```
uint32 {4}  - number of entries
// for each entry
   uint32 {4}  - offset of file or directory name (relative to first entry in name table)
   uint32 {4}  - offset of file or directory
   uint32 {4}  - size of file or directory
   uint32 {4}  - boolean: is directory (0x8000 for true, 0 for false)
   byte {4}    - padding

// name table
uint32 {4}  - length of name table
// for each entry
   string      - name of file or directory

// begin file data
// begin next directory (if applicable)

```


Is there a way to use MultiEx to work with directories when organized like this?

EDIT: I almost forgot--if it contains the directories "." and "..", that's current directory and previous directory, respectively; I've found this generally means there's only one directory in the archive. The ".." directory will also have an offset of -1 (that's where the 0xFFFFFFFF came from) and a size of 0.
## Post #7
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2020-10-18T17:45:25+00:00
- Post Title: Knowledge Adventure .bal files

Hello everyone,

I'm sorry that I haven't updated this post here. There is a QuickBMS script created by ALuigi which is able to extract all of the files from BAL archives. I'm still uncertain about the structure of some of the files contained within those archives, but this is certainly a start! The script is available here: [https://aluigi.altervista.org/bms/knowl ... enture.bms](https://aluigi.altervista.org/bms/knowledge_adventure.bms)

-Johnny
