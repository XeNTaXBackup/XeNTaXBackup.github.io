## Post #1
- Username: nightwish_oceanborn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 18, 2006 9:13 pm
- Post datetime: 2006-04-18T13:17:38+00:00
- Post Title: Harry Potter and the Goblet of Fire

Hi,
I really want to rip the textures but i don't know how.
I tried with multiexcommander,game extractor and dragon unpacker but i can't seem to find the texture files.
Can you help me???
Thanx Leonie
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-18T13:34:56+00:00
- Post Title: Harry Potter and the Goblet of Fire

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: nightwish_oceanborn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 18, 2006 9:13 pm
- Post datetime: 2006-04-19T12:03:11+00:00
- Post Title: Harry Potter and the Goblet of Fire

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-19T23:39:33+00:00
- Post Title: Harry Potter and the Goblet of Fire

Damn that was a big upload   

Hopefully there is a flaw in my specs.. but it does not appear so   

> ID - BIGF
>
> [4] - Int32 - File Size (Little Endian)?
>
> [4] - Int32 - Number of Table 1 Entries Package Container (Big Endian)
>
> [4] - Int32 - Table 1 Size (Offset not true Size) (Big Endian)
>
> [4] - Int32 - Offset to Hash? (Big Endian)
>
> [4] - Int32 - Hash? Size (Big Endian)
>
> 
>
> 
>
> Table 1 -
>
> 
>
> Loop~
>
> String - Null Terminated
>
> [4] - Int32 - Package Offset (Big Endian)
>
> [4] - Int32 - Package Size (Big Endian)
>
> End Loop
>
> 
>
> 
>
> From Package Offset(whatever)
>
> [4] - Int32 - Unknown (Little Endian?) <- Looks like an ID for what type of ENTRY (1820)
>
> [4] - Int32 - Header Size (Little Endian)
>
> [4] - Int32 - Unknown (Little Endian?)
>
> [4] - Int32 - # of Text Entries (Little Endian)
>
> 
>
> ~Strings - Null Terminated
>
> [4] - Int32 - Unknown <- Seems to pass data along somehow BF BF etc many combinations
>
> [4] - Int32 - Unknown <- Maybe an indication for another string to be read. (0 at end) (1 usually another string follows)
>
> 
>
> After this more data offsets follow: Begins as follows: almost the same as above
>
> [4] - Int32 - Unknown (Little Endian?) <- Looks like an ID for what type of ENTRY (1814)
>
> [8] - Bytes Uknown
>
> [4] - Int32 - Listing Size (Little Endian)
>
> [4] - Int32 - Dev String Size (Little Endian)
>
> ~Read Chars
>
> [4] - Int32 - Unknown <- Seems to pass data along somehow BF BF (again)
>
> [16] - Bytes Uknown
>
> [4] - Int32 - String Size some type of path/ File type string (Little Endian)
>
> ~ File path/ Type String
>
> [4] - Int32 - String Size Another Developer Type String(Little Endian)
>
> ~String
>
> [4] - Int32 - Unknown <- Seems to pass data along somehow BF BF (again)
>
> [12] - Bytes Uknown       <-- Not Static? Depends on Entry? Sometimes could be less or more
>
> [4] - Int32 - Data Size (Little Endian)
>
> ~ Data
>
> 
>
> 
>
> *if another file exists after ~data then it starts off reading from the 1814 entry. Above

Images Looked Like DXT ( I only Looked In Hex Editor but from what I saw looked like DXT )

*Heres hoping format doesn't hold up :p

**Edit... Yeah They Are DXT
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-20T01:40:10+00:00
- Post Title: Harry Potter and the Goblet of Fire

in my view they seems to be (atleast most of them) in FSH / SHPI format.
(some EA games image format).

but.....i may be blind =o ....
## Post #6
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-20T02:30:34+00:00
- Post Title: Harry Potter and the Goblet of Fire

> Reply from Strobe
>
> in my view they seems to be (atleast most of them) in FSH / SHPI format.
(some EA games image format).

but.....i may be blind =o ....

Nah it says FSH on the file and SHPI on the Type Tag, but I see DXT

Decimal Offset : 1088971 
[4] - Size of image
~ image (see attached (made header))
[harrypotterdxt3.zip](https://xentaxbackup.github.io/file/710_harrypotterdxt3.zip)
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-20T04:06:50+00:00
- Post Title: Harry Potter and the Goblet of Fire

Okay, you win :X

i first tried extracting the imagedata and attaching an own image header,
with DXT1 i got an very scrambled image, so i tested DXT3, and DXT5
and the reader refused to read them, so i thought "this cant be DXT"

but appearently i must have done something wrong with my
own hexxed DDS headers....hmmms... =o

im gonna take a look at yours.

EDIT:
Yups, DXT3 Images. the mistake i made was cutting too much of the beginning which i thought was part of the header, but it was DXT data. :X woops.
## Post #8
- Username: nightwish_oceanborn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 18, 2006 9:13 pm
- Post datetime: 2006-04-21T08:28:29+00:00
- Post Title: Harry Potter and the Goblet of Fire

how do i vieuw dtx3 files?
i'm sorry but i really don't have clue.
and thanx for helping
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-21T08:53:42+00:00
- Post Title: Harry Potter and the Goblet of Fire

Currently you cannot view them at all, as they are not stored as real DXT3 files in the archive, so first an extractor+converter is needed.
but when that is done you could just view them and edit in Photoshop
with an Nvidia DDS Plugin.

and the conversion process should be pretty simple. its just
adding an DDS header ontop of the DXT data.
## Post #10
- Username: nightwish_oceanborn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 18, 2006 9:13 pm
- Post datetime: 2006-04-21T10:32:37+00:00
- Post Title: Harry Potter and the Goblet of Fire

ok,thanx!!
What programs do i need to use?
I already have photoshop (cs2) and the dds plug-in.
## Post #11
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-21T10:47:06+00:00
- Post Title: Harry Potter and the Goblet of Fire

Sorry to say that i currently dont have a ripper/converter for this format yet.
maybe someone else has? =o

i will add a ripper for it with the next release of my own ripper,
but today i dont have the time. maybe on sunday or monday i might have this finished. even if someone allready have made a ripper for this
i will still add it , for compability reasons.

so you just have to wait a little while =/
## Post #12
- Username: nightwish_oceanborn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 18, 2006 9:13 pm
- Post datetime: 2006-04-21T13:04:52+00:00
- Post Title: Harry Potter and the Goblet of Fire

i don't mind waiting 
i think it's great your willing to make a ripper for this !!!
## Post #13
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2006-06-21T08:56:08+00:00
- Post Title: Harry Potter and the Goblet of Fire

can't find
## Post #14
- Username: primevalrex
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 14, 2009 7:25 pm
- Post datetime: 2009-06-26T08:42:18+00:00
- Post Title: Harry Potter and the Goblet of Fire

hi,
i want to have the mesh and the textures of that game aswell.
and i extracted the big file.
but all the things i got where str files.
and i already tried some converters but none worked of them.
when i extracted the big file those str files had textures in it but i could get them.
can someone help me please?
i really want that dragon model. :/
