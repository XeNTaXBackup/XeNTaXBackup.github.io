## Post #1
- Username: lordninjamelon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 24, 2018 9:34 pm
- Post datetime: 2018-12-24T14:18:07+00:00
- Post Title: Renowned Explorers - stuck on reversing folder structure

I've been trying to reverse [Renowned Explorers](https://store.steampowered.com/app/296970/Renowned_Explorers_International_Society/) game.
I think most of the data is inside their 471mb file called content.tim - [https://drive.google.com/open?id=1VFfQC ... uUfoVrfU_E](https://drive.google.com/open?id=1VFfQC7elJKWnz1rbYIlYUyuUfoVrfU_E)

What I know:
• There are about 370 DDS files inside, that [Dragon Unpacker 5](https://www.elberethzone.net/dragon-unpacker.html) found
• There is a ton of (33,650) hits for a string "texture"
• There are some config files / JSON starting at 0x1213CD1A
• We can see some file structure through here background = "common/backgrounds/shop" or eventTexture = "sprites/ui/events/caribbean/backgrounds/seatravel_caribbean"
• I used [offzip](http://aluigi.org/mytoolz.htm#offzip) to check for internal compression, but it only found few small 64kb and 128kb files. Less than 1% of total file size.

Using a hex editor, I managed to deduce some of the structure
It starts with a magic string 49 52 55 59  ("IRUY")
At 0x0E there is file offset 64 FE BB 1C () and at 0x16 there is the length of that data 86 92 90100 (103,046)
There are three more such offsets, and the final result I get is this 

```
OFFSET_B = 482,185,450 (found @ 0x1E) SIZE = 145,797 (found @ 0x26)
OFFSET_C = 482,331,247 (found @ 0x2A) SIZE = 55,860 (found @ 0x32)
OFFSET_D = 482,387,107 (found @ 0x36) SIZE = 390,276 (found @ 0x3E)
```

It is safe to guess that it's the correct interpretation, because you can add OFFSET with it's LENGTH to get the next offset. The last offset ends at the end of the file as well.

There is some extra data first offset. 
Between the OFFSET_A and OFFSET_A_SIZE there is another byte value @ 0x16 which is C1 52 13 00 (1,266,369), no idea what it is.
Values before first offset can be interpreted as such
0x04 = 82 00 (hex) = 130 (dec)
0x06 = 00 00 02 00 (hex) = 131,072 (dec)
0x0A = 63 9F 00 00 (hex) = 40,803 (dec)


I've tried checking all these different offsets, but did not manage to find any repeating patterns.
Any help or pointers to the right direction are appreciated!
