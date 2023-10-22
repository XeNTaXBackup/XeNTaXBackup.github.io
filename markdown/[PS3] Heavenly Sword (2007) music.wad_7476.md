## Post #1
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-10-08T10:46:44+00:00
- Post Title: [PS3] Heavenly Sword (2007) music.wad

Greetings. The first of my requests is that a way to extract the following file is found:

music.wad from Heavenly Sword (PS3)

The file in question is attached below, packed in RAR segments. It's 350 MB in size in total.

```
wad.r00 (47.68 MB)	http://www.multiupload.com/1KXAN3ATA8
wad.r01 (47.68 MB)	http://www.multiupload.com/JZ71Q90IBE
wad.r02 (47.68 MB)	http://www.multiupload.com/95DDNMENYA
wad.r03 (47.68 MB)	http://www.multiupload.com/P2YBXJXVH7
wad.r04 (47.68 MB)	http://www.multiupload.com/34XK33HE21
wad.r05 (8.69 MB)	http://www.multiupload.com/A5700T9SWR
```


I request that this file be extracted. Reason is that the current game rip soundtrack that is floating around comes from a line-in recording and from my observations, there are fragments of the tunes included missing -- maybe even entire tunes. The only way to get a complete set of tracks is to find a way to extract this file. I'd like to request help in just that, no more, no less.

Thank you in advance from the bottom of my heart.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-09T23:20:09+00:00
- Post Title: [PS3] Heavenly Sword (2007) music.wad

no filenames
good number of wav files though

```
idstring "0DAW"
get DUMMY long
get FILES long
get PNTR long

endian little
goto PNTR

for f = 0 < FILES
  savepos OFFSET
  idstring "RIFF"
  get WAVSIZE long
  math WAVSIZE += 8
  log "" OFFSET WAVSIZE
  math OFFSET += WAVSIZE
  goto OFFSET
next f

```

edit i just figure out the 16-byte headers starting from 0x30 but thats not needed here
## Post #3
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-10-14T15:21:58+00:00
- Post Title: [PS3] Heavenly Sword (2007) music.wad

Thank you so much!!!

Now to sort all that jazz out....  You've been a MONUMENTAL HELP!
