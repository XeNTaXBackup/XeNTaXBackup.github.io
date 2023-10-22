## Post #1
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2011-03-24T15:48:44+00:00
- Post Title: Pac file - Ken's rage xbox 360

Hello, I Have problem with the .pac file of ken's rage for xbox360. How can I extract the files inside?
it is name voice.pac  and so it may contain only audio file. Could  you help me?thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-24T22:29:27+00:00
- Post Title: Pac file - Ken's rage xbox 360

you must provide a file or a cut of it
## Post #3
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2011-03-24T23:13:57+00:00
- Post Title: Pac file - Ken's rage xbox 360

it's one file of 230 mb, how can I open it?

this is the file
[http://www.megaupload.com/?d=VFZX38Q4](http://www.megaupload.com/?d=VFZX38Q4)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-25T07:22:00+00:00
- Post Title: Pac file - Ken's rage xbox 360

there is no information table, which means that there is an index file somewhere in the folder.
anyway for this specific archive it's enough a normal scanner because the files inside are all wav or you can use the following script that does the same job (only for this archive!):

```
reverselong FILES
for i = 0 < FILES
    padding 0x800
    savepos OFFSET
    getdstring RIFF_SIGN 4
    get SIZE long
    math SIZE += 8
    log "" OFFSET SIZE
    math OFFSET += SIZE
    goto OFFSET
next i
```
## Post #5
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2011-03-25T11:25:26+00:00
- Post Title: Pac file - Ken's rage xbox 360

I tried with this script using quickbms thanks a lot, you are great 

now I have 6000 files with extension .dat, how can I open it?
[http://hotfile.com/dl/111778556/ebde06a ... b.dat.html](http://hotfile.com/dl/111778556/ebde06a/00000a2b.dat.html)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-25T11:44:14+00:00
- Post Title: Pac file - Ken's rage xbox 360

the dat extension is no longer used in quickbms by long time, I guess it's time for you to update :)
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #7
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2011-03-25T12:14:56+00:00
- Post Title: Pac file - Ken's rage xbox 360

thank you a lot. Now I have 6000 file .wav but they aren't playble. I'm not expert sorry
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-25T14:43:55+00:00
- Post Title: Pac file - Ken's rage xbox 360

if I remember correctly (no longer have them) they are XMA files so refer to the guides available online and on xentax about this format/codec
## Post #9
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2011-03-25T15:06:49+00:00
- Post Title: Pac file - Ken's rage xbox 360

> Reply from aluigi
>
> if I remember correctly (no longer have them) they are XMA files so refer to the guides available online and on xentax about this format/codec

Aspetta un attimo, adesso che ci penso, ma tu sei italiano? Comunque grazie dell'aiuto.

Thank you
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-25T16:11:14+00:00
- Post Title: Pac file - Ken's rage xbox 360

ah ah ah essi' che sono italiano :)

comunque il comando per xmaencode e':
xmaencode.exe /X output.wav input_xma.wav

xmaencode si trova nell'sdk dell'xbox ma lo si trova in giro ma, cosa piu' importante, NON e' garantito che converta quindi aspettati errori e testate contro al muro.
per il resto nella sezione audio dove hai postato ti sapranno dare tutte le info perche' con altri giochi come guitar hero e' la stessa cosa e ci sono vari tool da utilizzare.
purtroppo non ti posso aiutare di piu' perche' io mi occupo solo di archivi e crittazioni
## Post #11
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2011-03-25T16:44:16+00:00
- Post Title: Pac file - Ken's rage xbox 360

ahahah stavo facendo una fatica a scrivere in inglese 

Comunque adesso ti spiego meglio: Quando ho provato ad estrarre i file dal voice.pac la prima volta mi ha dato tutti files.dat  poi quando mi hai suggerito di aggiornare la versione me li ha dati tutti .wav  il problema è che non li riesco ad ascoltare, non partono proprio, è come se non fosse wav. Possibile?

Comunque ho scaricato xmaencode ma quando ci clicco sopra compare una schermata nera ma scompare subito e non riesco a leggere nulla.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-25T18:18:08+00:00
- Post Title: Pac file - Ken's rage xbox 360

e' perfettamente normale che tu non riesca ad ascoltarli.

in pratica i file WAV sono dei contenitori esattamente come gli AVI, ossia dentro possono avere dati audio codificati con vari codec in modo da usare meno spazio.
ad esempio ci sono file WAV che contengono dati ima_adpcm (uno dei codec), oppure msadpcm, oppure PCM (senza compressione) o persino codec sconosciuti.

in questo caso il codec in uso e' XMA o se non erro XMA2.

xmaencode e' un tool che funziona da riga di comando quindi devi lanciarlo da console.
e' semplicissimo ma casomai hai qualche dubbio dai un'occhiata su [http://aluigi.org/about.htm#howuse](http://aluigi.org/about.htm#howuse) oppure cerca una guida in italiano, tanto dopo 5 minuti vedrai che e' piu' semplice che usare i programmi visuali.
## Post #13
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2011-04-07T10:38:01+00:00
- Post Title: Pac file - Ken's rage xbox 360

ciao scusami se ti disturbo ancora, ma ci sono ancora dei problemi, in pratica mi hanno detto che l'header del file pac è sbagliato, da cosa può dipendere?
Comunque voglio fare una prova, cioè estrarre di nuovo il materiale del "linkdata.a" del gioco: per questo tipo di file c'è uno script ad hoc?Versione xbox360
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-07T11:55:41+00:00
- Post Title: Pac file - Ken's rage xbox 360

io non ho altri script
## Post #15
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2011-04-08T16:39:12+00:00
- Post Title: Pac file - Ken's rage xbox 360

The contents of this post was deleted because of possible forum rules violation.
