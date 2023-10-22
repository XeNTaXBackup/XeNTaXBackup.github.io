## Post #1
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-22T10:21:22+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

Gibts es eine deutsche Anleitung zum erstellen von Plugins fÃ¼r den MultEx Commander 4.0.0?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-22T17:15:49+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

Du meinst das hier unten, aber auf Deutsch? 

[http://wiki.xentax.com/index.php/MexCom ... _Plugin.29](http://wiki.xentax.com/index.php/MexCom_Manual#Creating_your_own_ActiveX_DLL_Plug-in_.28MexCom_Plugin.29)

Nein das gibst es (noch) nicht. Vielleicht das Deniz dir helfen kan?
## Post #3
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-22T18:01:45+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

> Reply from Mr.Mouse
>
> Du meinst das hier unten, aber auf Deutsch? 

http://wiki.xentax.com/index.php/MexCom ... _Plugin.29

Nein das gibst es (noch) nicht. Vielleicht das Deniz dir helfen kan?
Ja genau den Artikel meine ich, bin gerade dabei von englisch auf deutsch zu Ã¼bersetzen(benutze dazu ein WÃ¶rterbuch, dauert etwas lÃ¤nger). 
Eine andere Frage habe ich noch, Funktionieren auch PlugIns die mit VB.NET geschrieben wurden?
## Post #4
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-27T09:32:44+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

I'm write a plugin for scrapland(in Vb.NET), but the MultiEx 4.0 don't accept the plugin.
Have registred the plugin as Com-Active Library(is work).
Open the *.packed file but the MultiEx crash (No Erros Message).
gives some other chance to start the plugin?
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-27T10:18:07+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

> Reply from xennex
>
> I'm write a plugin for scrapland(in Vb.NET), but the MultiEx 4.0 don't accept the plugin.
Have registred the plugin as Com-Active Library(is work).
Open the *.packed file but the MultiEx crash (No Erros Message).
gives some other chance to start the plugin?

Please mail me about this. Bitte email mich, und attach auch die Plugin  mahl sehn was loss ist.
## Post #6
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-28T17:22:18+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

Warum nimmt der MultiEx Commander Die Erweiterung *.Packed nicht an?
Habe dazu einen Ordner Namens packed erstellt und die ddl reinkopiert, aber die dll wird vom MultiEx nicht geladen.
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-28T18:29:59+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

> Reply from xennex
>
> Warum nimmt der MultiEx Commander Die Erweiterung *.Packed nicht an?
Habe dazu einen Ordner Namens packed erstellt und die ddl reinkopiert, aber die dll wird vom MultiEx nicht geladen.

MultiEx Commander nimmt das schon an, aber die dll is keine "multiex" plugin, und darum braucht MultiEx Commander auch nicht *.packed an zu nehmen.
## Post #8
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-28T19:17:21+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

Habe noch mal die DLL ausprobiert die ich in VB.NET geschrieben habe.
Die Funktioniert nur wenn ich vorher nur ein anderes archiv geÃ¶ffnet habe.
Den Source Code habe ich dir geschickt, aber anscheinen fehlen noch einpaar funktionen??????
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-28T20:40:27+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

> Reply from xennex
>
> Habe noch mal die DLL ausprobiert die ich in VB.NET geschrieben habe.
Die Funktioniert nur wenn ich vorher nur ein anderes archiv geÃ¶ffnet habe.
Den Source Code habe ich dir geschickt, aber anscheinen fehlen noch einpaar funktionen??????

Wirklich? Und was sagt den Debug Log dann? (CTRL+L)
## Post #10
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-28T20:47:53+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

22:44:49- Accessing archive 
22:44:49- Archive process format  PGN
22:44:49- PGN Calling 
22:44:49- PGN Register  F:\Programme\MultiEx Commander2\MultiEx Commander2\data\plugins\packed\Scrapland.dll
22:44:49- PGN Connect  Scrapland.archive
22:44:49[!]- PGN not valid  F:\Programme\MultiEx Commander2\MultiEx Commander2\data\plugins\packed\Scrapland.dll
22:44:50- Reinitializing MexCom

Mit der Funktion bnIdentify habe ich eine MessageBox eingebaut, die auch in MultiEx Angezeigt wird.
Dann folgt danach die Fehlermeldung.
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-28T21:18:59+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

> Reply from xennex
>
> 22:44:49- Accessing archive 
22:44:49- Archive process format  PGN
22:44:49- PGN Calling 
22:44:49- PGN Register  F:\Programme\MultiEx Commander2\MultiEx Commander2\data\plugins\packed\Scrapland.dll
22:44:49- PGN Connect  Scrapland.archive
22:44:49[!]- PGN not valid  F:\Programme\MultiEx Commander2\MultiEx Commander2\data\plugins\packed\Scrapland.dll
22:44:50- Reinitializing MexCom

Mit der Funktion bnIdentify habe ich eine MessageBox eingebaut, die auch in MultiEx Angezeigt wird.
Dann folgt danach die Fehlermeldung.

Aber das is ja interessant, MexCom kan schon die DLL anrufen. Hmm. Habe dich auch ein PM geschikt.
## Post #12
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-29T11:23:49+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

Suuuuuuuuuper, Danke fÃ¼r die PM.
Und ich habe schon den Fehler bei mir gefunden.
Geschrieben haben ich
Public Function iList(ByVal strPath As String, ByVal iType As Integer, ByVal iStdList() As String) As Long

Sollte aber so aussehen
Public Function iList(ByRef strPath As String, ByRef iType As Integer, ByRef iStdList() As String) As Long


Ein sehr peinlicher Fehler  
Das ich den Fehler nicht schon frÃ¼her gesehenhabe(ByVal->ByRef).
Und nochmals danke fÃ¼r die PM von erstellung COM-DLL

PlugIn funktioniert schon super.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-29T11:53:25+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

> Reply from xennex
>
> Suuuuuuuuuper, Danke fÃ¼r die PM.
Und ich habe schon den Fehler bei mir gefunden.
Geschrieben haben ich
Public Function iList(ByVal strPath As String, ByVal iType As Integer, ByVal iStdList() As String) As Long

Sollte aber so aussehen
Public Function iList(ByRef strPath As String, ByRef iType As Integer, ByRef iStdList() As String) As Long


Ein sehr peinlicher Fehler  
Das ich den Fehler nicht schon frÃ¼her gesehenhabe(ByVal->ByRef).
Und nochmals danke fÃ¼r die PM von erstellung COM-DLL

PlugIn funktioniert schon super.

Geil! Koentest du mir die funktionierende Plugin auch schicken? Dies ist das erste mal das Eine "externe coder" ne MexCom ActiveX Plugin geschrieben hat! Super! Die Plugin soll auch im naechste Verzion inkludiert werden!!
## Post #14
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-29T13:32:12+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

Ne Frage habe ich noch.
mit welcher funktion kann man den platzbedarf in der listView festlegen?
zb. 
es sind 1899 Dateien im Archiv und mÃ¶chte dann 1899 zeilen ausgeben.
mit
Public Overridable Function iList(ByRef strPath As String, ByRef iType As Integer, ByRef iStdList() As String) As Long

kann man nur die dateinamen und offsets etc. reinschreiben.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-29T13:37:22+00:00
- Post Title: Active-Plugin erstellen - Anleitung auf deutsch

> Reply from xennex
>
> Ne Frage habe ich noch.
mit welcher funktion kann man den platzbedarf in der listView festlegen?
zb. 
es sind 1899 Dateien im Archiv und mÃ¶chte dann 1899 zeilen ausgeben.
mit
Public Overridable Function iList(ByRef strPath As String, ByRef iType As Integer, ByRef iStdList() As String) As Long

kann man nur die dateinamen und offsets etc. reinschreiben.

Ich verstehe nicht was du meinst, was ist "platzbedarf"? (Immer wieder die Hollaender  )
## Post #16
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-29T13:43:00+00:00
- Post Title: 

Scherzkeks lol.
ich habe nur drei funktion geschrieben.
Public Function bnIdentify(ByVal strPath As String) As Boolean
Public Function bnPlugInfo(ByRef Info() As String)
Public Overridable Function iList(ByRef strPath As String, ByRef iType As Integer, ByRef iStdList() As String) As Long

einige Funktione fehlen mir noch.
weil wenn ich vorher ein anderes archiv Ã¶ffne die weniger als 1899 dateien hat und dann  mein plugin starte komm eine Fehlermeldung, aber nicht wenn ich ein archiv Ã¶ffnen die grÃ¶ÃŸer ist als 1899 dateien und dann mein plugin starte.
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-29T13:55:24+00:00
- Post Title: 

> Reply from xennex
>
> Scherzkeks lol.
ich habe nur drei funktion geschrieben.
Public Function bnIdentify(ByVal strPath As String) As Boolean
Public Function bnPlugInfo(ByRef Info() As String)
Public Overridable Function iList(ByRef strPath As String, ByRef iType As Integer, ByRef iStdList() As String) As Long

einige Funktione fehlen mir noch.
weil wenn ich vorher ein anderes archiv Ã¶ffnen dir weniger als 1899 dateien hat und dann  mein plugin starte komm eine Fehlermeldung, aber nicht wenn ich ein archiv Ã¶ffnen die grÃ¶ÃŸer ist als 1899 dateien.

Ah du meinst in MexCom! Das ist ja ein merkwurdiger Fehler in MexCom. Das soll ich mich vielleicht selber mal ansehen.
## Post #18
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-29T14:02:06+00:00
- Post Title: 

Ich meine es so.
ich Ã¶ffne mit MexCom ein Archiv(zb. SpellForce 2 *.pak)
die hat Ã¼ber 4000 dateien.
Ã¶ffnen dann mein archiv(Scrapland *.packed) enthÃ¤lt genau 1899 dateien.
funktioniert tadelos.
funktioniert aber nicht wenn ich vorher ein archiv Ã¶ffne das kleiner ist als 1899 dateien.
dann kommt die fehlermeldung
14:59:16- Accessing archive 
14:59:16- Archive process format  PGN
14:59:16- PGN Calling 
14:59:16- PGN Register  F:\Programme\MultiEx Commander2\MultiEx Commander2\data\plugins\packed\ClassLibrary1.dll
14:59:16- PGN Connect  ClassLibrary1.archive
14:59:16- PGN Info  Scrapland Packed Files Extractor by xennex version 1.0.1, type (2), importation(0), varsreturned(3), restypespec(0), cancreate(0)
14:59:16[!]- PGN not valid  F:\Programme\MultiEx Commander2\MultiEx Commander2\data\plugins\packed\ClassLibrary1.dll
14:59:18- Reinitializing MexCom
