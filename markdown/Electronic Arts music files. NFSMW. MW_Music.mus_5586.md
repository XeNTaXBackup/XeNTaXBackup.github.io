## Post #1
- Username: Ar4
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 19, 2010 8:05 pm
- Post datetime: 2010-12-19T21:34:28+00:00
- Post Title: Electronic Arts music files. NFSMW. MW_Music.mus

Hello everyone!

I am trying to import my own music in NFS:MW
I used the tool I was able to found ([http://www.xentax.com/uploads/author/dandapani/schl.cpp](http://www.xentax.com/uploads/author/dandapani/schl.cpp))
This one extracted (splitted?) MW_Music.mus to 3257 asf files.
HEADER 
```
SCHl(...GSTR......e.......w.............SCCl........SCDld......8....
```

I was able to use sound eXchange tool to conver *.asf to *.wav
I played a bunch of wavs and they all were 0:03  long when played
At first I hexedited MW_Music.mus, found 1317 asf file data and replaced with other asf's data. Both  were exactly the same size. So I started game, and while listening "Fired Up", in middle of song I heard 3 seconds of other song -> "Lets Move"
Then I used sx.exe 
```
sx -sndstream duality.wav -=duality.asf
```
 to convert full song (Slipknot - Duality) to asf, and inserted it in MW_Music.mus (with hex editor), ingame all songs were muted. I guess attached file cotains some info or offsets, and if smth is wrong, music is stopped.

I have used vltedit (tool by arushan) to view database files, they contain some info about music too, but nothing important, I guess. 
Maybe somebody can help me with this?
[MW_Music.zip](https://xentaxbackup.github.io/file/3700_MW_Music.zip)
