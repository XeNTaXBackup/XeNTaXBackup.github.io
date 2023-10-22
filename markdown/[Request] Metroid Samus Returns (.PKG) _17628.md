## Post #1
- Username: hallinbirch
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 25, 2016 11:51 pm
- Post datetime: 2018-01-28T21:56:59+00:00
- Post Title: [Request] Metroid: Samus Returns (.PKG) ?

Hello.
I know that you guys have a lot of stuff to do, but if you are up to help this may be a good challenge or not (depending on your skill level)
long story short I bought this game and dumped the files and was immediately annoyed that instead of loose files I could easily manage they were all locked up inside these packs and I am not that experienced with package reversing.
so if you could help an old N008 that would be awesome
[pkg_fileZa.7z](https://xentaxbackup.github.io/file/13854_pkg_fileZa.7z)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-29T15:48:55+00:00
- Post Title: [Request] Metroid: Samus Returns (.PKG) ?

here is bms script to unpack the files in your varia.pkg sample, the other had nothing in it  

```
get HEADER_SZ long
get DATA_SZ long
get FILES long
for i = 1 to FILES
	get HASH long
	get OFFSET long
	get SIZE long
	savepos TMP
	math SIZE - OFFSET
	goto OFFSET
	getdstring EXT 4
	string NAME p "%s\%08x_%d.%s" FOLDER HASH i EXT 
	log NAME OFFSET SIZE
	goto TMP
next i
```
