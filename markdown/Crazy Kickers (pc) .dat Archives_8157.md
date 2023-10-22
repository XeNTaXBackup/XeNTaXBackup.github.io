## Post #1
- Username: afsoongar
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 4:53 pm
- Post datetime: 2012-01-31T06:28:33+00:00
- Post Title: Crazy Kickers (pc) *.dat Archives

Hi all,
can anyone help me to unpack and pack *.Dat archives?

samples: >> File Cutter
1 MB 

```
http://ifile.it/y9pj5ik/CrazyKickers.rar
```


```
Torque..........................k...............................data\pc\audio\data\action\ballbounce.ogg....
```


Torque Game Builder ?

regards,
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-31T07:32:16+00:00
- Post Title: Crazy Kickers (pc) *.dat Archives

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "Torque"
goto 0x20
get FILES long
goto 0x40
for i = 0 < FILES
    getdstring NAME 0x68
    get OFFSET long
    get SIZE long
    getdstring DUMMY 0x10
    log NAME OFFSET SIZE
next i
```
