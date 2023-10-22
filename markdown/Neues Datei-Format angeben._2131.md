## Post #1
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-05T22:09:44+00:00
- Post Title: Neues Datei-Format angeben.

Ich habe leide keine groÃŸe Engisch Kenntnisse, aber vieleicht kann mir ja einer helfen wie man ein neues Datei-Format anlegen kann.
Wollte das Spiel Scrapland hinzufÃ¼gen, aber ich kann die Ãœberschrift "adding new formats" nicht Ã¤ndern.
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-10-06T00:25:00+00:00
- Post Title: Neues Datei-Format angeben.

Not to be rude, but could you please post in English? (either that, or someone who knows German (at leaast, I think that's what he posted in...) could just 'reach over my head' and handle his request in the same language...)
## Post #3
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-06T08:32:11+00:00
- Post Title: Neues Datei-Format angeben.

@Dinoguy1000: Translated, his first sentence reads "Unfortunately, I don't have great knowledge of English". 
Seems like he has problems adding a new file format somewhere ...

@Xennex: KÃ¶nntest Du noch kurz sagen, wo genau Du Schwierigkeiten hast? Versuchst Du ein neues Format ins Wiki einzutragen?
## Post #4
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-06T15:20:48+00:00
- Post Title: Neues Datei-Format angeben.

> Reply from Deniz Oezmen
>
> @Dinoguy1000: Translated, his first sentence reads "Unfortunately, I don't have great knowledge of English". 
Seems like he has problems adding a new file format somewhere ...

@Xennex: KÃ¶nntest Du noch kurz sagen, wo genau Du Schwierigkeiten hast? Versuchst Du ein neues Format ins Wiki einzutragen?
Auf der Seite GRAFs steht das man ein neues Format anlegen oder ein vorhandenes bearbeiten kann.
Ich wollte erst das Spiel eingeben dann die erweiterung.
Das Problem ist nur, dass ich "Adding a Format" nicht bearbeiten kann sondern nur von 
== Introduction == 
bis 
=== The Last Step ===
vieleicht kann es ja ein anderer Ã¼bernehmen.

Hier der Code

Spieltitel: Scrapland
Dateierweiterung: *.packed
Formattyp: Archiv

4 Byte - Header(BFPK)
4 Byte - Nullen
4 int32 - Anzahl der Dateien

// Solange wiederholden bis Anzahl der Dateien
  4 int32 - VerzeichnisnamenlÃ¤nge = X1
  X1 Byte - Verzeichnisname
  4 int32 - DateigrÃ¶ÃŸe
  4 int32 - Datei-Offset

// Datei
X Byte - Datei
// Ende
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-06T15:36:16+00:00
- Post Title: Neues Datei-Format angeben.

Also, ich probier einmal auf Deutsch zu reden. Ich hoffe das klapt. 

Du sollst ein neue page machen, and da das template einfuhren:

```
file_extension=FILE EXTENSION|
format_type=Archive|
endian_order=Little Endian|
date_posted=~~~~~|
format_specifications=None written yet.|
notes=None|
bms_script=Not written yet|
programs=None|
documentation=None|
games=None
}}
```


Und dann jeder "item" specifizieren, wie so:

```
file_extension=packed|
format_type=Archive|
endian_order=Little Endian|
date_posted=~~~~~|
format_specifications=4 Byte - Header(BFPK)
4 Byte - Nullen
4 int32 - Anzahl der Dateien

// Solange wiederholden bis Anzahl der Dateien
4 int32 - VerzeichnisnamenlÃ¤nge = X1
X1 Byte - Verzeichnisname
4 int32 - DateigrÃ¶ÃŸe
4 int32 - Datei-Offset

// Datei
X Byte - Datei
// Ende|
notes=None|
bms_script=Not written yet|
programs=None|
documentation=None|
games=Scrapland
}}
```


Vieleicht das Deniz das besser auf Deutsch kann erklaern.
## Post #6
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-06T15:42:47+00:00
- Post Title: Neues Datei-Format angeben.

Ich weiÃŸ nicht, ob ih Dich ganz richtig verstanden habe, aber die Seite "Adding a format" soll auch nicht bearbeitet werden.

Ich gehe im folgenden davon aus, daÃŸ Du ein Konto auf dem Wiki eingerichtet; ich weiÃŸ nicht, ob man sonst alles frei Ã¤ndern kann:

1. Gehe auf die GRAFs-Seite, auf die Dein Spiel eingetragen werden soll. In Deinem Fall wÃ¤re das [http://wiki.xentax.com/index.php/GRAFs/S](http://wiki.xentax.com/index.php/GRAFs/S). Diese Seite editierst Du und fÃ¼gst an alphabetisch passender Stelle einen neuen Link ein. Hier wÃ¼rde sich

```
* Scrapland (<b> [[Scrapland PACKED|*.packed]] </b>)
```

anbieten.

2. Wenn Du diese Ã„nderungen Ã¼bernommen hast, sollte in der Liste der von Dir hinzugefÃ¼gte Eintrag als roter Link erscheinen. Wenn Du ihn anklickst, kommst Du zur eigentlichen Bearbeitungsseite. Dort fÃ¼gst Du zunÃ¤chst das Template-GerÃ¼st ein:

```
file_extension=FILE EXTENSION|
format_type=Archive|
endian_order=Little Endian|
date_posted=~~~~~|
format_specifications=None written yet.|
notes=None|
bms_script=Not written yet|
programs=None|
documentation=None|
games=None
}}
```


3. ... und ich sehe gerade, daÃŸ Mr.Mouse in der Zwischenzeit die weiteren Details schon beschrieben hat. 

Ich hoffe, das Prozedere ist dadurch etwas klarer geworden -- wenn nicht, einfach nochmal rÃ¼ckfragen. Am Anfang ist "wiki-en" etwas gewÃ¶hnungsbedÃ¼rftig. Ein biÃŸchen basteln zahlt sich aber aus.

@all: Only now did I notice that we have some kind of templates ... which means I entered all recent formats in a malformed manner. Oh well ... later.
## Post #7
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-06T16:14:44+00:00
- Post Title: Neues Datei-Format angeben.

Habe es endlich hinbekommen, die MenÃ¼ fÃ¼hrung war etwas umstÃ¤ndlich.
Werde es mit ein bischen Englisch Hinbekommen.
Danke an euch allen

And Mr.Mouse your german is very good
## Post #8
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-10-06T20:14:15+00:00
- Post Title: Neues Datei-Format angeben.

> Reply from Deniz Oezmen
>
> @Dinoguy1000: Translated, his first sentence reads "Unfortunately, I don't have great knowledge of English". 
Seems like he has problems adding a new file format somewhere ...
Heh, seems like I need to learn German... 

> @all: Only now did I notice that we have some kind of templates ... which means I entered all recent formats in a malformed manner. Oh well ... later.
Eh... don't worry about it too much, I'm working on a new template anyways, as that one has some issues with section edits (namely taking you to editing the template itself, instead of the GRAF page).

@anyone: I got the (really) general gist of what was discussed here (xennex had a problem posting a new GRAf entry on the WIKI, Mr.Mouse pointed out my template and how to use it, other people said other stuff), but I was wondering if anyone could summarise it for me, so I have a somewhat better idea of what happened? Plz and thx?
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-06T21:59:47+00:00
- Post Title: Neues Datei-Format angeben.

> Reply from Dinoguy1000
>
> Eh... don't worry about it too much, I'm working on a new template anyways
In that case I'll keep myself from rewriting everything. 

> Reply from Dinoguy1000
>
> I was wondering if anyone could summarise it for me, so I have a somewhat better idea of what happened?
Basically, Xennex misunderstood the directions at the "Adding a format" page a bit: He thought he had to edit that page itself (or the template page, for that matter) rather than the GRAFs page or the actual article page. Mr.Mouse and me pointed this out a bit more clearly.

I can't really tell whether the directions are at fault (regarding first-time Wiki editors) or if this was merely a language problem.


@Xennex: Vielen Dank fÃ¼r Deinen Eintrag. UnterstÃ¼tzung ist immer willkommen.
## Post #10
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-10-06T22:42:02+00:00
- Post Title: Neues Datei-Format angeben.

> Reply from Deniz Oezmen
>
> Dinoguy1000 wrote:I was wondering if anyone could summarise it for me, so I have a somewhat better idea of what happened?
Basically, Xennex misunderstood the directions at the "Adding a format" page a bit: He thought he had to edit that page itself (or the template page, for that matter) rather than the GRAFs page or the actual article page. Mr.Mouse and me pointed this out a bit more clearly.

I can't really tell whether the directions are at fault (regarding first-time Wiki editors) or if this was merely a language problem.
Well, you're free to review and revise them, if you want... I have a horrible problem of being able to quite clearly know what I want to write for tutorials, but when it comes to actually writing them, I just blank. And yet, I've never had that problem with tests in school...
## Post #11
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-07T12:30:20+00:00
- Post Title: Neues Datei-Format angeben.

> Reply from Dinoguy1000
>
> Well, you're free to review and revise them, if you want... I have a horrible problem of being able to quite clearly know what I want to write for tutorials, but when it comes to actually writing them, I just blank. And yet, I've never had that problem with tests in school...
I think the instructions are quite clear and well-written, but maybe you should ask somebody who doesn't already know how to edit this particular wiki.

Explaining something one already knows is a surprisingly hard thing to do. Nevertheless, I think you did a good job with that article!
## Post #12
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-10-10T06:54:29+00:00
- Post Title: Neues Datei-Format angeben.

Thanks, I worked quite hard on getting it to sound right, and I've recently been thinking about a rewrite to incorporate the FAQ section at the right into the main body, as well as introduce some new information. I'd definitely have to agree with writing about what you know being hard!
## Post #13
- Username: diegoc
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 03, 2006 1:22 am
- Post datetime: 2006-12-02T17:29:14+00:00
- Post Title: Neues Datei-Format angeben.

Hi
Is possible view and extract the files in the Scrapland game? How?

Thanks in advance
## Post #14
- Username: Nukem
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 28, 2006 9:00 pm
- Post datetime: 2007-02-13T12:30:34+00:00
- Post Title: Neues Datei-Format angeben.

> Reply from diegoc
>
> Hi
Is possible view and extract the files in the Scrapland game? How?

Thanks in advance

I'd guess you use the BMS script from [http://wiki.xentax.com/index.php/Scrapland_PACKED](http://wiki.xentax.com/index.php/Scrapland_PACKED) with the program here, but I'm a newbie myself, so that may be wrong...
