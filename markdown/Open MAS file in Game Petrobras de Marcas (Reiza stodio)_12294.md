## Post #1
- Username: Ha3aP
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 02, 2013 1:40 am
- Post datetime: 2014-11-30T15:48:37+00:00
- Post Title: Open MAS file in Game Petrobras de Marcas (Reiza stodio)

Hello!
Do you now how open MAS in this game (reiza studio)?
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-30T22:12:19+00:00
- Post Title: Open MAS file in Game Petrobras de Marcas (Reiza stodio)

I don't think there is an importer for this format.
Can you send some sample MAS files?
## Post #3
- Username: Ha3aP
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 02, 2013 1:40 am
- Post datetime: 2014-12-01T16:00:24+00:00
- Post Title: Open MAS file in Game Petrobras de Marcas (Reiza stodio)

> Reply from barti
>
> I don't think there is an importer for this format.
Can you send some sample MAS files?
[MAS](https://www.dropbox.com/s/8ovjd5l61de0jdv/Marcas_Common.zip?dl=0) file link
[Game link](http://www.gamemarcas.com.br/index.php/en/downloads-en) (free game)
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-01T23:21:46+00:00
- Post Title: Open MAS file in Game Petrobras de Marcas (Reiza stodio)

MAS QuickBMS script:

```

goto 16
get DUMMY   long
get FILES   long
get BASEOFF long

for i = 0 < files
	get DUMMY long # 0x14
	getdstring NAME 236
	get RELOFF long
	get SIZE   long
	get ZSIZE  long
	get DUMMY  long

	xmath OFFSET "FSIZE - BASEOFF + RELOFF"
	clog NAME OFFSET ZSIZE SIZE
next i
```


There are textures in sample file, but no models.
## Post #5
- Username: Ha3aP
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 02, 2013 1:40 am
- Post datetime: 2014-12-02T16:56:18+00:00
- Post Title: Open MAS file in Game Petrobras de Marcas (Reiza stodio)

> Reply from barti
>
> MAS QuickBMS script:
Wow! TNX!!!

This [zip](https://www.dropbox.com/s/5pn1o72iy3l4ozh/Marcas_Corolla.zip?dl=0) wight 3d model (gmt). Your script model do not unlocks.
## Post #6
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-02T19:57:46+00:00
- Post Title: Open MAS file in Game Petrobras de Marcas (Reiza stodio)

I actually realized this game is using rFactor's engine. You need aluigi's [rfactordec](http://aluigi.altervista.org/papers.htm#gmotor2) to decrypt these .gmt files. Then you can load them, for example in Zmodeler2.
## Post #7
- Username: Ha3aP
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 02, 2013 1:40 am
- Post datetime: 2014-12-02T20:06:33+00:00
- Post Title: Open MAS file in Game Petrobras de Marcas (Reiza stodio)

> Reply from barti
>
> I actually realized this game is using rFactor's engine. You need aluigi's rfactordec to decrypt these .gmt files. Then you can load them, for example in Zmodeler2. TNX!!!
