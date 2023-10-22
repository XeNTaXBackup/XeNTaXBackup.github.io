## Post #1
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-01T05:08:19+00:00
- Post Title: Tales of VS MGZ/Chain

Could someone take a look and see if there's a way to extract the model files?
[http://dl.dropbox.com/u/32409323/tovs.7z](http://dl.dropbox.com/u/32409323/tovs.7z)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-07-11T18:30:58+00:00
- Post Title: Tales of VS MGZ/Chain

Not sure if it works for all *.mgz. but works for your only one sample!!!

```
idstring "SIZE"
get USIZE long
savepos OFSRES 
get CSIZE asize
math CSIZE -= 8
clog RESNAME OFSRES CSIZE USIZE
```
## Post #3
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-11T21:50:37+00:00
- Post Title: Tales of VS MGZ/Chain

Thank you! Th is a BSM script right?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-12T01:12:40+00:00
- Post Title: Tales of VS MGZ/Chain

yes
## Post #5
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-30T23:34:49+00:00
- Post Title: Tales of VS MGZ/Chain

Thanks it works, but it leaves me with a .chain file.
[http://dl.dropbox.com/u/32409323/Rips/TOVCHain.7z](http://dl.dropbox.com/u/32409323/Rips/TOVCHain.7z)
These might be the model files or another compressed archive.

They are GMO files inside them. Ii there a gmo extractor?
