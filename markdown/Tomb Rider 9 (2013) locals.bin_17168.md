## Post #1
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-10-21T03:15:33+00:00
- Post Title: Tomb Rider 9 (2013) locals.bin

huy
i need to edit this locals.bin from Tomb Rider 2013. how can i unpack and repack?
[locals.rar](https://xentaxbackup.github.io/file/13473_locals.rar)
## Post #2
- Username: MajKSA
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 14, 2016 6:33 pm
- Post datetime: 2017-10-25T09:02:11+00:00
- Post Title: Tomb Rider 9 (2013) locals.bin

I tried to make an exporter but no luck, 
In the picture below is what i know about the file structure.
i hope this is useful if someone is willing to help you.
[local bin stru.png](https://xentaxbackup.github.io/file/13489_local bin stru.png)
## Post #3
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-12-15T07:58:58+00:00
- Post Title: Tomb Rider 9 (2013) locals.bin

I have not yet break the header, but I can easily see that at 0x20C you can spot absolute pointer to text file segment. Every text is in UTF8 encoding. This is Polish language and it also uses HTML for marking text language. This file is quite easy format. 

Header:
uint32 (here 7) - probably Polish language indicator. I don't really know why, but in my job we use '7' for language code for Polish too
uint32 - unknown
uint32 - I though it's text count, but it doesn't calculate. 
Looks like header is 584 bytes long, after that normal pointer list (absolute) appears. 

Every string is terminated with 0. I'm going for a meeting now, but I will code a tool for you when I get back.

Strings count as stated by MajKSA is wrong. 

EDIT:
This is standalone file, so manipulating it should be easy, also there's no EOF or sections, but the file has pointers in it, that complicates things a bit, but that's still fine

String at 0x3554 is indeed one string and means "Błąd Tomb Raider". Therefore every special character in this case polish ł and ą are made by using two bytes, this is casual encoding thing. I can't seem to find the header structure (before pointers)

Found pointers count:
uint32 - unknown/ as said above- looks like language ID. Here 7=polish
uint32 - unknown_A
uint32 - unknown_B
Add unknown_A and unknown_B to get all pointers list. Keep in mind you can encounter null pointers!
## Post #4
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-12-18T12:04:02+00:00
- Post Title: Tomb Rider 9 (2013) locals.bin

There you are:

```
import struct

curr = 0

lingual = open("locals.bin", "rb")
lingual.seek(4,0)
unk_A = struct.unpack('I', lingual.read(4))[0]
unk_B = struct.unpack('I', lingual.read(4))[0]
ffconst = unk_A + unk_B
pointerlist = []
while (curr < ffconst):
    returnme = lingual.read(4)
    pointerlist.append(struct.unpack('I', returnme)[0])
    curr = curr + 1
curr = 0
while (curr <= len(pointerlist)-1):
    if pointerlist[curr] < ((unk_A+unk_B)*4 ):
        curr = curr + 1
        continue
    lingual.seek(pointerlist[curr],0)
    charr = ""
    char_ = -1
    while (char_ != "\0"):
        char_ = lingual.read(1)
        charr+=str(char_)
    print(charr)
    curr = curr + 1

```


This will display all texts

For modifying I'm thinking of dumping whole script file and then rebuild the pointers basing on line, but there are some lines that have null pointer, so developer should also take note of it
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-12-18T19:13:34+00:00
- Post Title: Tomb Rider 9 (2013) locals.bin

keep pointerlist as 2 separate arrays - they are different things   

the first is something you need to leave as-is - it indexes the second array
the second is the string offsets you can change

the values are either 0 (fallback to default language maybe?) or pointers into the strings. values of 0 should be kept intact too!

strings are utf-8 encoded and must be kept that way - beware there are "special characters" for injecting font glyphs

edit: also note some strings support a html-like syntax! look at colours

```

```
## Post #6
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2018-04-04T22:09:45+00:00
- Post Title: Tomb Rider 9 (2013) locals.bin

[http://forum.zenhax.com/viewtopic.php?f=12&t=7662](http://forum.zenhax.com/viewtopic.php?f=12&t=7662)
