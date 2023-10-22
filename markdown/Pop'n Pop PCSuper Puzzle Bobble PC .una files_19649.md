## Post #1
- Username: QuoteDaBot
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 14, 2019 3:31 am
- Post datetime: 2019-03-13T19:38:52+00:00
- Post Title: Pop'n Pop PC/Super Puzzle Bobble PC .una files

I've been trying to crack open Pop'n Pop's PC port to try and fix the PC port somewhat, and while the PS1 version uses a more standard file layout, the .una files on the PC version have stumped me. Dragon Unpacker and Game Extractor can't make sense of the files, and looking at the .una files in a hex editor, I can see file names. I also noticed the PC version of Super Puzzle Bobble also uses the same, if not a very similar file archive. Can anyone make sense of this?

[https://mega.nz/#!5qBFlA6Y!zQplLSMF07Kb ... LxtQQtc3Vs](https://mega.nz/#!5qBFlA6Y!zQplLSMF07KbOtBuGLC2DhoXiErTCtBkJLxtQQtc3Vs)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-14T01:04:24+00:00
- Post Title: Pop'n Pop PC/Super Puzzle Bobble PC .una files

this bms script will extract the files from your una sample.  

```

get FOLDER basename
idstring "\x55\x4e\x41\x00\x30\x30\x31\x00"
get FILES long
getdstring ZERO 0x14 
for i = 0 < FILES
    getdstring NAME 0x20
    get OFFSET long
    get SIZE long
    getdstring ZERO 0x8
    string NAME p "%s\%s" FOLDER NAME
    log NAME OFFSET SIZE
next i

```

i don't know about the files content though.
