## Post #1
- Username: TommyJ23
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 14, 2011 3:47 am
- Post datetime: 2011-07-25T11:07:54+00:00
- Post Title: Settlers III

Hi guys,
I need some help, to decompile this language file. The file is from the game Settlers III. Please help me to de/compile the file. Thank you.


File: [http://www.mediafire.com/?rb7jva2k485t3jf](http://www.mediafire.com/?rb7jva2k485t3jf)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-07-29T19:34:34+00:00
- Post Title: Settlers III

```
Get U1 Long 0 ;
Get U1 Long 0 ;
Get U1 Long 0 ;
Get EOFF Long 0 ;
Set S Long 48 ;
GoTo S 0 ;
Get TSIZE Long 0 ;
Get EOFF Long 0 ;
Get EEND Long 0 ;
GoTo EOFF 0 ;
Get U1 Long 0 ;
Get ESIZE Long 0 ;
Math ESIZE -= 12 ;
Math ESIZE /= 4 ;
Get U1 Long 0 ;
SavePos S 0 ;
For T = 1 To ESIZE ;
GoTo S 0 ;
Get FOFF Long 0 ;
SavePos S 0 ;
If T <> ESIZE ;
Get FSIZE Long 0 ;
Math FSIZE -= FOFF ;
Else ;
Set FSIZE Long EEND ;
Math FSIZE -= FOFF ;
EndIf;
Set NAME Long T ;
String NAME += ".txt" ;
Log NAME FOFF FSIZE 0 0 ;
Next T ;

```


Use the above script in MultiEx Commander to extract text files like this:

```


SIEGBEDINGUNG: 
Erobern Sie die ganze Insel! 

 NIEDERLAGEBEDINGUNG: 
Ihre Siedlung wurde komplett zerstört. 

 SITUATION:
 Im Nordwesten hat sich bereits eine kleine römische Siedlung (R) entwickelt. Leider verfügt diese Siedlung über die einzige Goldlagerstätte auf der Insel. Sie  sollten also nicht so lange herumtrödeln, bis Ihr Gegner übermächtig wird.

1. TAGEBUCHEINTRAG DES SEPTIMUS MARIUS:
 Ich weiß nicht, was passiert ist. Gestern noch war ich Kapitän eines Handelsschiffes, befuhr die See - und das war alles, was ich jemals tun wollte. Ich war frei. Ich sah entfernte Länder, die andere nur vom Hörensagen kennen. Ich war glücklich.
 Dank Jupiter bin ich jetzt ein Herrscher, gebunden durch die Pflicht, ein fremdes Land zu regieren. Daß es fremd ist, ist egal. Ich bin die Fremde gewohnt. Aber ich soll hier herrschen, Krieg führen und siegen. Für Jupiter: höhere Ehre. Für mich: nur ein Test. Und am Ende Freiheit oder Untergang. Wie bei jeder Seereise...
 Ich weiß nicht, ob ich ein fähiger Feldherr bin, mir bleibt als Anker nur die Hoffnung. Aber wenn Hannibal, dieser Alptraum Roms, der größte aller Strategen, einer Familie von Händlern entspringen konnte, warum dann nicht auch ich? Und momentan ist mein Reich ja sowieso noch nicht viel größer als so manches Schiff, daß ich kommandiert habe... 
```
