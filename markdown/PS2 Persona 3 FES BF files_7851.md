## Post #1
- Username: drfail
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 13, 2011 5:17 am
- Post datetime: 2011-12-12T21:32:43+00:00
- Post Title: PS2 Persona 3 FES BF files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Sandersal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 09, 2012 8:44 am
- Post datetime: 2012-04-14T16:31:16+00:00
- Post Title: PS2 Persona 3 FES BF files

> Reply from drfail
>
> Hi all,

I'm a new member here (with 0 post counter doing a request right after he joins duh!!) ..anyway,
I've been "monitoring" xentax for quite a time and have read some tutorials,

I decided to edit Persona 3 FES' text files (the script), so I extracted the game's main CVM files (UltraISO did the job, and I repacked it using UltraISO and edited the header to CVM again, the game loaded for a bit then the emulator hanged...that's not our topic so lets ignore the CVM files for now)...

Enough for the intro, now:

I found out the text/script data is in BF files (BF files are in a directory named SCRIPT),



(there is a 519 bytes file, I think it'd be useful to use as a "dummy"/simple file).

and this is my work on it (using 010 editor as the tutorial suggested):
Code: Select alllong uk1; //All zeroes
long uk2; //4 different bytes for every file
char magic[4]; //"FLW0"

uint64 z1; //Match for all files

int uk3; //unknown (int?)

uint64 uk4; //Match for all files
uint64 uk5;

int uk6; //unknown (int?)

uint64 uk7; //Match for all files
uint uk8; //Always 32 for all files?

as for the editor, I'll write it myself (I know C#) but I need someone to help me figure out the file format since this is my first try.

Thank you!

I don´t know if you still need help. But I suggest you to edit the text directly with an HEX editor. Check the PM1 files for the main events dialogues and the BF files for the secondary events (Social Links, etc). It´s very easy to edit.

EDIT: However, the text has checkpoints. If you try to enlarge it, beware.
