## Post #1
- Username: themanwholikessounds
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 13, 2020 12:45 am
- Post datetime: 2021-11-09T05:17:55+00:00
- Post Title: Touhou Avant-Garde Discerning Paralleler Music

A Touhou fangame with a file format I cant figure out

Any help would be appreciated

[https://drive.google.com/file/d/1RmA3Nk ... sp=sharing](https://drive.google.com/file/d/1RmA3Nk6ycOHHpoCgnMwqfuvc5IptnhPU/view?usp=sharing)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-09T21:26:24+00:00
- Post Title: Touhou Avant-Garde Discerning Paralleler Music

That is DX archive. [http://wiki.xentax.com/index.php/DX_Archive](http://wiki.xentax.com/index.php/DX_Archive)
It's v8, because header isn't encrypted.

You can extract data with DXADecode, but only when you know the correct password.

Example:

```
DXADecode.exe -K:RANisGOD img2.dxa
```


Edit: Luckily for you this "music.dat" file isn't protected with password,
so you can unpack with this command:

```
DXADecode.exe music.dat
```
## Post #3
- Username: themanwholikessounds
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 13, 2020 12:45 am
- Post datetime: 2021-11-12T02:51:55+00:00
- Post Title: Touhou Avant-Garde Discerning Paralleler Music

It worked, thank you so much!
