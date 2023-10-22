## Post #1
- Username: BoulderBash
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 18, 2015 6:19 am
- Post datetime: 2015-12-18T01:52:49+00:00
- Post Title: Help With Editing Spyro: The Eternal Night's Files

I am trying to run an ISO of The Legend Of Spyro: The Eternal Night for PS2 with modified game files by extracting them with QuickBMS and editing them.

My Process:

1) Extract DATA_P2.RKV From the ISO
2) Extract the files from DATA_P2.RKV with QuickBMS
3) Edit the files I want to change

What I need to know now is how to take the edited game files and put them back into a RKV format so i can put that in the ISO and run the game. Does anyone know how I can do this?


Code I'm using to extract files:

```
Get files Long 0 ;
GoTo 0x80 0 ;
SavePos base 0 ;
Math qw = files ;
Math qw *= 0x14 ;
GoTo qw 0 SEEK_CUR ;
SavePos namebase 0 ;
For q = 1 TO files ;
GoTo base 0 ;
Get toname Long 0 ;
Get d Long 0 ;
Get size Long 0 ;
Get offset Long 0 ;
Get d Long 0 ;
SavePos base 0 ;
GoTo namebase 0 ;
GoTo toname 0 SEEK_CUR ;
Get name String 0 ;
Log name offset size 0 ;
Next q ;
```
