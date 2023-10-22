## Post #1
- Username: tuckdragon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 27, 2011 5:28 am
- Post datetime: 2011-06-26T21:31:35+00:00
- Post Title: 25 To Life .hog

I need help to unpack a .hog file from the game 25 to life.

Download:
[http://dl.dropbox.com/u/10322904/25%20t ... og/main.7z](http://dl.dropbox.com/u/10322904/25%20to%20life%20.hog/main.7z)

Thanx in advance !
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-26T22:17:50+00:00
- Post Title: 25 To Life .hog

script for QuickBMS:

```
get FILES long
goto 0x800
for i = 0 < FILES
    get NAME_OFF long
    get OFFSET long
    get SIZE long
    get CRC long
    savepos TMP
    goto NAME_OFF
    get NAME string
    goto TMP
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: tuckdragon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 27, 2011 5:28 am
- Post datetime: 2011-06-26T22:48:43+00:00
- Post Title: 25 To Life .hog

wow, got a response really fast ! thanx alot !
## Post #4
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-06-30T20:23:03+00:00
- Post Title: 25 To Life .hog

can you extract this .HOG from the same game
[https://drive.google.com/open?id=1uaZHS ... XXncJGMGbf](https://drive.google.com/open?id=1uaZHSFOz5kj29ha9qRtDWYXXncJGMGbf)
## Post #5
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2020-05-09T12:37:24+00:00
- Post Title: 25 To Life .hog

Hey. I ask administrators not to delete my comment. I read the forum rules, but who can create the decoder for this archive and the reverse packer? I am ready to reward that person. just from the heart, because for me it is extremely important. Do not consider this a freelance or some kind of hiring an employee, I am an ordinary player and really want to get access to this archive.

```
menu.hog - https://drive.google.com/file/d/1bz5CVqnb28eH2z1O5lmO8JcffRK0AxYa/view?usp=sharing
```

[https://drive.google.com/file/d/1bz5CVq ... sp=sharing](https://drive.google.com/file/d/1bz5CVqnb28eH2z1O5lmO8JcffRK0AxYa/view?usp=sharing)
