## Post #1
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-05-26T16:29:51+00:00
- Post Title: Rainbow Studios .REZ (MX Unleashed, Cars, Star Wars Racer 2)

[Previous discussion in Archived Requests forum](http://forum.xentax.com/viewtopic.php?f=15&t=1841)

A bit of background: Rainbow Studios used their .RES archive format on several games in the 2k era. Splashdown, Splashdown 2, Star Wars Racer Revenge, the MX Unleashed series (including MX vs ATV Unleashed) and the Cars movie games. [Previous efforts](http://forum.xentax.com/viewtopic.php?p=14822#p14822) from Mr. Mouse successfully extracted files, which are compressed with ZLIB. The files extract in 0x6000 chunks and are stored as [filename]0, [filename]1, [filename]2 etc in 0x6000 bytes until the entire file is extracted.

So here's where the question hits: Is there a way I can ZLIB compress individual files? So if I have a file called carinfo.txt that was extracted and pieced back together, then edited. Can I ZLIB compress that file somehow, then manually split it into chunks and manually splice it back into the .RES container? If I know how and where to change offsets and file sizes I have no problem manually rebuilding these. It certainly wouldn't be my first rodeo of the sort.


Here's the script, reposted from the original topic:

```
ComType ZLib1 ;
Get D Long 0 ;
SavePos T 0 ;
Get FJ Long 0 ;
Get U1 Long 0 ;
Get U2 Long 0 ;
Get U3 Long 0 ;
Set UCB Long 24576 ;
Math T += FJ ;
SavePos UO 0 ;
GoTo T 0 ;
Get U4 Long 0 ;
Get FN Long 0 ;
Get DOO Long 0 ;
SavePos DO 0 ;
Math DO += DOO ;
For T = 1 To FN ;
Get FNS Long 0 ;
GetDString FName FNS 0 ;
Get NOff Long 0 ;
Get UCS Long 0 ;
Set F Long 0 ;
Set Co Long UCS ;
Do ;
SavePos FT 0 ;
GoTo UO 0 ;
Get CS Int 0 ;
SavePos UO 0 ;
Set FNA String FName ;
String FNA += F ;
CLog FNA DO CS 0 0 UCB 0 ;
Math Co -= 24576 ;
Math F += 1 ;
Math DO += CS ;
Math DO += 1 ;
GoTo FT 0 ;
While Co > 0 ;
Next T ;

```
