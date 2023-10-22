## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-03-04T16:10:22+00:00
- Post Title: Knowledge Adventure .rsc files

For once, this is not a request, but rather something I managed to figure out on my own!

.rsc files, also used in Knowledge Adventure games, contain picture files, as well as what appear to be scene (.scn), actor (.atr), and script (.scr--not screensaver) files.

Structure:

```
uint32 {4}  - Number Of Files

// for each file
   char {12} - File Name // always 12 characters; NOT null-terminated, but could end with multiple nulls due to predetermined length
   uint32 {4} - File Offset
   uint32 {4} - File Size

// after [Number Of Files] blocks like above, data begins

```


A very straightforward structure, if I do say so myself--much easier than some other files I've looked at.

MultiEx script:

```
IDString 0 BWRF10 ;
Get NumFiles Long 0 ;
For I = 1 to NumFiles ;
GetDString FileName 12 0 ;
SavePos OffsetOffset 0 ;
Get FileOffset Long 0 ;
SavePos SizeOffset 0 ;
Get FileSize Long 0 ;
Log FileName FileOffset FileSize OffsetOffset SizeOffset;
Next I ;

```


Link (MEGA): [https://mega.nz/#!f9JTHSoS!bd5uVGRUbtDZ ... ZHZ7yNY4lI](https://mega.nz/#!f9JTHSoS!bd5uVGRUbtDZ61B7yhXgoHif3wVoz8lP-ZHZ7yNY4lI)

This format, like the .bal files I posted about before, is used in JumpStart games and possibly other Knowledge Adventure games as well. This particular one comes, again, from JumpStart 1st Grade Math.

NOTE: Some .rsc files won't contain any images, only scenes, actors, and scripts. Scripts can be viewed in any text editor (I personally swear by Notepad++, but any text editor can view it just fine). Incidentally, does anyone know what language those scripts are in? (Please don't say English.  I mean the scripting language.)
