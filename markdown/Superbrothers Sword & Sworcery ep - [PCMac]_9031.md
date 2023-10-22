## Post #1
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2012-06-03T17:45:40+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

Could someone explain to me how to translate this game?

Thanks so much!!
## Post #2
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-06-03T20:16:32+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

Unzip sworcery.dat (pass: GdHGhd4yuNF) and translate files
## Post #3
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2012-06-04T16:24:46+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

> Unzip sworcery.dat (pass: GdHGhd4yuNF) and translate files

GREAT!! Thanks!!! And then, how can i re-create the sworcery.dat file?
## Post #4
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-06-04T20:24:30+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

ehm zip data back with password and rename .zip to .dat?
## Post #5
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2012-06-04T20:28:31+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

> ehm zip data back with password and rename .zip to .dat?

Mmmhh I tried today but it did not work when starting the game, I'll try again later, thanks!
## Post #6
- Username: Espresso
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 10, 2012 5:27 pm
- Post datetime: 2012-06-10T14:40:08+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

With te sworcery.dat file comes also sworcery.dat.cat file and I think there lies the problem. Checksums poropably, but I'm not programmer. Mayby someone can confirm?

And guys, can someone write simple extract/import apilication? It would be great!

I guess I could provide sworcery.dat and sworcery.dat.cat
## Post #7
- Username: Violotodo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 31, 2012 8:45 am
- Post datetime: 2012-07-31T00:49:04+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

> Reply from Espresso
>
> With te sworcery.dat file comes also sworcery.dat.cat file and I think there lies the problem. Checksums poropably, but I'm not programmer. Mayby someone can confirm?

And guys, can someone write simple extract/import apilication? It would be great!

I guess I could provide sworcery.dat and sworcery.dat.cat


I also I have the same problem of verification, if I change anything sworcery.dat not work the game, I hope someone can help

by the way this is translated to the online translator, sorry if not well understood
## Post #8
- Username: Gimlao
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 10, 2014 9:26 am
- Post datetime: 2015-02-01T22:43:10+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

» [How to rebuild sworcery.dat.cat](http://steamcommunity.com/app/204060/discussions/0/392183857627067270/) «

Now everyone can translate the game ! \o/
## Post #9
- Username: Espresso
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 10, 2012 5:27 pm
- Post datetime: 2015-02-02T07:22:22+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

> Reply from Gimlao
>
> I recently found how to rebuild the sworcery.dat.cat file : https://db.tt/GXuRUkJ0
sworcery.rar wrote:7za.exe
7-Zip Command Line Version

rebuild_cat.exe
Source : http://www.hwupgrade.it/forum/showpost. ... stcount=36

EXTRACT.bat
Code: Select all7za x sworcery.dat locales\dialog.tsv -pGdHGhd4yuNF
7za x sworcery.dat locales\strings.tsv -pGdHGhd4yuNF
INSTALL.bat
Code: Select alldel sworcery.zip.tmp
del sworcery.dat.cat
ren sworcery.dat sworcery.zip
7za d sworcery.zip locales\dialog.tsv -pGdHGhd4yuNF
7za d sworcery.zip locales\strings.tsv -pGdHGhd4yuNF
7za a sworcery.zip locales\dialog.tsv -pGdHGhd4yuNF
7za a sworcery.zip locales\strings.tsv -pGdHGhd4yuNF
ren sworcery.zip sworcery.dat
rebuild_cat.exe

So I just write this lines in notepad and save as bat files?
## Post #10
- Username: Espresso
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 10, 2012 5:27 pm
- Post datetime: 2015-02-02T14:37:01+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

This doesn't work for me.
Extract does not extract, but I can do it by myself. Install.bat only deletes sworcery.dat.cat and don't even change the sworcery.dat

IDK what am I doing wrong. Please help.

Edit:
Sorry I didn't see the link to dropbox
## Post #11
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2017-05-11T00:21:58+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

Who knows how to force the game to use capital/lower letters for foreign translations?
Here is the issue with foreign characters: [http://steamcommunity.com/app/204060/di ... 5541443233](http://steamcommunity.com/app/204060/discussions/0/364042703855248638/#c357287935541443233)
## Post #12
- Username: Gimlao
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 10, 2014 9:26 am
- Post datetime: 2018-02-03T22:14:32+00:00
- Post Title: Superbrothers Sword & Sworcery ep - [PC/Mac]

"How to translate" now here :

[http://steamcommunity.com/app/204060/di ... 627067270/](http://steamcommunity.com/app/204060/discussions/0/392183857627067270/)

Also moved the rar file from Dropbox to Google Drive.
