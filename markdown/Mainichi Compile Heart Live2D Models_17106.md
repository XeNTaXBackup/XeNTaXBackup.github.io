## Post #1
- Username: sammyrms1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 06, 2016 9:37 am
- Post datetime: 2017-10-05T06:42:43+00:00
- Post Title: Mainichi Compile Heart Live2D Models

I have some Live2D models from the Compile Heart app that I want to convert into their regular file formats (.json, .moc, .png, etc.) Is there a way to decrypt the .bin files into their specific format?
[Here's one of the models I want to convert (See zip)](https://1drv.ms/u/s!AmVvgYN3WlM7i0snBrAgedg5P_U-)
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-05T08:21:22+00:00
- Post Title: Mainichi Compile Heart Live2D Models

This QuickBMS script will do the trick.

```
# ...I really don't need credit for this sorta thing. It's just a simple XOR. Too easy.

goto -0x01 0 SEEK_END
get XORByte byte
FileXOR XORByte 0
goto -0x09 0 SEEK_END
getdstring EXTENSION 0x08
get SIZE asize
math SIZE - 9
get NAME BASENAME
string NAME + .
string NAME + EXTENSION
log NAME 0 SIZE 0
```

(Or just download and run it, whatever works.)

(EDIT: Revised the script a little bit so now it applies the proper extensions.)
[https://mega.nz/#!axQRkJDJ!MZ6WfVpDauM- ... ob23-6y7pw](https://mega.nz/#!axQRkJDJ!MZ6WfVpDauM-M9AjSO18qvR0NW5EAE2tCob23-6y7pw)
