## Post #1
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-13T02:58:48+00:00
- Post Title: Tears to Tiara II: Haou no Matsuei (Noesis Script)

Here is a noesis script to load these character models with bones and weights.
There are a few models you need to comment out this line for to move the parts to the correct position.
rapi.rpgSetTransform(self.boneList[drawInfo[0]].getMatrix())
decrypt sdat
[viewtopic.php?f=10&t=10950](http://forum.xentax.com/viewtopic.php?f=10&t=10950)
quickbms script to extract bin files.

```
idstring "Filename"
get tbloff long
math tbloff x 4
math tbloff + 16
savepos tmp
get files long
math files / 4
for i = 0 < files
goto tmp
get noff long
math noff + 12
savepos tmp
goto tbloff
get offset long
get size long
savepos tbloff
goto noff
get name string
log name offset size
next i

```

[](http://postimg.org/image/k0543rk2p/full/)
[fmt_TearsToTiaraII_mdl.7z](https://xentaxbackup.github.io/file/6768_fmt_TearsToTiaraII_mdl.7z)
