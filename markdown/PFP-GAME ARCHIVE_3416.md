## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-03T11:31:43+00:00
- Post Title: PFP-GAME ARCHIVE

There are a lot of games utelizing 'n "PFP" data archive format. I have attached a small archive from "Dr. Daisy Pet Vet", although all games use the same archive format. Can anybody please assist writing an extractor for this archive type or symply include it into MultiEx Commander.

A sample PFP-archive can be downloaded here on one of our websites: [http://motionpress.com/pfp/game.rar](http://motionpress.com/pfp/game.rar).

I tried to upload it to xentax, even tried to cut it with the xentax cutter, but with no success.

Gourmania
Hot Dish 2
Nocturnal Boston Nightfall
NightShift legacy
Pet Shop Hop
Book of Legends
Chocolate Chase
Fashion Dash
The Clumsys
Mythic Marbles
Lost Reals - Legacy of the Sun Princess
Dr. Daisy Pet Vet (sample archive arrached - game.pfp)
Dream Chronicles
Wedding Dash
Hot Dish 2
Book of Legends
MahJonggs

Regards

Hendrik Pretorius
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-03T11:55:33+00:00
- Post Title: PFP-GAME ARCHIVE

can you attach a few sample archives to look at.
## Post #3
- Username: AoiMasamune
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 27, 2008 7:00 am
- Post datetime: 2009-04-03T13:26:54+00:00
- Post Title: PFP-GAME ARCHIVE

This is a really good example of the simplest archive format possible.

The archive begins with a 4 byte signature 'PFPK'.
Immediately after that is an 32 bit integer telling you how many files are in the archive.

Then it starts the file allocation table.
Each entry consists of:
Byte - Number of characters in the file's name.
String - File name.
Int32 - Address of the beginning of the file.
Int32 - Length of file in bytes.

No encryption. No compression. Quite boring actually.
This format should be a required task for an absolute newbie as an introduction to writing archive unpacking software.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-03T16:10:12+00:00
- Post Title: PFP-GAME ARCHIVE

You can just use a generic file ripper like jaeder Naub to rip the files.
I just tried it and it worked fine.
## Post #5
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-04T09:51:50+00:00
- Post Title: PFP-GAME ARCHIVE

I do use a generic ripper, but they don't extract the file structure and file names contained in the archive.

With regards to Jaeder Naub (integrated into MultiEx Commander), try running a scan on the pfp-file, and it return the following message: "JN No media found after scan!).

How do you re-pack files into a PFP-archive if you can only extract generic names?

Regards

Hendrik Pretorius
## Post #6
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-04T10:12:35+00:00
- Post Title: PFP-GAME ARCHIVE

AoiMasamune remarked above:"This format should be a required task for an absolute newbie as an introduction to writing archive unpacking software"

Please note that I do not post stuff here for others to evaluate on my intellect (I'm Vice-Chancellor of the Braxton University in South Africa, PhD) - games are just my hobby. 

XENTAX provides software to the public and donars called "MultiEx Commander". My original post clearly asked for this "simplest archive format possible" (sic.) - as you call it - to be incorporated into that software for those who don't have the technical capabilities so that it is available to them when they do come accross these archive formats.

Regards

Hendrik Pretorius
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-04T13:59:36+00:00
- Post Title: PFP-GAME ARCHIVE

I'm sure that AoiMasamune didn't refer to you but only to the file format.
from a technical point of view it's annoying when there are no proprietary encryptions or compressions involved in a file format, this is what he meant.
## Post #8
- Username: AoiMasamune
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 27, 2008 7:00 am
- Post datetime: 2009-04-04T17:09:26+00:00
- Post Title: PFP-GAME ARCHIVE

I meant no disrespect, truly. 

As Bugtest said, I was only talking about the the file format's simplicity. I made the mistake of assuming you were curious and possibly open to the idea of learning the trade yourself. It really would be a great format to cut your teeth on. I was only attempting to be helpful. 

I haven't actually used MultiEx Commander, as I reverse engineer all the archives I'm curious about myself and I write my own utilities. I really wouldn't want to write a plugin for it as I'd have to wrestle with a new programming language and that isn't exactly my favorite thing to do.

However, I'm considering writing an extractor for these files as an exercise to keep my skills sharp. Besides, an extractor that can also repack a file format is considerably more difficult than a ripper only, and I have limited experience in that area, so it might be fun.

Just be careful to not bite the hand that feeds you before you get fed.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-05T14:08:00+00:00
- Post Title: PFP-GAME ARCHIVE

in case someone still needs the extractor, the following is a script for quickbms:

```
get FILES long
for i = 0 < FILES
    get NAMESZ byte
    getdstring NAME NAMESZ
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
