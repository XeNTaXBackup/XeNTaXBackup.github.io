## Post #1
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2007-01-24T16:14:54+00:00
- Post Title: Problem mit Entropia Universe Archive

Ich habe ein Problem mit dem Archiv mit Entropia Universe.
Teilweise kann iich das Archiv schon lesen.

```
Int32 (4) Startoffset
Char  (4) Header (BNT2)
//Gehe zu Startoffset
  Int32 (4) anzahl der Dateien
// Wiederholung anzahl der dateien
  Char  (x) Dateiname (Solange wiederholen bis chr=10)
  int32 (4) Dateigröße
  int32 (4) Dateioffset
  int64 (8) Unbekannt
// Ende Wiederholung anzahl der dateien
Byte  (x) Datei

```

Das Problem besteht darin das ich nicht weiß wofür der Int64 wert steht, dachte erste das es eine Datei ID stimmt aber nicht, weill ich schon versucht habe eine andere datei zu ersetzen und mit dieser ID zu schreiben und das Spiel stürz abn kann mir da einer helfen?
[effectsequences.zip](https://xentaxbackup.github.io/file/1043_effectsequences.zip)
## Post #2
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2007-01-25T08:46:55+00:00
- Post Title: Problem mit Entropia Universe Archive

ok, i try in english.
i have a proplem with the game archive Entropia Universe, can extract but not replace(the game crash).
here is the gamearchive description

```
int32 (4) Start offset
char  (4) Header (BNT2)
//go to startoffset
  int32 (4) number of files
// for each file
  char  (x) filename (do while not char=10)
  int32 (4) file size
  int32 (4) file offset
  int64 (8) unknown
// End loop
byte  (x) File data

```

the problem is that i don't known what the int64 value is(Not file ID).
can anyone help me?
