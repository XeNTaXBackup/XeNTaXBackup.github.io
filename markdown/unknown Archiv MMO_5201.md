## Post #1
- Username: kataclysm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 13, 2010 9:27 pm
- Post datetime: 2010-10-13T13:45:00+00:00
- Post Title: unknown Archiv MMO

Hi

since im new to that ... some questions.
THX 4 Help

........

Archiv Files:
Data.lrs (47 MB)
Data.lrf (1,4 GB)

Filecutter (attachment):


 archiv.7z
(51.16 KiB) Downloaded 26 times



........

Both Files are not encrypted.
Data.lrs: various file paths included
Data.lrf: only data included

........

maybe there are only a few bits added / removed:
all fileformats included in the client (bmps , tgas, etc) have been editet like this (there have just a few bits been added bevore the headers) + rename to fantasy fileformat...
so i guess the archiv has been modified in a similar way.
But all modifications @ files and attemps to extract via various tools resulted negative

........

I´ve decompiled the game.exe
tried to find out how the exe is accessing the archiv
no chance untill now ... :/

Thx 4 help / ideas
sry for bad english
## Post #2
- Username: kataclysm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 13, 2010 9:27 pm
- Post datetime: 2010-10-13T18:03:39+00:00
- Post Title: unknown Archiv MMO

*update*

traced the exe
start: first call of ".lrs" / ".lrf"
eof: random loading of files out of the archiv *i guess*


 trace.7z
(37.05 KiB) Downloaded 26 times
## Post #3
- Username: kataclysm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 13, 2010 9:27 pm
- Post datetime: 2010-10-15T12:49:42+00:00
- Post Title: unknown Archiv MMO

*update*

game.exe loaded into OllyDBG 2
Search for -> Names

All the imports and exports @ dll s are listed now.

plus:

```
Adress: 00400120 Type: Analyser | Name: <STRUCT IMAGE_NT_SIGNATURE>
Adress: 00400124 Type: Analyser | Name: <STRUCT IMAGE_FILE_HEADER>
Adress: 00400138 Type: Analyser | Name: <STRUCT IMAGE_OPTIONAL_HEADER>
Adress: 00400198 Type: Analyser | Name: <STRUCT IMAGE_DATA_DIRECTORY>
Adress: 00400218 Type: Analyser | Name: <STRUCT IMAGE_SECTION_HEADER>
Adress: 00400240 Type: Analyser | Name: <STRUCT IMAGE_SECTION_HEADER>
Adress: 00400268 Type: Analyser | Name: <STRUCT IMAGE_SECTION_HEADER>
Adress: 00400290 Type: Analyser | Name: <STRUCT IMAGE_SECTION_HEADER>

```


maybe they can tell me what to do? (asm)
but where can i find the code?
first visible address in modul game (cpu main thread) is 00401000
(in executable modules list the base of modul game is: 00400000 - so if it´s there ... how can i take a closer look?)

crypt.32.dll is also listed @ executable modules list. but no imports /exports.
## Post #4
- Username: kataclysm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 13, 2010 9:27 pm
- Post datetime: 2010-10-23T00:08:10+00:00
- Post Title: unknown Archiv MMO

*update*

found out what these analyser types are

since noone is able to help ... so it seems ... im trying now to identify the archiv access related functions within the main.exe.

... any tipps, infos or help would be nice
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-23T00:55:32+00:00
- Post Title: unknown Archiv MMO

what is the mmo
## Post #6
- Username: kataclysm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 13, 2010 9:27 pm
- Post datetime: 2010-10-24T12:24:20+00:00
- Post Title: unknown Archiv MMO

Laghaim Korea

*update*
at about 95% of the games functions are restored now
going deeper into it...
## Post #7
- Username: kataclysm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 13, 2010 9:27 pm
- Post datetime: 2010-12-17T11:28:29+00:00
- Post Title: unknown Archiv MMO

*update*

had not much time the last months but i found what ive searched for.
And ive learned a lot since then XD

Unfortunatly I dont have enough time to learn c++ as well to write a tool 
+ understand exactly what the pseudocode functions do that ive localised responsible for archiv file eccess.

Im not sure if i should post this stuff here cause its public and thats a lot of code but if someone likes to take a look at it ... (and create `n extractor tool  )
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-17T18:44:12+00:00
- Post Title: unknown Archiv MMO

post what you found and someone may be able to help.
## Post #9
- Username: kataclysm
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 13, 2010 9:27 pm
- Post datetime: 2010-12-19T05:17:13+00:00
- Post Title: unknown Archiv MMO

hm as mentioned thats a lot of stuff ...

there are a lot functions following plus the needed links to the used global variables in the data area of the game.exe (+ the functions injecting values in these ones) ...
## Post #10
- Username: bigsam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 26, 2012 2:29 am
- Post datetime: 2012-07-25T18:38:55+00:00
- Post Title: unknown Archiv MMO

kataclysm, do you still have this information?
And do you have any update about this matter?
