## Post #1
- Username: beretta
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 24, 2011 8:25 am
- Post datetime: 2013-10-29T21:12:44+00:00
- Post Title: Deadly Premonition The Director's Cut .001 format

Hi, 

Deadly Premonition The Director's Cut was just released but unfortunately the files are archived into strange file types, 001 to 003 etc. I have tried the regular zip programs for the hell of it
but they wont open them.

DPSerial.001
DPSerial.002
DPSerial.003

Thanks.
## Post #2
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-10-30T09:05:45+00:00
- Post Title: Deadly Premonition The Director's Cut .001 format

```
getdstring name 0x100
get size long
savepos offset
log name offset size
math offset + size
goto offset
math size % 0x10
if size == 0
getdstring dummy 0x10
else 
math TMP2 = 0x10
math TMP2 - size
getdstring dummy TMP2
endif
next i
```

Script ends with error, but it doesn't matter, all files extract from arc
