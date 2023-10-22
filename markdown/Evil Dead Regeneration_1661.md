## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-03T20:01:02+00:00
- Post Title: Evil Dead Regeneration

new request

Evil Dead Regeneration

cold fear similar package (fsb3 header)
[ASH_03.zip](https://xentaxbackup.github.io/file/549_ASH_03.zip)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-03T20:25:30+00:00
- Post Title: Evil Dead Regeneration

hi mate .... Game Exctractor excellent open your archive ....    

this script for MultiEx Commander

```
Get FNum Long 0 ;
Get FO Long 0 ;
Math FO += 24 ;
Get DataLen Long 0 ;
Get Dummy1 Long 0 ;
Get DummyNull Long 0 ;
For n = 1 To FNum ;
SavePos Start 0 ;
Get EntryLen Int 0 ;
Math Start += EntryLen ;
SavePos EndFN 0 ;
Math EndFN += 34 ;
Get FN String 0 ;
GoTo EndFN 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
GoTo Start 0 ;
Log FN FO FS 0 FSO ;
Math FO += FS ;
Next n ;
```
